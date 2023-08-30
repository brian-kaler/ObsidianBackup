


## MACHINE POLICIES

  ### HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Policies\Servicing
	  RepairContentServerSource	: delete (2 is enabled)
	  CheckBox_NeverUseWU		: 2
	  CheckBox_SidestepWSUS	: delete
  ### HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\WindowsStore
	  **RequirePrivateStoreOnly	: 0**
	  **RemoveWindowsStore 		: 1** < Currently 0
	  **DisableOSUpgrade 		: 1**
	  **AutoDownload			: 4**  
  ### HKEY_LOCAL_MACHINE\\Software\Policies\Microsoft\Windows\WindowsUpdate
	None

## USER POLICIES

  ### HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\WindowsUpdate
		**DisableWindowsUpdateAccessMode: 1**


Possible OU/GPO issue