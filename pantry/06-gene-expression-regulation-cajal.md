# CAJAL Figure Intelligence — Chapter 6: Gene Expression and Regulation

**Source:** `chapters/06-gene-expression-regulation.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Argues you are not your genome; you are your genome expressed. Five regulatory layers (transcriptional, post-transcriptional, translational, post-translational, epigenetic), each with its own timescale. *lac* operon as Boolean AND gate (cleanest proof of concept). Eukaryotic combinatorial TF + enhancer + Mediator + TAD architecture. Epigenetic memory (DNA methylation, histone marks, X-inactivation via XIST). MicroRNAs (RNAi platform, patisiran). Ubiquitin-proteasome (cyclin B at metaphase). Opens and closes with the calico cat. Seven author-placed figures. Strong video candidate at the operon switching.

---

## Density Recommendation

**7 figures, Mechanistic density.** All seven author-placed figures earn their place — the chapter is structurally layered (five regulatory layers), and each layer needs its own visual anchor. The figures sit at the exact junctures where the chapter's claims get specific: the layer pipeline (6.1), the *lac* AND gate's observable consequence (6.2), the TAD architecture (6.3), DNMT1 maintenance methylation (6.4), the calico clonal-history readout (6.5), the miRNA pipeline (6.6), and the ubiquitin-proteasome cascade (6.7). Do not compress.

---

## Zone Map

- **MC:** *lac* operon Boolean AND gate (lactose AND ¬glucose). Combinatorial TF code defining cell identity (~1,600 TFs; MyoD master regulator; Yamanaka iPSC four-factor cocktail). Epigenetic memory through cell division (DNMT1 reading hemi-methylated CpG; PRC2 depositing H3K27me3 on new nucleosomes). XIST mechanism (long non-coding RNA → coating → PRC2 recruitment → DNA methylation). MicroRNA seed pairing and RISC. Ubiquitin-proteasome destruction of cyclin B at metaphase-anaphase. Cancer-as-regulatory-disease thesis.
- **VG:** Five-layer pipeline timescales (ms post-translational → minutes transcriptional → essentially permanent epigenetic). Diauxic growth curve kink. TADs as cohesin-extruded loops bounded by CTCF. Enhancer-promoter looping. Calico patch boundaries as clonal-history readout. Nucleosome and histone tail modification positions.
- **PQ:** ~20,000 protein-coding genes / 11,000–13,000 expressed per cell / ~7,000 housekeeping. ~1,600 TFs (~8% of all genes). cAMP rises 5 µM → 100 µM on glucose limitation. 50-fold CAP boost. ~17,000 nt XIST. ~2,000 miRNAs / each targets hundreds of mRNAs / ~60% of all genes regulated. 600+ E3 ligases. 26S proteasome.

---

## Figure 6.1 — Five Regulatory Layers as a Vertical Pipeline

**Priority: Critical.** The chapter's organizing scaffold. Without this figure as a navigational backbone, the rest of the chapter is a list. With it, every subsequent section has a position in the layer stack.

### Block 1 — Illustrae paste block

A vertical five-tier composition. From top to bottom, each tier is a horizontal rectangle in a distinct Okabe-Ito color, with a small icon inside indicating the layer's mechanism. Tier 1 (Transcriptional, Blue `#0072B2`): a small DNA strand with an RNA polymerase oval. Tier 2 (Post-transcriptional, Sky Blue `#56B4E9`): a small mRNA strand with a scissors-like spliceosome icon. Tier 3 (Translational, Bluish Green `#009E73`): a small ribosome icon (two stacked ovals). Tier 4 (Post-translational, Orange `#E69F00`): a small protein-with-ubiquitin-chain icon. Tier 5 (Epigenetic, Reddish Purple `#CC79A7`): a small DNA segment with methyl-group dots and a nucleosome bead. To the right of each tier, a horizontal Vermillion `#D55E00` 1pt bar of differing length indicates the layer's characteristic timescale — Tier 4 shortest (milliseconds), Tier 1 medium, Tier 5 longest (permanent through divisions). A vertical Black `#000000` 1pt arrow on the far left runs top to bottom labeled by position only as "earliest intervention → latest intervention." White background, flat vector, single-column 89mm preferred (vertical orientation).

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm preferred (vertical), vector, white background.
[C] Five horizontal tiers stacked vertically. Each tier represents one regulatory layer with a distinct color and a small mechanism icon. To the right, timescale indicator bars of varying length communicate that post-translational is fastest (ms) and epigenetic is slowest / most persistent.
[O] Vertical stack with timescale comparison column on right.
[P] Tier 1 Blue. Tier 2 Sky Blue. Tier 3 Bluish Green. Tier 4 Orange. Tier 5 Reddish Purple. Timescale bars Vermillion. Direction arrow Black.
[E] No specific protein names rendered as graphics, no quantitative timescale numbers, no enzyme structural detail, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, layer names rendered as graphics, timescale numbers, protein names, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 6.2 — Diauxic Growth Curve

