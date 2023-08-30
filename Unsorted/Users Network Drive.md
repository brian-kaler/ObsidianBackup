
write me a powershell script that returns all the mapped drives for the currently logged in user
Here's a PowerShell script that returns all the mapped drives for the currently logged in user:

```
$drives = Get-WmiObject -Class Win32_MappedLogicalDisk | Where-Object {$_.ProviderName -ne $null}

foreach ($drive in $drives) {
    Write-Host "Drive letter: $($drive.DeviceID)"
    Write-Host "Network path: $($drive.ProviderName)"
}
```

This script uses the `Get-WmiObject` cmdlet to retrieve information about all mapped drives on the system. It then filters out any drives that aren't mapped to a network location by checking if the `ProviderName` property is not `null`.

Finally, it loops through each mapped drive and writes out the drive letter and network path using the `Write-Host` cmdlet.
