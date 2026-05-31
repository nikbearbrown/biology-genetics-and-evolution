# CAJAL Figure Intelligence — Chapter 10: Population Genetics and Natural Selection

**Source:** `chapters/10-population-genetics.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Hardy-Weinberg equilibrium as the null hypothesis; the five forces that violate it (mutation, selection, drift, gene flow, non-random mating); worked example of sickle-cell balanced polymorphism in West Africa with q* = sAA / (sAA + sSS) ≈ 0.111. Seven author-placed figures.

---

## Density Recommendation

**7 figures, Mechanistic density.** All seven earn their place. The chapter is built around quantitative predictions, and each figure either grounds an equation (random mating, mutation-selection balance, drift, inbreeding) or visualizes the worked sickle-cell case (allele-frequency dynamics, geographic overlay).

---

## Zone Map

- **MC:** Hardy-Weinberg random-mating Punnett-style derivation → p², 2pq, q². Genetic-drift trajectories under different Ne. Inbreeding shifting genotype frequencies without shifting allele frequencies. Sickle-cell balanced polymorphism: q* = sAA/(sAA+sSS).
- **VG:** Allele-frequency counting worked example. Geographic overlay of HbS frequency against historical malaria endemicity.
- **PQ:** Mutation-selection balance equilibrium q* = √(μ/s). Drift variance pq/(2Ne). Sickle-cell equilibrium at q ≈ 0.111 matching observed 0.08–0.12.

---

## Figure 10.1 — Hardy-Weinberg Random Mating Diagram

**Priority: Critical.** The null hypothesis made visible. A Punnett-style derivation showing why p² + 2pq + q² = 1.

### Block 1 — Illustrae paste block

A two-panel composition. Panel 1 (gamete pool): a horizontal bar representing the gene pool, divided proportionally into a Blue `#0072B2` filled segment (A allele, frequency p) and a Sky Blue `#56B4E9` filled segment (a allele, frequency q). The width ratio of the segments reflects p : q (e.g., p = 0.7, q = 0.3). Panel 2 (Punnett-style 2×2 genotype grid): a Black `#000000` 1pt outlined 2×2 square with rows labeled-position for "egg: A (p)" and "egg: a (q)" and columns labeled-position for "sperm: A (p)" and "sperm: a (q)". The four cells filled as follows: top-left (AA) filled Blue with area proportional to p²; top-right (Aa) filled Bluish Green `#009E73` with area proportional to pq; bottom-left (Aa) filled Bluish Green with area proportional to pq; bottom-right (aa) filled Sky Blue with area proportional to q². Below the grid, a horizontal stacked bar summarizes the resulting genotype frequencies (Blue p², Bluish Green 2pq, Sky Blue q²) with the three segments labeled-position with their proportions. A Vermillion `#D55E00` 1pt curved arrow connects the gene pool back to itself, indicating "frequencies unchanged in next generation." White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Hardy-Weinberg derivation: gamete pool with allele frequencies p and q; random mating fills a 2×2 grid; genotype frequencies p², 2pq, q²; allele frequencies unchanged next generation.
[O] Gamete-pool bar (top), 2×2 Punnett-style grid (middle), genotype-frequency summary bar (bottom), conservation arrow (right).
[P] A allele Blue. a allele Sky Blue. Heterozygote Aa Bluish Green. Grid outline Black 1pt. Conservation arrow Vermillion.
[E] No specific numerical p, q values rendered as text, no genotype labels as text, no axis numbers, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, allele frequency values, genotype labels, numerical proportions, equation text, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 10.2 — Allele Frequency Counting Worked Example

**Priority: Important.** Makes the "what we are counting" section concrete: from individual genotypes to allele frequencies.

### Block 1 — Illustrae paste block

A two-region composition. Upper region: a small population of 10 stylized diploid individuals drawn as Black `#000000` 1pt outlined ovals, each containing two small filled rectangles representing the two alleles at one locus. Three individuals are AA (both rectangles Blue `#0072B2`), four are Aa (one Blue, one Sky Blue `#56B4E9`), three are aa (both Sky Blue). Lower region: a horizontal counting diagram — a Bluish Green `#009E73` filled rectangle labeled-position for "Total alleles = 2N = 20"; below it, two adjacent stacked bars showing the allele-count totals: Blue bar = 10 A alleles (3×2 + 4×1), Sky Blue bar = 10 a alleles (3×2 + 4×1). Below the bars, a horizontal proportion diagram showing p = 0.5 and q = 0.5 as two equal segments. Vermillion `#D55E00` 1pt arrows lead from the genotype counts upstairs to the allele tallies downstairs. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] From genotypes to allele frequencies: count alleles across all individuals (2N total), tally per allele, compute p and q.
[O] Top region shows 10 individuals with their alleles; bottom region tallies allele counts and computes p, q.
[P] A allele Blue. a allele Sky Blue. Individual outline Black 1pt. Total-allele bar Bluish Green. Tally arrows Vermillion.
[E] No numerical p, q values rendered, no individual ID labels, no equation text, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, frequency values, individual IDs, equation text, axis-label words, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 10.3 — Mutation-Selection Balance

