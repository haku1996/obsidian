```templater
<% (await tp.system.suggester((item) => item.basename, app.vault.getMarkdownFiles(), false, "Please link previous sprint plan")).basename %>

<% (await tp.system.suggester((item) => item.basename, app.vault.getMarkdownFiles().filter(file => file.path.startsWith("Note")), false, "Please link previous sprint plan")).basename %>
```


<% tp.file.rename( await tp.system.prompt("Rename")) %>

::up =[[<% (await tp.system.suggester((item) => item.basename,app.vault.getMarkdownFiles().filter(file => file.path.startsWith("Note")), false, "Enter Parent Note")).basename %>]]

<% (await tp.system.suggester((item) => item.basename, Object.values(app.vault.adapter.files).filter( item => Object.values(item)[0] == "folder").map(item => Object.values(item)[1] ).sort(), false, "Test")).basename %>


<% tp.file.move("/Journal/tttt")%>
<% tp.file.rename( await tp.system.prompt("Rename")) %>

