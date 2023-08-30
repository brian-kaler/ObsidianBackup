write a powershell script that runs chkdsk on all drives on a windows 10 system, it should write the results in separate text files for each disk checked.Here's a PowerShell script that will run chkdsk on all drives in a Windows 10 system and write the results to separate text files for each disk checked:

```
# Get all drives on the system excluding the system drive.
$drives = Get-WmiObject -Class Win32_LogicalDisk -Filter "DriveType=3" | Select-Object -ExpandProperty DeviceID | where {$_ -ne "C:"}

# Loop through each drive and run chkdsk
foreach ($drive in $drives) {
    $result = Invoke-Expression "chkdsk $drive /F /R /X"

    # Write the result to a text file
    $filename = "chkdsk_$($drive.Replace(':', ''))_$(Get-Date -Format 'yyyyMMdd_HHmmss').txt"
    Set-Content -Path $filename -Value $result
}
```

This script first uses the `Get-WmiObject` cmdlet to get all logical disks on the system. It then loops through each drive and runs chkdsk with the `/F`, `/R`, and `/X` parameters, which respectively fix errors, locate bad sectors and recover readable information, and force dismount of the volume if necessary.

The output of chkdsk is stored in a variable called `$result`. The script then creates a filename based on the drive letter and current date/time, and uses `Set-Content` to write the contents of `$result` to a text file with that filename.

Note that running chkdsk with these parameters may take some time depending on the size of your disks. You may want to run this script outside of business hours or at a time when it won't cause disruption to users.