**Priority: Important.** Equilibrium between mutation creating and selection removing a deleterious recessive; q* = √(μ/s).

### Block 1 — Illustrae paste block

A two-panel composition. Panel 1 (concept): a Black `#000000` 1pt outlined box labeled-position for "gene pool" containing a small population of A and a alleles drawn as Blue `#0072B2` and Sky Blue `#56B4E9` filled small circles. A Bluish Green `#009E73` 1.5pt arrow labeled-position for "μ (mutation in)" points into the box, generating new Sky Blue circles. A Vermillion `#D55E00` 1.5pt arrow labeled-position for "s (selection out)" points out of the box, removing Sky Blue circles. The two arrows are visually balanced in thickness at the equilibrium point. Panel 2 (equilibrium curve): a single line plot. Horizontal axis: selection coefficient s from 0.01 to 1, Black 1pt log scale. Vertical axis: equilibrium frequency q*, Black 1pt log scale. A solid Blue `#0072B2` 1.5pt curve traces q* = √(μ/s) for μ = 10⁻⁵, descending from upper-left to lower-right. A second dashed Sky Blue 1.5pt curve traces the same relationship for μ = 10⁻⁴ (higher), sitting above the Blue curve. A small Vermillion filled dot marks a representative equilibrium point at s = 0.5, μ = 10⁻⁵, giving q* ≈ 0.0045. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Mutation-selection balance for a deleterious recessive: mutation creates the allele at rate μ; selection removes it at rate s; equilibrium q* ≈ √(μ/s). Stronger selection lowers q*; higher mutation rate raises q*.
[O] Conceptual panel (left) with in/out arrows on a gene pool; quantitative panel (right) with q* vs. s on log-log axes for two μ values.
[P] A allele Blue. a allele Sky Blue. Mutation arrow Bluish Green. Selection arrow Vermillion. Equilibrium curves Blue (low μ) and Sky Blue dashed (high μ). Sample point Vermillion. Axes Black 1pt.
[E] No equation text rendered, no axis-label words, no numerical values, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, equation text, numerical values, axis labels, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 10.4 — Genetic Drift Trajectories

**Priority: Critical.** Drift visualized as multiple replicate populations wandering under different Ne. The Ne-dependence of drift magnitude is the chapter's most important quantitative claim about the force.

### Block 1 — Illustrae paste block

A two-panel horizontal composition. Each panel shows allele-frequency trajectories over time. Horizontal axis: generations from 0 to ~200, Black `#000000` 1pt. Vertical axis: allele frequency p from 0 to 1, Black 1pt with horizontal reference lines at p = 0 and p = 1 (fixation/loss boundaries). Panel 1 (Small Ne = 50): ten semi-transparent Sky Blue `#56B4E9` 1pt replicate lines starting at p = 0.5 and wandering dramatically across the panel; several lines hit the p = 0 or p = 1 boundary (fixation/loss) and stay there as flat segments along the boundary. Panel 2 (Large Ne = 10,000): ten semi-transparent Sky Blue 1pt replicate lines starting at p = 0.5 and barely wandering; all stay tightly clustered near p = 0.5 across the full time range. In both panels, a Blue `#0072B2` 2pt solid line at p = 0.5 indicates the expected mean. A small Vermillion `#D55E00` filled label in the corner of each panel encodes Ne size as a stylized icon (smaller circle for Ne = 50, larger for Ne = 10,000). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Genetic drift over generations under two Ne values. Small Ne (50): replicates wander, many fix or are lost. Large Ne (10,000): replicates cluster tightly near starting frequency. Variance per generation = pq/(2Ne).
[O] Two side-by-side panels with identical axes; replicate trajectories in each; expected mean line.
[P] Replicate lines semi-transparent Sky Blue 1pt. Expected mean Blue solid 2pt. Fixation/loss boundaries Black. Ne-size indicator Vermillion. Axes Black 1pt.
[E] No specific Ne values rendered as text, no axis-label words, no replicate-count text, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, Ne values, replicate counts, axis labels, equation text, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 10.5 — Inbreeding Effect on Genotype Frequencies

