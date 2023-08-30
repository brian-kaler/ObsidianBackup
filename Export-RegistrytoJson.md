

Write a powershell script that collects registry values recursively into a custom object.   It should collect registry keys as an array and values as hashtables.

Sure! Here's a PowerShell script that collects registry values recursively into a custom object:

```powershell
# Function to recursively collect registry values
function Get-RegistryValues {
    param (
        [Parameter(Mandatory=$true)]
        [string]$Path
    )

    # Create an empty array to store registry keys
    $keys = @()

    # Recursively collect registry values
    function Get-RegistryKeys {
        param (
            [Parameter(Mandatory=$true)]
            [Microsoft.Win32.RegistryKey]$Key,
            [Parameter(Mandatory=$true)]
            [string]$Path
        )

        foreach ($subKey in $Key.GetSubKeyNames()) {
            $subKeyName = "$Path\$subKey"
            $subKeyObj = @{
                Name = $subKeyName
                Values = @{}
                Keys = @()
            }
            
            # Enumerate registry values for the current subkey
            foreach ($valueName in $Key.OpenSubKey($subKey).GetValueNames()) {
                $valueData = $Key.OpenSubKey($subKeyName).GetValue($valueName)
                $subKeyObj.Values[$valueName] = $valueData
            }

            # Recursively get subkeys and add them to the current subkey object
            foreach ($subSubKeyName in $Key.OpenSubkey($subKeyName).GetSubKeyNames()) {
                Get-RegistryKeys -Key ($key.OpenSubkey("$subKeyName\$subSubKeyName")) -Path "$Path\$subKeyName"            
                $subKeyObj.Keys += "$Path\$subKeyName\$subSubKeyName"
            }

            # Add the current subkey object to the keys array
            $keys += New-Object PSObject -Property $subKeyObj
        }
    }

    # Connect to local machine registry hive and start collecting keys recursively
    try {
        Get-RegistryKeys -Key ([Microsoft.Win32.Registry]::LocalMachine) -Path $Path
    }
    catch {
        Write-Host "Failed to collect registry values: $_" -ForegroundColor Red
    }

    # Return the keys array
    return $keys
}

# Usage example: Collect registry values recursively under HKLM\Software into a custom object
$results = Get-RegistryValues -Path "Software"

# Print the collected registry values
$results | Format-Table -AutoSize
```

In this script, you can specify the registry path from where you want to start



Sure! Here's an example of a PowerShell script that collects registry values recursively and converts them into JSON data:

```powershell
# Define the registry path you want to collect values from
$registryPath = "HKLM:\Software"

# Function to recursively get registry values
function Get-RegistryValues {
    param (
        [parameter(Mandatory = $true)]
        [string]$Path
    )

    # Get all subkeys under the current path
    $subKeys = Get-ChildItem -Path $Path

    # Create an empty array to store the registry values
    $registryValues = @()

    foreach ($subKey in $subKeys) {
        # Get all properties (values) of the subkey
        $properties = Get-ItemProperty -Path $subKey.PSPath

        foreach ($property in $properties.PSObject.Properties) {
            # Create a custom object to store the registry value details
            $registryValue = New-Object -TypeName PSObject

            # Add properties to the custom object
            $registryValue | Add-Member -MemberType NoteProperty -Name "RegistryPath" -Value "$($property.PSChildName)"
            $registryValue | Add-Member -MemberType NoteProperty -Name "Value" -Value "$($property.Value)"
            $registryValue | Add-Member -MemberType NoteProperty -Name "DataType" -Value "$($property.Type)"

            # Add the custom object to the array
            $registryValues += $registryValue
        }

        # Recursively call the function for subkeys, if any exist
        if (Test-Path "$($subKey.PSPath)") {
            Get-RegistryValues -Path "$($subKey.PSPath)"
        }
    }

    return $registryValues
}

# Call the function to get registry values recursively from the specified path
$registryValues = Get-RegistryValues -Path $registryPath

# Convert the custom object to JSON data
$jsonData = $registryValues | ConvertTo-Json

# Output the JSON data
Write-Output $jsonData
```

In this script, you need to specify the registry path you want to collect values from by assigning it to the `$registryPath` variable. The `Get-RegistryValues` function recursively retrieves all registry values under the specified path and creates a custom object for each value. The custom objects are then stored in an array, which is


Sure! Here's a PowerShell script that exports Windows registry values to JSON format recursively:

```powershell
function Export-RegistryToJson {
    param (
        [Parameter(Mandatory=$true)]
        [ValidateNotNullOrEmpty()]
        [String]$Path,

        [Parameter(Mandatory=$true)]
        [ValidateNotNullOrEmpty()]
        [String]$OutputFile
    )

    Begin {
        $result = @{}
    }

    Process {
        if (Test-Path -Path $Path) {
            $keys = Get-ChildItem -LiteralPath $Path

            foreach ($key in $keys) {
                if ($key.PSIsContainer) {
                    $subKeyPath = Join-Path -Path $Path -ChildPath $key.PSChildName
                    Export-RegistryToJson -Path $subKeyPath -OutputFile $OutputFile
                }
                else {
                    try {
                        $value = Get-ItemProperty -LiteralPath $key.PSPath -ErrorAction Stop | Select-Object -Property *
                        if ($value) {
                            $result[$key.PSChildName] = @{
                                Name  = $value.PSChildName
                                Value = ConvertTo-Json -InputObject ($value | Select-Object *)
                            }
                        }
                    }
                    catch {
                        Write-Host "Failed to retrieve value for registry key: $($key.PSChildName)"
                    }
                }
            }
        }
        else {
            Write-Host "Invalid registry path: $($path)"
        }
    }

    End {
        if ($result.Count -gt 0) {
            ConvertTo-Json -InputObject $result | Out-File -FilePath $OutputFile
            Write-Host "Export completed successfully to $($OutputFile)"
        }
    }
}

# Usage example:
Export-RegistryToJson -Path "HKLM:\SOFTWARE\Microsoft" -OutputFile "C:\registry.json"
```

This script defines a function `Export-RegistryToJson` that takes two mandatory parameters: `Path` (the registry path to export) and `OutputFile` (the file path to save the JSON result).

The function recursively iterates through the registry keys and retrieves their values using `Get-ItemProperty`. It then adds the key value pair to the `$result` hashtable.

After all registry keys have been processed, the `$result` hashtable is converted to JSON format using `ConvertTo-Json` and saved to the specified output



Sure! Here's a PowerShell script that exports Windows registry values to JSON format:

```powershell
# Define the registry key path
$regKeyPath = "HKLM:\Software\Microsoft\Windows NT\CurrentVersion"

# Get all values under the specified registry key
$regValues = Get-ItemProperty -Path $regKeyPath | Select-Object -Property *

# Convert the registry values to JSON format
$jsonData = $regValues | ConvertTo-Json

# Specify the output file path
$outputFilePath = "C:\path\to\output.json"

# Write the JSON data to the output file
$jsonData | Out-File -FilePath $outputFilePath

Write-Host "Registry values have been exported to $outputFilePath in JSON format."
```

Make sure to replace `HKLM:\Software\Microsoft\Windows NT\CurrentVersion` with the desired registry key path you want to export. Also, update `$outputFilePath` with the desired output file path.

When you run this script, it will retrieve all values under the specified registry key and convert them into a JSON format. Finally, it will save the JSON data into a file specified by `$outputFilePath`.