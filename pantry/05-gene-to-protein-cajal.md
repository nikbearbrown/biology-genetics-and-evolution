# CAJAL Figure Intelligence — Chapter 5: From Gene to Protein

**Source:** `chapters/05-gene-to-protein.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Argues the genetic code is a universal engineering substrate — the same machinery that builds your actin reads a synthetic mRNA vaccine without modification. Two molecular machines (RNA polymerase, the ribosome) plus the universal code. Anchored at one end by the COVID mRNA vaccine and at the other by sickle-cell hemoglobin (one A→T → one Val for Glu → polymerization → vaso-occlusion). **No author-placed figures in this chapter.** Strong video candidates at transcription and translation.

---

## Density Recommendation

**4 figures, Mechanistic density.** The chapter has no `![...](images/...)` markers — author has not yet placed figures. The mechanisms here are dynamic and unfamiliar (transcription bubble, spliceosome chemistry, ribosome elongation cycle, sickle-cell molecular cascade), and the chapter is the hinge between Mendel-era genetics and molecular medicine. Four figures earn their place. Author should slot these into the manuscript before final layout. Transcription and the ribosome cycle both qualify as strong video candidates.

---

## Zone Map

- **MC:** Central dogma (sequence information flow: DNA→RNA→protein, no protein→sequence reverse). Two-machine architecture (RNA polymerase + ribosome). Universal genetic code (64 codons → 20 amino acids + stop). Wobble (~32 tRNAs for 61 sense codons). Sickle-cell molecular cascade (codon 6 GAG→GUG → Glu→Val → HbS polymerization → sickled cell). Universality as engineering substrate (Humulin 1982, mRNA vaccines 2020).
- **VG:** Transcription bubble (~12–14 bp melted, moving with polymerase). Template vs coding strand. The three eukaryotic mRNA modifications (5' cap, poly-A tail, splicing). Spliceosome two transesterification steps and lariat intermediate. Ribosome three sites (A, P, E) and elongation cycle. Antibiotic binding sites on 30S vs 50S.
- **PQ:** 64 codons / 20 amino acids / 3 stop. ~32 tRNAs. Bacterial elongation ~20 aa/sec; eukaryotic 2–6 aa/sec. Pol II ~25–50 nt/sec. Translation error ~1 per 10⁴ aa. Spike mRNA ~4,300 nt / 30 µg per dose. β-globin 146 aa. Dscam 38,016 isoforms. 70S vs 80S ribosomes.

---

## Figure 5.1 — Transcription Bubble and Template/Coding Strand

**Priority: Critical.** The template-vs-coding-strand confusion is the chapter's single most pinnable vocabulary item. A figure that locks geometry to terminology pays off across the rest of the chapter (and Chapter 6, and every subsequent chapter that quotes a sequence).

### Block 1 — Illustrae paste block

A horizontal composition. A double-stranded DNA segment runs left to right, drawn as two parallel Blue `#0072B2` 1pt lines with a Vermillion `#D55E00` filled oval (RNA polymerase) straddling them in the middle. Inside the polymerase, the two DNA strands are separated to form the transcription bubble (~14 bp wide region drawn as a small open space). The top strand (coding strand, sense strand) is labeled by position only with a small Black `#000000` 5'→3' arrow on its left end. The bottom strand (template strand) has a 3'→5' arrow on its left end — making the antiparallel orientation visible. A single Bluish Green `#009E73` 1pt nascent RNA strand emerges from the back of the polymerase, peeling upward from the template strand, with its 5' end pointing back to the left and its 3' end inside the polymerase active site. Three small Orange `#E69F00` filled circles ahead of the polymerase (right side) represent incoming NTPs. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] DNA duplex horizontal. RNA polymerase straddles a transcription bubble. Coding (top) strand 5'→3' left to right; template (bottom) strand 3'→5' left to right (antiparallel). Nascent RNA peels off the template strand, exits the back of the polymerase to the upper-left.
[O] Horizontal, polymerase centered. Direction arrows on each DNA strand. RNA exit clearly upward and backward (left).
[P] DNA strands Blue. RNA polymerase Vermillion. Nascent RNA Bluish Green. Incoming NTPs Orange. Direction arrows Black.
[E] No protein domain detail, no specific transcription factor names, no nucleotide-level chemistry, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, sequence letters, protein names rendered as graphics, nucleotide chemistry, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 5.2 — Eukaryotic mRNA Processing (Cap, Splice, Tail)

**Priority: Critical.** The three modifications eukaryotes cannot skip. The before/after contrast is what students need: pre-mRNA with introns vs mature mRNA after splicing, capping, and polyadenylation.

### Block 1 — Illustrae paste block

