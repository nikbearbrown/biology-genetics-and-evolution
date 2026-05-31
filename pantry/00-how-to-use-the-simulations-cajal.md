# CAJAL Figure Intelligence — Chapter 0: How to Use the Simulations

**Source:** `chapters/00-how-to-use-the-simulations.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. The opening "how-to" chapter. Frames Mendel's combinatorial problem, introduces the Punnett-square scaling (2×2, 4×4, 8×8 ... 128×128), and the three-file / four-move LLM prompt discipline (Show / Say / Constrain / Verify). No author-placed figures via `![...]()`, but the Punnett-square scaling argument is the most diagrammable claim in the chapter.

---

## Density Recommendation

**2 figures, Conceptual density.** One figure earns its place for the combinatorial-scaling claim (the napkin-runs-out-of-room argument); a second for the four-move prompt scaffolding. The historical Mendel scene, the three-files vocabulary (CLAUDE.md / DESIGN.md / PROJECT.md), and the exploration tasks are prose-shaped and self-sufficient.

---

## Zone Map

- **MC:** The Punnett-square scaling mechanism — N loci → 2^N gametes per parent → 4^N cells in the grid. The four-move prompt structure (Show, Say, Constrain, Verify) as a falsifiable-verification pipeline.
- **VG:** The "napkin runs out of room" claim is intrinsically visual. The four-move structure is a small flowchart.
- **PQ:** 2^N gamete counts. 4^N cell counts. 28,000 plants (Mendel's sample size). 16,384 cells at N=7. 2,187 all-dominant out of 16,384. 5,474 round / 1,850 wrinkled (2.96:1).

---

## Figure 0.1 — Punnett-Square Combinatorial Scaling

**Priority: Critical.** The chapter's central numerical argument. The reader must feel the exponential explosion that motivates abandoning hand computation.

### Block 1 — Illustrae paste block

A horizontal sequence of four nested Punnett-square grids, increasing in resolution left to right, drawn as a four-panel composition. Panel 1 (N=1): a 2×2 grid, four large cells. One cell Sky Blue `#56B4E9` filled (AA), two cells Blue `#0072B2` filled (Aa, heterozygous), one cell Reddish Purple `#CC79A7` filled (aa). Panel 2 (N=2): a 4×4 grid, 16 cells, same color logic — corners Sky Blue and Reddish Purple, intermediates Blue. Panel 3 (N=3): an 8×8 grid, 64 cells. Panel 4 (N=7): a 128×128 grid, 16,384 cells, rendered as a dense pixel pattern where the fractal-like distribution of homozygous-dominant (Sky Blue), heterozygous (Blue), and homozygous-recessive (Reddish Purple) cells emerges. Between each panel, a thin Vermillion `#D55E00` 1pt arrow indicates "×4 cells per locus." Below each panel, a tiny indicator bar (typography post-applied: 4, 16, 64, 16384 cells). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Four nested Punnett-square grids at N=1, 2, 3, 7. Cell counts grow as 4^N: 4, 16, 64, 16384. Cells colored by genotype class: homozygous-dominant Sky Blue, heterozygous Blue, homozygous-recessive Reddish Purple.
[O] Horizontal left-to-right sequence. Panels increase in cell density but stay roughly the same outer dimensions, so the visual punch is the increasing fineness of the grid. Vermillion arrows between panels.
[P] Homozygous-dominant cells Sky Blue `#56B4E9` filled. Heterozygous cells Blue `#0072B2` filled. Homozygous-recessive cells Reddish Purple `#CC79A7` filled. Scaling arrows Vermillion `#D55E00` 1pt. Grid lines Black `#000000` 0.25pt (thin so the color carries the signal, not the rule).
[E] No cell labels, no genotype strings inside cells, no numerical cell counts inside the image, no axis labels, no decorative ornament, no shadows. The N=7 panel must read as a coherent pattern at 174mm width, not as 16,384 distinguishable cells.

### Block 3 — Negative prompt