**Priority: Important.** The observable consequence of the *lac* AND gate — a visible kink in a growth curve where the operon switches state. The figure makes "Boolean logic implemented in molecules" empirically visible.

### Block 1 — Illustrae paste block

A simple two-axis line plot. X-axis: time, no numerical labels. Y-axis: cell density, no numerical labels. A single Blue `#0072B2` 1pt curve rises steeply (exponential growth on glucose), then flattens horizontally for a short plateau region (the ~20-minute pause), then rises again at a slightly shallower slope (slower growth on lactose). Behind the curve, a Sky Blue `#56B4E9` 15% opacity shaded region marks the glucose-consumption phase (early). A Vermillion `#D55E00` 15% opacity shaded region marks the diauxic-shift pause. A Bluish Green `#009E73` 15% opacity region marks the lactose-consumption phase (late). A small Orange `#E69F00` annotation arrow points to the kink between the first rise and the plateau, indicating "*lac* operon AND gate switches state here." White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Growth curve. Three phases shown by background shading: glucose phase (Sky Blue), pause (Vermillion), lactose phase (Bluish Green). Single Blue curve through all three. Annotation arrow points to the kink at phase 1 → phase 2 transition.
[O] Standard x-y plot. Background phase shading provides the structural context.
[P] Growth curve Blue. Glucose-phase background Sky Blue 15%. Pause-phase background Vermillion 15%. Lactose-phase background Bluish Green 15%. Annotation arrow Orange.
[E] No numerical axis values, no specific time durations rendered, no operon mechanism overlaid on the plot, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, axis numerical values, time durations, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 6.3 — TAD Architecture (Enhancer-Promoter Looping)

**Priority: Critical.** The 3D-genome insight is unfamiliar to most students. The figure has to show: enhancer and promoter in linear sequence may be far apart, but in 3D they touch via a loop, and the loop is constrained to a TAD bounded by CTCF.

### Block 1 — Illustrae paste block

A horizontal composition with two complementary views. Top view (linear sequence): a horizontal Blue `#0072B2` 1pt DNA line, ~200mm long. Along it, from left to right: a Vermillion `#D55E00` filled triangle marking a CTCF boundary site, then within the TAD region a Bluish Green `#009E73` filled rectangle marking an enhancer, then a long stretch of DNA, then an Orange `#E69F00` filled rectangle marking a promoter, then another Vermillion CTCF boundary triangle marking the TAD's right edge. Bottom view (3D-folded): the same DNA line drawn now as a loop, with the enhancer and promoter brought into physical contact, the bulk of intervening DNA bulging outward. Between enhancer and promoter sits a Reddish Purple `#CC79A7` filled oval (Mediator complex) bridging them. Outside the loop, on either side, two Sky Blue `#56B4E9` filled rings (cohesin) sit at the loop base. The two CTCF boundary triangles flank the loop base. A small Black `#000000` 1pt arrow runs from the top view to the bottom view indicating "linear → 3D." White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Two views of the same DNA segment. Top: linear sequence showing enhancer + intervening DNA + promoter, flanked by two CTCF sites. Bottom: 3D loop conformation with enhancer-promoter contact, Mediator bridge, cohesin rings at base, CTCF boundaries flanking. The intervening DNA bulges as a loop.
[O] Horizontal stacked: top linear, bottom 3D-folded. Arrow connecting them.
[P] DNA backbone Blue. CTCF boundaries Vermillion triangles. Enhancer Bluish Green. Promoter Orange. Mediator complex Reddish Purple oval. Cohesin rings Sky Blue.
[E] No specific TF names, no Mediator subunit names, no base-pair coordinates, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, TF names, Mediator subunit names, base-pair coordinates, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 6.4 — DNMT1 Maintenance Methylation at the Replication Fork

