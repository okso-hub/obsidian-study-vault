---
type: moc
status: active
created: 2026-07-01
aliases: [Courses]
---

# Courses

## Current semester (2026-HWS)
```dataview
TABLE without id file.link AS "Course", file.folder AS "Folder"
FROM "02_Courses"
WHERE type = "moc" AND semester = "2026-HWS"
```

## All semesters
```dataview
TABLE semester, course
FROM "02_Courses"
WHERE type = "moc"
SORT semester DESC, course ASC
```

## Upcoming exams
```dataview
TABLE course, due
FROM "02_Courses"
WHERE type = "exam-prep" AND status != "done"
SORT due ASC
```
