
| Table |  |  |
| ----------- | ------ |
| Created On | <% tp.file.creation_date("YYYY-MM-DD h:mm") %> |
| Summary     | <% tp.file.cursor_append %>       |
| Description |        |
| Steps to Reproduce |  |
| Expected Result   |        |
| Actual Result     |        |
| Priority          | High / Medium / Low |
| Severity          | Critical / Major / Minor |
| Environment       |        |
| Browser           |        |
| Operating System  |        |
| Reproducible?     | Yes / No   |
| Attachments       |        |



<%*  
let publishedDate = await tp.system.suggester(["none", tp.date.now(), "placeholder"], ["none", tp.date.now(), "placeholder"]);  
if (publishedDate == "placeholder") {  
publishedDate = await tp.system.prompt("enter published date");  
}  
%>  
Published date: <% publishedDate %>