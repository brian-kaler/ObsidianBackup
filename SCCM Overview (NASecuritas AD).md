

**Primary Site
	Roles
		Distribution Point
		Management Point
		Asset Intelligence
		Reporting Services
		Site Database Servers
		SMS Provider
		Software Update Point (WSUS)
		Cloud Management Gateway connection point
	Addt. Software
		SQL Server 2022 Standard
		PatchMyPC Publisher
		*Modern Driver Management (Optional)*
	Specifications
		16 Cores
		104GB Memory
		1500 GB Local Storage**
**Distribution Point (Canada)
	Roles
		Distribution Point
	Specifications
		4 Cores
		8GB Memory
		500 GB Local Storage
Distribution Point (Mexico) 
	Roles
		Distribution Point
	Specifications
		4 Cores
		8GB Memory
		500 GB Local Storage
Content Storage (Content Source)
	Specifications
		2TB Network Storage (CIFS Compatible)
		DFS Accessible**
**Cloud Management Gateway**
	




Hi Jim,

Per our discussion today I wanted to get you a high level overview of what I think we would need. 

The outline below assumes that the servers would be HA or at least fault tolerant, with a 3 server configuration.   

The primary site has high requirements in specifications due to the combination of all of the services it will be providing and is in line with what Microsoft recommends.  The 1.5 TB requested would to take into account for the SCCM database, PowerBI, Software Updates (WSUS), and other content as it would also serve as a distribution point.

Distribution points for both Mexico and Canada would be essential as the content will vary greatly between these 2 regions.  I'm including the content breakdown for the distribution points below.

DFS Network storage is requested, 2TB would be required to store content for all of Configuration Manager operations including PatchMyPC applications.

Modern Driver Management is optional here but I recommend it as we don't have a good idea of what driver management in Intune will provide, this will provide a good fallback option to deliver drivers when needed.

Risk factors

- Intune - Deploying Configuration Manager without operating system imaging requires both Intune and Cloud Management Gateway.   Any blocking issues for configuration here would impact deploying Configuration Manger.
- Device deployment using Intune requires a completely different methodology to testing new hardware.  Unknown risks are presented here, but will likely result in longer initial unboxing set-up times for the customer.