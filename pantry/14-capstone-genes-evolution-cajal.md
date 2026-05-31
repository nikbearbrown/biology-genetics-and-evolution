# CAJAL Figure Intelligence — Chapter 14: Capstone — From Genes to Evolutionary Change

**Source:** `chapters/14-capstone-genes-evolution.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Capstone synthesizes three timescales (bacterial antibiotic resistance in hours-to-days; human lactase persistence in millennia; hominin evolution in millions of years) running on the same mechanism stack of mutation / drift / selection / gene flow. Cases include NDM-1 carbapenem resistance and conjugation, MRSA mecA, sickle-cell equilibrium under malaria, Out-of-Africa bottleneck and serial founder pattern, Neanderthal admixture and EPAS1 Denisovan introgression, Human Accelerated Regions, NOTCH2NL and cortical expansion. No author-placed `![](images/...)` figures.

---

## Density Recommendation

**5 figures, Mechanistic density.** Capstone integrates the book; the figures must integrate too. The chapter has zero author-placed images but the synthesis benefits from a small number of high-density visualizations that each carry one of the chapter's organizing claims: the three-timescales / one-stack frame, β-lactam resistance mechanisms with horizontal transfer, the sickle-cell heterozygote-advantage equilibrium, Out-of-Africa serial founder geographic pattern, and the Neanderthal / Denisovan admixture summary. Each earns its place by carrying the load no prose paragraph can.

---

## Zone Map

- **MC:** Same algorithm at three timescales — fixation time T_fix ≈ (2/s) ln(2 Ne) yields ~22 hours in bacterial gut (s≈1, Ne=10⁹), ~10,000 years in human population (s≈0.07, Ne=10⁴). β-lactam resistance mechanisms (PBP point mutation / mecA acquisition / β-lactamase production). Horizontal gene transfer (transformation / transduction / conjugation) as gene flow without reproduction. Sickle-cell heterozygote-advantage equilibrium p* = t/(s+t). Out-of-Africa bottleneck producing serial-founder loss of diversity. Neanderthal admixture detected by D-statistic (ABBA-BABA), block lengths as molecular clock. EPAS1 Denisovan introgression for Tibetan high-altitude adaptation.
- **VG:** NDM-1 first reported Chennai 2008; spread on plasmids globally in under 5 years. *Klebsiella* / Enterobacteriaceae conjugation. MRSA SCC*mec* mobile element. TEM β-lactamase family (200+ variants). Lactase persistence regulatory variants at multiple sites in MCM6 enhancer in four independent pastoralist populations. HbS allele on five independent haplotype backgrounds (Bantu, Benin, Senegal, Cameroon, Arab-Indian). Victoria Gray's 2023 Casgevy CRISPR therapy at BCL11A erythroid enhancer. HAR1 in Cajal-Retzius neurons. NOTCH2NL at 1q21.1 chromosomal instability. Pääbo 2010 Vindija Cave draft genome; 2022 Nobel Prize.
- **PQ:** Bacterial Ne 10⁹–10¹², human effective Ne ~10⁴. Bacterial generation 20 min–few hours, human 25 years. Bacterial mutation rate ~10⁻¹⁰ per base; human ~1.2×10⁻⁸ per base. AMR caused 1.27M attributable deaths in 2019. Lactase persistence sweep s ≈ 0.05–0.10. HbS equilibrium p* = 0.1 / 0.6 ≈ 0.167; West African allele frequency 0.08–0.16; African American ~0.04 after ~15 generations. Non-African humans carry ~1–4% Neanderthal ancestry. ~80% of Tibetan EPAS1 haplotypes are Denisovan-introgressed. HAR1: 18 substitutions on human lineage vs 2 chimp, ~70× neutral rate. Pollard 2006. Sankararaman 2014 — ~40% of Neanderthal genome reconstructible. Human autosomal FST 0.10–0.15 between continents; Lewontin 1972: 85% variation within populations. Humans and chimps ~98.8% coding identity, ~4–5% total divergence.

---

## Figure 14.1 — Three Timescales, One Stack

**Priority: Critical.** Opens the chapter's central organizing claim. Same mechanism running at vastly different rates because of population-size and generation-time parameters.

### Block 1 — Illustrae paste block

A horizontal three-column composition. Each column represents one timescale case. Top of each column — a representative population icon: Column 1 (bacterial) — a small Vermillion `#D55E00` filled cluster of dot-shaped cells; Column 2 (human pastoralist) — a small Bluish Green `#009E73` filled human silhouette; Column 3 (hominin lineage) — a small Reddish Purple `#CC79A7` filled hominin skull silhouette. Below each population icon, three parameter rows aligned horizontally across the columns: Row 1 "Ne" with horizontal bars scaled by log-magnitude (bacterial bar widest in Blue `#0072B2`, human pastoralist bar narrowest in Blue, hominin lineage bar intermediate in Blue); Row 2 "generation time" with bars scaled (bacterial bar shortest in Orange `#E69F00`, human longest in Orange, hominin longest in Orange); Row 3 "T_fix from sweep equation" with bars scaled (bacterial bar shortest in Sky Blue `#56B4E9` labeled position "~22 hours", human longest in Sky Blue labeled position "~10,000 years", hominin labeled position "millions of years"). At the bottom of all three columns, a single shared Black `#000000` 1pt horizontal bracket labeled position "same mechanism stack: mutation / drift / selection / gene flow". White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Three columns showing bacterial / human pastoralist / hominin lineage timescales. Each column has population icon, Ne bar, generation-time bar, T_fix bar. Single shared bracket below unifies all three under one mechanism stack.
[O] Three vertical columns side by side. Three parameter rows aligned horizontally across columns. Unifying bracket spans all columns at bottom.
[P] Bacteria Vermillion cluster. Human Bluish Green silhouette. Hominin Reddish Purple skull. Ne bars Blue. Generation bars Orange. T_fix bars Sky Blue. Unifying bracket Black.
[E] No specific Ne / generation / T_fix numerical labels rendered, no specific organism species names, no quantitative axes, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, numerical parameter values, species names, axis labels, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 14.2 — β-Lactam Resistance Mechanisms and Horizontal Gene Transfer

