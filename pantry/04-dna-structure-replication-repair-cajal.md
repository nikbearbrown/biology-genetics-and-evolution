# CAJAL Figure Intelligence — Chapter 4: DNA Structure, Replication, and Repair

**Source:** `chapters/04-dna-structure-replication-repair.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Argues the ~10⁻⁹ per-base error rate is not a property of the molecule but the product of three nested error-correction layers (polymerase selection, 3'→5' proofreading, mismatch repair) plus three additional pathways for non-replication damage (BER, NER, double-strand break repair via HR/NHEJ). Five author-placed figures. Strong video candidate at replication fork.

---

## Density Recommendation

**5 figures, Mechanistic density.** All five author-placed figures earn their place. The chapter is mechanism-heavy and the figures sit at the exact junctures where text alone bruises: nucleotide chemistry (4.1), base-pairing geometry (4.2), Meselson-Stahl logic (4.3), the replication fork (4.4), and synthetic lethality (4.5). The fork figure is the chapter's spine; do not compress it.

---

## Zone Map

- **MC:** Three error-correction layers compounding to ~10⁻⁹. Semiconservative replication. The replication-fork player sequence (helicase → SSB → topoisomerase → primase → pol → RNase H / FEN1 → ligase). Leading vs lagging strand asymmetry forced by antiparallelism + 5'→3' polymerase constraint. MMR strand-discrimination (Dam methylation in *E. coli*; nicks in eukaryotes). Synthetic lethality (BRCA + PARP).
- **VG:** Nucleotide three parts (phosphate, sugar, base). A-T two H-bonds vs G-C three H-bonds. Antiparallel strand orientation. Helix dimensions (~2 nm diameter, ~10 bp / 3.4 nm per turn, major/minor grooves). Meselson-Stahl density-gradient band patterns. Okazaki fragments. Telomere shortening.
- **PQ:** ~3 mutations per cell division. 10⁵ → 10⁷ → 10⁹ accuracy stack. ~1,000 nt/sec polymerase. 30,000–50,000 eukaryotic origins. 6 hours for full human replication. 10,000 depurinations / cell / day. BRCA1 60–72% lifetime breast cancer risk. ~50 Hayflick limit population doublings. Telomere TTAGGG hexamer.

---

## Figure 4.1 — A Single Nucleotide (Three Components)

**Priority: Important.** Foundation for the rest of the chapter. Students who do not internalize phosphate–sugar–base structure cannot follow phosphodiester bonds, 3'-OH chemistry, or proofreading.

### Block 1 — Illustrae paste block

A single-nucleotide schematic, vertically arranged. Top: a phosphate group represented as a Vermillion `#D55E00` filled circle with three small open circles around it (oxygen atoms implied by negative space, no atomic labels). Middle: the deoxyribose sugar represented as a Sky Blue `#56B4E9` filled pentagon with the 5'-carbon attachment point indicated by a short Black `#000000` 1pt connecting line to the phosphate above, and the 3'-OH attachment point indicated by a small Bluish Green `#009E73` open circle at the lower right of the pentagon. Bottom-right: the nitrogenous base represented as a Blue `#0072B2` filled hexagon (purine, two rings shown as a fused hexagon-pentagon shape) or alternatively a single Reddish Purple `#CC79A7` hexagon (pyrimidine, one ring). Connection from sugar to base is a Black 1pt N-glycosidic bond line. White background, flat vector, single-column 89mm. The asymmetry of 5' and 3' ends is visually clear by position alone.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] Three-component nucleotide. Phosphate (top) bonded via 5'-carbon to deoxyribose pentagon (middle). 3'-OH on the sugar shown as a Bluish Green node. Base (bottom right) bonded to sugar via N-glycosidic line. Show one purine and one pyrimidine option side by side or in a single composite.
[O] Vertical stack: phosphate / sugar / base. Directionality (5' top, 3' lower-right) implied by geometry.
[P] Phosphate Vermillion. Sugar Sky Blue. 3'-OH Bluish Green. Purine Blue. Pyrimidine Reddish Purple. Bonds Black 1pt.
[E] No carbon numbering rendered as graphics, no atomic labels, no chemical formulas, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, carbon numbering, atomic symbols, chemical formulas, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 4.2 — A-T and G-C Base Pairs

