# CAJAL Figure Intelligence — Chapter 12: Phylogenetics and the History of Life

**Source:** `chapters/12-phylogenetics-history-of-life.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Chapter walks tree-reading vocabulary, three tree-building methods (parsimony / maximum likelihood / Bayesian), a worked great-ape phylogeny with Jukes-Cantor correction, the three-domain framework and Asgard archaea, endosymbiotic theory, the four-billion-year timeline including the Big Five mass extinctions, and the limits of the tree model under horizontal gene transfer. No author-placed `![](images/...)` figures — chapter ships as pure prose.

---

## Density Recommendation

**5 figures, Mechanistic density.** Chapter ships with zero author-placed figures but the argument is dense with tree-reading, distance-correction, tree-building, deep history, and endosymbiosis content that needs visual anchoring. Recommend a focused set: tree anatomy and the three group-types; a primate distance/tree worked example showing Jukes-Cantor correction; the three-domain tree with Asgard; the endosymbiosis schematic; and a deep-time / mass-extinction timeline. Each earns its place by carrying load no prose paragraph can substitute for.

---

## Zone Map

- **MC:** Tree anatomy (tips, nodes, branches, root, sister groups, clades) and the monophyletic / paraphyletic / polyphyletic distinction. Jukes-Cantor correction d = -(3/4)ln(1 - (4/3)p) and the inflation it produces at deep divergence. Three-domain framework with Archaea sister to Eukarya; eukaryotes nested inside Asgard archaea. Endosymbiotic origin of mitochondria and chloroplasts with five independent lines of evidence. Horizontal gene transfer breaking the strict tree at the prokaryote root.
- **VG:** Woese's 16S rRNA discovery of Archaea. Great-ape topology (((Human, Chimp), Gorilla), Orangutan) from *COX1*. Molecular-clock calibration from Miocene fossil great apes (~14 Ma orangutan split). Hug 2016 16-ribosomal-protein tree across 3,083 genomes. Lynn Margulis 1967 endosymbiosis paper. Lokiarchaeota / Asgard discovery from Mid-Atlantic Loki's Castle. *Prometheoarchaeum syntrophicum* (2019–2020). Big Five mass extinctions with named causes.
- **PQ:** 16S rRNA ~1,540 nucleotides. Human mt DNA 16,569 bp encoding 13 proteins + 22 tRNAs + 2 rRNAs. p = 0.028 → d_JC = 0.0285; p = 0.088 → d_JC = 0.094; p = 0.35 → d_JC ≈ 0.47; formula undefined at p ≥ 0.75. Substitution rate ~3.4×10⁻⁹ per site per year. Chimp–human split ~6–7 Ma (worked example yields 4.3 Ma from 250-bp single gene). LUCA ~3.5–4 Ga. GOE ~2.4 Ga. End-Permian ~96% marine species lost (Siberian Traps, 3×10⁶ km³ basalt). End-Cretaceous ~75% (Chicxulub, ~10 km body). Sixth Extinction 100–1,000× background rates.

---

## Figure 12.1 — Tree Anatomy and the Three Group Types

**Priority: Critical.** The chapter opens with how to read a tree without misreading it; tip / node / branch / root / sister / clade vocabulary needs a canonical reference figure, and the monophyletic / paraphyletic / polyphyletic distinction is where students fail.

### Block 1 — Illustrae paste block

A two-panel composition. Left panel — labeled tree anatomy: a single phylogenetic tree drawn with Black `#000000` 1pt branches, rooted at the bottom-left with a small Vermillion `#D55E00` filled triangle marking the root. Six tips drawn as small Sky Blue `#56B4E9` filled circles at the top edge. Internal nodes shown as small Bluish Green `#009E73` filled circles at each branching point. One pair of sister taxa highlighted by a Blue `#0072B2` 1.5pt bracket above two adjacent tips. One clade (ancestor + all descendants) highlighted by an Orange `#E69F00` 20% opacity background wash enclosing one internal node and all its descendant tips. Right panel — three-group-type contrast: three small tree icons stacked vertically, each tree drawn in Black 1pt with five tips. Top tree — monophyletic: all descendants of one node shaded in Bluish Green `#009E73` 20% wash (complete clade). Middle tree — paraphyletic: same tree with one descendant tip-and-branch left unshaded while the rest are Vermillion `#D55E00` 20% wash (ancestor + some descendants). Bottom tree — polyphyletic: same tree with two non-adjacent tips shaded in Reddish Purple `#CC79A7` 20% wash, no shared shaded ancestor (convergent grouping). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Left: one tree with root, tips, internal nodes, sister bracket, and one shaded clade. Right: three stacked small trees illustrating monophyletic (complete clade shaded), paraphyletic (one descendant excluded), polyphyletic (two non-adjacent tips shaded).
[O] Two side-by-side panels. Left panel one large tree. Right panel three small trees stacked top to bottom.
[P] Branches Black. Root Vermillion triangle. Tips Sky Blue. Internal nodes Bluish Green. Sister bracket Blue. Clade shade Orange wash. Monophyletic Bluish Green wash. Paraphyletic Vermillion wash. Polyphyletic Reddish Purple wash.
[E] No specific taxon names, no specific clade names rendered, no time axis, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, taxon names, clade names, time scale, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 12.2 — Great-Ape Phylogeny from COX1 with Jukes-Cantor Correction