**Priority: Critical.** Carries Case 1 — three molecular routes to resistance and three pathways for spreading it. The chapter's mechanism-dense backbone case.

### Block 1 — Illustrae paste block

A two-panel composition. Top panel — three resistance mechanisms: a single bacterial cell drawn as a Sky Blue `#56B4E9` filled rod with a Vermillion `#D55E00` outline cell wall. Three callout arrows lead to three mechanism insets above the cell. Inset 1 (left) — PBP point mutation: a small enzyme blob in Bluish Green `#009E73` with a small Orange `#E69F00` dot indicating a substitution residue; a β-lactam ring icon (small Vermillion filled diamond) hovers near but doesn't dock. Inset 2 (center) — mecA acquisition: an alternative PBP shown as a Reddish Purple `#CC79A7` filled blob distinct from the native PBP; a small mobile-element ribbon in Black `#000000` 1pt connects to the chromosome. Inset 3 (right) — β-lactamase production: a small Vermillion β-lactamase blob actively cleaving a β-lactam-ring icon shown as broken into two pieces in Vermillion. Bottom panel — three HGT pathways: a horizontal row of three bacterial-pair scenarios. Scenario 1 (transformation) — a donor cell shown lysed and releasing free DNA fragments as Blue `#0072B2` 1pt curved strands; a recipient cell taking up one strand. Scenario 2 (transduction) — a small Reddish Purple `#CC79A7` phage particle with capsid carrying a Blue DNA fragment, hovering between donor and recipient. Scenario 3 (conjugation) — two cells connected by a Black 1pt pilus, with an Orange `#E69F00` filled plasmid loop transferring along the pilus from donor to recipient. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Top: three resistance mechanisms (PBP point mutation, mecA acquisition, β-lactamase production) as callout insets from a single bacterial cell. Bottom: three HGT pathways (transformation, transduction, conjugation) as three bacterial-pair scenarios.
[O] Two stacked panels. Top: single cell with three mechanism insets above. Bottom: three side-by-side donor-recipient scenarios.
[P] Bacterial cell Sky Blue with Vermillion outline. PBP enzyme Bluish Green; mutation site Orange; mecA blob Reddish Purple; β-lactamase Vermillion; β-lactam ring Vermillion. Free DNA Blue. Phage Reddish Purple. Pilus Black. Plasmid Orange.
[E] No specific gene names within image, no specific protein names rendered, no chemical structures of antibiotics, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene names, protein names, chemical structures, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 14.3 — Sickle-Cell Heterozygote Advantage Equilibrium

