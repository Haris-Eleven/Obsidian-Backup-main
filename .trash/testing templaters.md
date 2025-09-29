%*
const title = tp.file.title;
const excalidrawPath = `Drawings/${title}.excalidraw.md`;

// Create the new Excalidraw file (blank frontmatter)
await tp.file.create_new(`---\n---\n`, excalidrawPath, false);

// Get the active view
const leaf = app.workspace.getActiveViewOfType(app.plugins.plugins["templater-obsidian"].templater.get_view_type());

// Open the Excalidraw file in a split pane
const newLeaf = app.workspace.splitRight(leaf);
newLeaf.openFile(app.vault.getAbstractFileByPath(excalidrawPath));

tR += `# ${title}\n\n![[${excalidrawPath}]]`;
%>
