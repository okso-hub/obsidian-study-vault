# Examples — a demo of the vault in action

This folder mirrors the vault's real structure and shows what each folder looks like once you've been running the system for a few weeks. Everything here is fictional — a made-up student in the 2026-HWS taking `IE-616 Data Mining 1` and drafting a thesis proposal a year later.

## Why this exists

Reading empty templates doesn't tell you what a filled note *should look like*. This folder answers questions like:

- How do I actually write a Cornell-style lecture note?
- What does a good "core claim in one sentence" look like on a paper?
- How much do I write in a project log, weekly review, daily note?
- How do MOCs get populated over time via `moc:` frontmatter?

## Contents

Each folder mirrors a real top-level vault folder, so you can compare 1:1:

```
_meta/examples/
├── Home.md                                ← example dashboard, scoped to this folder
├── 00_Inbox/
│   └── podcast-twiml-rag-eval.md          ← a raw inbox capture
├── 01_Projects/
│   ├── _project-index.md                  ← projects overview
│   └── thesis-proposal-rag.md             ← a longer-running project
├── 02_Courses/
│   ├── _course-index.md                   ← courses overview
│   └── 2026-HWS/IE-616-data-mining-1/
│       ├── IE-616.md                      ← Course-MOC (dataview aggregates the rest)
│       ├── lectures/
│       │   ├── 2026-09-09-intro-kdd.md    ← first lecture, done
│       │   └── 2026-09-16-frequent-itemsets-apriori.md
│       ├── exercises/
│       │   └── ex-02-apriori.md           ← homework with due date
│       ├── readings/
│       │   └── han-2011-data-mining-concepts.md
│       └── exam/
│           └── IE-616-exam-2027-02.md     ← exam prep with auto topic list
├── 03_Areas/
│   └── machine-learning.md                ← filled Area MOC, note the resources
├── 04_Resources/
│   ├── papers/lewis-2020-rag.md
│   └── cheatsheets/pandas-basics.md
├── 06_Daily/
│   └── 2026-09-16.md                      ← daily note
└── 2026-W38.md                            ← weekly review
```

## How Dataview queries work in here (important!)

Notes in `_meta/examples/` are **deliberately excluded** from the vault's real dashboards. The queries in [`../../Home.md`](../../Home.md), the real [`../../03_Areas/`](../../03_Areas/) MOCs, and [`../../02_Courses/_course-index.md`](../../02_Courses/_course-index.md) all use `FROM "" AND -"_meta"` — so this example world does not pollute your real "Due in 14 days".

The queries **inside** the examples (e.g. in `IE-616.md`, in the exam-prep note, in the machine-learning Area MOC, in the weekly review) are scoped to `FROM "_meta/examples/…"` — so they render live within the demo without leaking out.

## When you copy an example to your real vault

If you take one of these notes as a starting point:

1. Move it into the corresponding real folder (e.g. drag `lewis-2020-rag.md` from `_meta/examples/04_Resources/papers/` → `../../04_Resources/papers/`).
2. If it contains a Dataview query scoped to `"_meta/examples/…"`, change that path back to the real one (usually `"02_Courses"` or drop the FROM entirely and rely on `WHERE`).
3. Update the `created` and `due` dates to real values.

## When you're comfortable, delete this folder

Nothing outside `_meta/examples/` depends on it. Once the system feels natural, you can delete `_meta/examples/` entirely without breaking anything.

## For future clones of this repo

If someone forks this vault to use it as a template, the `_meta/examples/` folder acts as living documentation — better than a static README, because they can open it in Obsidian and see the real graph, backlinks, and Dataview output.
