# CAJAL Figure Intelligence — Chapter 8: Mutation, DNA Damage, and Cancer Genetics

**Source:** `chapters/08-mutation-dna-damage-cancer.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. The hinge chapter — same molecular event (point mutation) as either disease (somatic, cancer) or evolutionary raw material (germline). Covers mutation typology, sources (spontaneous + induced), Ames test, mutation-rate arithmetic, Knudson's two-hit model, Fearon-Vogelstein colorectal progression, and mutational signatures. Five author-placed figures.

---

## Density Recommendation

**5 figures, Mechanistic density.** All five earn their place. The chapter argues that the same chemistry plays in two registers, and each figure either grounds a mechanism (Ames, signatures) or scaffolds an arithmetic claim (mutation rates, Knudson, multi-step progression).

---

## Zone Map

- **MC:** Ames test — chemical → mutagen → revertant colony count, with S9 metabolic activation. Knudson two-hit kinetics — hereditary one-hit vs. sporadic two-hit retinoblastoma. Fearon-Vogelstein cumulative driver-hit progression APC → KRAS → SMAD4 → TP53.
- **VG:** Mutational signature spectrum (96-context bar chart for SBS4 tobacco vs. SBS7 UV) — the tumor's archaeological record.
- **PQ:** Mutation rates across organisms on log scale (SARS-CoV-2 10⁻⁶ → E. coli 10⁻¹⁰), spanning four orders of magnitude.

---

## Figure 8.1 — Ames Test Workflow

**Priority: Important.** Closes the chain from molecular event to public-health screening; mechanistically rich because of the S9 metabolic-activation insight.

### Block 1 — Illustrae paste block

A four-stage horizontal workflow. Stage 1: a Black `#000000` 1pt outlined test-tube containing a Sky Blue `#56B4E9` filled drop labeled-position for the chemical under test. Stage 2: the chemical mixed with a Reddish Purple `#CC79A7` filled small irregular blob (S9 rat-liver homogenate) shown combining via a Black 1pt arrow. Stage 3: the activated mixture being added to a Petri dish — a Black 1pt outlined circle — containing a faint Sky Blue lawn of his⁻ Salmonella; a small Orange `#E69F00` filled bar (minimal medium without histidine) annotated as the substrate. Stage 4: the same Petri dish after incubation, now with scattered small Bluish Green `#009E73` filled dots (revertant colonies) on top of the lawn, with the colony count visible. A second smaller Petri dish below (control, no chemical) shows only one or two Bluish Green dots for comparison. Black 1pt arrows connect the stages. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Ames test: test chemical activated with S9 rat-liver homogenate, applied to his⁻ Salmonella on minimal medium; revertant colonies indicate mutagenicity; control plate shows baseline.
[O] Four-stage horizontal workflow; control plate below treated plate at the same scale.
[P] Test chemical Sky Blue. S9 fraction Reddish Purple. Petri dish outline Black 1pt. Bacterial lawn faint Sky Blue. Minimal-medium indicator Orange. Revertant colonies Bluish Green. Process arrows Black 1pt.
[E] No specific strain numbers as text, no chemical names, no plate-count numbers, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, strain numbers, chemical names, colony-count numbers, lab-protocol text, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 8.2 — Mutation Rates Across Organisms (Log Scale)

**Priority: Important.** Quantitative comparison spanning four orders of magnitude; grounds the drift-barrier discussion and the per-generation human arithmetic.

### Block 1 — Illustrae paste block

A horizontal bar chart on a log-scale vertical axis. Vertical axis: per-base-per-replication mutation rate from 10⁻¹¹ at the bottom to 10⁻⁴ at the top, Black `#000000` 1pt axis with tick marks at each decade. Horizontal axis: five categories arranged left to right — E. coli, Humans, HIV reverse transcriptase, SARS-CoV-2, with no rendered text. Bars: E. coli ~2 × 10⁻¹⁰ drawn as a short Blue `#0072B2` filled rectangle; Humans ~1.2 × 10⁻⁸ as a Sky Blue `#56B4E9` filled rectangle (about two decades taller); HIV ~3 × 10⁻⁵ as a Vermillion `#D55E00` filled rectangle (much taller); SARS-CoV-2 ~1.3 × 10⁻⁶ as an Orange `#E69F00` filled rectangle. All bars share the same uniform width and rest on the horizontal axis baseline. Each bar's top edge clearly visible against the log gridlines. White background, flat vector, single-column 89mm.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] Per-base-per-replication mutation rates compared across organisms on a log scale, spanning four orders of magnitude from E. coli to RNA viruses.
[O] Vertical bar chart, organisms on x-axis, rate on log y-axis.
[P] E. coli Blue. Humans Sky Blue. HIV-RT Vermillion. SARS-CoV-2 Orange. Axis Black 1pt.
[E] No numerical rate values rendered as text, no organism names rendered as text, no axis-label words, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, numerical values, organism names, axis-label words, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 8.3 — Knudson Two-Hit Model

