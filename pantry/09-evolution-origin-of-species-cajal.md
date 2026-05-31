# CAJAL Figure Intelligence — Chapter 9: Evolution and the Origin of Species

**Source:** `chapters/09-evolution-origin-of-species.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Four-ingredient Darwinian mechanism worked through the Grant finches on Daphne Major (drought 1976–77), the breeder's equation R = h²S, three modes of selection, seven lines of evidence, and speciation (allopatric + sympatric/polyploid). Six author-placed figures.

---

## Density Recommendation

**6 figures, Mechanistic density.** All six earn their place. The chapter alternates between empirical data (Grant time series, parent-offspring regression), conceptual diagrams (selection modes, homology, polyploidy), and one biogeographic map (Wallace Line). Each is load-bearing for a different rhetorical move.

---

## Zone Map

- **MC:** Parent-offspring regression as the operational definition of heritability. Three modes of selection (directional/stabilizing/disruptive) acting on phenotype distributions. Polyploidy speciation in a single generation.
- **VG:** Forelimb homology across human/bat/whale/horse/bird — common bone plan, different functions. Wallace Line as the biogeographic boundary.
- **PQ:** Beak depth time series on Daphne Major across decades of drought/rain cycles. Selection differential S = 0.6 mm → R = 0.42 mm predicted, 0.3 mm observed.

---

## Figure 9.1 — Parent-Offspring Regression for Beak Depth

**Priority: Important.** The operational definition of heritability rendered as a scatter plot; h² ≈ 0.7 is the slope of the best-fit line.

### Block 1 — Illustrae paste block

A single scatter plot. Horizontal axis: midparent beak depth (mm), Black `#000000` 1pt with tick marks at integer values from 7 to 13. Vertical axis: offspring beak depth (mm), Black 1pt with the same range and tick marks. Inside the axes, a cloud of small Sky Blue `#56B4E9` filled circles representing individual parent-offspring pairs, arrayed in a clear positive diagonal pattern from lower-left to upper-right. A solid Blue `#0072B2` 1.5pt best-fit regression line drawn through the cloud with positive slope (~0.7). A dashed Bluish Green `#009E73` 1pt reference line at slope 1 (the maximum-possible-heritability reference) for visual comparison, drawn at a steeper angle than the regression line. A small Vermillion `#D55E00` filled bracket on the right margin indicates the angle between the two lines as the "shortfall from h² = 1." White background, flat vector, single-column 89mm.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] Parent-offspring regression: midparent beak depth on x, offspring beak depth on y. Slope of regression line equals narrow-sense heritability (h² ≈ 0.7). Reference slope=1 shown for comparison.
[O] Single scatter plot with two lines overlaid: regression line (solid Blue), h²=1 reference (dashed Bluish Green).
[P] Data points Sky Blue. Regression line Blue solid 1.5pt. Reference line Bluish Green dashed 1pt. Shortfall bracket Vermillion. Axes Black 1pt.
[E] No specific numerical heritability value rendered, no axis-label words, no individual point labels, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, axis-label words, numerical values, point labels, statistical-test annotations, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 9.2 — Beak Depth Time Series on Daphne Major

**Priority: Critical.** The headline empirical claim: directional selection visible in real time, oscillating with drought/rain cycles across 40+ years.

### Block 1 — Illustrae paste block

A single horizontal time-series line plot. Horizontal axis: year from ~1973 to ~2013, Black `#000000` 1pt with tick marks at five-year intervals. Vertical axis: mean beak depth (mm), Black 1pt, ranging from ~8.5 to ~10.5. The main trace is a Blue `#0072B2` 1.5pt continuous line showing population-mean beak depth across years, drawn with visible peaks and troughs corresponding to selection events. A sharp upward step from ~9.4 to ~10.0 at 1977 (the drought year) is the most prominent feature, marked by a Vermillion `#D55E00` filled vertical band spanning the drought interval. Subsequent oscillations show further upward shifts during dry years and downward returns during wet years. Background shading: faint Sky Blue `#56B4E9` 5% horizontal bands corresponding to documented wet (El Niño) years; faint Orange `#E69F00` 5% horizontal bands for documented dry years. A small Bluish Green `#009E73` filled triangle annotates the 1977 drought as the chapter's worked example. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Mean beak depth on Daphne Major 1973–2013. Sharp upward shift in 1977 drought; oscillations across subsequent drought/rain cycles. Directional selection visible in real time.
[O] Single time-series line plot; vertical band marks the 1977 drought; background shading indicates wet/dry years.
[P] Mean-trace line Blue solid 1.5pt. 1977 drought band Vermillion. Wet-year shading faint Sky Blue. Dry-year shading faint Orange. Worked-example marker Bluish Green. Axes Black 1pt.
[E] No year text rendered, no specific mean values labeled, no event names rendered, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, year text, mean values, event names, axis-label words, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 9.3 — Three Modes of Selection

**Priority: Critical.** The conceptual triad. Each panel shows what selection does to a phenotype distribution.

### Block 1 — Illustrae paste block

