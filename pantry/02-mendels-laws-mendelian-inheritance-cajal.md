# CAJAL Figure Intelligence — Chapter 2: Mendel's Laws and Mendelian Inheritance

**Source:** `chapters/02-mendels-laws-mendelian-inheritance.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Mendel's combinatorial framework: the apparatus (pea plant, pure-breeding lines, binary traits, large sample size), the 3:1 monohybrid ratio that forces a particle-and-segregation mechanism, the Punnett square as bookkeeping for the product rule, the 9:3:3:1 dihybrid, the 27:9:9:9:3:3:3:1 trihybrid, the test cross as a resolution device, and the Fisher controversy about too-clean data. Cystic-fibrosis recurrence-risk arithmetic anchors the modern clinical application. Four author-placed figures. CRITICAL: Mendel's pea phenotypes are conventionally drawn in red-green (round = green, wrinkled = yellow; yellow vs green seeds; violet vs white flowers) — but red-green palettes are exactly what CAJAL rejects. Remap pea seed phenotypes to Sky Blue (dominant) and Reddish Purple (recessive) throughout, and note this in the design log.

---

## Density Recommendation

**4 figures, Mechanistic density.** Each author-placed figure earns its place: the 2×2 monohybrid Punnett square, the 4×4 dihybrid Punnett square (with product-rule comparison), the trihybrid 27:9:9:9:3:3:3:1 bar chart, and the test-cross diagram. These four collectively carry the chapter's combinatorial argument — that the Punnett square scales as 4^n and the product rule scales as n multiplications.

---

## Zone Map

- **MC:** The mechanism producing 1/4: two factors per locus, equal segregation, random fertilization. Product rule for independent loci: P(A and B) = P(A) × P(B). Test cross as a resolution device (homozygote vs heterozygote ambiguity collapses to a 1:0 vs 1:1 distinguishable ratio).
- **VG:** Punnett-square scaling from 2×2 (monohybrid) to 4×4 (dihybrid) to 8×8 (trihybrid). Phenotype-class distribution under the (3 + 1)^n binomial expansion.
- **PQ:** 3:1 monohybrid ratio. 9:3:3:1 dihybrid. 27:9:9:9:3:3:3:1 trihybrid (sums to 64). Mendel's specific counts: 5,474 round / 1,850 wrinkled (2.96:1). 705 violet / 224 white (3.15:1). 28,000 plants. CF carrier-couple per-pregnancy risk: 1/4. Binomial: P(2 of 4 affected) = 6 × (1/4)² × (3/4)² ≈ 0.211. P(0 of 4 affected) ≈ 0.316. Fisher's aggregate p ≈ 1/25,000.

---

## Figure 2.1 — Monohybrid Punnett Square (Rr × Rr)

**Priority: Critical.** The 2×2 grid the chapter's argument is built on. Reader must see the four equally likely cells, the three dominant-phenotype outcomes vs one recessive, and the 1:2:1 genotype ratio underneath the 3:1 phenotype ratio.

### Block 1 — Illustrae paste block

A 2×2 Punnett square as a large four-cell grid. Top header row: two gamete indicators above the grid — one Sky Blue `#56B4E9` filled circle (R gamete from parent 1, probability 1/2) on the left and one Reddish Purple `#CC79A7` filled circle (r gamete from parent 1, probability 1/2) on the right. Left header column: same two gamete indicators stacked vertically (R and r from parent 2). The four cells of the grid: top-left RR cell filled solid Sky Blue `#56B4E9`; top-right Rr cell filled solid Blue `#0072B2` (heterozygous, intermediate color); bottom-left Rr cell filled solid Blue `#0072B2`; bottom-right rr cell filled solid Reddish Purple `#CC79A7`. Cell borders Black `#000000` 1pt. Below the grid, two horizontal summary bars: top bar split into three Sky Blue / Blue / Blue / Reddish Purple segments at 1/4 / 1/4 / 1/4 / 1/4 (genotype distribution 1 RR : 2 Rr : 1 rr); bottom bar split into Sky-Blue-three-quarters / Reddish-Purple-one-quarter (phenotype distribution 3 dominant : 1 recessive under complete dominance). A small Vermillion `#D55E00` 0.75pt connector arrow runs from the rr cell down to the rightmost segment of the phenotype bar, marking which cell produces the recessive phenotype. White background, flat vector, single-column 89mm.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] Monohybrid Rr × Rr Punnett square — 2×2 grid, four cells, color-coded by genotype class. Below the grid, two stacked summary bars: genotype 1:2:1 and phenotype 3:1.
[O] Grid centered, header gametes outside top and left edges. Summary bars stacked below the grid.
[P] Homozygous-dominant cells Sky Blue `#56B4E9` filled. Heterozygous cells Blue `#0072B2` filled. Homozygous-recessive cells Reddish Purple `#CC79A7` filled. Gamete-indicator circles Sky Blue / Reddish Purple. Cell borders Black `#000000` 1pt. Phenotype-recessive connector arrow Vermillion `#D55E00` 0.75pt.
[E] No allele letters rendered as text inside the cells, no ratio numbers inside the image, no header labels rendered as text, no cell-coordinate labels, no decorative ornament, no shadows. Note: chapter's traditional pea palette would be green vs yellow seed colors — explicitly remapped to Sky Blue / Reddish Purple here for color-vision accessibility (red-green is the most common deficiency and pea-seed phenotypes are conventionally rendered exactly in that palette in legacy textbooks).

