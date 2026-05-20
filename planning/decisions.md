# Research Decisions Log

Records non-obvious choices with rationale. Append-only; don't rewrite history.

Format: `## YYYY-MM-DD -- <short title>` with **Context**, **Decision**, **Why**.

---

## 2026-04-19 -- Repository restructure to DDD-style layout

**Context**: Root had TODO.md + review.md, and paper/ contained main.tex + manuscript.md + references.bib together. manuscript.md was a superseded Markdown form.

**Decision**: Move manuscript.md to planning/drafts/. Keep main.tex and references.bib in paper/ as canonical. Move TODO.md and review.md to planning/. Add experiments/ and literature/ skeletons for future work.

**Why**: Single source of truth for the manuscript; meta-work separated; room to grow if empirical work is added.

---

## 2026-05-21 -- Research Program placement: Program 5 (companion to ai-slop-paper)

**Context**: Portfolio registry flagged aichemist as needing a placement decision between Program 5 (Synthetic Content and Measurement) and Program 6 (Analogy / theory layer). The AGI-as-alchemy thesis touches both axes: it is partly a theory/analogy contribution (Program 6) and partly a critique of how AGI claims function as measurement distortion / promissory output (Program 5).

**Decision**: Place under Program 5 as companion to ai-slop-paper. Apply the standard 3-line companion header in README.

**Why**: The load-bearing argument is *material*, not analogical — the alchemy comparison is a vehicle for the resource-consumption / promissory-output asymmetry claim, which is a measurement-and-accounting argument. The AGS reframing is likewise about reproducible scoped accounting, not about analogy mechanics. Program 6 (pythia, analogic-appropriation, whetstone) is where the *analogy as method* sits; aichemist uses the analogy but is not about the analogy.