**Priority: Critical.** The mechanism of epigenetic heritability. Without this figure, "methylation is inherited through division" is an assertion; with it, the mechanism is mechanical: DNMT1 reads hemi-methylated CpG and adds the missing methyl to the new strand.

### Block 1 — Illustrae paste block

A horizontal Y-fork composition reusing the visual template from Chapter 4's replication fork. Parental duplex on the left, Blue `#0072B2` 1pt strands. Both parental strands are decorated with small Reddish Purple `#CC79A7` filled circles at regular intervals — methyl groups on CpG dinucleotides. The fork opens to the right, separating into two daughter duplexes. On each daughter duplex, the parental strand retains its Reddish Purple methyl marks, and the new strand (initially) has no methyl marks — drawn as a bare Sky Blue `#56B4E9` line. A Bluish Green `#009E73` filled oval representing DNMT1 sits at one CpG site on the upper daughter duplex, in the act of adding a Reddish Purple methyl group to the new strand at that position. A small Orange `#E69F00` arrow indicates the methyl group being deposited. Further down the lower daughter duplex, the new strand is shown after DNMT1 has finished its work — both strands now fully marked with Reddish Purple methyl circles, identical to the parental state. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Replication Y-fork. Parental duplex with both strands methylated (Reddish Purple circles on Blue DNA). Two daughter duplexes emerging right. Upper daughter: DNMT1 in process of methylating new strand. Lower daughter: methylation complete, both strands marked, indistinguishable from parental state.
[O] Horizontal Y left-to-right. Visual continuity from upper-daughter (in progress) to lower-daughter (complete).
[P] Parental strands Blue. New strands Sky Blue. Methyl marks Reddish Purple. DNMT1 enzyme Bluish Green oval. Active-methylation arrow Orange.
[E] No specific CpG sequence rendered, no methyl chemical structure, no protein domain detail, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, CpG sequence letters, methyl chemical structure, protein domain detail, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 6.5 — Calico Cat With Patch Boundaries Annotated

**Priority: Important.** The chapter's opening and closing image. The patch boundaries are the embryonic clonal history made visible. Figure must show: each patch = one clone = one X-inactivation choice fixed in an embryonic ancestor.

### Block 1 — Illustrae paste block

A simplified cat silhouette in profile, full body, sitting or standing. The body is divided into irregular patches with sharp boundaries: orange patches (Orange `#E69F00` filled), black patches (Black `#000000` filled), and white patches (white = background, outlined Sky Blue `#56B4E9` 1pt). Two small annotation callouts: one points to an orange patch with a small inset showing a single cell silhouette containing two X-chromosome icons drawn as small vertical bars — the left X drawn full Bluish Green `#009E73` (active), the right X drawn faded Sky Blue (silenced) labeled by position. The other callout points to an adjacent black patch with the same inset but the X-states reversed — left X faded, right X active. A short Reddish Purple `#CC79A7` 1pt arrow between the two insets indicates "different X-inactivation choice in embryonic ancestor." The patches grow from clonal expansion is indicated by a small Vermillion `#D55E00` annotation at one patch boundary showing a few-cell embryo origin diagram (small cluster of circles, then expanding outward to fill the patch). White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Cat profile silhouette with three-color patches (orange / black / white). Two callout insets, one for an orange patch and one for a black patch, each showing a cell with two X chromosomes, one active and one silenced — choices reversed between patches. Connector indicates the difference is the X-inactivation choice. Small embryo origin diagram annotates clonal expansion.
[O] Cat silhouette dominates the composition. Insets sit at margins. Connecting arrow between insets crosses the patch boundary on the cat body.
[P] Orange patches Orange. Black patches Black. White patches Sky Blue outline. Active X Bluish Green. Silenced X Sky Blue faded. Choice-reversal arrow Reddish Purple. Embryo-origin annotation Vermillion.
[E] No detailed cat anatomy, no realistic fur texture, no facial detail, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene names, cell-type names, realistic cat anatomy, detailed fur, facial features, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 6.6 — MiRNA Biogenesis and RISC Silencing

