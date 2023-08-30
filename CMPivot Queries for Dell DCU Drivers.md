Baseline parameters

```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates*')
```

Failures
```
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\Failed\\*')
```

Success

```
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\Success\\*')
```

Successful BIOS Updates
```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\Success\\*') | where (Property == 'UpdateType') | where (Value == 'BIOS')
```

Failed BIOS Updates

```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\Failed\\*') | where (Property == 'UpdateType') | where (Value == 'BIOS')
```

DCUExec History

```
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\DCUExecHistory*')
```

ReturnCode Status

```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates*') | where Property == 'Returncode'
```

ScanResult Status

```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates*') | where Property == 'ScanResult'
```

DaysSinceUpdate Status

```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates*') | where Property == 'DaysSinceUpdate'
```

Count of failed updates

```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates*') | where Property == 'CountofFailedUpdates'
```

Raw update data (not extensive)

```cmpivot
Registry('HKLM:\\software\\Securitas\\DellUpdates\\UpdateHistory*')
```

BIOS Password (EncryptionFile)

```cmpivot
File('c:\software\dcuconfig\encryptedpassword.txt')
```

DCU Exec log

```cmpivot
FileContent('c:\software\dcuconfig\DCUExec.log')
```

DCU Activity Log

```cmpivot
FileContent('C:\ProgramData\dell\UpdateService\Log\Activity.log')
```

Model with Installed BIOS sorted by date

```cmpivot
 
```

BIOS Updates by model (Piechart)

```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\*')   
| project device, property, value   
| where (value contains 'Installing')  
| where (value contains 'BIOS')  
| join (ComputerSystem | project device, Model=Model)  
| order by Value  
| take 500  
| project Device, Property, model  
| summarize dcount(device) by Model  
| render piechart
```

BIOS Updates performed in the last 40 days (column chart)

```cmpivot
Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\*')   
| project device, property, value   
| where (value contains 'Installing')  
| where (value contains 'BIOS')  
| project date=substring(value,0,10), device  
| summarize dcount(device) by date  
| order by date  
| take 40  
| render columnchart with(title='BIOS Updates performed in the last 40 days (Latest ==> Oldest)', ytitle='amount')
```

Successful updates with exitcode

```cmpivot
Device  
| join (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\Success\\*') | where property == 'Category')  
| project Device, Manufacturer, Model, Category=Value, FK = Key  
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\Success\\*') | where property == 'Name')  
| where Key == FK  
| project Device, Manufacturer, Model, Category, DriverName=Value, FK=Key  
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\Success\\*') | where property == 'ExitCode')  
| where Key == FK  
| project Device, Manufacturer, Model, Category, DriverName, Exitcode=Value, Key
```

All updates with calculated details

```cmpivot
Device    
| join (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where property == 'Category')    
| project Device, Manufacturer, Model, Category=Value, FK = Key    
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where property == 'Name')    
| where Key == FK    
| project Device, Manufacturer, Model, Category, DriverName=Value, FK=Key    
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where property == 'ExitCode')    
| where Key == FK  
| project Device, Manufacturer, Model, Category, Drivername, Exitcode=Value, FK=Key    
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where property == 'Date')    
| where Key == FK  
| project Device, Manufacturer, Model, Category, DriverName, ReleaseDate=Value, Result=substring(Key,indexof(Key,'UpdateHistory\\')+14,(strlen(Key)-indexof(Key,'UpdateHistory\\')-20)), Exitcode, ProductID=substring(Key,strlen(Key)-5,5) , Key  
```

Top 10 BIOS Updates by Model

```cmpivot
Device    
| join (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where property == 'Category')    
| project Device, Manufacturer, Model, Category=Value, FK = Key    
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where property == 'Name')    
| where Key == FK    
| project Device, Manufacturer, Model, Category, DriverName=Value, FK=Key    
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where property == 'ExitCode')    
| where Key == FK  
| project Device, Manufacturer, Model, Category, Drivername, Exitcode=Value, FK=Key    
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where property == 'Date')    
| where Key == FK  
| project Device, Manufacturer, Model, Category, DriverName, ReleaseDate=Value,  Result=substring(Key,indexof(Key,'UpdateHistory\\')+14,(strlen(Key)-indexof(Key,'UpdateHistory\\')-20)), Exitcode, ProductID=substring(Key,strlen(Key)-5,5) , Key  
| where Category == 'BIOS' and Result == 'Success'  
| summarize dcount(device) by Model  
| top 10 by dcount_  
| order by dcount_ desc  
| render barchart with(title='Top 10 BIOS Updates by Model' )
```

Devices by count of BIOs Update result

```cmpivot
Device  
| join (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where (Property == 'Category'))  
| project Device, Manufacturer, Model, Category = Value, FK = Key  
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where (Property == 'Name'))  
| where (Key == FK)  
| project Device, Manufacturer, Model, Category, DriverName = Value, FK = Key  
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where (Property == 'ExitCode'))  
| where (Key == FK)  
| project Device, Manufacturer, Model, Category, Drivername, Exitcode = Value, FK = Key  
| join kind=rightouter (Registry('hklm:\\SOFTWARE\\Securitas\\DellUpdates\\UpdateHistory\\*\\*') | where (Property == 'Date'))  
| where (Key == FK)  
| project Device, Manufacturer, Model, Category, DriverName, ReleaseDate = Value, Result = substring( Key, (indexof( Key, 'UpdateHistory\\' ) + 14), ((strlen( Key ) - indexof( Key, 'UpdateHistory\\' )) - 20) ), Exitcode, ProductID = substring( Key, (strlen( Key ) - 5), 5 ), Key  
| where (Category == 'BIOS')  
| summarize Count = count() by Device, Result
```