**Priority: Critical.** The dominance asymmetry made visible. Hereditary (one hit pre-installed, second hit somatic) vs. sporadic (both hits somatic) is the founding logic of tumor-suppressor biology.

### Block 1 — Illustrae paste block

A two-row parallel comparison. Top row (Hereditary case): three cells drawn left-to-right as Black `#000000` 1pt outlined circles. Cell 1: shows both RB1 alleles as two Sky Blue `#56B4E9` filled rectangles inside the cell, one with a Vermillion `#D55E00` filled X overlay (first hit, germline). Cell 2: same as Cell 1 — every cell in the body starts with one hit. Cell 3: now both rectangles have Vermillion X overlays (second hit acquired somatically); the cell is filled with a faint Vermillion 10% tint indicating tumor initiation. A Black 1pt arrow connects Cell 2 to Cell 3 labeled-position for "rate = µ·D". Bottom row (Sporadic case): same three-cell layout. Cell 1: both alleles intact (two Sky Blue rectangles, no X). Cell 2: one X acquired. Cell 3: both X's acquired. Two sequential Black 1pt arrows labeled-position for "rate = µ·D" each. To the right of each row, a small kinetics graph: hereditary shows tumor-incidence-vs-age as a Blue `#0072B2` line rising linearly (one-hit kinetics, early); sporadic shows a Bluish Green `#009E73` curve rising quadratically (two-hit kinetics, late). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Knudson two-hit: hereditary cases start with one inherited mutant allele, require one somatic hit (linear kinetics, early bilateral onset); sporadic cases require two independent somatic hits (quadratic kinetics, late unilateral onset).
[O] Two parallel rows of three cells each; kinetics graph to the right of each row.
[P] Cells Black 1pt outline. Functional alleles Sky Blue. Hit (mutated allele) Vermillion X overlay. Tumor cell Vermillion 10% tint. Hereditary kinetics line Blue. Sporadic kinetics curve Bluish Green. Process arrows Black 1pt.
[E] No specific gene names rendered, no probability values as text, no axis labels as text on small kinetics graphs, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene names, probability values, axis labels, mathematical formulas, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 8.4 — Fearon-Vogelstein Colorectal Progression

**Priority: Critical.** The pan-cancer template. Sequential driver-hit accumulation visualized as a tissue-level progression timeline.

### Block 1 — Illustrae paste block

A horizontal five-stage cascade representing colonic epithelium over time. Each stage drawn as a stylized cross-section of a colonic crypt — a Black `#000000` 1pt outlined invagination shape with cells arrayed along the sides. Stage 1 (Normal): orderly Sky Blue `#56B4E9` filled cells arranged along the crypt wall, narrow crypt. Stage 2 (Small adenoma, APC loss): crypt slightly widened; cells now Blue `#0072B2` filled (hyperproliferative); a small Vermillion `#D55E00` filled circle annotates the APC hit. Stage 3 (Large adenoma, +KRAS): crypt much expanded with extra cells layered upward forming a small polyp shape; cells deeper Blue; two Vermillion circles (APC + KRAS). Stage 4 (Late adenoma, +SMAD4): polyp larger and more disordered, cells with mixed orientations; three Vermillion circles. Stage 5 (Invasive carcinoma, +TP53): basement membrane breached (Black 1pt line interrupted), cells spilling through; four Vermillion circles. Below the cascade, a horizontal Bluish Green `#009E73` 1.5pt arrow shows "10–30 years" time axis with tick marks aligned to each stage. White background, flat vector, double-column 174mm preferred (full-width if available).

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Colorectal cancer progression: normal epithelium → APC loss (small adenoma) → +KRAS (large adenoma) → +SMAD4 (late adenoma) → +TP53 (invasive carcinoma). Driver-hit accumulation visualized at the tissue level over 10–30 years.
[O] Five-stage horizontal cascade of crypt cross-sections; timeline axis below.
[P] Normal cells Sky Blue. Hyperproliferative cells Blue. Crypt outline Black 1pt. Driver-hit markers Vermillion. Timeline arrow Bluish Green.
[E] No driver-gene names rendered as text, no specific year numbers, no histology stain colors, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, driver-gene names, year numbers, histology stains, anatomical-label text, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 8.5 — Mutational Signature Spectrum (SBS4 Tobacco vs. SBS7 UV)