**Priority: Critical.** The hydrogen-bond geometry — two bonds for A-T, three for G-C — is the physical mechanism enforcing fidelity. Must be visible.

### Block 1 — Illustrae paste block

A two-panel side-by-side composition. Left panel: adenine and thymine paired. Adenine drawn as a Blue `#0072B2` filled fused-ring shape (hexagon + pentagon, the two-ring purine) on the left. Thymine drawn as a Reddish Purple `#CC79A7` filled hexagon (single-ring pyrimidine) on the right. Between them, **two** parallel Black `#000000` 1pt dashed lines representing the two hydrogen bonds. Right panel: guanine and cytosine paired. Guanine drawn as a Blue filled fused-ring shape on the left. Cytosine drawn as a Reddish Purple filled hexagon on the right. Between them, **three** parallel Black 1pt dashed lines. A short Sky Blue `#56B4E9` line on the outside of each base indicates where the sugar-phosphate backbone attaches. The two backbone attachment lines on each side are antiparallel (one labeled by position as "up," the other as "down" using a small Black arrow on the backbone-line ends). White background, flat vector, single-column 89mm.

### Block 2 — Full SCOPE prompt

[S] Single-column 89mm, vector, white background.
[C] Two panels. Panel 1: A-T pair with exactly two horizontal dashed H-bonds. Panel 2: G-C pair with exactly three horizontal dashed H-bonds. Backbone attachment points on outer edges show antiparallel strand direction via small arrows.
[O] Side by side, equal panel sizes. Hydrogen bond count is the visual punchline — make the 2-vs-3 contrast unmistakable.
[P] Purines (A, G) Blue. Pyrimidines (T, C) Reddish Purple. Backbone connectors Sky Blue. H-bonds Black 1pt dashed.
[E] No atomic-level chemical structure, no donor/acceptor annotations rendered as graphics, no specific atom names, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, atomic symbols, donor/acceptor annotations, chemical formulas, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 4.3 — Meselson-Stahl Density-Gradient Band Predictions

**Priority: Critical.** "The most beautiful experiment in biology" earns a clean visual. The three competing models predict distinguishable band patterns; the figure has to make that distinguishability obvious.

### Block 1 — Illustrae paste block

A three-column horizontal composition, each column a different model (Conservative, Semiconservative, Dispersive). Within each column, three vertical tubes drawn as Black `#000000` 1pt outline rectangles, labeled by position only as "Gen 0 (heavy)," "Gen 1," "Gen 2." Inside each tube, horizontal bands represent DNA at different densities — high (top of tube) is Blue `#0072B2` thick band, intermediate is Bluish Green `#009E73` thick band, low (bottom of tube) is Sky Blue `#56B4E9` thick band. Column 1 (Conservative): Gen 0 = Blue band only. Gen 1 = Blue band + Sky Blue band (two bands). Gen 2 = same two bands, smaller Blue, larger Sky Blue. Column 2 (Semiconservative): Gen 0 = Blue band. Gen 1 = Bluish Green band only (single intermediate band). Gen 2 = Bluish Green band + Sky Blue band (intermediate + light, equal amounts). Column 3 (Dispersive): Gen 0 = Blue band. Gen 1 = Bluish Green band (intermediate). Gen 2 = a single band drifted slightly lighter (between Bluish Green and Sky Blue, no splitting). At the bottom of each column, a Vermillion `#D55E00` checkmark or X indicates which models the data ruled in (Semiconservative ✓) or out (Conservative ✗ at Gen 1; Dispersive ✗ at Gen 2). White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] Three model columns × three generation rows = 9 centrifuge-tube diagrams. Band positions encode density: Blue (heavy ¹⁵N), Bluish Green (intermediate hybrid), Sky Blue (light ¹⁴N). Conservative predicts two bands at Gen 1. Semiconservative predicts one intermediate band at Gen 1 and two bands at Gen 2 (intermediate + light). Dispersive predicts one band at Gen 1 that drifts lighter at Gen 2 without splitting.
[O] Three columns, three rows. Outcome row at bottom marks the experiment's verdict.
[P] Heavy Blue. Hybrid intermediate Bluish Green. Light Sky Blue. Verdict marks Vermillion. Tube outlines Black 1pt.
[E] No molecular detail inside tubes, no density numbers, no isotope chemical formulas, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, density numbers, isotope formulas, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 4.4 — Moving Replication Fork

