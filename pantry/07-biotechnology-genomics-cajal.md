# CAJAL Figure Intelligence — Chapter 7: Biotechnology and Genomics

**Source:** `chapters/07-biotechnology-genomics.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Four-verb framework (Copy, Cut, Read, Write): PCR with Taq polymerase; restriction enzymes and CRISPR-Cas9; Sanger/Illumina/long-read sequencing; clinical CRISPR editing (Casgevy). Seven author-placed figures.

---

## Density Recommendation

**7 figures, Mechanistic density.** All seven earn their place. The chapter's argument depends on showing the molecular events that make each "verb" possible — thermal cycling, sequence-specific cleavage, programmable cutting, sequencing chemistry, and the cost trajectory that follows.

---

## Zone Map

- **MC:** PCR thermal cycle (denature/anneal/extend) — exponential amplification. CRISPR-Cas9 RNP search, PAM recognition, and double-strand break. Restriction-enzyme palindromic cleavage and sticky-end ligation. Illumina sequencing-by-synthesis with reversible terminators on a flow cell.
- **VG:** Recombinant cloning workflow (cut, ligate, transform). Sanger chromatogram readout (4-color ddNTPs by size).
- **PQ:** Cost-per-genome curve 2001–2024 (~$95M → ~$200, six orders of magnitude) plotted against Moore's Law reference. Cycle math (Nâ‚€ × 2â¿).

---

## Figure 7.1 — PCR Three-Stage Thermal Cycle

**Priority: Critical.** Foundation of the "Copy" verb; the load-bearing image for the whole amplification logic.

### Block 1 — Illustrae paste block

A three-panel horizontal cascade showing one PCR cycle. Panel 1 (Denaturation, ~94°C): a double-stranded DNA molecule drawn as two parallel Blue `#0072B2` 1.5pt horizontal strands with short Sky Blue `#56B4E9` rungs (base pairs); a small Vermillion `#D55E00` thermometer icon and the rungs pulling apart into two separated strands. Panel 2 (Annealing, ~55°C): the two single strands now apart; two short Orange `#E69F00` filled bars (primers) docked onto each strand at the boundaries of the target region; thermometer in cooler Sky Blue. Panel 3 (Extension, 72°C): a Bluish Green `#009E73` filled circle (Taq polymerase) sitting on each primer, with a new daughter strand being synthesized as a Bluish Green 1.5pt line extending 5'→3' from each primer along the template. Arrows Black `#000000` 1pt connect the three panels in a horizontal cascade, and a small curved arrow returns from Panel 3 to Panel 1 indicating cyclic repetition. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] One PCR cycle in three temperature stages. Denaturation separates dsDNA. Annealing binds primers at target boundaries. Extension synthesizes new strands 5'→3' with Taq. Cycle repeats exponentially.
[O] Horizontal three-panel cascade left-to-right. Return arrow indicates repetition.
[P] DNA strands Blue. Base pairs Sky Blue. Primers Orange. Taq polymerase Bluish Green. New synthesis Bluish Green. Heat indicator Vermillion. Process arrows Black 1pt.
[E] No specific sequence letters, no numerical temperatures rendered as graphics, no specific buffer components, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, sequence letters, base identities rendered, temperature values, buffer components, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 7.2 — EcoRI Cleavage and Sticky Ends

**Priority: Important.** Anchors the "Cut" verb at the level of restriction enzymes; visualizes palindromic recognition and the sticky-end product that makes ligation possible.

### Block 1 — Illustrae paste block

