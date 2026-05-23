# Biology Plus One Genetics and Evolution

**Author:** Nik Bear Brown
**Publisher:** Bear Brown, LLC
**Status:** Draft
**Started:** 2026-05-15

## Structure

```
book.md                 ← book description and high-level outline (planning)
outline.md              ← starter table of contents (planning)
vision.md               ← Tic TOC Phase 1: vision and positioning
architecture.md         ← Tic TOC Phase 2: learning architecture
chapters-spec.md        ← Tic TOC Phase 3: chapter specifications
risks.md                ← Tic TOC Phase 4: scope, market, risks
pantry/                 ← scratch storage for fragments, snippets, leftovers
chapters/
    00-frontmatter.md   ← copyright, dedication, preface
    01-introduction.md  ← Chapter 0 / Introduction
    02-chapter-01.md    ← Chapter 1
    ...
    04-chapter-03.md    ← Chapter 3
    99-back-matter.md   ← acknowledgments, about the author, notes, references, index
```

## Planning Documents

| File | Purpose |
|------|---------|
| `book.md` | One-sentence pitch, the argument, the gap, the reader, high-level outline. |
| `outline.md` | Chapter-level table of contents — keep in sync with `chapters/`. |
| `vision.md` | Tic TOC Phase 1 — book concept, type, learner profile, thesis, field positioning. |
| `architecture.md` | Tic TOC Phase 2 — learning outcomes, sequencing, three-act arc, prerequisites. |
| `chapters-spec.md` | Tic TOC Phase 3 — per-chapter specs, cases, contested claims, coverage gaps. |
| `risks.md` | Tic TOC Phase 4 — comparable texts, features, out of scope, adoption risks. |
| `pantry/` | Scratch storage for fragments and snippets that don't yet belong in a chapter. |

These files are for planning only. They are not compiled into the EPUB.

The four Tic TOC files are templated with `[NEEDS HUMAN INPUT]` markers
and a `*Phase N output from Tic TOC*` header signature. Run Tic TOC's
`/scaffold silent` to fill them from `book.md`, `outline.md`, `pantry/`,
and `chapters/`. Or build them section-by-section through the interactive
phase commands (`/i1` → `/m4`).

## Chapters

| File | Title | Status |
|------|-------|--------|
| 00-frontmatter.md | Front Matter (copyright, dedication, preface) | ☐ |
| 01-introduction.md | Introduction | ☐ |
| 02-chapter-01.md | Chapter 1 | ☐ |
| 03-chapter-02.md | Chapter 2 | ☐ |
| 04-chapter-03.md | Chapter 3 | ☐ |
| 99-back-matter.md | Back Matter (acknowledgments, notes, references, index) | ☐ |

## Build

```bash
./build.sh
```

Output goes to `output/` (gitignored).

## Figures

```bash
./graphs.sh
```

Processes `<!-- → [TYPE: description] -->` comments in every chapter:
- Tabular figures → classed markdown tables (`.infographic-table`, `.comparison-table`, `.data-table`)
- Non-tabular figures → placeholder images in `images/`, ready to replace
- CSS log appended to `styles/kindle-book.css` on each run

Review `chapters/*-updated.md`, then promote:
```bash
for f in chapters/*-updated.md; do mv "$f" "${f/-updated/}"; done
```

## Styles

| File | Purpose |
|------|---------|
| `styles/kindle.css` | Shared base — typography, figure table classes. Do not edit per book. |
| `styles/kindle-book.css` | Book-specific overrides. Edit freely. `graphs.sh` appends its log here. |

## Publish

Upload `output/biology-plus-one-genetics-and-evolution.epub` to [KDP](https://kdp.amazon.com).

---

## What This Book Is

<!-- TODO: populate from chapter content -->

---

## Who This Book Is For

<!-- TODO: populate from chapter content -->

---

## How to Read It

<!-- TODO: populate from chapter content -->

---

## Table of Contents

| Chapter | Title | File |
|---------|-------|------|
| 0 | Chapter 00 — How to Use the Simulations | [chapters/00-how-to-use-the-simulations.md](chapters/00-how-to-use-the-simulations.md) |
| 1 | Chapter 01 — Meiosis and the Basis of Inheritance | [chapters/01-meiosis-basis-of-inheritance.md](chapters/01-meiosis-basis-of-inheritance.md) |
| 2 | Chapter 02 — Mendel's Laws and Mendelian Inheritance | [chapters/02-mendels-laws-mendelian-inheritance.md](chapters/02-mendels-laws-mendelian-inheritance.md) |
| 3 | Chapter 03 — Extensions of Mendelian Genetics | [chapters/03-extensions-mendelian-genetics.md](chapters/03-extensions-mendelian-genetics.md) |
| 4 | Chapter 04 — DNA Structure, Replication, and Repair | [chapters/04-dna-structure-replication-repair.md](chapters/04-dna-structure-replication-repair.md) |
| 5 | Chapter 05 — From Gene to Protein: Transcription and Translation | [chapters/05-gene-to-protein.md](chapters/05-gene-to-protein.md) |
| 6 | Chapter 06 — Gene Expression and Regulation: One Genome, Many Cells | [chapters/06-gene-expression-regulation.md](chapters/06-gene-expression-regulation.md) |
| 7 | Chapter 07 — Biotechnology and Genomics: We Learned to Read the Letters, and Then We Learned to Write Them | [chapters/07-biotechnology-genomics.md](chapters/07-biotechnology-genomics.md) |
| 8 | Chapter 08 — Mutation, DNA Damage, and Cancer Genetics: The Hinge Between Disease and Evolution | [chapters/08-mutation-dna-damage-cancer.md](chapters/08-mutation-dna-damage-cancer.md) |
| 9 | Chapter 09 — Evolution and the Origin of Species: How Populations Change and How One Kind Becomes Two | [chapters/09-evolution-origin-of-species.md](chapters/09-evolution-origin-of-species.md) |
| 10 | Chapter 10 — Population Genetics and Natural Selection: How Allele Frequencies Change, and How to Predict Them | [chapters/10-population-genetics.md](chapters/10-population-genetics.md) |
| 11 | Chapter 11 — Speciation: How One Lineage Becomes Two, and Why "Species" Is the Useful Lie | [chapters/11-speciation.md](chapters/11-speciation.md) |
| 12 | Chapter 12 — Phylogenetics and the History of Life: Reading the Tree from the Speciation Events That Built It | [chapters/12-phylogenetics-history-of-life.md](chapters/12-phylogenetics-history-of-life.md) |
| 13 | Chapter 13 — Molecular Evolution and Evo-Devo: How Sequences Change and How Bodies Get Built From the Same Toolbox | [chapters/13-molecular-evolution-evo-devo.md](chapters/13-molecular-evolution-evo-devo.md) |
| 14 | Chapter 14 — Capstone: From Genes to Evolutionary Change | [chapters/14-capstone-genes-evolution.md](chapters/14-capstone-genes-evolution.md) |

---

## Signature Simulations

<!-- TODO: populate from chapter content -->

---

## The +1 Layer

This book contains a chapter explaining how to use the LLM Exercise blocks embedded across the chapters. Each exercise is a structured prompt the reader can paste into an LLM tool of their choice; the chapter explains the pattern and when each variant applies.

---

## Copyright

Copyright © 2026 Nik Bear Brown. All rights reserved. See LICENSE.md for full terms.

