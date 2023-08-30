```dataview
table Completed, Priority, Project, defer-date as "Defer Date", due-date as "Due Date", recur-length as "Recur Length", defer-date + recur-length as "Next Date"
from #tasks
where defer-date < date(now) and completed != 1
sort doDate asc
```
