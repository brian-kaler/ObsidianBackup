write a powershell script that returns unknown devices found on a windows 10 machineHere's a PowerShell script that will return a list of unknown devices found on a Windows 10 machine:

```
$devices = Get-PnpDevice -PresentOnly

foreach ($device in $devices) {
    if ($device.Status -eq "Unknown") {
        Write-Host "Unknown device found: $($device.FriendlyName)"
    }
}
```

This script uses the `Get-PnpDevice` cmdlet to retrieve a list of all present devices on the machine. It then loops through each device and checks if its status is "Unknown". If it is, it will output the friendly name of the device to the console.