**Priority: Important.** Inbreeding reshuffles diploid pairings without changing allele frequencies. The conservation of p, q with a shift of 2pq → p² + 2pq(1−F) + q² is the visual payoff.

### Block 1 — Illustrae paste block

A two-panel composition. Panel 1 (random mating, F = 0): a Hardy-Weinberg horizontal stacked bar of width 1, divided into three segments — Blue `#0072B2` segment (AA, area p²), Bluish Green `#009E73` segment (Aa, area 2pq), Sky Blue `#56B4E9` segment (aa, area q²). The Bluish Green Aa segment is widest, reflecting maximum heterozygosity. Panel 2 (inbreeding, F > 0): same total width, but now the Bluish Green Aa segment has been narrowed by an amount labeled-position for "Fpq lost from heterozygotes"; that lost area is split evenly and added to the Blue AA segment and the Sky Blue aa segment (each gains Fpq/2). Vermillion `#D55E00` 1pt brackets show the additions to the homozygote classes. Below both panels, two narrow Bluish Green horizontal allele-frequency bars (divided into Blue p and Sky Blue q) are identical, demonstrating that allele frequencies have not changed. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Inbreeding shifts genotype frequencies: heterozygote frequency drops by Fpq; that deficit is split evenly between the two homozygote classes. Allele frequencies p and q unchanged.
[O] Two genotype-frequency bars (random mating vs. inbreeding) above two identical allele-frequency bars.
[P] AA Blue. Aa Bluish Green. aa Sky Blue. Heterozygote-loss bracket Vermillion. Conserved-allele bars Blue/Sky Blue.
[E] No F values rendered, no equations as text, no axis labels, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, F values, equations, axis labels, genotype names as text, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 10.6 — Sickle-Cell Balanced Polymorphism

**Priority: Critical.** The chapter's worked-example payoff. q* = sAA/(sAA+sSS) ≈ 0.111 matched against observed 0.08–0.12. The convergence-from-any-start property is the visual.

### Block 1 — Illustrae paste block

A two-panel composition. Panel 1 (fitness comparison): a horizontal bar chart with three bars representing genotype fitnesses. HbAA bar (Blue `#0072B2` filled, height 0.9). HbAS bar (Bluish Green `#009E73` filled, height 1.0 — the reference fittest). HbSS bar (Vermillion `#D55E00` filled, height 0.2). The HbAS bar is tallest and clearly marked with a Black `#000000` 1pt small star icon to indicate the heterozygote advantage. Panel 2 (frequency convergence): a single time-series line plot. Horizontal axis: generations 0 to 200, Black 1pt. Vertical axis: HbS allele frequency q from 0 to 1, Black 1pt. Three semi-transparent Sky Blue `#56B4E9` 1pt trajectory lines starting from p₀ = 0.01, 0.5, and 0.95 respectively; all three trajectories converge over generations to a common equilibrium near q = 0.111. A dashed Orange `#E69F00` 1.5pt horizontal line at q = 0.111 marks the predicted equilibrium q*. A small Vermillion filled bracket on the right margin marks the observed empirical range 0.08–0.12 in West Africa. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Sickle-cell balanced polymorphism: HbAS heterozygote has highest fitness; HbAA and HbSS pay costs. Equilibrium q* = sAA/(sAA+sSS) ≈ 0.111. All starting frequencies converge to the equilibrium.
[O] Fitness bar chart (left); allele-frequency convergence trajectories (right) with equilibrium line and observed-range bracket.
[P] HbAA Blue. HbAS Bluish Green. HbSS Vermillion. Heterozygote-advantage star Black. Convergence trajectories Sky Blue. Predicted equilibrium Orange dashed. Observed range bracket Vermillion. Axes Black 1pt.
[E] No genotype-name text rendered, no fitness values as numbers, no axis-label words, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, genotype names, fitness values, axis labels, equation text, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 10.7 — HbS Frequency Geographic Overlay

**Priority: Important.** The biogeographic confirmation: HbS frequency tracks historical malaria endemicity. Maps the chapter's quantitative claim onto Africa.

### Block 1 — Illustrae paste block

