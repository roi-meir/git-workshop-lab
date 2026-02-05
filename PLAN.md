# Git Workshop — Project Plan

Workshop for labmates (PhD students from various fields) using **Quarto + reveal.js**: slide deck + interactive hands-on.

**Focus:** Single researchers — version history, reproducibility, and a clear daily workflow on your own machine (and optionally on a cluster). Sharing/collaboration is secondary and kept short.

---

## 1. Project structure

```
git-workshop/
├── _quarto.yml              # Project config (formats, options)
├── PLAN.md                  # This plan
├── README.md                # How to run the workshop
├── slides/
│   └── slides.qmd           # Main reveal.js slide deck
├── workshop/
│   ├── exercises.qmd        # Rendered exercise handout (HTML)
│   └── exercises/           # Step-by-step files (optional refs)
│       ├── 01-setup.md
│       ├── 02-first-repo.md
│       └── 03-collaborate.md
└── .cursor/
    └── skills/
        └── authoring/       # Quarto-authoring skill (existing)
```

- **slides/** — Single Quarto presentation (`format: revealjs`).
- **workshop/** — Practical part: one `exercises.qmd` (narrative + code blocks) that renders to HTML; optional `exercises/*.md` for splitting or printing.
- **README.md** — Prerequisites, how to render slides and workshop, how to run the session (follow slides then switch to exercises).

---

## 2. Slide deck outline (slides/slides.qmd)

### Intro: motivation and why Git (not Drive / cluster)

| Section | Slides | Content |
|--------|--------|--------|
| **Welcome** | 1 | Title, audience (PhDs, various fields), goals |
| **Why version control?** | 1 | Pain: lost changes, “which file was the good one?”, thesis_final_v2_FINAL, experiments you can’t reproduce. Goal: one place, full history, “what changed when”. |
| **Why not Drive / shared folder / cluster only?** | 1 | Drive: no real history, sync conflicts, no “why” for changes. Cluster: same — no per-file history, no clear snapshots. Git: history + messages + works offline and on cluster. |
| **Why Git specifically?** | 1 | Free, works everywhere (laptop, cluster, server), standard in research/code; you can add GitHub/GitLab later for backup or sharing. |

### Core: concepts and basic workflow (expanded)

| Section | Slides | Content |
|--------|--------|--------|
| **What is Git?** | 1–2 | Repo = folder Git tracks. Commit = snapshot + message. History = chain of commits. Branch = parallel line (optional for single user). |
| **Basic workflow — the loop** | 1 | Edit files → `git status` → `git add` (stage) → `git commit -m "message"` → repeat. Emphasize: stage then commit, every time. |
| **Basic workflow — commands in detail** | 2–3 | **Status & history:** `git status`, `git status -s`, `git log`, `git log --oneline`. **Stage:** `git add <file>`, `git add .`, `git add -p` (optional). **Commit:** `git commit -m "message"`, why good messages matter. **Inspect:** `git diff` (working vs staged), `git diff --staged` (staged vs last commit). **Restore:** `git restore <file>` (discard changes), `git restore --staged <file>` (unstage). One slide per group or a clear table. |
| **Basic workflow — diagram** | 1 | Simple picture: working dir → (add) → staging area → (commit) → repo history. |
| **IDE integration** | 2–3 | Why use IDE: same workflow, diffs, stage/commit in editor. **RStudio:** Git pane (status, diff, stage, commit, branches, push/pull); options for Git executable; new project from Git. **VS Code:** Source Control view (changes, stage, commit); branch in status bar; clone via Command Palette. |
| **Setup** | 1 | Install Git, `user.name` / `user.email` (one-time per machine). |
| **Branches (short)** | 1 | What’s a branch; `git switch -c`, `git switch`, `git merge`; useful for trying ideas without touching main line. |
| **Remote & backup (short)** | 1 | Optional: remote = copy on server (GitHub/GitLab); `git remote add`, `git push` for backup or later sharing. No emphasis on collaboration. |
| **Hands-on** | 1 | “Switch to workshop/exercises.” |
| **Wrap-up** | 1 | Summary (workflow, key commands), further resources, Q&A. |

Total ~15–18 slides. Single-researcher focus; collaboration is one short slide or optional. Use `##` for each slide; `::: {.incremental}` for bullets; `::: {.notes}` for speaker notes; callouts for tips; expand **commands and basic workflow** with tables and one diagram (working dir → staging → commit).

---

## 3. Interactive workshop outline (workshop/exercises.qmd)

Designed to be done **together** after the slides, in order. Focus: **you on your machine**; remote/collaboration is one short part at the end.

| Part | Goal | Activities |
|------|------|------------|
| **Setup** | Same Git version & config | Check `git --version`, set `user.name` / `user.email` if needed |
| **First repo** | One commit on one machine | `git init`, add a small file (e.g. `README.md`), `git status`, `git add`, `git commit -m "..."`, `git log` / `git log --oneline` |
| **Basic workflow (repeat)** | Reinforce the loop | Change file, `git status`, `git diff`, `git add`, `git commit`, `git log`. Optionally: `git restore` to discard, `git diff --staged` |
| **Branches** | Safe parallel work | Create branch, make a change, commit, switch back to main, merge. No remote required. |
| **Remote (optional)** | Backup or later sharing | Create repo on GitHub/GitLab, `git remote add`, `git push`. Optional short pair exercise for “pull” only if time. |

Each part: short instruction block + exact commands in fenced code blocks. Optional: `exercises/01-setup.md`, `02-first-repo.md`, `03-collaborate.md` as refs; collaboration exercise can be dropped or shortened.

---

## 4. Flow of the session

1. **Present** — Go through `slides/slides.qmd` (reveal.js). Spend most time on **motivation (why Git, not Drive/cluster)** and **basic workflow + commands**.
2. **Hands-on** — Open `workshop/exercises.qmd` (rendered HTML or source); do each part in order, everyone on their machine. Prioritize: setup → first repo → repeat workflow → branches; remote/collaboration only if time.
3. **Pause for questions** after “Basic workflow” and after “Branches”.

---

## 5. Technical choices (Quarto + reveal.js)

- **Format:** `format: revealjs` in slides’ YAML (per quarto-authoring skill).
- **Slides:** Level-2 headers (`##`) = one slide each; `---` not used as primary separator.
- **Incremental:** `::: {.incremental}` for bullet lists.
- **Notes:** `::: {.notes}` for speaker notes.
- **Layout:** `::: {.columns}` + `::: {.column width="50%"}` for side-by-side (e.g. command vs result).
- **Callouts:** `.callout-tip`, `.callout-warning`, `.callout-important` for motivation and “don’t skip this” steps.
- **Code:** Fenced blocks with language (`bash` / `text`) for all commands and outputs; no execution in slides.

All of the above follow the quarto-authoring skill and references (conversion-xaringan, yaml-front-matter, layout, callouts).
