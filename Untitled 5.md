
| Table |  |  |
| ----------- | ------ |
| Created On | 2023-08-02 2:59 |
| Summary     | (content) => {
      const active_view = app.workspace.getActiveViewOfType(import_obsidian8.MarkdownView);
      if (active_view === null) {
        log_error(new TemplaterError("No active view, can't append to cursor."));
        return;
      }
      const editor = active_view.editor;
      const doc = editor.getDoc();
      doc.replaceSelection(content);
      return "";
    }       |
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



  
Published date: not sure what this does