A vertical two-row composition. Top row (pre-mRNA): a horizontal Bluish Green `#009E73` 1pt strand representing the pre-mRNA. It has three exons drawn as Blue `#0072B2` filled rectangles (E1, E2, E3 — labeled by position only, no rendered text) interspersed with two intron regions drawn as thinner Sky Blue `#56B4E9` open lines. The 5' end has no cap. The 3' end has no tail. Bottom row (mature mRNA): the three Blue exon rectangles are now joined into a continuous sequence with no intervening intron regions. At the 5' end (left), a Vermillion `#D55E00` filled circle represents the 7-methylguanosine cap, attached via a small "5'-5'" geometric indicator (a short doubled-back line). At the 3' end (right), a Reddish Purple `#CC79A7` repeating-A tail extends as a series of small filled circles, ~10 visible. Between the two rows, two Orange `#E69F00` 1pt curved arrows arc downward from the pre-mRNA introns toward a small spliceosome icon (Bluish Green filled oval) sitting between the rows; from the spliceosome, two intron lariats (small Black `#000000` 1pt loops) are released. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Two rows. Top: pre-mRNA with 3 exon blocks + 2 introns + no cap + no tail. Bottom: mature mRNA with 3 exons joined + 5' cap + poly-A tail. Spliceosome between rows excises introns as lariats.
[O] Vertical two-row before/after with processing apparatus between.
[P] Exons Blue. Introns Sky Blue thinner. mRNA backbone Bluish Green. 5' cap Vermillion. Poly-A tail Reddish Purple. Spliceosome Bluish Green oval. Lariats Black loops. Splicing arrows Orange.
[E] No splice site consensus sequences rendered, no exon/intron numbering as graphics, no snRNP subunit names, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, sequence letters, splice site consensus, snRNP names, exon numbers, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 5.3 — Ribosome Elongation Cycle (A/P/E Sites)

**Priority: Critical.** The single hardest dynamic mechanism in the chapter. Three sites, one cycle of (entry → peptide bond → translocation → exit). Static figure must convey the three-position geometry; video would deliver the cycle.

### Block 1 — Illustrae paste block

A horizontal composition. Two large stacked ovals represent the ribosomal subunits: top Reddish Purple `#CC79A7` filled (large 50S subunit) and bottom Sky Blue `#56B4E9` filled (small 30S subunit), with a horizontal Bluish Green `#009E73` 1pt mRNA strand threaded through the gap between them, running left to right. Three vertical slots in the gap mark, from left to right, the E site, P site, and A site. In the A site (rightmost): an incoming tRNA drawn as a Blue `#0072B2` filled inverted-L shape, with a small Orange `#E69F00` filled circle at its top (the attached amino acid) and a small EF-Tu+GTP Bluish Green filled oval associated with it. In the P site (middle): a tRNA with a chain of 4–5 Orange filled circles extending upward from it (the growing peptide chain). In the E site (leftmost): an empty tRNA Blue inverted-L shape with no amino acid, partially exiting downward and to the left. Below the figure, a Black `#000000` 1pt circular arrow with three way-points labeled by position only indicates the three-step cycle: A-site entry → peptide bond → translocation. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Ribosome cross-section. Large 50S subunit (top), small 30S subunit (bottom), mRNA threaded between. Three tRNA sites from left to right: E (empty tRNA exiting), P (tRNA with growing peptide chain), A (incoming charged tRNA with single amino acid and EF-Tu).
[O] Horizontal with mRNA threading left-to-right (matching 5'→3' reading direction). Cyclic arrow below indicates direction of progression.
[P] Large subunit Reddish Purple. Small subunit Sky Blue. mRNA Bluish Green. tRNAs Blue. Amino acids / peptide chain Orange. EF-Tu Bluish Green oval.
[E] No specific tRNA sequences, no codon letters rendered, no ribosomal protein names, no rRNA secondary structure, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, codon letters, tRNA names, ribosomal protein labels, rRNA secondary structure, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 5.4 — Sickle-Cell Cascade: One Base to Polymer

**Priority: Critical.** The chapter's clinical spine. The cascade is multi-scale (codon → amino acid → surface chemistry → polymer fiber → sickled cell → blocked capillary), and the multi-scale image is exactly what students need to internalize "molecular biology is clinical biology."

### Block 1 — Illustrae paste block

