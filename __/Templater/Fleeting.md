Entered value: <% tp.system.prompt("Please enter a value") %>
Mood today: <% tp.system.prompt("What is your mood today ?", "happy") %>

Mood today: <% tp.system.suggester(["Happy", "Sad", "Confused"], ["Happy", "Sad", "Confused"]) %>
Picked file: [[<% (await tp.system.suggester((item) => item.basename, app.vault.getMarkdownFiles())).basename %>]]asename, app.vault.getMarkdownFiles())).basename %>]]





tp.system有三個API
* 貼上剪貼簿內容
* 下拉選單
* 打字輸入