---
date: 2022-06-23
modified: 2022-07-15
---
## Metadata
up:: [[Toolmap]]

---

Basic Field:: Value
**Bold Field**:: Nice!
You can also write [field:: inline fields]; multiple [field2:: on the same line].
If you want to hide the (field3:: key), you can do that too.

```dataview
TABLE 
file.day AS "如果本來裡面就有時間", 
file.cday as "創建時間", 
file.mtime AS "修改日期", 
status AS "都行" 
FROM "Tool"
```