### Block 3 — Negative prompt

text labels, allele letters, ratio numbers, header labels, cell coordinates, gibberish letters, titles, captions, green seed colors, yellow seed colors, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 2.2 — Dihybrid Cross: 4×4 Punnett Square and Product-Rule Comparison

**Priority: Critical.** The chapter's argument that the Punnett square *is* the product rule, drawn as a grid. Reader must see the 16 cells, the four phenotype classes, and the product-rule decomposition that gives the same answer with four multiplications.

### Block 1 — Illustrae paste block

A two-element composition. Left element (larger): the 4×4 Punnett square for YyRr × YyRr. Sixteen cells arranged in four rows and four columns. Header gametes above the grid: four small circles labeled (by position, not text) YR, Yr, yR, yr — colored as Sky Blue `#56B4E9` (YR), light-Blue (Yr, a mid-shade indicated visually by a half-Sky-Blue / half-Reddish-Purple split), light-Blue (yR, same split convention reversed), Reddish Purple `#CC79A7` (yr). Left-column gametes are the same set vertically stacked. The 16 cells colored by phenotype class under complete dominance: 9 cells with at least one Y AND at least one R filled Sky Blue (dominant-dominant); 3 cells Y_ rr filled Bluish Green `#009E73` (yellow-wrinkled / Y-dominant-but-r-recessive); 3 cells yy R_ filled Blue `#0072B2` (green-round / y-recessive-but-R-dominant); 1 cell yy rr filled Reddish Purple `#CC79A7` (recessive-recessive). Right element (smaller): a small product-rule decomposition diagram — four nested multiplication blocks showing 3/4 × 3/4 = 9/16, 3/4 × 1/4 = 3/16, 1/4 × 3/4 = 3/16, 1/4 × 1/4 = 1/16. Each block rendered as two small colored squares (Sky Blue or Reddish Purple, representing P(dominant)=3/4 and P(recessive)=1/4 at each locus) joined by a small Black `#000000` × symbol, with the result square colored to match the corresponding phenotype class. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Left: 4×4 Punnett square for YyRr × YyRr with 16 cells colored by phenotype class. Nine Sky Blue (dominant-dominant), three Bluish Green (Y_ rr), three Blue (yy R_), one Reddish Purple (yy rr). Right: product-rule decomposition showing the same four phenotype-class probabilities (9/16, 3/16, 3/16, 1/16) computed as products of marginal monohybrid probabilities.
[O] Side by side, Punnett square on left (larger), product-rule blocks on right (smaller, stacked vertically).
[P] Y_R_ class Sky Blue `#56B4E9` filled. Y_rr class Bluish Green `#009E73` filled. yyR_ class Blue `#0072B2` filled. yyrr class Reddish Purple `#CC79A7` filled. Header-gamete indicators bichromatic where heterozygous. Cell borders Black `#000000` 1pt. Multiplication symbols Black 1pt.
[E] No allele letters inside cells, no probability fractions rendered as text inside the image, no axis labels, no decorative ornament, no shadows. The chapter's standard green-vs-yellow pea-seed convention is deliberately remapped here for accessibility.

