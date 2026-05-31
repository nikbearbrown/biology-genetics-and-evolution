# CAJAL Figure Intelligence — Chapter 3: Extensions of Mendelian Genetics

**Source:** `chapters/03-extensions-mendelian-genetics.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. The chapter argues that strict Mendelian inheritance is one model with six assumptions; every "extension" is a story about which assumption fails. Concrete anchors: incomplete dominance (snapdragons, FH), codominance (ABO), recessive epistasis (Bombay 3:3:3:7 ratio), Lab coat color (9:3:4), polygenic 1:4:6:4:1 → bell curve, pleiotropy (sickle-cell), penetrance (BRCA1 two-sister), environmental modification (PKU, G6PD), mitochondrial maternal inheritance, imprinting (Prader-Willi / Angelman). **No author-placed figures in this chapter.**

---

## Density Recommendation

**3 figures, Argument density.** The chapter has no `![...](images/...)` markers — author has not yet placed figures. CAJAL recommends three new figures earn their place because the chapter pivots on three visualizable mechanisms that text alone bruises: the modified F₂ ratio table-as-tree (epistasis), the binomial → Gaussian convergence (polygenic), and the genotype-to-phenotype function as the thing being modified by every extension (the chapter's spine). Author should slot these into the manuscript before final layout.

---

## Zone Map

- **MC:** The six Mendelian assumptions and the table of which extension breaks which. The genotype-to-phenotype function as the locus of every extension. Modified F₂ ratios as arithmetic-from-Punnett-then-reassignment.
- **VG:** Bombay-pathway substrate logic (H gene product is substrate for ABO enzymes — no substrate, no phenotype). Polygenic binomial → Gaussian convergence. Pedigree differences (autosomal-dominant-with-reduced-penetrance vs autosomal-recessive vs mitochondrial vs imprinting).
- **PQ:** 1:2:1 (incomplete dominance / codominance), 9:3:3:1 (Mendelian dihybrid), 9:3:4 (recessive epistasis, Labs), 12:3:1 (dominant epistasis), 9:7 (duplicate recessive), 15:1 (duplicate dominant), 13:3 (suppression), 3:3:3:7 (Bombay). BRCA1 penetrance 60–72%. Sickle-cell allele 5–15% in malaria zones. Mitochondrial genome 16,569 bp / 37 genes.

---

## Figure 3.1 — Modified F₂ Ratios as Punnett-Square-Plus-Reassignment

**Priority: Critical.** This is the chapter's mechanical engine. Every extension that modifies a 9:3:3:1 ratio does it by collapsing or relabeling specific genotype classes, not by changing meiotic segregation. One figure makes this explicit.

### Block 1 — Illustrae paste block

A horizontal three-panel composition. Left panel: a standard 4×4 dihybrid Punnett square with the 16 cells colored by the four standard 9:3:3:1 phenotype classes — 9 cells Blue `#0072B2`, 3 cells Sky Blue `#56B4E9`, 3 cells Bluish Green `#009E73`, 1 cell Orange `#E69F00`. Label-free; phenotype-class membership read by color. Middle panel: the same 16-cell grid, now recolored for recessive epistasis (9:3:4) — the 3 cells that were Bluish Green and the 1 cell that was Orange both become Vermillion `#D55E00`, merging into a single 4-cell class. Right panel: the same 16-cell grid, now recolored for dominant epistasis (12:3:1) — the 9 Blue cells and the 3 Sky Blue cells merge into a single Blue class (12), 3 Bluish Green cells stay (3), 1 Orange stays (1). A Black `#000000` 1pt arrow runs left→middle→right indicating "same gametogenesis, different phenotype assignment rule." White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Three 4×4 Punnett squares in horizontal sequence. Panel 1: standard 9:3:3:1, four phenotype classes. Panel 2: recessive epistasis 9:3:4, three classes (two original classes merged into Vermillion). Panel 3: dominant epistasis 12:3:1, three classes (two original classes merged into Blue). The Punnett-square genotype layout is identical across all three panels.
[O] Horizontal three-panel sequence with a connecting arrow.
[P] Standard classes: Blue (9 class), Sky Blue (3 class), Bluish Green (3 class), Orange (1 class). Merged epistasis classes: Vermillion (recessive merge), Blue (dominant merge).
[E] No text labels inside Punnett cells, no genotype letters rendered as graphics, no enzyme names, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, genotype letters in cells, percent signs, enzyme names, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 3.2 — Polygenic Inheritance: Binomial Convergence to Gaussian

**Priority: Critical.** The polygenic-to-Gaussian convergence is the chapter's mathematically deepest move (central limit theorem applied to additive Mendelian alleles). Text alone cannot deliver the visual shock of "1:4:6:4:1 with 2 loci → smooth bell with 20 loci."

### Block 1 — Illustrae paste block