**Priority: Critical.** The chapter's spine. Must show leading vs lagging asymmetry, Okazaki fragments, and the player sequence at the fork.

### Block 1 — Illustrae paste block

A horizontal Y-shaped composition. On the left, the parental duplex enters as two parallel Blue `#0072B2` 1pt strands (the two parental templates). At the fork (center), the strands separate: top template runs left-to-right (3'→5' as fork moves right), bottom template runs left-to-right (5'→3' as fork moves right). At the cusp, a Reddish Purple `#CC79A7` wedge represents helicase, with a small Bluish Green `#009E73` disc behind it labeled by position as topoisomerase. Small Sky Blue `#56B4E9` filled ovals coat the separated single strands (SSBs). On the top template (leading strand): one continuous Vermillion `#D55E00` 1pt new strand extending rightward toward the fork, with a small Orange `#E69F00` filled oval at its 3' end representing polymerase ε / pol III. A single Bluish Green RNA primer at its origin. On the bottom template (lagging strand): three short Vermillion 1pt new-strand segments (Okazaki fragments) running rightward, each starting with a small Bluish Green RNA primer and extending away from the fork. Small Orange polymerase ovals at the 3' end of the most recent fragment. A single Reddish Purple ligase symbol (small circle) sits at one already-joined fragment junction. Below the figure, the direction of fork movement is indicated by a Black `#000000` 1pt arrow pointing right. White background, flat vector, double-column 174mm preferred (full-width if available).

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Y-shaped fork. Parental duplex enters from the left; two daughter duplexes exit toward the right. Helicase wedge at the fork cusp. SSBs coat separated strands. Topoisomerase behind helicase. Leading strand (top): single continuous new strand with one primer and one polymerase. Lagging strand (bottom): 3–4 Okazaki fragments, each with its own RNA primer, polymerase at the active fragment, ligase at one junction.
[O] Horizontal Y oriented left-to-right with fork-movement arrow.
[P] Parental templates Blue. New strands Vermillion. RNA primers Bluish Green. Helicase Reddish Purple. SSBs Sky Blue. Polymerase Orange. Ligase Reddish Purple small circle. Topoisomerase Bluish Green disc.
[E] No protein domain detail, no specific enzyme amino-acid structure, no nucleotide-level detail, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, protein names rendered as graphics, enzyme structures, nucleotide-level chemistry, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 4.5 — Synthetic Lethality: BRCA Loss + PARP Inhibition

**Priority: Critical.** The clinical payoff of the entire chapter. The 2×2 logic — normal vs BRCA-deficient cell, untreated vs PARP-inhibited — only one cell dies. Must be visible as a 2×2.

### Block 1 — Illustrae paste block