**Priority: Critical.** MiRNAs regulate ~60% of human protein-coding genes; patisiran is the platform application. Pipeline figure makes the multi-step biogenesis legible.

### Block 1 — Illustrae paste block

A vertical pipeline composition. Top section (nucleus, indicated by Sky Blue `#56B4E9` 1pt rounded-rectangle outline boundary): a Bluish Green `#009E73` 1pt primary transcript with a clear hairpin loop in the middle. A Vermillion `#D55E00` filled oval (Drosha) cuts the hairpin, releasing a Bluish Green ~70-nt precursor with a shorter hairpin. The precursor exits the nucleus through a small Orange `#E69F00` gap in the boundary. Middle section (cytoplasm): the precursor enters and meets a Reddish Purple `#CC79A7` filled oval (Dicer) which cleaves it to a short double-stranded duplex (two Bluish Green parallel lines, ~22 nt). One strand is loaded into a larger Blue `#0072B2` filled oval (Argonaute / RISC). The other strand is discarded (small Vermillion 1pt squiggle drifting away). Bottom section: the RISC complex carrying the loaded Bluish Green miRNA strand encounters a target mRNA (long horizontal Bluish Green line). The seed region (nucleotides 2–8 of the miRNA, drawn as a short highlighted Orange segment) base-pairs with the mRNA's 3' UTR. Two parallel outcomes radiate from the binding event: a Black `#000000` "STOP" symbol indicating translation block, and a Vermillion deadenylation symbol showing the poly-A tail being chewed off. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Three-section vertical pipeline. Nucleus (top): primary transcript hairpin → Drosha cleavage → precursor → export. Cytoplasm (middle): Dicer cleaves to duplex → one strand loaded into Argonaute (RISC), other strand discarded. Bottom: RISC + miRNA seed pairs with target mRNA 3' UTR → two outcomes (translation block, mRNA degradation via deadenylation).
[O] Vertical pipeline with nucleus / cytoplasm boundary distinguished by enclosure.
[P] miRNA / RNA Bluish Green. Drosha Vermillion. Dicer Reddish Purple. Argonaute / RISC Blue. Seed region highlight Orange. Nucleus boundary Sky Blue. Discard / deadenylation Vermillion.
[E] No specific miRNA sequence, no Argonaute domain structure, no Drosha co-factors named, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, miRNA sequence, protein domain detail, cofactor names, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 6.7 — Ubiquitin-Proteasome System

**Priority: Critical.** Post-translational control's most dramatic example — cyclin B destruction collapses CDK1 activity and triggers anaphase. The figure must show: ubiquitin cascade (E1→E2→E3→substrate), polyubiquitin chain, and proteasomal degradation.

### Block 1 — Illustrae paste block

