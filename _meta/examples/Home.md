---
type: moc
status: active
created: 2026-09-01
aliases: [Home, Start, Dashboard]
---

# Home (example)

> [!tip] The one rule
> **If it has a date, it goes in the `due` field.** Everything else is optional.

## 📅 Due in the next 14 days
```dataview
TABLE due, type, status, course
FROM "_meta/examples"
WHERE due AND due <= date(today) + dur(14 days) AND status != "done" AND status != "archived"
SORT due ASC
```

## 🔧 Currently in progress
```dataview
TABLE type, course, due
FROM "_meta/examples"
WHERE status = "in-progress" AND type != "moc"
SORT file.mtime DESC
LIMIT 20
```

## 📥 Inbox (clean up!)
```dataview
LIST file.link
FROM "_meta/examples/00_Inbox"
SORT file.ctime DESC
```

## 🎓 Courses this semester
> Update the semester filter below manually each term (`2026-HWS` → `2027-FSS` → …)
```dataview
TABLE without id file.link AS "Course", file.folder AS "Folder"
FROM "_meta/examples/02_Courses"
WHERE type = "moc" AND semester = "2026-HWS"
```

## ⏳ Waiting on / blocked
```dataview
LIST
FROM "_meta/examples"
WHERE status = "waiting"
```

## 🗓️ Latest weekly review
```dataview
LIST file.link
FROM "_meta/examples"
WHERE type = "weekly-review"
SORT file.name DESC
LIMIT 1
```

---

**Navigation:** [[_project-index|Projects]] · [[_course-index|Courses]] · [[../../README|How this vault works]]

> This is the example Home. The real dashboard lives at [`../../Home.md`](../../Home.md) and uses `FROM "" AND -"_meta"` to exclude this folder.