**Priority: Critical.** The chapter's worked end-to-end example. Hardy-Weinberg under selection with named fitness parameters; equilibrium frequency from t / (s+t).

### Block 1 — Illustrae paste block

A two-panel composition. Left panel — fitness triangle: three genotype boxes arranged in a small triangle. Top vertex — heterozygote HbA/HbS drawn in Bluish Green `#009E73` filled rounded rectangle labeled position "fitness 1.0". Bottom-left vertex — homozygous HbA/HbA in Blue `#0072B2` filled labeled position "fitness 1-t (malaria cost)". Bottom-right vertex — homozygous HbS/HbS in Vermillion `#D55E00` filled labeled position "fitness 1-s (disease cost)". Above the triangle a small icon cluster: a Reddish Purple `#CC79A7` filled mosquito silhouette near the HbA/HbA box; a small distorted sickle-shaped red-cell silhouette in Vermillion near the HbS/HbS box; a small normal biconcave red-cell silhouette in Bluish Green near the heterozygote box. Right panel — allele-frequency equilibrium plot: x-axis labeled position "HbS allele frequency p" from 0 to 0.3. Y-axis labeled position "Δp per generation". A Black `#000000` 1pt curve crosses zero at p* ≈ 0.17, with a small Orange `#E69F00` filled circle marker at the crossing labeled position "equilibrium p*". To the left of the crossing the curve is above zero (Δp positive, allele rises); to the right it is below zero (Δp negative, allele falls). Small empirical anchor markers: a Bluish Green `#009E73` filled triangle at p ≈ 0.12 labeled position "West Africa observed"; a Sky Blue `#56B4E9` filled square at p ≈ 0.04 labeled position "African American (post-malaria relaxation)". White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Left: three-genotype fitness triangle with heterozygote at fitness 1, AA homozygote with malaria cost, SS homozygote with disease cost. Right: Δp vs p curve crossing zero at equilibrium p* with two empirical anchor markers for West African and African American frequencies.
[O] Two side-by-side panels. Left triangle with iconic anchors. Right x-y plot with crossing-point marker and empirical anchors.
[P] Heterozygote Bluish Green. AA Blue. SS Vermillion. Mosquito Reddish Purple. Sickle cell Vermillion. Normal cell Bluish Green. Δp curve Black. Equilibrium marker Orange. West Africa anchor Bluish Green. African American anchor Sky Blue.
[E] No specific allele frequency numerical values rendered in image, no specific population names, no equation rendering, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, allele frequency values, population names, equations, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 14.4 — Out-of-Africa Serial Founder Pattern

**Priority: Important.** The clearest demographic signal in any species' population genetics — distance from East Africa correlates negatively with within-population heterozygosity. Anchors Case 2.

### Block 1 — Illustrae paste block