A horizontal cascade composition reading left to right. Left: a target protein (large Sky Blue `#56B4E9` filled irregular blob) sits idle. A small Bluish Green `#009E73` filled circle (single ubiquitin molecule) is handed sequentially through three enzymes drawn as Orange `#E69F00` filled rounded rectangles in series: E1 (activating) → E2 (conjugating) → E3 (ligase). The E3 ligase makes contact with the target protein and transfers ubiquitin onto a small Reddish Purple `#CC79A7` filled circle on the substrate's surface representing a lysine attachment site. The cycle repeats: more ubiquitin moieties are added, forming a chain of Bluish Green circles attached at the same lysine — drawn as 4–5 chained circles. Center-right: the polyubiquitinated substrate is recognized by the 26S proteasome, drawn as a Vermillion `#D55E00` filled hollow barrel-shape with a small Reddish Purple cap on top (regulatory particle). The substrate is shown threading into the barrel via the cap. Right: out the other end of the proteasome, small Black `#000000` 1pt squiggles emerge representing short peptide fragments. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Horizontal cascade. Substrate protein (left). Three-enzyme cascade E1→E2→E3 hands ubiquitin moieties. E3 transfers to substrate lysine. Polyubiquitin chain builds. 26S proteasome (Vermillion barrel + Reddish Purple regulatory cap) recognizes the chain, unfolds the substrate, threads it through, releases short peptide fragments at the far end.
[O] Horizontal left-to-right cascade with the proteasome as the major visual anchor near right of center.
[P] Substrate Sky Blue. Ubiquitin Bluish Green. E1/E2/E3 enzymes Orange. Lysine attachment Reddish Purple. Proteasome barrel Vermillion. Regulatory cap Reddish Purple. Output peptides Black squiggles.
[E] No specific E3 ligase names, no ubiquitin chemical structure, no proteasome subunit detail, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, enzyme names, ubiquitin chemical structure, proteasome subunit names, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Liver vs neuron expression table (lines 35–40, manuscript-broken).** Restore as a table in typography, not as a figure.
- **Histone-mark reference table (lines 154–156, manuscript-broken).** Reference table; reproduce typographically.
- **Truth table for *lac* operon (clean table in manuscript).** Already a typography artifact.
- **Glucocorticoid receptor / NF-κB signaling cascades.** Would each need its own figure; chapter is already at 7 author-placed figures. Defer to a signaling supplement.
- **AI Wayback Machine (Jacob, Monod).** Out of scope.

---

## Video Candidate Pass

**FIGURE 6.1 (Five layers):** STATIC SUFFICIENT — the navigational scaffold benefits from being permanently visible, not animated.
**FIGURE 6.2 (Diauxic growth curve):** STATIC SUFFICIENT — a curve plot is what it is.
**FIGURE 6.3 (TAD architecture):** **MILD VIDEO CANDIDATE.** Animation morphing the linear sequence into the 3D loop would dramatize the cohesin loop-extrusion mechanism. Useful but not essential — the two-view static figure delivers the key insight.
**FIGURE 6.4 (DNMT1 maintenance):** **MILD VIDEO CANDIDATE.** Animation of replication forking + DNMT1 traveling along, methylating the new strand at each CpG, would dramatize the heritability mechanism. Similar to Ch 4's replication fork — could share an animation framework.
**FIGURE 6.5 (Calico cat):** STATIC SUFFICIENT — the patch boundaries are the punchline; animation adds nothing.
**FIGURE 6.6 (miRNA pipeline):** STATIC SUFFICIENT — the pipeline structure conveys the multi-step process. A click-through interactive could let students step through stages, but a printed pipeline serves the same purpose.
**FIGURE 6.7 (Ubiquitin-proteasome):** **STRONG VIDEO CANDIDATE.** This is the chapter's most kinetic mechanism. Watching ubiquitin moieties added one at a time, the chain growing, the substrate getting recognized, threaded through the proteasome, and emerging as peptides — the cascade is the mechanism. Cyclin-B-at-metaphase variant ("collapse in minutes → anaphase triggered") delivers a clinical/cell-cycle punch as a concrete instance.

**Video candidates identified: 1 strong, 2 mild.** Recommended: **Fig 6.7 (ubiquitin-proteasome cascade).** Bonus: a brief operon-switching animation (lactose arrives → allolactose forms → repressor releases → polymerase binds → first transcripts appear → feedback amplifies) would make the AND-gate logic visceral. Author may want to consider an extra "Fig 6.2b" interactive showing the four input combinations toggling state.

---

## Split-point note

Chapter cross-references Chapter 4 (DNMT1 at the replication fork — visual template should match Fig 4.4's fork orientation and color treatment), Chapter 5 (same RNA polymerase machinery, here under regulation; Fig 6.3's promoter geometry should echo Fig 5.1's), and forward-references Chapter 8 (cancer-as-regulatory-disease thesis pays off in the cancer chapter — DNMT inhibitors, HDAC inhibitors, BRCA epigenetics). Calico-cat figure (6.5) is the chapter's bookend; consider placing it twice (open and close) or pairing with a forward-reference to a future evo-devo / phenotype chapter.
