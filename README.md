# Git Workshop

A slide deck and hands-on workshop for labmates (PhD students from various fields), built with **Quarto + reveal.js**.

**Live site:** [https://roi-meir.github.io/git-workshop-lab/](https://roi-meir.github.io/git-workshop-lab/) — slides, exercises.

## Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) installed
- Git installed (we’ll check in the workshop)
- A GitHub or GitLab account (for the collaboration part)

## Render the materials

From the project root:

```bash
# Slides (reveal.js)
quarto render slides/slides.qmd

# Workshop handout (HTML)
quarto render workshop/exercises.qmd
```

Outputs:

- `slides/slides.html` — open in a browser to present
- `workshop/exercises.html` — open for the hands-on part

## Running the session

1. **Present** — Open `slides/slides.html` and go through the deck.
2. **Hands-on** — Open `workshop/exercises.html` (or the `.qmd` source) and do the exercises in order together.
3. Pause after “Basic workflow” and after “Branches / Collaboration” for questions.

## Project layout

- `slides/slides.qmd` — Main presentation (reveal.js)
- `workshop/exercises.qmd` — Step-by-step exercises (HTML)
- `workshop/exercises/` — Optional split exercise files