**Priority: Critical.** The chapter's most explicit worked example. Distance correction is the chapter's central quantitative move; the recovered topology and clock calibration are the payoff.

### Block 1 — Illustrae paste block

A three-panel composition arranged left to right. Left panel — distance matrix as a heatmap grid: 4×4 cell grid (human, chimp, gorilla, orangutan along both axes). Diagonal cells Black `#000000` filled (self-comparisons). Off-diagonal cells filled on a Sky Blue `#56B4E9` to Vermillion `#D55E00` ramp with low distances Sky Blue and high distances Vermillion. Two small tick marks indicate the rough range. Middle panel — p vs Jukes-Cantor correction curve: a single x-y plot. X-axis labeled position "raw p-distance" from 0 to 0.75. Y-axis labeled position "Jukes-Cantor distance" from 0 to high. A Blue `#0072B2` 1pt diagonal reference line indicating "uncorrected" and a Vermillion `#D55E00` 1pt curve rising and accelerating upward illustrating the correction. A Black 1pt vertical asymptote at p = 0.75 marked with a small Vermillion X. Right panel — recovered great-ape tree: a four-taxon tree drawn with Black `#000000` 1pt branches in cladogram style, topology (((Human, Chimp), Gorilla), Orangutan). Tip nodes drawn as small Bluish Green `#009E73` filled circles. Two molecular-clock calibration markers along the tree: a small Orange `#E69F00` filled diamond at the orangutan–African ape node labeled position "~14 Ma" and another at the human–chimp node labeled position "~6 Ma". White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Left: 4×4 distance heatmap for human, chimp, gorilla, orangutan. Middle: raw p vs Jukes-Cantor curve with vertical asymptote at p = 0.75. Right: recovered (((Human, Chimp), Gorilla), Orangutan) tree with two clock calibration diamonds.
[O] Three horizontal panels left to right: heatmap, correction curve, tree.
[P] Heatmap ramp Sky Blue (low) to Vermillion (high). Diagonal Black. Uncorrected reference Blue line. Jukes-Cantor curve Vermillion. Asymptote marker Vermillion X. Tree branches Black. Tips Bluish Green. Clock calibration diamonds Orange.
[E] No specific distance values rendered, no specific Ma numbers in the curve, no sequence data shown, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, taxon names within image, distance numbers, sequence letters, Ma numbers, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 12.3 — Three-Domain Tree with Asgard Archaea

**Priority: Critical.** Woese's discovery reframed as the modern Asgard-inclusive version — eukaryotes nested inside Archaea rather than as a sister clade. Carries the chapter's deepest historical claim.

### Block 1 — Illustrae paste block

