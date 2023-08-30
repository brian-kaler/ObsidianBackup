###Fleeting Notes







## ✅ Today


```tasks
scheduled on {{date:YYYY-MM-DD}}
hide scheduled date
hide done date
```


​
## ⏰ Past


```tasks
((not done) OR (done on {{date:YYYY-MM-DD}}))
(scheduled before {{date:YYYY-MM-DD}})
```


​
## ☎️ Meetings


```button
name New Meeting
type note(Meetings/<% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD") + ' - ' + '\<\% tp.date.now("X") \%\>' %>, split) template
action Meeting
templater true
```


​


```dataview
TABLE join(file.outlinks) AS Outlinks
WHERE when=date(this.file.name) AND contains(tags, "meeting")
```


​
## 📝 Notes


```button
name New Note
type note(<% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD") + ' - ' + '\<\% tp.date.now("X") \%\>' %>, split) template
action Note
templater true
```


​


```dataview
TABLE join(file.outlinks) AS Outlinks
WHERE when=date(this.file.name) AND contains(tags, "note")
```