A two-panel horizontal sequence diagram. Panel 1 (recognition): a horizontal stretch of dsDNA drawn as two parallel Blue `#0072B2` 1.5pt strands with a centered six-base palindromic recognition region shown as Sky Blue `#56B4E9` filled small rectangles on each strand (six per strand, paired vertically). A Reddish Purple `#CC79A7` filled blob (EcoRI homodimer) sits on top of the recognition site spanning both strands. Panel 2 (cleavage and sticky ends): the same dsDNA after cutting, with each strand cleaved offset between bases on each side — top strand cut at one position, bottom strand at the complementary offset position — producing two fragments each with a four-base single-stranded 5' overhang (Vermillion `#D55E00` 1pt highlight on the overhanging bases). Black `#000000` 1pt arrow connects Panel 1 to Panel 2. White background, flat vector, single-column 89mm.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] EcoRI recognizes a six-base palindrome on dsDNA and cleaves both strands at offset positions, producing complementary four-base sticky ends.
[O] Two-panel horizontal: before-cut (enzyme bound) and after-cut (two fragments with overhangs).
[P] DNA strands Blue. Base-pair rungs Sky Blue. EcoRI enzyme Reddish Purple. Sticky-end overhangs Vermillion highlight. Process arrow Black 1pt.
[E] No specific base letters rendered, no enzyme-name text, no chemical bond structures, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, base letters, enzyme name graphics, chemical bond drawings, atomic detail, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 7.3 — Recombinant DNA Cloning Workflow

**Priority: Important.** The end-to-end workflow that produced recombinant insulin and built modern biopharma. Composition of cut + ligate + transform.

### Block 1 — Illustrae paste block

A four-stage horizontal workflow. Stage 1: a Blue `#0072B2` filled circle (bacterial plasmid) and a Sky Blue `#56B4E9` linear DNA fragment (human gene of interest), both with small Vermillion `#D55E00` arrowhead marks at identical recognition sites. Stage 2: a Reddish Purple `#CC79A7` filled blob (restriction enzyme) cutting both — the plasmid becomes linearized with sticky ends, the gene fragment is shown with matching sticky ends. Stage 3: ligation — the cut plasmid and the gene fragment now joined into a single circular construct (Blue ring with the Sky Blue insert embedded), with a small Bluish Green `#009E73` filled icon (DNA ligase) at the joint. Stage 4: transformation — the recombinant plasmid being taken up by a Black `#000000` 1pt outlined rod-shaped bacterial cell, and the cell shown dividing into a colony of identical cells, each carrying the construct. Black 1pt arrows connect the four stages. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Recombinant cloning: cut vector and insert with same restriction enzyme; ligate sticky ends to form recombinant plasmid; transform into bacterial cell; clonally expand.
[O] Four-stage horizontal workflow.
[P] Plasmid Blue. Insert Sky Blue. Restriction enzyme Reddish Purple. Ligase Bluish Green. Cut sites Vermillion marks. Bacterial cell Black 1pt outline.
[E] No specific gene names, no plasmid map markings (origin, selectable marker not specifically labeled), no protein-product downstream, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene names, plasmid map labels, antibiotic-resistance markers, protein names, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 7.4 — CRISPR-Cas9 Mechanism

**Priority: Critical.** The chapter's signature mechanism. Must show RNP loading, PAM-adjacent scanning, R-loop formation, and double-strand break with the two repair-pathway fork.

### Block 1 — Illustrae paste block

A three-panel mechanistic composition. Panel 1 (RNP search): a Reddish Purple `#CC79A7` filled large blob (Cas9 protein) with a Sky Blue `#56B4E9` 1.5pt curved line (sgRNA) threaded through it; the complex sitting above a horizontal stretch of dsDNA drawn as two Blue `#0072B2` 1.5pt parallel strands; small Vermillion `#D55E00` filled triangles scattered along the DNA marking NGG PAM sites. Panel 2 (R-loop and cut): the Cas9-sgRNA complex docked at one PAM; the 20-base region adjacent to the PAM shown with the sgRNA hybridized to one DNA strand and the other strand displaced as a Sky Blue loop; two small Bluish Green `#009E73` filled scissor-like marks on the two strands three bases upstream of the PAM indicating the DSB. Panel 3 (repair fork): the DSB shown as a clean cut; two diverging Black `#000000` 1pt arrows lead to two outcomes — left, NHEJ, where the ends are rejoined with a small Vermillion indel mark (frameshift); right, HDR, where an Orange `#E69F00` filled bar (donor template) is shown bridging the gap and the cut is repaired to the new sequence. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] CRISPR mechanism: Cas9-sgRNA scans for NGG PAM; matched protospacer forms R-loop; HNH/RuvC cleave 3 bp upstream of PAM; repair forks into NHEJ (indel/knockout) or HDR (template-directed precise edit).
[O] Three-panel horizontal sequence; final panel branches into two outcomes.
[P] Cas9 Reddish Purple. sgRNA Sky Blue curved line. DNA strands Blue. PAM markers Vermillion. Cut indicators Bluish Green. Indel mark Vermillion. HDR template Orange. Process arrows Black 1pt.
[E] No specific 20-nt spacer letters, no HNH/RuvC domain labels rendered, no PAM letters rendered, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, sequence letters, PAM letters rendered, domain names, sgRNA secondary structure detail, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 7.5 — Sanger Sequencing Chromatogram

