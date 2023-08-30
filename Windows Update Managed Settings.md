
Top Issues

- Windows 10 machines are automatically upgrading to Windows 11
- Store applications are blocked


https://www.ajtek.ca/wsus/dual-scan-making-sense-of-why-so-many-admins-have-issues/
	additional reference:
	https://www.ajtek.ca/wsus/how-to-setup-manage-and-maintain-wsus-part-4-creating-your-gpos-for-an-inheritance-setup/

https://cloudblogs.microsoft.com/windowsserver/2017/01/09/why-wsus-and-sccm-managed-clients-are-reaching-out-to-microsoft-online/

Very similiar settings mentioned, not the full list but to keep values as unconfigured.


Filter Windows 11 on TargetReleaseVersion?
Does the activation (win10 pro) effect this upgrade.

https://www.reddit.com/r/SCCM/comments/y3s9jg/prevent_sccm_managed_clients_reching_out_to/

highlighted post:
```

	We went through an absurd amount of testing for this and these are the settings we came up with. Do not set any other WSUS/Windows Update/Windows update for business settings or they will conflict and re-enable dual scan:

Computer Configuration/Administrative Templates/System/Specify settings for optional component installation and component repair

-   ​ Never attempt to download payload from Windows Update - Disabled
    
-   Download repair content and optional features directly from Windows Update instead of Windows Server Update Services (WSUS) - Enabled
    

Windows Components/Store

-   Only display the private store within the Microsoft Store - Disabled
    
-   Turn off Automatic Download and Install of updates - Disabled
    
-   Turn off the offer to update to the latest version of Windows - Enabled
    
-   Turn off the Store application - Disabled
    

Windows Components/Windows Update

-   Remove access to use all Windows Update features Enabled
    

The MECM agent will set a few more WU policies, don't try and set those manually.

These settings will:

-   Only allow windows updates to come from SCCM.
    
-   Allow administrators to install optional features from Microsoft directly without it being in WSUS, like RSAT tools
    
-   Allow Store access (we have two GPOs, one allows only the private store)
    
-   Disable the ability for users to run dual scan (which would reach out to microsoft directly)
```




Path: Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings

Type: REG_QWORD:

Setting: SvOfferDeclined

Value: 0 disable banner and blocks in-place upgrades to Windows 11.

The value of the registry key is inconsequential as long as it exists. For unification, the suggestion would be to make the value 0.


## update 5/24/2023

New engineer:
Elias Rodriguez Vargas

SvOfferDeclined is depreciated!




TargetReleaseVersion
ProductVersion
TargetReleaseVersionInfo