A vertical four-tier composition. Tier 1 (codon level): two horizontal mRNA segments side by side, each ~6 nucleotides drawn as small Bluish Green `#009E73` filled circles. Wild-type segment has the position-6 codon highlighted Sky Blue `#56B4E9` (GAG). Mutant segment has the same position highlighted Vermillion `#D55E00` (GUG). Tier 2 (amino acid): two β-globin protein cartoons drawn as Blue `#0072B2` filled wavy ribbon shapes. Wild-type has a single Sky Blue filled circle at position 6 (glutamate, negatively charged, surface). Mutant has a single Vermillion filled circle at position 6 (valine, hydrophobic patch). Tier 3 (tetramer): two hemoglobin tetramers, each four Blue filled ovals in a 2×2 arrangement. Wild-type tetramer is uniform Blue. Mutant tetramer has two Vermillion patches on the surface of the two β-chains. A small Orange `#E69F00` arrow shows the patch on one tetramer fitting into a complementary pocket on a second tetramer to its right, beginning polymerization. Tier 4 (cell): two red blood cells. Wild-type is a Sky Blue filled biconcave disc shape. Mutant is a Reddish Purple `#CC79A7` filled crescent (sickle) shape with internal stiff fibers drawn as Vermillion 1pt parallel lines. Vertical Black `#000000` 1pt arrows connect tier 1 → tier 2 → tier 3 → tier 4, with the chapter's reading direction. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Four tiers. Tier 1: WT codon GAG (Sky Blue) vs mutant GUG (Vermillion). Tier 2: β-globin ribbon with Glu (Sky Blue) vs Val (Vermillion) at position 6. Tier 3: tetramer uniform vs tetramer with hydrophobic patches initiating polymerization. Tier 4: biconcave disc vs sickled crescent with fiber lines. WT and mutant in two parallel columns; left = wild-type, right = mutant. Vertical arrows connect tiers.
[O] Vertical four-tier cascade in two-column comparison.
[P] mRNA backbone Bluish Green. WT codon / Glu / WT cell Sky Blue. Mutant codon / Val / hydrophobic patch / mutant fibers Vermillion. β-globin ribbon Blue. Tetramer Blue ovals. Sickled cell Reddish Purple. Polymerization initiation arrow Orange.
[E] No protein structural ribbon detail at atomic level, no codon letters as graphics, no specific amino acid chemical structures, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, codon sequence letters, amino acid chemical structures, atomic detail, ribbon-level protein structure, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Historical experiment box (Crick/Brenner triplet code 1961, Hershey-Chase blender, etc.).** Picture-research territory.
- **Genetic code table (64 codons → 20 amino acids).** Typography artifact; reproduce as a clean table, not as a figure.
- **Antibiotic binding sites diagram (aminoglycosides, tetracyclines, chloramphenicol, macrolides).** Could be a useful figure, but each drug class would need its own panel; defer to a pharmacology supplement rather than crowd the main chapter.
- **mRNA vaccine lipid nanoparticle structure.** Forward-references vaccinology; defer.
- **AI Wayback Machine (none in this chapter).** Not applicable.

---

## Video Candidate Pass

**FIGURE 5.1 (Transcription bubble):** **MILD VIDEO CANDIDATE.** Animation showing the polymerase moving along template, the bubble traveling with it, and the nascent RNA peeling off the back would dramatize the dynamic nature. Useful but not essential.
**FIGURE 5.2 (mRNA processing):** STATIC SUFFICIENT — could animate the spliceosome two-step transesterification (5' splice attack, then 3' splice attack, lariat release), but the before/after static comparison delivers the gist.
**FIGURE 5.3 (Ribosome cycle):** **STRONG VIDEO CANDIDATE.** This is the chapter's most cinematic mechanism. Watching a tRNA enter the A site, peptide bond form, translocation by one codon, empty tRNA leave from E site, then repeat — the cycle is the mechanism. Mechanism-as-learning-target criterion is met across multiple steps. Bacterial elongation at ~20 aa/sec is also a useful pacing anchor (speed up by 10x for video viewing).
**FIGURE 5.4 (Sickle cascade):** STATIC SUFFICIENT — the multi-scale composition delivers the cascade in one read. An animated zoom-in/zoom-out across scales could be a supplementary video.

**Video candidates identified: 1 strong, 1 mild.** Recommended: **Fig 5.3 (ribosome elongation cycle).** The COVID-vaccine framing pays off when students see the ribosome read codons one at a time — it's the exact mechanism the chapter opens with.

---

## Split-point note

Chapter forward-references Chapter 6 (gene regulation — same RNA polymerase machinery, different control logic) and Chapter 9 (balancing selection at the sickle-cell allele). Figure 5.1 (transcription bubble with Pol II) sets the visual template for Chapter 6's TF + enhancer + Mediator imagery — coordinate. The sickle-cell cascade (Fig 5.4) was anchored in Chapter 3 (pleiotropy example) and reappears in Chapter 9 (heterozygote advantage); the cell-level imagery should be visually consistent across the three chapters.