A single rooted tree composition. Root at the bottom-center as a small Vermillion `#D55E00` filled triangle labeled position "LUCA". Two main branches diverging upward — left to Bacteria, right to (Archaea + Eukarya). Bacteria branch drawn in Blue `#0072B2` 1.5pt fanning into several Sky Blue `#56B4E9` filled tip-circles representing major bacterial lineages. Archaea side drawn in Reddish Purple `#CC79A7` 1.5pt fanning into Reddish Purple filled tip-circles for major archaeal phyla. Within the Archaea side, one branch leads to the Asgard superphylum highlighted by an Orange `#E69F00` 20% opacity wash region containing several tip-circles labeled position "Lokiarchaeota", "Thorarchaeota", "Heimdallarchaeota". Nested *inside* the Asgard region, one branch continues upward and expands into the Eukarya — a small Bluish Green `#009E73` 20% opacity wash region containing tip-circles for plants, animals, fungi, protists. A small arrow with Vermillion `#D55E00` filled circle next to the eukaryote root indicates the proto-mitochondrial endosymbiotic event with a thin Vermillion connecting line back to the α-proteobacterial position on the Bacteria branch. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Rooted three-domain tree with LUCA at root. Bacteria branch left. Archaea branch right with Asgard superphylum highlighted; Eukarya nested inside Asgard. Proto-mitochondrial endosymbiosis indicated by an arrow from the α-proteobacterial position back to the eukaryote root.
[O] Rooted tree, root at bottom-center, two main branches fanning upward. Highlighted regions for Asgard (Orange wash) and Eukarya (Bluish Green wash). Endosymbiosis arrow as a thin curved Vermillion line.
[P] Root marker Vermillion. Bacteria branch and tips Blue / Sky Blue. Archaea branch and tips Reddish Purple. Asgard wash Orange. Eukarya wash Bluish Green. Endosymbiosis arrow Vermillion.
[E] No specific species names within image, no specific time scale on tree, no specific Ga numbers, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, species names, time scale, Ga numbers, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 12.4 — Endosymbiosis: Five Lines of Evidence

**Priority: Important.** The chapter walks five distinct evidentiary threads; the visual anchor is the engulfment event itself with each evidence type spatially annotated on the resulting double-membraned organelle.

### Block 1 — Illustrae paste block

A two-stage composition. Left stage — engulfment event: a large Reddish Purple `#CC79A7` filled rounded cell outline (the proto-eukaryotic / archaeal host). Inside the host, a smaller Blue `#0072B2` filled rod-shaped cell (the α-proteobacterial proto-mitochondrion) shown mid-engulfment, partially surrounded by a host-derived Reddish Purple double-line membrane. A Black `#000000` 1pt arrow leads rightward to stage two. Right stage — integrated mitochondrion: a cross-section view of a single mitochondrion drawn as a large oval. Outer membrane drawn as a Reddish Purple `#CC79A7` 1.5pt outer line (host-derived). Inner membrane drawn as a Blue `#0072B2` 1.5pt inner line with characteristic cristae folds (bacterial-derived). Inside the matrix: a small circular Blue closed loop labeled position "mtDNA" (evidence 2); two small Bluish Green `#009E73` filled circles labeled position "70S ribosomes" (evidence 3); a curved Vermillion `#D55E00` 1pt arrow indicating binary fission with a small division line across the organelle (evidence 4); a small Orange `#E69F00` filled marker connected by a thin Orange dashed line back to a tiny α-proteobacterial silhouette icon outside the organelle labeled position "rRNA phylogeny" (evidence 5). The double-membrane structure itself is evidence 1, called out by a Sky Blue `#56B4E9` annotation bracket. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Left: engulfment event with host cell containing partially-engulfed proto-mitochondrion. Right: integrated mitochondrion cross-section with five lines of evidence visually annotated — double membrane, circular DNA, 70S ribosomes, binary fission, α-proteobacterial rRNA affinity.
[O] Two horizontal stages with arrow between. Right stage shows organelle cross-section with each evidence marker spatially placed.
[P] Host cell Reddish Purple. Proto-mitochondrion Blue. Outer membrane Reddish Purple. Inner membrane Blue. mtDNA circular loop Blue. 70S ribosomes Bluish Green. Binary fission arrow Vermillion. rRNA phylogeny link Orange dashed. Double-membrane evidence bracket Sky Blue.
[E] No specific protein names, no specific gene names, no specific lipid chemistry, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, protein names, gene names, lipid chemistry, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 12.5 — Four-Billion-Year Timeline with the Big Five Extinctions

**Priority: Important.** Pulls the chapter's deep-time narrative into one synoptic timeline. Mass extinctions as inflection points anchor the otherwise abstract billion-year scale.

### Block 1 — Illustrae paste block

