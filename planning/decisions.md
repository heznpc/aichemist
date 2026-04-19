# Research Decisions Log

Records non-obvious choices with rationale. Append-only; don't rewrite history.

Format: `## YYYY-MM-DD -- <short title>` with **Context**, **Decision**, **Why**.

---

## 2026-04-19 -- Repository restructure to DDD-style layout

**Context**: Root had TODO.md + review.md, and paper/ contained main.tex + manuscript.md + references.bib together. manuscript.md was a superseded Markdown form.

**Decision**: Move manuscript.md to planning/drafts/. Keep main.tex and references.bib in paper/ as canonical. Move TODO.md and review.md to planning/. Add experiments/ and literature/ skeletons for future work.

**Why**: Single source of truth for the manuscript; meta-work separated; room to grow if empirical work is added.
