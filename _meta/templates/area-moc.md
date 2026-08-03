---
type: moc
status: active
created: {{date:YYYY-MM-DD}}
aliases: []
---

# {{title}}

**What belongs here:** 

**Core resources:**
- 

## Notes in this area
```dataview
LIST
FROM "" AND -"_meta"
WHERE contains(moc, this.file.link)
SORT file.mtime DESC
LIMIT 50
```
