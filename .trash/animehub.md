<%*
const title = tp.file.title;
const excalidrawPath = `Drawings/${title}.excalidraw`;

await tp.file.create_new(`---\n---\n`, excalidrawPath, false);
%>

# <% tp.file.title %>

![[<%* tR += excalidrawPath %>]]