**Priority: Important.** The COSMIC-style 96-context bar chart is the visual signature of modern cancer genomics; comparing two signatures shows that different mutagens leave different fingerprints.

### Block 1 — Illustrae paste block

A two-panel vertical stack of 96-context bar charts. Each panel has a Black `#000000` 1pt horizontal axis with 96 evenly spaced vertical bars, grouped visually into six segments of 16 bars (one segment per substitution class: C→A, C→G, C→T, T→A, T→C, T→G), with thin Black 0.5pt vertical separators between segments. Vertical axis: relative mutation frequency, Black 1pt axis. Top panel (SBS4, tobacco): bars predominantly tall in the C→A segment (Bluish Green `#009E73` filled) with the other five segments showing low bars. The Bluish Green C→A region clearly dominates. Bottom panel (SBS7, UV): bars predominantly tall in the C→T segment (Blue `#0072B2` filled) with subsidiary peaks at T→T and CC contexts. The Blue C→T region clearly dominates. The six segments in each panel use a consistent ordering. Bars in non-dominant segments are drawn in a uniform Sky Blue `#56B4E9` filled low height. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] COSMIC-style 96-trinucleotide-context mutational signature spectra. SBS4 (tobacco) dominated by C→A transversions. SBS7 (UV) dominated by C→T at dipyrimidines. Different mutagens leave distinct fingerprints.
[O] Two stacked horizontal bar-chart panels with identical 96-context layout.
[P] SBS4 dominant C→A bars Bluish Green. SBS7 dominant C→T bars Blue. Non-dominant bars Sky Blue. Axes and segment separators Black.
[E] No textual labels under the 96 contexts, no signature names rendered, no specific frequency values, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, trinucleotide context labels, signature names, frequency values, axis-label words, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **β-globin four-mutations table (lines 54–59).** Typography reference table; the markdown is malformed and the content is naturally tabular text.
- **AI Wayback Machine prompt (none in this chapter, but exercise blocks lines 257–283).** End-of-chapter exercises, not figures.
- **The two-faces somatic-vs-germline conceptual diagram (lines 228–253).** Could be a figure, but the chapter delivers the contrast through clean prose and the existing Knudson figure already carries the dominance asymmetry visually. Not author-placed.

---

## Video Candidate Pass

**FIGURE 8.1 (Ames test):** STATIC SUFFICIENT. Workflow is sequential but each stage is a discrete state — animation would add little beyond timing.
**FIGURE 8.2 (Mutation rates):** STATIC SUFFICIENT.
**FIGURE 8.3 (Knudson):** **MILD VIDEO CANDIDATE.** Showing cell divisions ticking forward in both hereditary and sporadic lineages, with mutations stochastically appearing on each allele, makes the kinetic argument visceral — viewers see why one-hit hereditary kinetics produces early bilateral tumors while two-hit sporadic kinetics produces late unilateral tumors. The kinetics graphs filling in over time is the payoff.
**FIGURE 8.4 (Fearon-Vogelstein):** **STRONG VIDEO CANDIDATE.** The 10–30 year clonal-evolution timeline is intrinsically temporal. Animation showing a normal crypt acquiring driver hits one by one, each clonal expansion visibly outgrowing its neighbors before the next driver lands, dramatizes somatic evolution exactly as the chapter argues. DNA-repair-pathway choice (NHEJ vs. HDR) could also be foregrounded in the same animation, connecting back to Ch 7's CRISPR repair fork.
**FIGURE 8.5 (Mutational signatures):** STATIC SUFFICIENT.

**Video candidates identified: 1 strong + 1 mild.** Recommended: **Fig 8.4 (multi-step carcinogenesis).** The somatic-evolution-in-time framing is the chapter's central claim and the static cascade can only hint at it; animated clonal expansion under sequential selection is the chapter in motion.

---

## Split-point note

Chapter is a hinge between the genetics half (Ch 1–7) and the evolution half (Ch 9–10). Knudson kinetics share mathematics with Hardy-Weinberg dynamics in Ch 10 (the *p(t+1) = p(t)(1+s)* formula appears in both); maintain visual conventions for "allele" so that a Ch 8 RB1 allele and a Ch 10 population-genetics allele look like the same kind of object. Mutational-signature SBS1 is the molecular clock referenced forward to Ch 13 — keep the 96-context bar layout consistent if that figure is revisited.
