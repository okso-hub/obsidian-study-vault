---
type: moc
status: active
created: 2026-07-01
aliases: [Projects]
---

# Projects

## Active projects
```dataview
TABLE due, status
FROM "01_Projects"
WHERE type = "project" AND status = "in-progress"
SORT due ASC
```

## Waiting on
```dataview
LIST
FROM "01_Projects"
WHERE type = "project" AND status = "waiting"
```

## Completed
```dataview
LIST
FROM "01_Projects"
WHERE type = "project" AND status = "done"
SORT file.mtime DESC
```
