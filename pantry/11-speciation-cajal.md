# CAJAL Figure Intelligence — Chapter 11: Speciation

**Source:** `chapters/11-speciation.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Chapter walks the machinery by which one lineage becomes two: BSC and its limits, prezygotic vs postzygotic barriers, allopatric (vicariance / dispersal) and sympatric (polyploidy / host shift / sensory drive) routes, Dobzhansky-Muller snowball, adaptive radiation, and the Nm / m/s phase space. Five author-placed figures.

---

## Density Recommendation

**5 figures, Mechanistic density.** Chapter's argument depends on visible mechanisms — chromosome arithmetic for polyploidy, host-shift timing for *Rhagoletis*, the quadratic snowball, the Big Bird genealogy on Daphne Major, and the Nm/m·s phase diagram. All five earn their place.

---

## Zone Map

- **MC:** Reproductive-isolation barriers organized prezygotic vs postzygotic. Polyploidy chromosome arithmetic (triploid univalent segregation → (1/2)^n). Dobzhansky-Muller incompatibility accumulation (t² snowball). Big Bird beak-coupled song → assortative mating. Nm and m/s as the dimensionless controllers of speciation / fusion / stable polymorphism.
- **VG:** Lake Victoria cichlids and depth-spectral environment. *Rhagoletis* host shift on apples vs hawthorn with eclosion timing offset. Hawaiian honeycreeper radiation. *Ensatina* ring species around the Central Valley. Hexaploid wheat genome assembly. Mule chromosome arithmetic. Daphne Major Big Bird lineage. Islands-of-divergence FST pattern.
- **PQ:** 500 cichlid species in <100,000 years; 14,600-year refilled Lake Victoria. *Drosophila* speciation 1.5–5 Myr. Pacific–Caribbean *Alpheus* 1–3% mtDNA divergence. (1/2)^7 = 1/128 balanced gamete probability. Horse 64 / donkey 62 / mule 63 chromosomes. Big Bird lineage in 7 generations from 1981 founder. *BMP4*, *ALX1*, *HMGA2* beak loci.

---

## Figure 11.1 — Chromosome-Pairing Diagram (Polyploidy)

**Priority: Critical.** The mechanism that makes polyploidy speciation possible in one generation. Visible chromosome pairing is the whole argument.

### Block 1 — Illustrae paste block

A three-panel vertical composition showing three meiotic pairing scenarios. Top panel — diploid parent (2n=14): seven pairs of homologous chromosomes drawn as Sky Blue `#56B4E9` filled rod-pairs aligned as bivalents, each pair side by side. Middle panel — triploid (3n=21): seven chromosome triplets, each triplet drawn as three Sky Blue rods of identical length; in each triplet two rods pair as a bivalent (touching) while the third rod sits offset to one side as a univalent in Vermillion `#D55E00` outline only (unfilled, indicating mispairing). Bottom panel — tetraploid (4n=28): fourteen pairs of Sky Blue rod-bivalents arranged in regular rows, all properly paired. To the right of each panel a small outcome indicator — diploid: Bluish Green `#009E73` filled circle (balanced gametes); triploid: Vermillion `#D55E00` filled circle with an X overlay (mostly unbalanced); tetraploid: Bluish Green filled circle (balanced gametes). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Three meiotic pairing scenarios stacked. Diploid bivalents (all paired). Triploid triplets (two pair, one univalent). Tetraploid bivalents (all paired). Outcome indicator beside each.
[O] Vertical stack of three panels, top to bottom: diploid, triploid, tetraploid. Outcome circles right-aligned.
[P] Chromosomes Sky Blue filled rods. Univalents Vermillion outline only. Balanced-outcome Bluish Green. Unbalanced-outcome Vermillion with X.
[E] No specific gene loci, no centromere markers, no banding patterns, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene loci, centromere markers, chromosome banding, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 11.2 — Rhagoletis Host-Shift Speciation Timeline

**Priority: Important.** A clean visualization of how habitat + temporal isolation built in 150 generations. Demonstrates sympatric speciation by selection outpacing migration.

### Block 1 — Illustrae paste block