A three-panel horizontal composition. Each panel shows a phenotype-distribution-before-and-after pair: a faint Sky Blue `#56B4E9` filled bell-curve (parent generation, drawn lighter) overlaid with a darker Blue `#0072B2` filled bell-curve (offspring generation). Below each distribution, a small fitness function curve in Bluish Green `#009E73` 1.5pt line showing which phenotypes were favored. Panel 1 (Directional): the Blue offspring curve is shifted to the right of the faint Sky Blue parent curve; fitness function below rises monotonically from left to right. Panel 2 (Stabilizing): offspring curve sits at the same mean as parent but is narrower and taller; fitness function below is a hump centered on the mean. Panel 3 (Disruptive): offspring distribution is bimodal with two peaks flanking a central trough; fitness function below is U-shaped (low in middle, high at extremes), drawn as a Bluish Green inverted hump. Each panel's distributions and fitness function share a common horizontal phenotype axis (Black `#000000` 1pt). A small Vermillion `#D55E00` filled arrow under each panel indicates the direction of mean shift (right for directional, no arrow for stabilizing, outward splay for disruptive). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Three modes of selection acting on a phenotype distribution. Directional shifts the mean. Stabilizing narrows variance. Disruptive produces bimodality.
[O] Three side-by-side panels; each with parent/offspring distributions stacked and a fitness function below.
[P] Parent distribution faint Sky Blue. Offspring distribution Blue. Fitness function Bluish Green 1.5pt line. Direction-of-change arrows Vermillion. Axes Black 1pt.
[E] No mode names rendered, no axis-label words, no numerical fitness values, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, mode names, axis-label words, numerical values, fitness equations, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 9.4 — Forelimb Homology Across Vertebrates

**Priority: Critical.** The canonical visual argument for common descent. Same bones, different functions, side-by-side.

### Block 1 — Illustrae paste block

A five-panel horizontal comparison of forelimb skeletons. Each panel shows a stylized forelimb skeleton drawn as Black `#000000` 1pt outlines, oriented in the same direction (proximal end at left, distal end at right). Across all five, the corresponding bones are color-coded identically: humerus Blue `#0072B2`, radius Sky Blue `#56B4E9`, ulna Bluish Green `#009E73`, wrist bones (carpals) Reddish Purple `#CC79A7`, palm bones (metacarpals) Orange `#E69F00`, digit bones (phalanges) Vermillion `#D55E00`. Panel 1 (Human arm): proportions of a human arm/hand. Panel 2 (Bat wing): elongated phalanges supporting wing membrane (drawn as faint Sky Blue 10% filled webbing). Panel 3 (Whale flipper): shortened bones embedded in a fin outline. Panel 4 (Horse foreleg): humerus and radius reduced relative to extended digit. Panel 5 (Bird wing): fused bones with feathers indicated by short Black 0.5pt lines. The five panels are visually aligned along the humerus position so the homologous-bone correspondence is obvious at a glance. White background, flat vector, double-column 174mm preferred (full-width if available).

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Forelimb homology in five vertebrates: human, bat, whale, horse, bird. Same set of bones in the same relative positions, modified for different functions.
[O] Five panels side by side, oriented identically, aligned at the humerus position.
[P] Humerus Blue. Radius Sky Blue. Ulna Bluish Green. Carpals Reddish Purple. Metacarpals Orange. Phalanges Vermillion. Outlines Black 1pt. Membranes/feathers faint Sky Blue 10%.
[E] No species names rendered, no bone names rendered, no anatomical-direction labels, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, species names, bone names, anatomical-direction labels, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 9.5 — Wallace Line Map

**Priority: Important.** Biogeography made geographic. The deep ocean trench that never bridged at lowest sea levels — Asian fauna on one side, Australasian on the other.

### Block 1 — Illustrae paste block

A simplified map of the Indonesian archipelago between Southeast Asia and Australia. Landmasses drawn as Black `#000000` 1pt outlined shapes filled with faint Sky Blue `#56B4E9` 15% tint. To the west of the Wallace Line: the islands of Sumatra, Java, Borneo, Bali — these islands tinted a slightly stronger Sky Blue 25% (Asian biogeographic zone). To the east: Lombok, Sulawesi, the Lesser Sundas, New Guinea, Australia — tinted Orange `#E69F00` 20% (Australasian biogeographic zone). The Wallace Line itself drawn as a Vermillion `#D55E00` 2pt solid line running between Bali and Lombok and curving northward between Borneo and Sulawesi, visibly bisecting the archipelago. Small Reddish Purple `#CC79A7` filled silhouette icons indicate representative Asian fauna (e.g., tiger, monkey) on the west side and Australasian fauna (e.g., marsupial, cockatoo) on the east side, each at a generic stylized scale. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Wallace Line: a sharp biogeographic boundary running between Bali and Lombok and between Borneo and Sulawesi. Asian fauna west; Australasian (marsupial-dominated) fauna east. Marks a deep trench never bridged at lowest Pleistocene sea levels.
[O] Map of the Malay Archipelago; Wallace Line as a bold line bisecting the islands; fauna icons on each side.
[P] Landmass outlines Black 1pt. Asian-side tint Sky Blue. Australasian-side tint Orange. Wallace Line Vermillion 2pt. Fauna silhouettes Reddish Purple.
[E] No place names rendered, no compass rose, no latitude/longitude text, no scale bar text, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, place names, latitude longitude labels, compass rose, scale bar text, country borders, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 9.6 — Polyploidy Speciation Mechanism

