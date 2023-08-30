

#memo

Greetings,

Please be advised we have limited reports of an issue following the deployment of Global Protect VPN client on customer PCs.   If you see this issue on any pc demonstrating the symptoms below, please notify L3 EUS.   

Symptoms: 
	- Customer reports that they cannot connect to Wifi or Ethernet after receiving the Global Protect VPN Client
	- Network adapters are missing IP information
		- ipconfig output has minimal output, or with minimal details and no random class-b ip address
	- Network adapters in device manager do not show any issues, and Network Connections appear as normal.
		![[Pasted image 20230524072522.png]]

Solution: 
	1. Uninstall Checkpoint VPN 
	2. Reboot the PC
	3. Confirm with the customer that the connectivity is restored.