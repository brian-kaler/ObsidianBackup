provide support for a machine with the wrong timezone set on a local machine and windows store applications failing to updat


1) Right click on the time and date in the far right corner of the taskbar. Choose Adjust Date and time settings, at the top make sure the time is correct. If it’s wrong, manually adjust it and make sure the sliders for Set time automatically and Set time zone automatically are set to on.
2) Run the following command from a Administrative powershell session:
	1) Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate" -Name "DoNotConnectToWindowsUpdateInternetLocations" -Value 0; Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate" -Name "UseWUServer" -Value 1
3) Reboot the machine, and open the windows store application to verify that the application updates are running.


write troubleshooting advice for enabling internet windows update on a windows 10 machine so that windows store applications will update automatically



write a oneline powershell command to turn on the disable the registry key "DoNotConnecttoWindowsUpdateInternetLocations" and enable the "UseWUServer" registry key.

```
$s_donotconnecttowindowsupdate = "HKLM:\Software\Policies\Microsoft\Windows\WindowsUpdate","DoNotConnecttoWindowsUpdateInternetLocations"

$s_useWUserver = "HKLM:\Software\Policies\Microsoft\Windows\WindowsUpdate\AU","UseWUServer"

  

#enable Updates from the internet

Try{

    Set-ItemProperty -Path $s_donotconnecttowindowsupdate[0] -name $s_donotconnecttowindowsupdate[1] -Value 0 -ErrorAction stop -Verbose

    Set-ItemProperty -Path $s_useWUserver[0] -name $s_useWUserver[1] -Value 0 -ErrorAction stop -Verbose

}

Catch{

    Write-Host "Script was not able to modify Windows Update settings"

}

Finally{

    Write-Host "Internet Windows Updates: Enabled"

}
> [!failure]- Failure 
>   Error: Request failed, status 404
>   
>   - app.js:1 new t
>     app://obsidian.md/app.js:1:717762
>   
>   - app.js:1 Jw
>     app://obsidian.md/app.js:1:717954
>   
>   - app.js:1 
>     app://obsidian.md/app.js:1:718631
>   
>   - app.js:1 
>     app://obsidian.md/app.js:1:235836
>   
>   - app.js:1 Object.next
>     app://obsidian.md/app.js:1:235941
>   
>   - app.js:1 a
>     app://obsidian.md/app.js:1:234680
>   
>  