A single map of Africa drawn as a Black `#000000` 1pt outlined continent silhouette. Two overlaid distributions. Layer 1 (historical falciparum malaria endemicity, before modern eradication efforts): a faint Orange `#E69F00` 20% fill across the malaria belt — sub-Saharan Africa roughly between the Sahara and southern Africa, with the densest band in West and Central Africa. Layer 2 (HbS allele frequency contours): a series of Blue `#0072B2` 1.5pt contour lines overlaid on the map at HbS frequencies of 0.02, 0.05, 0.08, and 0.12, with the highest-frequency (0.12) contour as a closed loop centered on West Africa. The visual coincidence between the Orange malaria zone and the high-frequency Blue contours is the rhetorical point — the two distributions visibly overlap. A small Vermillion `#D55E00` filled circle marks a representative West African sampling site with HbS ≈ 0.10. Off the continent's western side, a separate small Reddish Purple `#CC79A7` filled circle in the western Atlantic represents the African-American population with HbS ≈ 0.04, connected to the West African circle by a Sky Blue `#56B4E9` 1pt curved arrow labeled-position for "10–15 generations of relaxed selection." White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] HbS allele frequency contours overlaid on the historical falciparum malaria belt in Africa. Highest HbS in malarial West Africa (~0.10–0.12). African-American HbS (~0.04) shown declining after 10–15 generations of relaxed selection.
[O] Africa silhouette with malaria-zone tint and HbS contours; African-American population marked off the continent with an arrow.
[P] Continent outline Black 1pt. Malaria zone faint Orange. HbS contours Blue 1.5pt. West African sample Vermillion. African-American sample Reddish Purple. Migration arrow Sky Blue 1pt.
[E] No country names, no city names, no contour-value labels, no scale bar, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, country names, city names, contour values, scale bar text, latitude/longitude, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Five-forces summary table (lines 247–252).** Typography reference table summarizing each force's violated HWE assumption, key parameter, and worked example. Better as text.
- **LLM Exercise simulation prompts (lines 268–383).** Code-generation prompt for an interactive simulator, not a figure asset.
- **AI Wayback Machine block (lines 387–405).** External-link / picture-research content, not a figure.

---

## Video Candidate Pass

**FIGURE 10.1 (Hardy-Weinberg):** STATIC SUFFICIENT.
**FIGURE 10.2 (Allele frequency counting):** STATIC SUFFICIENT.
**FIGURE 10.3 (Mutation-selection balance):** STATIC SUFFICIENT.
**FIGURE 10.4 (Drift trajectories):** **STRONG VIDEO CANDIDATE.** Drift is intrinsically stochastic and intrinsically temporal. Animation showing many replicate populations evolving generation by generation under different Ne values, with the variance pq/(2Ne) visibly different in real time, makes the "drift is sampling error compounded over time" claim concrete. The fixation-or-loss endpoint is the dramatic payoff that static lines only suggest.
**FIGURE 10.5 (Inbreeding):** **MILD VIDEO CANDIDATE.** Animating the heterozygote bar shrinking with rising F, with the two homozygote bars symmetrically growing, while the allele-frequency bar below stays unchanged, makes the conservation-of-alleles claim viscerally clear.
**FIGURE 10.6 (Sickle-cell convergence):** **STRONG VIDEO CANDIDATE.** Showing the three starting frequencies converging to q* over generations, then the malaria-eradication phase change with the equilibrium collapsing toward q = 0, dramatizes the chapter's central claim that the framework predicts both equilibria and post-shock dynamics. The Ch 7-style "before/after" structure is built into the model. Selection dynamics over generations is exactly the criterion the prompt asks us to flag.
**FIGURE 10.7 (Geographic overlay):** STATIC SUFFICIENT.

**Video candidates identified: 2 strong + 1 mild.** Recommended: **Fig 10.4 (drift trajectories)** and **Fig 10.6 (sickle-cell convergence + malaria phase shift).** Both meet the mechanism-as-learning-target criterion; together they let students see drift and selection as competing temporal processes — exactly the Ne × s framing the chapter relies on.

---

## Split-point note

Chapter closes the genetics-and-evolution arc. The selection equation *p(t+1) = p(t)(1+s)* is the same formula that drives clonal expansion in Ch 8 (cancer-as-somatic-evolution); maintain visual conventions so a Ch 8 driver-mutation expansion plot and a Ch 10 directional-selection plot look like cousins. The HbS worked example references the β-globin mutation introduced in earlier chapters — coordinate the molecular-level pictogram of HbS so it's recognizable across chapters. Forward references to Ch 11+ (phylogenetics, molecular clocks) should pick up the same allele-frequency-over-time visual convention used here in Figs 10.4 and 10.6.