A horizontal timeline composition spanning roughly 1850 to present. Top: a single ancestral *Rhagoletis* population on hawthorn drawn as a Bluish Green `#009E73` filled oval. At ~1850, the population splits into two parallel horizontal tracks. Upper track — hawthorn-using population in Bluish Green: a Bluish Green filled hawthorn-fruit icon (small circle) at right, the population maintaining late-August eclosion. Lower track — apple-using population in Orange `#E69F00`: an Orange filled apple-fruit icon at right, the population shifting to late-July eclosion. Between the tracks two stacked horizontal eclosion-timing distributions drawn as smooth Blue `#0072B2` curves — the upper curve centered on late August (hawthorn timing), the lower curve centered on late July (apple timing), with a narrow overlap zone in the middle. To the right at the present-day endpoint a small FST panel: a Blue bar at low height labeled position "genome-wide" and a Vermillion `#D55E00` bar at high height labeled position "host-preference loci". Black `#000000` 1pt timeline axis. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Single ancestral population splits ~1850 into apple and hawthorn host races. Parallel timelines diverge in eclosion timing. Present-day islands-of-divergence FST pattern at host-preference loci.
[O] Horizontal timeline, single ancestor on left, two parallel tracks fanning right, eclosion-timing distributions between tracks, FST bars at present-day endpoint.
[P] Hawthorn Bluish Green. Apple Orange. Eclosion curves Blue. Genome-wide FST Blue (low). Host-preference FST Vermillion (high). Axis Black.
[E] No specific calendar dates rendered, no quantitative FST numbers, no specific gene names, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, calendar dates, gene names, FST numbers, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 11.3 — Dobzhansky-Muller Snowball Effect

**Priority: Critical.** The t² quadratic accumulation is the chapter's most counterintuitive quantitative claim. Visual contrast of linear vs quadratic is the payload.

### Block 1 — Illustrae paste block

A two-panel composition. Left panel — schematic of the DMI mechanism: ancestral genotype AABB at top (Sky Blue `#56B4E9` filled box). Two arrows diverging down-left and down-right to two derived genotypes. Down-left arrow leads to population X with genotype aaBB (Bluish Green `#009E73` filled box, where lowercase a is shown in Bluish Green color). Down-right arrow leads to population Y with genotype AAbb (Orange `#E69F00` filled box, where lowercase b is shown in Orange). Below the two derived populations, a hybrid box AaBb in Vermillion `#D55E00` outline with a small Vermillion lightning-bolt icon indicating incompatibility. Right panel — accumulation curves: an x-axis labeled position "divergence time" and a y-axis labeled position "incompatibilities". Two curves drawn: a Blue `#0072B2` 1pt straight line rising linearly (labeled position "expected linear") and a Vermillion `#D55E00` 1pt curve rising quadratically and crossing well above the linear line at the right edge (labeled position "observed snowball"). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Left: DMI mechanism with ancestor AABB diverging to aaBB and AAbb, hybrid AaBb showing incompatibility. Right: linear vs quadratic accumulation curves over divergence time.
[O] Two side-by-side panels. Left: divergence tree top-down. Right: x-y curve plot.
[P] Ancestor Sky Blue. Population X allele Bluish Green. Population Y allele Orange. Hybrid Vermillion outline. Linear curve Blue. Quadratic curve Vermillion.
[E] No specific gene names, no numbered axes, no equation rendering, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene names, numerical axes, equations, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 11.4 — Big Bird Lineage on Daphne Major

**Priority: Important.** Genealogical timeline of the best-documented contemporary vertebrate speciation event. Connects beak morphology to song-mediated assortative mating.

### Block 1 — Illustrae paste block

A vertical genealogy composition. Top row — year 1981: a single Reddish Purple `#CC79A7` filled circle labeled position "immigrant" connected to a Bluish Green `#009E73` filled circle labeled position "local female". Below, generations descend as a branching genealogy across 7 horizontal rows. Each generation's offspring drawn as small filled circles colored on a gradient: the Big Bird lineage offspring carry the Reddish Purple coloration intensifying generation by generation, while local *G. fortis* individuals stay Bluish Green. Edges connecting parents to offspring drawn as Black `#000000` 1pt lines. To the right of the genealogy a small beak-shape side panel: two stylized beak silhouettes in Black outline — a smaller, shallower one labeled position "local fortis beak" and a larger, deeper one labeled position "Big Bird beak". Below the beaks two stylized waveform icons: a higher-frequency Blue `#0072B2` waveform beside the small beak, a lower-frequency Vermillion `#D55E00` waveform beside the large beak. By generation 7, the Big Bird lineage forms a closed sub-cluster of Reddish Purple circles breeding only with itself. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Genealogy of Big Bird lineage on Daphne Major from 1981 immigrant across 7 generations. Color intensifies along Big Bird lineage. By generation 7 the lineage forms a closed self-breeding cluster. Side panel: beak shape coupled to song frequency.
[O] Vertical genealogy with branching tree top-down. Side panel right of genealogy with beak silhouettes and waveform icons.
[P] Immigrant and Big Bird descendants Reddish Purple. Local *fortis* Bluish Green. Edges Black. Local-beak song Blue waveform. Big-Bird-beak song Vermillion waveform.
[E] No specific bird names, no specific beak measurements, no Hz numbers on waveforms, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, bird species names, beak measurements, frequency numbers, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 11.5 — Phase Diagram of Speciation Outcomes

