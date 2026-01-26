# Tasks

```dataview
TASK
WHERE !contains(lower(file.path), "template")
GROUP BY file.link + " ➤ " + meta(section).subpath
SORT rows.file.ctime DESC
```