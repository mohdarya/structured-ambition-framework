---
tags:
  - quick-capture
created: <% tp.file.creation_date("YYYY-MM-DD hh:mm a") %>
related-notes: []
---
<%*
const year = tp.date.now("YYYY");
const month = tp.date.now("MM-MMMM");
const week = tp.date.now("WW");
const day = tp.date.now("DD");
const time = tp.date.now("HHmmssSSS");

// Paths
const baseFolder = ""
const basePath = `${baseFolder}/${year}/${month}/${day}`;
const oldFilePath = `${basePath}/quick-capture.md`;
const newFilePath = `${basePath}/${time}.md`;

// Ensure the script runs only on the "quick-capture" file
if (tp.file.title == "quick-capture") {
    // Ensure the folder structure exists
    if (!(await app.vault.adapter.exists(basePath))) {
        await app.vault.adapter.mkdir(basePath);
    }

    // Create the new file
    const newFile = await app.vault.create(newFilePath, "");
    if (newFile) {
        // Open the new file
        await app.workspace.getLeaf(false).openFile(newFile);
    }
}else{

// Delete the current file
    const currentFile = app.vault.getAbstractFileByPath(oldFilePath);
    if (currentFile) {
        await app.vault.delete(currentFile);
    }
    }
%>