A stylized world-map composition (highly schematic, not photographic geography). A large continental landmass shapes drawn in Black `#000000` 1pt outline with continental fills in soft Sky Blue `#56B4E9` 15% wash. East Africa marked by a Bluish Green `#009E73` filled star as the source population. From the star, several arrowed migration paths radiate outward — a thick Bluish Green `#009E73` 2pt arrow exiting Africa toward the Middle East, then branching into thinner arrows fanning out: northward into Europe (Blue `#0072B2`), eastward through Central Asia into East Asia (Orange `#E69F00`), further eastward through Beringia into the Americas (Vermillion `#D55E00`), and southward into Oceania (Reddish Purple `#CC79A7`). At several waypoints along each route, small circle markers indicate founding populations; each circle's size decreases progressively along the route, visualizing serial bottleneck loss of diversity. A small inset legend at the corner shows a single-column bar chart of within-population heterozygosity vs distance from East Africa, with a clear monotonically decreasing trend — large Bluish Green bar (Africa), medium Blue bar (Europe), smaller Orange bar (East Asia), small Vermillion bar (Americas), smallest Reddish Purple bar (remote Pacific Islands). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Stylized continental map with East African source star and migration arrows fanning to Europe, East Asia, Americas, Oceania. Circle markers at waypoints shrink along each route. Inset bar chart of within-population diversity vs distance from East Africa with monotonic decrease.
[O] Map-style composition with route arrows. Inset bar chart in corner.
[P] Continents Black outline with Sky Blue 15% wash. East African source star Bluish Green. Route arrows in distinct destination colors (Bluish Green / Blue / Orange / Vermillion / Reddish Purple). Inset bars in matching destination colors.
[E] No country names, no specific city names, no specific geographic detail beyond continental outlines, no specific kya / years numbers, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, country names, city names, geographic place names, kya numbers, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 14.5 — Neanderthal and Denisovan Admixture Summary

**Priority: Critical.** The Pääbo synthesis — what the ancient genomes told us. Carries Case 3 and the chapter's strongest "species concept stretches at the edges" point.

### Block 1 — Illustrae paste block

A composite composition. Left side — population tree with admixture arrows: a rooted tree drawn in Black `#000000` 1pt branches showing modern African populations on the left tip, modern non-African populations to its right, Neanderthal as a separate branch further right, and Denisovan as the rightmost branch. Each tip drawn as a small filled circle: Africans Bluish Green `#009E73`, non-Africans Blue `#0072B2`, Neanderthal Reddish Purple `#CC79A7`, Denisovan Orange `#E69F00`. Two curved admixture arrows: a Reddish Purple curved arrow from the Neanderthal lineage into the non-African branch labeled position "~2% ancestry"; an Orange curved arrow from the Denisovan lineage specifically into a Melanesian / Tibetan sub-branch labeled position "EPAS1 introgression". Right side — Neanderthal-ancestry genome map: a horizontal row of stylized chromosome silhouettes (chromosomes 1 through 22 plus X), each drawn in Sky Blue `#56B4E9` 1pt outline. Inside each chromosome, small Reddish Purple `#CC79A7` filled blocks scattered at varying positions and widths representing Neanderthal-derived haplotype blocks. The X chromosome silhouette shows visibly fewer Reddish Purple blocks than the autosomes (depletion). A small annotation arrow points to a sparsely-populated gene-rich region on chromosome 7 indicating "depleted near genes". A small Bluish Green checkmark callout on chromosome 2 indicates "EPAS1 — retained, beneficial". White background, flat vector, full-page 174mm or larger preferred.

### Block 2 — Full SCOPE prompt

