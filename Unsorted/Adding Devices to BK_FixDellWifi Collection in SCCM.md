
## adding devices to the collection

- In SCCM go to the following folder and collection:

	Device Collections > Admin > Brian 

	Find the "BK_FixDellWifi" collection

Right click the collection and click "add resources"

![[2023-04-04 14_03_56-userdpt02 - Remote Desktop Connection.png]]

Add the system name in the name string contains field and click Search, then select from search results and click the Add button.  Repeat the steps until you have all machines added.

## running the script

- Right click on the collection "bk_dellwififix" and click the Run Script action
![[2023-04-04 14_04_14-userdpt02 - Remote Desktop Connection.png]]

- Search for "Wifi" or find the  script named "Invoke-DCUWifiFix"
![[2023-04-04 14_04_32-userdpt02 - Remote Desktop Connection.png]]
- complete the wizard and a script status window will appear, be patient as this may take 5-10 minutes (or longer) before any script output occurs, you are looking for the output as pictured below for a successful run.
![[2023-04-04 14_05_08-userdpt02 - Remote Desktop Connection.png]]
- It's a good idea to do a visual inspection of the login screen of the laptop and find if there is a missing Wifi symbol on the login screen, presence of the Wifi indicator will indicate the driver is installed.  Below is pictured an example of machine without a Wifi driver, so the indicator shows a globe icon. ![[A51879D0.jpg]]