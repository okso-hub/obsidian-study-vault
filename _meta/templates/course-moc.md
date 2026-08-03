---
type: moc
status: active
created: {{date:YYYY-MM-DD}}
course: 
semester: 
moc: []
aliases: []
---

# {{title}}

**Instructor:** 
**ECTS:** 
**Exam format:** 
**Schedule:** 

## Lectures
```dataview
TABLE without id file.link AS "Note", status
FROM "02_Courses"
WHERE course = this.course AND type = "lecture"
SORT file.name ASC
```

## Readings
```dataview
TABLE authors, year, status
FROM "02_Courses"
WHERE course = this.course AND type = "reading"
```

## Exam
```dataview
LIST
FROM "02_Courses"
WHERE course = this.course AND type = "exam-prep"
```