**Priority: Important.** The "Read" verb at its origins; the chromatogram is the literal output that every wet-lab biologist still sees.

### Block 1 — Illustrae paste block

A two-region composition. Upper region (chain-termination diagram): a single-stranded DNA template drawn as a horizontal Blue `#0072B2` 1.5pt line; a primer (short Orange `#E69F00` bar) at the 5' end; several daughter strands shown growing rightward to different lengths, each terminated by a small color-coded filled circle representing the incorporated ddNTP — circles colored Sky Blue `#56B4E9`, Blue `#0072B2`, Bluish Green `#009E73`, and Vermillion `#D55E00` (one color per base, four bases). Lower region (chromatogram readout): a horizontal axis with a series of colored peaks in left-to-right order along the axis — each peak is one base position, drawn as a smooth curve in the matching color of the terminating ddNTP from the upper region. Peaks are evenly spaced and roughly uniform in height. A Black `#000000` 1pt arrow indicates the migration direction (smaller fragments left, larger fragments right). White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Sanger sequencing: chain-terminating ddNTPs produce a population of fragments terminated at every position; capillary electrophoresis separates by size; fluorescence detection produces a chromatogram of color-coded peaks read left to right.
[O] Two-region vertical stack: termination diagram above, chromatogram below, conceptually linked.
[P] Template Blue. Primer Orange. Four ddNTP colors: Sky Blue, Blue, Bluish Green, Vermillion (one per base). Migration arrow Black 1pt.
[E] No specific base letters under the peaks, no specific size-marker values, no instrument detail, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, base letters under peaks, size markers, instrument details, gel-image elements, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 7.6 — Illumina Sequencing-by-Synthesis

**Priority: Critical.** The cost-collapse engine. Bridge amplification on a flow cell plus reversible terminators is what made $200 genomes possible.

### Block 1 — Illustrae paste block

A two-panel horizontal composition. Panel 1 (flow cell with clusters): a Black `#000000` 1pt outlined rectangle representing a flow-cell tile, with the inner surface populated by many small Sky Blue `#56B4E9` filled circular cluster spots — each cluster is a dense tight group of identical strands, drawn as a small dot. A magnified inset (Black 1pt outlined circle pulled out) shows one cluster as a tight bundle of short Blue `#0072B2` 1pt strands rising from the surface, each anchored to a short Bluish Green `#009E73` filled oligo on the surface. Panel 2 (one synthesis cycle): a single cluster shown in cross-section; one reversible-terminator nucleotide being added to each strand; the added nucleotides drawn as small filled circles in one of four colors (Sky Blue, Blue, Bluish Green, Vermillion `#D55E00`) — one color per base; an Orange `#E69F00` curved arrow indicates "image the flow cell" and a second Orange arrow indicates "remove block and dye, repeat." White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Illumina sequencing: bridge-amplified clusters on a flow cell; one reversible-terminator nucleotide added per cycle to every cluster; image; deblock; repeat. Massively parallel readout of millions of clusters.
[O] Two panels: flow cell with cluster array (left), single cluster's per-cycle chemistry (right).
[P] Flow-cell outline Black 1pt. Clusters Sky Blue. Anchor oligos Bluish Green. Cluster strands Blue. Four base colors: Sky Blue, Blue, Bluish Green, Vermillion. Process arrows Orange.
[E] No specific base letters, no instrument-vendor labels, no specific cycle numbers, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, base letters, vendor names, cycle numbers, fluorescence-spectrum graphs, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 7.7 — Cost-per-Genome Curve (Log Scale)

**Priority: Critical.** The chapter's headline data. The six-orders-of-magnitude collapse, plotted against Moore's Law, is the empirical claim the rest of the chapter supports.

### Block 1 — Illustrae paste block

