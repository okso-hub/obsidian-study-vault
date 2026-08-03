---
type: moc
status: active
created: 2026-09-01
aliases: [Projects]
---

# Projects (example)

## Active projects
```dataview
TABLE due, status
FROM "_meta/examples/01_Projects"
WHERE type = "project" AND status = "in-progress"
SORT due ASC
```

## Waiting on
```dataview
LIST
FROM "_meta/examples/01_Projects"
WHERE type = "project" AND status = "waiting"
```

## Completed
```dataview
LIST
FROM "_meta/examples/01_Projects"
WHERE type = "project" AND status = "done"
SORT file.mtime DESC
```