A horizontal timeline composition spanning 4 Ga on the left to present on the right. The timeline drawn as a Black `#000000` 2pt baseline with logarithmic-feel spacing so deep-time events have room. Major event markers as small Sky Blue `#56B4E9` filled circles at positions ~4 Ga (Earth forms), ~3.5 Ga (LUCA), ~2.7 Ga (oxygenic photosynthesis), ~2 Ga (eukaryotes), ~1 Ga (chloroplasts), ~600 Ma (multicellularity), ~540 Ma (Cambrian explosion). The Great Oxidation Event at ~2.4 Ga marked by a larger Orange `#E69F00` filled diamond with a Vermillion `#D55E00` upward step in a thin background bar (atmospheric O₂ rising from ~0 to ~2%). The Big Five mass extinctions marked by five tall Vermillion `#D55E00` filled triangular spikes pointing downward from the timeline at ~440 Ma, ~370 Ma, ~252 Ma, ~200 Ma, ~66 Ma — the End-Permian spike drawn tallest to indicate ~96% loss, others scaled by their respective severity. Present-day "Sixth Extinction" marked by a Reddish Purple `#CC79A7` filled triangular spike at the far right, drawn dashed in outline to indicate "in progress". Above the timeline a thin Bluish Green `#009E73` filled bar runs from ~2.7 Ga to present indicating "biosphere oxygen presence". White background, flat vector, double-column 174mm preferred or full-page if available.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Horizontal 4-Ga timeline with major biological events as circle markers, Great Oxidation Event as Orange diamond with O₂ step, Big Five mass extinctions as downward Vermillion spikes scaled by severity, Sixth Extinction as dashed Reddish Purple spike, oxygen-presence bar from ~2.7 Ga onward.
[O] Horizontal timeline, deep past left, present right. Markers above and below the baseline at the appropriate temporal positions.
[P] Timeline baseline Black. Biological event markers Sky Blue. GOE marker Orange diamond. O₂ step Vermillion. Mass-extinction spikes Vermillion. Sixth Extinction Reddish Purple dashed. Oxygen bar Bluish Green.
[E] No specific Ma / Ga numerical labels rendered, no specific species names, no graph axis numbers, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, Ma / Ga numbers, species names, axis ticks, percent labels, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **The Big Five extinction causes summary (lines 174–178).** Typography-as-table; the prose list is the right tool.
- **Distance matrix table for great-ape COX1 (lines 73–80).** Author-built reference table; Fig 12.2 visualizes the matrix as a heatmap, not as a typographic table.
- **Three tree-building methods (parsimony / ML / Bayesian) side-by-side.** Could be a sixth figure but the methods are best taught through prose + the worked Fig 12.2; a methods-comparison schematic risks being visual filler.
- **Web-of-life / horizontal gene transfer schematic.** Worth considering as Fig 12.6 if budget allows, but the prose argument is mostly conceptual rather than mechanism-visual.
- **Lynn Margulis / Carl Woese portraits.** Picture research, biographical material, not CAJAL deliverables.

---

## Video Candidate Pass

**FIGURE 12.1 (Tree anatomy):** STATIC SUFFICIENT.
**FIGURE 12.2 (Great-ape worked example):** **MILD VIDEO CANDIDATE.** Animating the neighbor-joining construction step by step — starting with the distance matrix, joining Human-Chimp first, collapsing the matrix, joining Gorilla next, finishing with Orangutan as outgroup — would dramatize how the tree falls out of the data.
**FIGURE 12.3 (Three-domain tree):** STATIC SUFFICIENT.
**FIGURE 12.4 (Endosymbiosis):** **MILD VIDEO CANDIDATE.** Animating the engulfment, the gradual gene transfer from organelle to nucleus over evolutionary time, and the persistence of the double membrane could make the deep-time mechanism visceral.
**FIGURE 12.5 (4-Ga timeline):** STATIC SUFFICIENT.

**STRONG VIDEO CANDIDATE — not on the figure list: phylogenetic tree-building from sequence alignment.** The chapter's central methodological move — turn local present-tense sequence differences into a hypothesis about history — is paradigmatically dynamic. Show four sequences with visible nucleotide differences highlighted column by column; compute the pairwise distance matrix in real time; apply the Jukes-Cantor correction visibly inflating large distances; run neighbor-joining to build the tree; then add a fifth sequence and watch the tree update. **Recommended as the chapter's primary animation deliverable** — it teaches both the algorithm and the epistemology in one motion.

**Video candidates identified: 1 strong (sequence-to-tree pipeline) + 2 mild (Fig 12.2, Fig 12.4).** Recommended: **the sequence-to-tree animation** as the chapter's centerpiece video. Hits both mechanism-as-learning-target and before/after-process criteria simultaneously.

---

## Split-point note

Chapter cross-references Ch 11 speciation (each tree node is a speciation event) and forward-references Ch 13 molecular evolution (what changes accumulate along the branches). Fig 12.5 timeline must coordinate visually with whatever deep-time figure Ch 13 uses; the Great Oxidation Event marker should match across chapters. Fig 12.3's three-domain tree palette (Blue Bacteria / Reddish Purple Archaea / Bluish Green Eukarya) should be the book's standard domain-color convention reused wherever any domain is referenced.