A single log-scale line chart. Horizontal axis: years 2001 to 2024 marked at intervals, Black `#000000` 1pt axis with tick marks. Vertical axis: cost in dollars on a logarithmic scale spanning 10² to 10⁸, Black 1pt axis. Two lines plotted across the axis area: a solid Blue `#0072B2` 2pt line tracing the NHGRI cost-per-genome curve (starting near 10⁸ in 2001, descending steadily and steepening sharply after roughly 2007–2008, leveling near 200 by 2024); a dashed Bluish Green `#009E73` 1.5pt reference line representing Moore's Law (halving every 18 months from the same 2001 starting point, descending at a constant slope and ending well above the Blue line by 2024). Four small Vermillion `#D55E00` filled circles annotate specific years on the Blue line for milestone events. Background a faint Sky Blue `#56B4E9` 5% horizontal band where the two curves visibly diverge after ~2008. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Cost-per-human-genome from 2001 ($95M) to 2024 ($200) on log scale. Diverges below Moore's Law starting ~2008 with Illumina's massively parallel chemistry.
[O] Single log-y line chart, time on x. Two curves: actual cost (Blue solid) and Moore's Law reference (Bluish Green dashed). Milestone markers along actual cost.
[P] Axis Black 1pt. Actual cost Blue solid 2pt. Moore's Law dashed Bluish Green 1.5pt. Milestone markers Vermillion. Divergence band faint Sky Blue.
[E] No textual axis labels rendered as graphics, no annotation text, no event names rendered, no grid behind axes, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, axis label words, year text, dollar amounts as text, event names, gridlines as decoration, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **PCR variants table (lines 80–86).** Typography reference table comparing qPCR/RT-PCR/dPCR; the markdown is malformed and the content is better as a tidy text table.
- **CRISPR variants table (lines 153–161).** Typography reference table for base editors, prime editors, CRISPRi/a; better as text.
- **Genome-scale technologies table (lines 247–254).** Typography reference table for RNA-seq, scRNA-seq, GWAS, liquid biopsy.
- **AI Wayback Machine prompts (lines 403–423).** Picture-research / external-link content, not a figure.
- **LLM Exercise spec (lines 270–399).** Code-generation prompt, not a figure asset.

---

## Video Candidate Pass

**FIGURE 7.1 (PCR thermal cycle):** **STRONG VIDEO CANDIDATE.** Cyclic-process criterion met. Three temperature stages cycling repeatedly with exponential strand doubling is the textbook video moment — viewers see "1 → 2 → 4 → 8 → … billions" as the cycles tick.
**FIGURE 7.2 (EcoRI):** STATIC SUFFICIENT.
**FIGURE 7.3 (Cloning workflow):** STATIC SUFFICIENT.
**FIGURE 7.4 (CRISPR mechanism):** **STRONG VIDEO CANDIDATE.** Search-and-cut is intrinsically dynamic — Cas9 scanning DNA, pausing at PAMs, R-loop formation, the cut, then the NHEJ/HDR fork unfolding in time. The mechanism-as-learning-target criterion is met at multiple steps and the cellular drama is what makes the chapter memorable.
**FIGURE 7.5 (Sanger chromatogram):** STATIC SUFFICIENT.
**FIGURE 7.6 (Illumina SBS):** **MILD VIDEO CANDIDATE.** Cycle-by-cycle base addition across millions of clusters simultaneously could dramatize the parallelism that explains the cost collapse; the static version is adequate but the animation makes "massively parallel" visceral.
**FIGURE 7.7 (Cost curve):** STATIC SUFFICIENT.

**Video candidates identified: 2 strong + 1 mild.** Recommended: **Fig 7.1 (PCR cycle)** and **Fig 7.4 (CRISPR mechanism).** Both meet the mechanism-as-learning-target criterion and both contain the visible-only-in-time elements (exponential doubling; search-and-cleave) that static figures cannot match.

---

## Split-point note

Chapter references back to Ch 5–6 (DNA structure, transcription/translation) for primer/template chemistry, and forward to Ch 8 (DNA damage and repair pathways NHEJ/HDR re-used). Coordinate visual styles so dsDNA looks identical to the Ch 5–6 conventions, and so the NHEJ/HDR repair fork in Fig 7.4 matches the repair-pathway figure expected in Ch 8.