### Block 3 — Negative prompt

text labels, allele letters, probability fractions, axis labels, gibberish letters, titles, captions, green seed colors, yellow seed colors, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 2.3 — Trihybrid Phenotype-Class Distribution (27:9:9:9:3:3:3:1)

**Priority: Important.** The (3 + 1)^n expansion made visible. Reader must see eight phenotype classes summing to 64 and feel that the product rule generalizes cleanly.

### Block 1 — Illustrae paste block

A horizontal bar chart with eight vertical bars, one per phenotype class for AaBbCc × AaBbCc. From left to right, the bars are scaled to heights proportional to: 27, 9, 9, 9, 3, 3, 3, 1 (out of 64). Bar colors by the number of recessive loci in the phenotype class: bar 1 (all-dominant, 0 recessive loci) Sky Blue `#56B4E9` filled, height 27; bars 2, 3, 4 (1 recessive locus each) Blue `#0072B2` filled, height 9; bars 5, 6, 7 (2 recessive loci each) Bluish Green `#009E73` filled, height 3; bar 8 (all-recessive, 3 recessive loci) Reddish Purple `#CC79A7` filled, height 1. A horizontal Black `#000000` 0.5pt baseline. Above the chart, a thin Orange `#E69F00` filled summation bar runs the full width, divided into segments of width proportional to each bar's height — a visual check that the eight classes sum to 64. White background, flat vector, single-column 89mm.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] Bar chart of eight phenotype classes for the trihybrid AaBbCc × AaBbCc cross, ratio 27:9:9:9:3:3:3:1 (sum 64). Bars colored by number of recessive loci in the class. Summation bar above the chart shows the eight segments composing the total 64.
[O] Vertical bars in descending then ascending pattern (27 / 9 / 9 / 9 / 3 / 3 / 3 / 1). Summation bar horizontal across the top.
[P] All-dominant class Sky Blue `#56B4E9` filled. One-recessive classes Blue `#0072B2` filled. Two-recessive classes Bluish Green `#009E73` filled. All-recessive class Reddish Purple `#CC79A7` filled. Summation bar Orange `#E69F00` filled. Baseline Black `#000000` 0.5pt.
[E] No axis labels rendered as text, no numerical bar values inside the image, no phenotype-class strings (A_B_C_, etc.) rendered as text, no chart title, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, axis labels, numerical bar values, phenotype-class strings, chart title, gibberish letters, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 2.4 — Test Cross Diagram (Unknown Round × rr Tester)

**Priority: Important.** The diagnostic logic that distinguishes homozygous-dominant from heterozygous. Two outcomes shown side by side: unknown was RR vs unknown was Rr.

### Block 1 — Illustrae paste block

