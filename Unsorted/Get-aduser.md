
tell me how to use the powershell cmdlet get-aduser to get a user account using only samaccountnameTo use the PowerShell cmdlet Get-ADUser to get a user account using only samAccountName, follow these steps:

1. Open PowerShell with administrative privileges.

2. Type the following command and press Enter:
Get-ADUser -Filter {samAccountName -eq "username"}

Replace "username" with the actual username of the user account you want to retrieve.

3. If the command is successful, you should see a list of properties for the user account, such as Name, Description, Enabled, PasswordNeverExpires, and more.

Note that if you have multiple domains or forests in your environment, you may need to specify the appropriate domain or forest using the -Server parameter. For example:
Get-ADUser -Filter {samAccountName -eq "username"} -Server "domain.com"

Also, if you want to retrieve only specific properties for the user account instead of all properties, use the -Properties parameter followed by a comma-separated list of property names. For example:
Get-ADUser -Filter {samAccountName -eq "username"} -Properties Name,EmailAddress

This will retrieve only the Name and EmailAddress properties for the specified user account.