
Prerequisites:
SCCM Module
CSV File generated from the Export-PrimaryUserDevices script.


## 0. Preparation: Exporting CSV for New-UserDeviceDeployment.ps1

This script runs without any input, it takes all users and devices and uses their affinity data to establish a Device <-> User mapping.  It can potentially take hours to run so use it sparingly.  When completed it was ask you to specific the filename for output.

Scriptname: Export-PrimaryUserDevices

### What's inside of the CSV?

DeviceResourceId - the ID of the device used in SCCM
UserResourceId - the ID of the user used in SCCM
Device - the device name
Username - the user name
PhysicalOffice - the AD attribute for the user's local office

Primarily the scripts will use the Device and Username but additional properties are collected for script improvement in the future.

## SCRIPT MUST BE EDITED! EACH SECTION BELOW GOES INTO DETAILED PARAMETERS

## 1. Folder processing variables
### Input (before Execution)
#### User collections based on the targeted audiences
Variables below use the folder names found in the SCCM console and returns all collections found under that folder name.
```parameters
	targetFolderName - string - the unique name of the folder being targeted
	excludeCollections - string (comma separated) - a list of collections to ignore
```

### Input (at Execution)
Script will prompt the user with a dialog of the collections found based on the variables above, the user will need to ctrl+click to select multiple collections.  The order in which each collection is clicked determines the order in which they will be scheduled.   

Multiple groups can be created by selecting fewer than are displayed on the screen, the dialog will repeat until all groups are selected.

### Output
Returns a PSCustom object, some of the properties were obtained from a separate provided CSV file containing device memberships.

Existing properties are displayed in *Italics* while new properties are in **BOLD**

UserDevices
	Properties
		*Device
		DeviceResourceId	
		Username	
		UserResourceId
		PhysicalOffice*
		**SourceUserCollection**

## 2. Users collection processing
### Takes user collections provided and creates subgroups
Uses the sourceUserCollection found in step 1 to divide each collection into multiple subgroups for scaling the schedule, the date 

```Parameters
	desiredGroupCount - int - the smallest daily schedule
```

### Input
None provided during execution, must be edited in the parameters (top of script)

### Output
Adds additional Properties to the existing object.

Existing properties are displayed in *Italics* while new properties are in **BOLD**

UserDevices
	Properties
		*Device
		DeviceResourceId	
		Username	
		UserResourceId
		PhysicalOffice
		SourceUserCollection*
		**GroupSchedule**

## 3. Scheduling devices
### Input (before Execution)
#### Schedules devices and scales by time scale
Uses the GroupSchedule property created in step #2 and determines the dates that the groups can be combined to form larger collections for the deployment.  Properties are added that dictate the date of the scheduled deployment, the level of scaling each date of the deployment, and the deployment collection for that date.

```Parameters
	desiredScheduleStart - datetime - Start of the schedule
	desiredScheduleEnd - datetime - End of the schedule
	config_SchSafety - datetime - 7 days after the desiredScheduleStart
	config_SchSafety2 - datetime - 14 days after the desiredScheduleStart
	desiredGroupCount_4x - int - desiredGroupCount x 4
	desiredGroupCount_10x - int - desiredGroupCount x 10
```
### Input (at Execution)
The user is prompted with the number of schedules needed and the number of total devices in the deployment, if the numbers look correct the user needs to confirm with 'y' and enter.

### Output
Adds additional Properties to the existing object.   

Existing properties are displayed in *Italics* while new properties are in **BOLD**

UserDevices
	Properties
		*Device
		DeviceResourceId	
		Username	
		UserResourceId
		PhysicalOffice
		SourceUserCollection
		GroupSchedule*
		**SafetyLevel
		ScheduleDate
		ScheduleCollection
		HRDate**

## 4. Applying memberships and schedule script
### Creates deployment collections and adds members

### Input (at Execution)
The user is prompted during the script to create the collections and add memberships.  Since this is the most time consuming step in the process, the user must provide 'y' and enter to continue.

### Output

Creates collections and direct memberships for the devices collected and categorized in previous steps #1 - 3.

#### Automated Operation

Writes a JSON FILE that is used to aide in automated deployment, see the other script solution 'Invoke-Schedule' for how to provide this.

#### Manual Operation

Collections are created with a format:

	UserDevices_[SCHEDULED DEPLOYMENT DATE]_[SOURCEUSERCOLLECTION]

This allows an operator to manually and easily identify WHO and WHEN devices need to be deployed only a daily basis.  
