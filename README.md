# Obsidian Study Vault

An Obsidian vault for a Data Science master's program, built on PARA + Dataview + a minimal set of templates. The design goal is low maintenance: a small, fixed structure and one required habit, so the system stays useful without constant upkeep.

**Curious what a filled-in vault looks like?** See [`_meta/examples/`](_meta/examples/README.md) — a complete mirror of the structure with realistic notes. It's excluded from all real Dataview queries, so it won't pollute your dashboards.

---

## The one rule
**If it has a date, put it in the `due` field.** Everything else you can skip.
Only `type` and `status` are required frontmatter. Done.

## Where do I put what?

| What | Where |
|---|---|
| Quick note, no time to sort | `00_Inbox/` (clean up later) |
| Lecture note | `02_Courses/<semester>/<course>/lectures/` |
| Exercise / homework | `02_Courses/…/exercises/` |
| Paper / reading (course-specific) | `02_Courses/…/readings/` |
| Paper / book (cross-course, long-lived) | `04_Resources/papers/` or `04_Resources/books/` |
| Project (thesis, term paper, application) | `01_Projects/` |
| Long-lived knowledge (statistics, ML, …) | link via `moc:` to `03_Areas/<area>.md` |
| Cheatsheet, snippet | `04_Resources/cheatsheets/` or `04_Resources/snippets/` |
| Done / over | `05_Archive/` |

## Creating a new note
1. `Cmd+N` — lands in `00_Inbox/` automatically (setting: default location).
2. Insert a template (`Cmd+P` → *Templates: Insert template*).
3. Fill in at least `type` and `status`. If a date is set: `due`.
4. Once you know where it belongs: move it to the right folder.

## The weekly review (Sunday, 15 min)
New note from the `weekly-review.md` template. Work through the five sections, done.
This is the one recurring habit that keeps the vault current — it surfaces the inbox, open items, and anything with a `due` date.

## When you've forgotten the system
1. Open `Home.md`.
2. Empty `00_Inbox/`.
3. Do a weekly review.
4. Keep going. No need to set up something new.

## Semester start ritual (5 min)
1. Create a new folder `02_Courses/<year>-<HWS|FSS>/` (if it doesn't exist).
2. Per course: sub-folder `<CODE>-<slug>/` with `lectures/`, `exercises/`, `readings/`, `exam/`.
3. Create a Course-MOC from the `course-moc.md` template; filename = course code (e.g. `IE-660.md`).
4. Update the semester filter in `Home.md` (`semester = "2026-HWS"`) to the new semester.

## Naming conventions
- Filenames: **kebab-case, lowercase, no umlauts**.
- Lectures: `YYYY-MM-DD-<slug>.md`
- Readings: `<firstauthor>-<year>-<slug>.md`
- Course-MOC: `<CODE>.md` (short — `[[IE-660]]` is quick to type)
- Weekly reviews: `YYYY-Www.md` (ISO week, e.g. `2026-W37.md`)
- Daily: `YYYY-MM-DD.md`
- H1 title inside the file may be natural English (or German for personal notes) — filename is for machines, title is for humans. `aliases:` keeps linking convenient.

## What NOT to do
- ❌ Don't invent new top-level folders (`00_`–`06_` and `_meta/` are enough).
- ❌ Don't invent new `type:` values.
- ❌ Don't "complete" frontmatter out of guilt. Optional means optional.
- ❌ Don't install a plugin zoo. The vault runs on Core + Dataview + Obsidian Git.
- ❌ No ad-hoc topic-MOCs. MOCs live only in `03_Areas/` and `02_Courses/…/<COURSE>.md`.
- ❌ Don't store real notes under `_meta/`. It's vault infrastructure (templates, examples, assets) — dashboards deliberately ignore it via `FROM "" AND -"_meta"`.

## Language convention
- **Everything academic in English:** lectures, readings, MOCs, exam prep, projects.
- **Personal stuff may stay in German:** daily notes, project logs ("today frustrated because…"), weekly-review reflections, German admin (deadlines from Portal2, BAföG, forms).

## Obsidian settings to set after setup
- Options → Files & Links → **Default location for new notes**: `00_Inbox`
- Options → Files & Links → **Default location for new attachments**: `_meta/assets`
- Options → Core Plugins → **Templates**: Template folder location = `_meta/templates`
- Options → Core Plugins → **Daily notes**: New file location = `06_Daily`, Template file location = `_meta/templates/daily.md`, Date format = `YYYY-MM-DD`
- Options → About → **On startup, open**: `Home.md`

## Recommended community plugins
- **Dataview** — the Home dashboard won't run without it (but note-creation still works)
- **Obsidian Git** — versioning/backup
- optional later: **Advanced Tables**, **MathJax extensions** for ML/stats formulas

## Frontmatter cheatsheet
```yaml
type: lecture | reading | exam-prep | weekly-review | moc | project | daily | note   # required
status: inbox | active | in-progress | waiting | done | archived                     # required
created: YYYY-MM-DD
due: YYYY-MM-DD                        # ← the one discipline
course: IE-660                         # only on course notes
semester: 2026-HWS                     # only on course notes
tags: [ml, statistics]                 # kebab-case
moc: ["[[machine-learning]]"]          # links up to Areas/Course-MOCs
```

## Vault layout at a glance

```
ma-ds/
├── Home.md                 ← dashboard (open this on startup)
├── README.md               ← you are here
├── 00_Inbox/               ← unsorted captures
├── 01_Projects/            ← thesis, term papers, applications
├── 02_Courses/             ← per-semester course notes
├── 03_Areas/               ← long-lived knowledge (Areas of interest)
├── 04_Resources/           ← papers, books, cheatsheets, snippets
├── 05_Archive/             ← finished / stale
├── 06_Daily/               ← daily notes
└── _meta/                  ← vault infrastructure (ignored by dashboards)
    ├── templates/          ← 9 note templates
    ├── examples/           ← a filled-in demo of the whole vault
    └── assets/             ← images, PDFs
```