A horizontal three-panel composition, three histograms side by side. Panel 1 (n=2 loci, 5 classes): bars at heights 1, 4, 6, 4, 1, all Sky Blue `#56B4E9` filled rectangles, jagged stair-step appearance. Panel 2 (n=5 loci, 11 classes): bars in binomial coefficient heights 1, 10, 45, 120, 210, 252, 210, 120, 45, 10, 1, Bluish Green `#009E73` filled rectangles — taller, narrower bars, beginning to suggest a curve. Panel 3 (n=20 loci, 41 classes): bars so narrow they appear continuous, Blue `#0072B2` filled, with a Black `#000000` 1pt smooth Gaussian curve overlaid — visually indistinguishable from a normal distribution. Below each panel, the number of contributing loci is implied by panel position. A small Vermillion `#D55E00` annotation arrow points from panel 1 to panel 3 indicating direction of convergence. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Three histograms: n=2 (5 bars, binomial 1:4:6:4:1), n=5 (11 bars, binomial coefficients), n=20 (41 narrow bars with overlaid Gaussian curve). All bars baseline-aligned. Histograms scaled to same total area, not same maximum bar height.
[O] Horizontal three-panel comparison, left to right, with directional arrow.
[P] n=2 Sky Blue. n=5 Bluish Green. n=20 Blue with Black Gaussian overlay. Direction arrow Vermillion.
[E] No axis numerical labels, no class names, no normal distribution equation rendered, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, numerical axis values, equations, percent signs, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 3.3 — Bombay Phenotype Substrate Logic

**Priority: Important.** The Bombay example is the chapter's worked-end-to-end mechanism. The conceptual point — H-gene product is the substrate for ABO enzymes, no substrate means no product regardless of ABO genotype — is a substrate-pathway diagram, which is what biology students need to see for epistasis to feel mechanistic rather than verbal.

### Block 1 — Illustrae paste block

A vertical two-pathway composition. Top row: a precursor molecule (small Black `#000000` open circle) sits at the top, labeled by position only. To its left, the H-gene enzyme (Blue `#0072B2` filled oval) acts on it via a Blue 1pt arrow, producing the H antigen (Sky Blue `#56B4E9` filled circle). Middle row: the H antigen feeds into two parallel branches. Branch 1: the I^A enzyme (Bluish Green `#009E73` filled oval) modifies H antigen, producing A antigen (Bluish Green filled circle with a small attached square representing N-acetylgalactosamine). Branch 2: the I^B enzyme (Vermillion `#D55E00` filled oval) modifies H antigen, producing B antigen (Vermillion filled circle with a small attached triangle representing galactose). Bottom row: the same pathway shown with the H enzyme grayed-out (Reddish Purple `#CC79A7` outline only, unfilled) representing the *hh* Bombay genotype. Now the precursor → H antigen step is broken, no H antigen exists, and the I^A and I^B branches sit empty with no substrate (downstream A and B antigen circles shown as open Black outlines, unfilled). A Black 1pt vertical divider separates "normal H present" (top) from "Bombay hh" (bottom). White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Two-row substrate-pathway diagram. Top row: precursor → H antigen → (branch to A antigen via I^A enzyme; branch to B antigen via I^B enzyme). Bottom row: same pathway with H enzyme inactive — precursor present, but no H antigen, both downstream branches empty regardless of ABO genotype.
[O] Vertical two-row comparison with horizontal substrate flow within each row.
[P] Precursor Black open circle. H antigen Sky Blue. I^A enzyme Bluish Green. A antigen Bluish Green. I^B enzyme Vermillion. B antigen Vermillion. Inactive H enzyme Reddish Purple outline only. Empty downstream products Black outlines only.
[E] No specific monosaccharide chemical structures rendered, no atomic detail, no enzyme amino acid sequences, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, enzyme names rendered as graphics, monosaccharide chemical structures, atomic detail, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Six-assumptions table (text-prose section).** The "Assumption 1 — Complete dominance ... Assumption 6 — Autosomal loci" structure is a reference list; rendering it as a graphic adds nothing typography cannot already deliver.
- **Epistasis ratio table (lines 141–149).** Already a clean table in the manuscript; do not duplicate as a figure.
- **Two-sister BRCA1 narrative.** Pedigree-style figure would help but is downstream content (Chapter 8 cancer); defer.
- **AI Wayback Machine box (Karl Landsteiner).** Out of scope.

---

## Video Candidate Pass

**FIGURE 3.1 (Modified F₂ ratios):** STATIC SUFFICIENT — the comparison is what carries the meaning, not motion. Could be a mild click-through interactive (toggle epistasis type, watch cells recolor), but a printed comparison delivers the same insight.
**FIGURE 3.2 (Polygenic → Gaussian):** **MILD VIDEO CANDIDATE.** Sliding n from 2 to 100 and watching the histogram smooth into a bell would dramatize the central limit theorem; useful as an interactive widget more than a video.
**FIGURE 3.3 (Bombay substrate logic):** STATIC SUFFICIENT — the two-row contrast (functional vs broken) delivers the mechanism in one read.

**Video candidates identified: 0 strong, 1 mild.** Recommended interactive: a polygenic slider widget for Figure 3.2 in the LLM-exercise companion. No mechanism in this chapter genuinely requires animation.

---

## Split-point note

Chapter cross-references Chapter 2 (3:1 and 9:3:3:1 Mendelian baseline) and forward-references Chapter 8 (BRCA1 cancer biology) and Chapter 9 (heterozygote advantage and balancing selection for sickle-cell allele frequencies). Figure 3.1 should visually echo Chapter 2's Punnett-square treatment so the "same skeleton, modified function" claim lands visually as well as textually.