[S] Full-page 174mm preferred, vector, white background.
[C] Left: rooted tree of African / non-African / Neanderthal / Denisovan with two curved admixture arrows (Neanderthal → non-African; Denisovan → Tibetan / Melanesian). Right: 23 stylized chromosome silhouettes with Neanderthal-haplotype blocks scattered inside; X chromosome shows depletion; EPAS1 region marked as retained beneficial.
[O] Left half — tree with admixture arrows. Right half — chromosome panel array.
[P] Africans Bluish Green. Non-Africans Blue. Neanderthal Reddish Purple. Denisovan Orange. Tree branches Black. Admixture arrows in source-population colors. Chromosomes Sky Blue outline. Neanderthal blocks Reddish Purple. EPAS1 retention marker Bluish Green.
[E] No specific chromosome numbers rendered as labels, no specific gene names beyond EPAS1 callout, no specific kya / years numbers, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, chromosome numbers, gene names, kya numbers, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **NDM-1 global spread map.** Picture research / epidemiology figure rather than CAJAL deliverable; the conjugation mechanism is the part Fig 14.2 visualizes.
- **Fitness cost / compensatory mutation toy model.** The arithmetic is text-native and short; a figure would not add load.
- **Lactase persistence MCM6 enhancer convergence panel.** Strong overlap with Ch 13 Fig 13.3 stickleback Pitx1 convergence — the chapter's case is parallel and reading the cross-reference is the better pedagogical move than duplicating the visual template.
- **FOXP2 self-correction story.** Already declined in Ch 13; same reasoning — text-native, no figure adds load.
- **HAR1, NOTCH2NL paralogs, HARs generally.** Each could be its own figure; for a 5-figure budget the three-cases backbone takes priority and these molecular details belong in prose.
- **"What every chapter contributed" enumeration.** Pure synthesis prose; no figure.
- **AI Wayback Machine Svante Pääbo material.** Picture research.
- **Race / ancestry / FST framing.** Sociopolitically charged; the careful framing the author provides in prose is the right tool. Any figure here risks oversimplifying. Decline.

---

## Video Candidate Pass

**FIGURE 14.1 (Three timescales):** STATIC SUFFICIENT.
**FIGURE 14.2 (β-lactam resistance + HGT):** **MILD VIDEO CANDIDATE.** Animating conjugation specifically — pilus extending, contact established, plasmid threading through — would dramatize "gene flow without reproduction" as a process.
**FIGURE 14.3 (Sickle-cell equilibrium):** **MILD VIDEO CANDIDATE.** A slider-driven version where the user varies t and s and watches p* shift along the Δp curve would make the equilibrium feel like a result you can compute, not a number you memorize.
**FIGURE 14.4 (Out-of-Africa):** STATIC SUFFICIENT.
**FIGURE 14.5 (Admixture summary):** STATIC SUFFICIENT.

**STRONG VIDEO CANDIDATE — anchored on Case 1's bacterial selective sweep.** Show a bacterial colony at high magnification: at t=0 a population of susceptible cells in Sky Blue with a single Vermillion-marked resistant cell among them. Apply antibiotic. Susceptibles die (fade to gray). Resistant cell divides. Sweep through generations as the resistant clone fills the niche; a real-time counter shows generations elapsed and the calculated T_fix ≈ 43 generations / ~22 hours. Then switch the timescale to the human pastoralist case — same algorithm, same curve, different parameters — and watch the lactase-persistence allele rise over 400 generations / 10,000 years. The split-screen comparison makes the chapter's organizing claim ("same algorithm, three timescales") visceral. Hits before/after-process and mechanism-as-learning-target. **Recommended as the chapter's primary animation deliverable** — fits the capstone's synthesis role.

**Video candidates identified: 1 strong (bacterial sweep / human sweep split-screen) + 2 mild (Fig 14.2 conjugation, Fig 14.3 interactive equilibrium).** Recommended: **the split-screen sweep animation** as the capstone's centerpiece video.

---

## Split-point note

Capstone references every prior chapter explicitly in its "What every chapter contributed" section. Figure palettes and motifs must match the book-wide conventions established by Chapters 10–13 — particularly the Nm / m·s phase-space coloring from Ch 11 Fig 11.5, the dN/dS spectrum coloring from Ch 13 Fig 13.4, and the three-domain coloring (Blue / Reddish Purple / Bluish Green) from Ch 12 Fig 12.3. Fig 14.5's chromosome map should reuse the Sky Blue outline / Reddish Purple block convention from any prior introgression / admixture figure if one exists in earlier chapters. Coordinate with the book's overall figure-numbering convention before commissioning.