**Priority: Critical.** Sympatric speciation in a single generation. The mechanism is mechanistically beautiful and the diagram has to show why the triploid is sterile.

### Block 1 — Illustrae paste block

A three-row vertical mechanism diagram. Row 1 (Origin of the tetraploid): a parental diploid plant indicated by a Sky Blue `#56B4E9` filled small leaf icon with "2n=14" indicated by two pairs of Black `#000000` 1pt short chromosomes drawn in the cell-icon to one side. A meiotic-error arrow leads down to an unreduced diploid gamete (Sky Blue larger icon, two pairs of chromosomes). Two such unreduced gametes fuse to form a tetraploid offspring (Blue `#0072B2` filled larger leaf icon with four pairs of chromosomes). Row 2 (Sterile triploid hybrid): tetraploid (Blue, 4n=28) shown crossing with diploid parent (Sky Blue, 2n=14); fusion of normal-diploid gamete (n=14) from tetraploid with normal-haploid gamete (n=7) from diploid produces a triploid offspring (Reddish Purple `#CC79A7` filled icon, 3n=21). The triploid's meiosis is shown to the right as three unpaired chromosomes that cannot partition evenly — drawn as a Vermillion `#D55E00` X overlay indicating sterility. Row 3 (Fertile tetraploid lineage): two tetraploids cross; their unreduced-diploid gametes (n=14 each) fuse to produce another tetraploid (Blue filled icon, 4n=28); a Bluish Green `#009E73` checkmark indicates fertility. Process arrows Black 1pt throughout. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Polyploidy speciation: unreduced gametes fuse to form a tetraploid; the tetraploid × diploid cross produces a sterile triploid (chromosomes cannot partition evenly); tetraploid × tetraploid produces fertile offspring. Reproductive isolation in one generation.
[O] Three vertical rows: origin, sterile hybrid, fertile lineage. Cross arrows between gametes.
[P] Diploid parent Sky Blue. Tetraploid Blue. Triploid hybrid Reddish Purple. Sterility marker Vermillion X. Fertility marker Bluish Green check. Chromosomes Black 1pt. Process arrows Black 1pt.
[E] No chromosome-number text rendered as graphics, no species names, no gamete-type labels as text, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, chromosome numbers, species names, gamete labels, ploidy-formula text, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Cytochrome c divergence table (lines 116–124).** Typography reference table; the markdown is malformed and the content is naturally tabular text.
- **Reproductive isolating barriers table (lines 144–146).** Typography reference table comparing pre- and post-zygotic barriers.
- **LLM exercise prompts (lines 231–258).** Picture-research / external-prompt content, not figures.
- **AI Wayback Machine block (lines 261–281).** External-link content, not a figure.
- **Five-misconceptions section (lines 171–183).** Pure exposition with no diagrammable mechanism distinct from the existing figures.

---

## Video Candidate Pass

**FIGURE 9.1 (Parent-offspring regression):** STATIC SUFFICIENT.
**FIGURE 9.2 (Beak depth time series):** **MILD VIDEO CANDIDATE.** Animating the time series with year-by-year ticker and the population histogram shifting in real time alongside it could make the four-decade record viscerally connect to the underlying generations.
**FIGURE 9.3 (Selection modes):** **STRONG VIDEO CANDIDATE.** Selection dynamics in time are the chapter's central mechanism. Animation showing successive generations under each fitness function — the directional histogram crawling rightward, the stabilizing histogram narrowing, the disruptive histogram splitting into a bimodal peak — dramatizes the mechanism in a way the static three-panel comparison only hints at. The mechanism-as-learning-target criterion is met three times in one figure.
**FIGURE 9.4 (Forelimb homology):** STATIC SUFFICIENT.
**FIGURE 9.5 (Wallace Line):** STATIC SUFFICIENT.
**FIGURE 9.6 (Polyploidy):** **MILD VIDEO CANDIDATE.** Showing meiosis stepping through the partition failure in the triploid (three chromosomes trying to align on a bipolar spindle and failing) versus the clean tetraploid partition could make the sterility mechanism visceral.

**Video candidates identified: 1 strong + 2 mild.** Recommended: **Fig 9.3 (selection modes).** Showing the same starting distribution evolve under three different fitness landscapes is the textbook video moment for evolutionary biology; the static figure cannot match the dynamic transformation that students need to internalize.

---

## Split-point note

Chapter sets up Ch 10's quantitative population genetics. The breeder's equation R = h²S is the phenotype-level handoff to Hardy-Weinberg's allele-level framework. Maintain visual conventions for "allele frequency" and "phenotype distribution" so Fig 9.3's distributions and Ch 10's allele-frequency plots use compatible iconography — e.g., the Sky Blue / Blue contrast for "before/after" or "parent/offspring" should carry forward.