A two-panel composition. Left panel (unknown is RR): a small Sky Blue `#56B4E9` filled circle (the unknown parent, homozygous-dominant) mating to a Reddish Purple `#CC79A7` filled circle (the rr tester). Below the mating, a 2×1 Punnett-square strip (one row, two columns) showing two offspring cells, both filled Blue `#0072B2` (Rr, heterozygous, dominant phenotype). Beneath the strip, a horizontal phenotype-distribution bar showing 100% Sky-Blue (all dominant). Right panel (unknown is Rr): same setup but unknown parent is Blue `#0072B2` filled (heterozygous). The 2×2 Punnett strip below shows two cells — one Blue Rr (dominant) and one Reddish Purple rr (recessive). Beneath the strip, a horizontal phenotype-distribution bar split 50/50 between Sky-Blue (dominant) and Reddish Purple (recessive). Between the two panels, a vertical Black `#000000` 0.5pt divider. White background, flat vector, single-column 89mm.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] Two-panel test-cross comparison. Left: unknown is RR — all offspring dominant (1:0 ratio). Right: unknown is Rr — offspring split 1:1 dominant : recessive. The presence of any recessive offspring at the predicted frequency identifies the unknown as heterozygous.
[O] Two panels side by side, vertical divider between. Each panel: parental icons at top, offspring cells in middle, phenotype-distribution bar at bottom.
[P] Homozygous-dominant parent Sky Blue `#56B4E9` filled. Heterozygous parent Blue `#0072B2` filled. Homozygous-recessive parent / offspring Reddish Purple `#CC79A7` filled. Heterozygous offspring Blue. Phenotype bars use the same palette. Cell borders Black `#000000` 1pt. Divider Black 0.5pt.
[E] No genotype labels rendered as text inside the image, no ratio numbers, no panel titles, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, genotype letters, ratio numbers, panel titles, gibberish letters, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Seven-traits character table (lines 32–34).** Tabular reference of dominant/recessive states; typography.
- **F2 counts table across seven traits (lines 58–60).** Mendel's published counts; render as a typeset table.
- **Binomial recurrence-risk table for CF families (lines 150–154).** A 5-column probability table; typography. (If the table becomes a chart, defer to the simulator's Panel 4 readout, not a print figure.)
- **Pea-plant botanical illustration.** Decorative; the chapter's argument is about counts, not morphology. The AI Wayback Machine and the historical-scene prose carry the period flavor.
- **Mendel portrait.** Photographic; not figure intelligence.
- **CFTR molecular structure or chloride-channel cartoon.** Chapter mentions CF as a clinical application of the 1:2:1 ratio, not as a molecular target. Defer to a later molecular-genetics chapter if needed.
- **Fisher chi-square distribution chart.** Mentioned in the Fisher-controversy section; the statistic is a number, not a figure. The exercises ask the reader to compute chi-square, which the simulator's Panel 3 covers — print figure not warranted.
- **Naudin / Kölreuter comparison vignette.** Historical context, prose.

---

## Video Candidate Pass

**FIGURE 2.1 (Monohybrid Punnett square):** **STRONG VIDEO CANDIDATE.** Animation that draws the 2×2 grid cell-by-cell from gamete combinations and then collapses to the 1:2:1 / 3:1 summary bars is the canonical Mendelian-arithmetic demonstration. The chapter's Panel 1 / Panel 2 simulators already cover this interactively; the recommendation here is a polished standalone video for course adoption.
**FIGURE 2.2 (Dihybrid 4×4 + product rule):** **STRONG VIDEO CANDIDATE.** The Punnett-square = product-rule equivalence is the chapter's central argument and is much easier to feel when the 16 cells light up in groups of 9 / 3 / 3 / 1 in synchrony with the product-rule decomposition on the right. This is the textbook video moment for showing that two different bookkeepings produce identical answers.
**FIGURE 2.3 (Trihybrid bar chart):** **MILD VIDEO CANDIDATE.** An animation that builds up the eight bars one at a time as the (3 + 1)^3 binomial expansion is computed could dramatize "the framework generalizes cleanly." Static probably suffices; the simulator covers the interactive case.
**FIGURE 2.4 (Test cross):** STATIC SUFFICIENT.

**Video candidates identified: 2 strong + 1 mild.** Recommended for production: **Fig 2.1 (monohybrid Punnett build) and Fig 2.2 (Punnett ≡ product rule).** These pair naturally with Chapter 1's meiosis videos — Ch 1 shows where the gametes come from, Ch 2 shows how the gametes combine. Together they form a four-video set that anchors the genetics half of the book.

---

## Split-point note

The genotype-class palette (Sky Blue homozygous-dominant / Blue heterozygous / Reddish Purple homozygous-recessive) established here propagates forward through Ch 3 (extensions). For Ch 3's incomplete-dominance section, Blue retains its heterozygous-intermediate meaning naturally — pink snapdragons in the print figure become Blue (intermediate between Sky Blue and Reddish Purple), which is exactly what incomplete dominance means biologically. Coordinate so the metaphor reads as "color blending = phenotype blending."

**Palette divergence note for the design log:** The chapter's interactive simulators use DESIGN.md's blue triad (#1a5276 / #2980b9 / #85c1e9). The CAJAL print pantry uses the Okabe-Ito accessible palette and additionally remaps Mendel's pea phenotypes (conventionally rendered in red-green: round vs wrinkled, green vs yellow seeds, violet vs white flowers) onto Sky Blue vs Reddish Purple. This is a deliberate accessibility choice — red-green color vision deficiency affects ~8% of males (a number the chapter itself cites for color blindness in the X-linked section), and the same population is exactly the audience the introductory-genetics chapter speaks to. Note the divergence in the master design log.