**Priority: Critical.** Three outcomes (speciation, fusion, stable polymorphism) as regions in a two-parameter space. Synthesizes the whole chapter into one map.

### Block 1 — Illustrae paste block

A two-dimensional phase diagram. X-axis labeled position "Nm (migrants per generation)" running left to right from low to high. Y-axis labeled position "m/s (migration vs selection)" running bottom to top from low to high. The plotting area is divided into three diagonal regions by two Black `#000000` 1pt dividing curves. Lower-left region — low Nm, low m/s — filled with Blue `#0072B2` 20% opacity wash and a small Blue marker indicating "speciation"; an inset *Rhagoletis*-style icon (small Orange `#E69F00` filled apple) sits in this region as the empirical anchor. Middle diagonal band — intermediate values — filled with Bluish Green `#009E73` 20% opacity wash, marker indicating "stable polymorphism / islands of divergence"; an inset two-bar islands-of-divergence motif (one short Blue bar and one tall Vermillion `#D55E00` bar) sits here. Upper-right region — high Nm, high m/s — filled with Vermillion `#D55E00` 20% opacity wash, marker indicating "fusion"; an inset Sky Blue `#56B4E9` filled droplet icon represents Lake Victoria turbidity-driven fusion. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Two-axis phase diagram. X = Nm, Y = m/s. Three regions: speciation (lower-left), stable polymorphism (middle band), fusion (upper-right). Empirical anchor icon in each region.
[O] Cartesian plot with two dividing curves separating three diagonal regions. Empirical icons placed in each region.
[P] Speciation region Blue wash. Polymorphism band Bluish Green wash. Fusion region Vermillion wash. Region icons in source-mechanism palette colors (Orange apple, Vermillion FST bar, Sky Blue droplet). Axes Black.
[E] No specific numerical axis ticks, no quantitative thresholds, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, numerical axis ticks, threshold values, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Two-column "isolating barriers" table (lines 62–64).** Typography reference table; the author's own table is the right tool here.
- **Ensatina ring species map.** Geographic / picture-research; better served by a base map figure if commissioned separately.
- **Hawaiian honeycreeper beak gallery and Hawaiian silverswords gallery.** Adaptive radiation illustrations are picture-research deliverables, not vector schematics.
- **Allopatric vicariance vs dispersal contrast (Isthmus of Panama and Hawaiian colonization).** Could be added as Fig 11.0 if a sixth slot opens; for a 5-figure budget the polyploidy / *Rhagoletis* / DMI / Big Bird / phase diagram set covers the chapter's argument more completely.

---

## Video Candidate Pass

**FIGURE 11.1 (Chromosome pairing):** **MILD VIDEO CANDIDATE.** Animating meiotic pairing — diploid bivalents resolving cleanly, triploid univalents segregating randomly with a probability counter ticking 1/128, tetraploid bivalents resolving cleanly — would make the arithmetic feel inevitable rather than asserted.
**FIGURE 11.2 (Rhagoletis):** STATIC SUFFICIENT.
**FIGURE 11.3 (DMI snowball):** STATIC SUFFICIENT for the curves; the mechanism panel could optionally animate genotype divergence.
**FIGURE 11.4 (Big Bird):** **MILD VIDEO CANDIDATE.** A 7-generation walkthrough showing the lineage closing on itself, with the song-beak coupling cue when each mate choice is made, would dramatize how reproductive isolation accumulated in observable time.
**FIGURE 11.5 (Phase diagram):** STATIC SUFFICIENT.

**STRONG VIDEO CANDIDATE — not on the figure list: an animated allopatric vs sympatric speciation contrast.** The chapter's central conceptual hinge — geographic isolation vs in-place divergence as alternative paths to the same endpoint — is a paradigmatic before/after process that earns animation. Show two ancestral populations side by side: one bisected by a rising land barrier (vicariance), the other diverging in place via a depth gradient (sensory drive in *Pundamilia*), then both reaching reproductive isolation by different routes. **Recommended as the chapter's primary animation deliverable.**

**Video candidates identified: 1 strong (allopatric/sympatric contrast) + 2 mild (Fig 11.1, Fig 11.4).** Recommended: **the allopatric/sympatric contrast as a chapter-opening animation**, with optional Fig 11.1 chromosome-pairing animation if budget allows.

---

## Split-point note

Chapter cross-references Ch 10 (five forces, Nm, FST) heavily — coordinate the Fig 11.5 phase diagram's Nm axis with whatever notation Ch 10's figures use. Chapter 12 builds directly on the speciation events as branch points; the Big Bird lineage figure should establish a tree-style visual vocabulary that Ch 12 phylogeny figures can extend.
