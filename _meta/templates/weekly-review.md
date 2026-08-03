---
type: weekly-review
status: done
created: {{date:YYYY-MM-DD}}
---

# Weekly review W{{date:ww}} ({{date:YYYY-MM-DD}})

## 1. Empty the inbox
```dataview
LIST
FROM "00_Inbox"
```

## 2. What did I learn?
- 

## 3. What's open / blocked?
```dataview
TABLE status, due
FROM "" AND -"_meta"
WHERE (status = "waiting" OR status = "in-progress") AND type != "moc"
SORT due ASC
```

## 4. Next week: top 3
- [ ] 
- [ ] 
- [ ] 

## 5. System check
- [ ] Frontmatter of new notes ok?
- [ ] All deadlines in the `due` field?
- [ ] Anything to move to the archive?
