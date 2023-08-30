#SCCMBUILD


Checklist Items

- [x] Database setup
	- [x] Reporting services installed
- [x] Base Collections
- [x] Boundaries
- [x] Discovery
- [ ] Distribution Points
	- [x] pson1m1sccmdp01
		- [x] admin rights needed
	- [x] pson1u1sccmdp01
- [ ] Site Backup
	- [x] Get DFS Link for backup
		- [x] Extend F: Drive Size to 750 GB
- [ ] Applications
	- [x] DFS Structure
	- [x] Zscaler App
		- [ ] Azure AD groups version of the application.
		- [x] 3.9.183?
		- [ ] 
	- [x] Crowdstrike app
		- [ ] Tags
		- [ ] 
	- [ ] 
- [x] Upgrade
- [x] Site Maintenance tasks
- [ ] SQL Reporting Services
	- [x] SSRS Not installed
		- [x] Install Service
	- [ ] Configure
		- [ ] https://learn.microsoft.com/en-us/mem/configmgr/core/servers/manage/configuring-reporting
- [ ] Software updates
	- [x] Service Install
	- [x] Dedicated Update Drive
	- [ ] Configuration
		- [x] ADR for Workstation
		- [x] ADR / Server
		- [x] ADR / Office 365
		- [ ] Delegated access for L2 Cloud/Server
			- [ ] added Domain Admins, still need a group




Jim's notes 8/14

- [ ] Validate new DFS namespace is available (Starting with 750GB) – Frank is ready just need to know which share on the SCCM server to point DFS too.  This should be for updates, packages, drivers etc..
- [ ] 
- [ ] Validate SCCM patching is working for servers and complete by 8/18.  Work with Cloud services team 
- [ ] SCCM Delegation for server teams – Can they do the same thing they are doing today in new SCCM and only have the ability to patch and see Server collections,etc..
- [ ] •	Collection filtering based on AD groups like they do today (Test,dev,prod)
- [ ] •	Setup crowdstrike applications using the default tags for US, Can & Mexico) using new DFS as source location