text labels, genotype strings, allele letters inside cells, cell-count annotations, axis labels, titles, captions, gibberish letters, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 0.2 — The Four-Move Prompt Structure

**Priority: Important.** The procedural argument the chapter teaches. A clean visual locks the discipline in memory the way a flowchart does.

### Block 1 — Illustrae paste block

A vertical four-step flow composition. Four large Sky Blue `#56B4E9` filled rounded rectangles stacked vertically, connected by Black `#000000` 1pt downward arrows. Each rectangle is labeled by position (typography post-applied: "Show," "Say," "Constrain," "Verify"). The fourth rectangle ("Verify") is rendered in Blue `#0072B2` filled rather than Sky Blue, marking it as the load-bearing move. Beside the Verify rectangle, a small Vermillion `#D55E00` filled circular badge (the falsifiable-integer-check indicator) attached by a short connector. To the left of each of the first three rectangles, a small Bluish Green `#009E73` filled icon-sized square indicates the artifact each move produces (governing files, biological paragraph, slider/range/format rules); to the left of the Verify rectangle, an Orange `#E69F00` filled icon-sized square indicates the integer-check output. White background, flat vector, single-column 89mm.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] Four-stage vertical flow representing the Show / Say / Constrain / Verify prompt structure. Verify highlighted as load-bearing. Each stage paired with a small artifact-indicator square.
[O] Vertical top-to-bottom. Equal spacing. Verify visually distinct (deeper Blue) and badge-attached.
[P] Show / Say / Constrain rectangles Sky Blue `#56B4E9` filled. Verify rectangle Blue `#0072B2` filled. Integer-check badge Vermillion `#D55E00`. Artifact-indicator squares Bluish Green `#009E73`; Verify artifact Orange `#E69F00`. Flow arrows Black `#000000` 1pt.
[E] No text labels inside the image, no code snippets, no laptop or terminal iconography, no checkmark icons, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, words, code snippets, terminal windows, laptop icons, checkmark icons, X marks, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Mendel-in-the-pea-plot historical scene.** Prose. A figure would be an illustration, not a diagram, and the AI Wayback Machine block already directs the reader to source material.
- **CFTR molecular structure.** Mentioned once as a clinical hook; chapter does not require the protein.
- **CLAUDE.md / DESIGN.md / PROJECT.md file-icon vignette.** Three filenames is typography, not a figure.
- **Bin(n, 1/4) probability distribution chart.** The sample-size discussion is prose-shaped; the relevant figure belongs in Ch 10 (drift) where this becomes load-bearing.
- **Snapdragon incomplete-dominance illustration.** Defer to Ch 3 where incomplete dominance is the chapter topic.

---

## Video Candidate Pass

**FIGURE 0.1 (Punnett-square scaling):** **MILD VIDEO CANDIDATE.** A slider-driven animation stepping N from 1 to 7 would dramatize the 4^N explosion in a way the static four-panel cannot match — but the static is the printed-page asset and reads cleanly. The interactive simulation the chapter builds (`00-punnett-square.html`) is itself the dynamic version; the figure should remain static so the reader has a print reference next to the live simulator.
**FIGURE 0.2 (Four-move structure):** STATIC SUFFICIENT. Procedural flowchart; animation adds nothing.

**Video candidates identified: 0 strong + 1 mild.** No production recommended — the interactive simulator already covers the dynamic case.

---

## Split-point note

The Sky Blue / Blue / Reddish Purple genotype-class palette established here (homozygous-dominant / heterozygous / homozygous-recessive) must propagate consistently through Ch 1 (meiosis), Ch 2 (Mendel), and Ch 3 (extensions). Note: the chapter's own DESIGN.md proposes #1a5276 / #2980b9 / #85c1e9 (a blue triad) — for CAJAL print figures we remap to the Okabe-Ito accessible palette (Sky Blue / Blue / Reddish Purple), because the original triad sits entirely within blue and loses contrast at small sizes. The book's DESIGN.md governs the interactive HTML simulations; the print pantry uses the Okabe-Ito mapping. Note the divergence in the design log.
