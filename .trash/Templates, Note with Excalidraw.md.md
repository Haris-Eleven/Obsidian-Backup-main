<%*
const title = tp.file.title;
const excalidrawPath = `Drawings/${title}.excalidraw.md`;

const excalidrawContent = `---
excalidraw-plugin: raw
---
%% Drawing
{"type":"excalidraw","version":2,"source":"https://excalidraw.com","elements":[],"appState":{"viewBackgroundColor":"#ffffff","gridSize":null},"files":{}}
`;

// Create a new valid Excalidraw file
await tp.file.create_new(excalidrawContent, excalidrawPath, false);

// Give Obsidian time to index the new file
await app.vault.adapter.read(excalidrawPath);

// Grab the file
const file = app.vault.getAbstractFileByPath(excalidrawPath);

if (file) {
  const newLeaf = app.workspace.splitActiveLeaf();
  await newLeaf.openFile(file);
} else {
  console.log("❌ File not found:", excalidrawPath);
}

tR += `# ${title}\n\n![[${excalidrawPath}]]`;
%>