A 2×2 grid composition. Rows: top row "BRCA functional," bottom row "BRCA-deficient." Columns: left column "untreated," right column "PARP inhibitor." Each cell in the grid contains a simple cell silhouette (Sky Blue `#56B4E9` filled oval representing a cell). Inside the cell, two small icons indicate repair-pathway status: a Bluish Green `#009E73` filled circle for "HR active" and a Vermillion `#D55E00` filled circle for "BER active." If a pathway is lost, the corresponding circle is replaced with a Black `#000000` open circle (outline only). Top-left cell: both Bluish Green and Vermillion circles present, cell intact. Top-right cell: Bluish Green present (HR intact), Vermillion replaced with Black open circle (BER blocked by PARP inhibitor) — cell still intact because HR rescues. Bottom-left cell: Bluish Green replaced with Black open circle (HR lost from BRCA mutation), Vermillion present — cell intact because BER handles damage. Bottom-right cell: both circles Black open — cell silhouette outlined in Reddish Purple `#CC79A7` with a Black diagonal slash through it indicating cell death. A small Orange `#E69F00` "synthetic lethal" annotation marker sits beside the bottom-right cell. White background, flat vector, double-column 174mm.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm, vector, white background.
[C] 2×2 grid. Rows: BRCA functional / BRCA deficient. Columns: untreated / PARP inhibitor. Each cell silhouette shows two repair pathway icons: HR (Bluish Green filled = active, Black open = lost) and BER (Vermillion filled = active, Black open = blocked). Only the bottom-right cell (both pathways disabled) shows cell death.
[O] 2×2 matrix with consistent cell silhouette in each cell.
[P] Cell body Sky Blue. HR active Bluish Green / lost Black open. BER active Vermillion / blocked Black open. Dead cell outline Reddish Purple with Black slash. Synthetic-lethal marker Orange.
[E] No protein names rendered as graphics, no drug molecule structures, no specific cancer cell types, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, protein names, drug structures, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Repair-pathway comparison table (lines 191–197).** The manuscript already has a (broken-looking) table; restore it as typography, not as a figure.
- **Three-experiment history (Griffith, Avery-MacLeod-McCarty, Hershey-Chase).** Historical narrative; portraits or experimental diagrams would be picture-research, declined.
- **Telomere shortening / Hayflick limit.** Forward-references Chapter 8 (cancer); defer figure design to that chapter.
- **AI Wayback Machine (Rosalind Franklin).** Out of scope.
- **HTML simulator prompt block.** Pedagogy artifact, not a figure.

---

## Video Candidate Pass

**FIGURE 4.1 (Nucleotide):** STATIC SUFFICIENT.
**FIGURE 4.2 (Base pairs):** STATIC SUFFICIENT.
**FIGURE 4.3 (Meselson-Stahl):** STATIC SUFFICIENT — could animate the three-generation sequence (heavy → hybrid → split) per model, but the static three-column comparison delivers the falsification logic in one read.
**FIGURE 4.4 (Replication fork):** **STRONG VIDEO CANDIDATE.** The fork is the chapter's hardest mechanism precisely because it is dynamic — helicase moving, polymerases extending, primase laying primers ahead of the lagging strand, Okazaki fragments forming and getting ligated. Animation makes leading/lagging asymmetry visceral. The "why is the lagging strand awkward" question collapses into one obvious answer when you watch the fork move. Mechanism-as-learning-target criterion is met.
**FIGURE 4.5 (Synthetic lethality):** STATIC SUFFICIENT — the 2×2 is the punchline. A brief click-through showing damage accumulating in only the bottom-right cell could supplement, but the static grid carries the meaning.

**Video candidates identified: 1 strong.** Recommended: **Fig 4.4 (replication fork).** Reference scenes from the chapter's HTML-simulator prompt block (Panel 1) for animation specs — they're already written.

---

## Split-point note

Chapter forward-references Chapter 8 (cancer, mutation accumulation, telomerase reactivation) and Chapter 3 (BRCA1 penetrance). Figure 4.5 (synthetic lethality) and the BRCA discussion should coordinate visually with Chapter 3's BRCA1 two-sister anchor — same color treatment for BRCA-deficient state. The replication-fork visual (4.4) should set the style template for any fork imagery reused in Chapter 6 (DNMT1 maintenance methylation at the fork, Fig 6.4).
