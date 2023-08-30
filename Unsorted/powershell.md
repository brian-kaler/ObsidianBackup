
write a oneline powershell command to turn on the disable the registry key "DoNotConnecttoWindowsUpdateInternetLocations" and enable the "UseWUServer" registry key.


Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate" -Name "DoNotConnectToWindowsUpdateInternetLocations" -Value 0;Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate" -Name "UseWUServer" -Value 1

