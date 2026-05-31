# CAJAL Figure Intelligence — Chapter 13: Molecular Evolution and Evo-Devo

**Source:** `chapters/13-molecular-evolution-evo-devo.md`
**Mode:** `/scan silent`
**Domain note:** Genetics and evolution textbook. Chapter walks two halves: how sequences evolve (Kimura's neutral theory, dN/dS, selective sweeps, transposable elements, gene duplication) and how regulatory change builds bodies (Hox collinearity, the five toolkit signaling pathways, modular enhancers, heterochrony / heterotopy). Stickleback Pitx1 pelvic-enhancer deletion runs as the through-line example; FOXP2 as the self-correcting case. Two author-placed figures.

---

## Density Recommendation

**5 figures, Mechanistic density.** Chapter argument requires visible chromosome-level / sequence-level / regulatory-level / morphology-level machinery. Two author-placed figures (Hox collinearity, modular enhancer) need full architecture; recommend three additional CAJAL figures for stickleback Pitx1, dN/dS spectrum + selective sweep, and the gene duplication fate triad. Five total earn their place.

---

## Zone Map

- **MC:** Neutral fixation rate K = μ derivation (the two 2Ne factors cancel). dN/dS spectrum (< 1 purifying, ≈ 1 neutral, > 1 positive) read through codon degeneracy. Selective sweep as a diversity valley around a fixed beneficial allele; hard vs soft sweep. Hox collinearity — chromosomal order matches anterior-posterior expression order. Modular cis-regulatory architecture lets evolution edit one tissue at a time without pleiotropy. Heterochrony (timing) and heterotopy (location) as the two levers on a conserved toolkit.
- **VG:** Stickleback pelvic spine loss with Pitx1 pelvic enhancer deletion, different specific deletions in different lakes. Histone H4 dN/dS ≈ 0. HIV V3 loop dN/dS > 5. MHC balancing selection. Dolphin olfactory pseudogenes. Lactase persistence sweep in northern Europeans. LINE-1 and Alu transposable elements. Syncytin captured from ERV envelope genes, independently in multiple mammalian lineages. RAG1/RAG2 from Transib transposase → V(D)J recombination. Hemoglobin gene family duplication / subfunctionalization. McGinnis cross-phylum homeobox hybridization. Snake body elongation via HoxC6/HoxC8 expansion. Sonic Hedgehog reuse. Butterfly wing eyespots from heterotopic Distalless. King-Wilson 1975 prediction. FOXP2 with two amino acid changes, Neanderthal sharing, 2018 revision.
- **PQ:** ~45–54% of human genome from transposable elements. L1 ~17% of genome. Alu ~11%, ~1M copies, ~300 bp. Human Hox: 39 genes in 4 clusters. Fly Hox: 8 genes in 2 clusters. Lactase persistence sweep s ≈ 0.05–0.10, last 5,000–10,000 years. Histones H3/H4 differ by 2 amino acids cow vs pea over ~1.5 Gyr. FOXP2: 715 aa, 2 nonsynonymous and 1 synonymous change on human lineage; dN/dS ≈ 0.67.

---

## Figure 13.1 — Hox Collinearity (author-placed)

**Priority: Critical.** The chapter's central evo-devo insight is anchored on collinearity. Visible alignment between chromosomal order and body-axis expression order is the payload.

### Block 1 — Illustrae paste block

A two-panel composition. Top panel — chromosomal Hox cluster: a horizontal Black `#000000` 1pt chromosome backbone with 8 Hox-gene boxes in a row, colored on a gradient from Blue `#0072B2` at the 3' end (left) through Sky Blue `#56B4E9`, Bluish Green `#009E73`, Orange `#E69F00`, Vermillion `#D55E00`, to Reddish Purple `#CC79A7` at the 5' end (right). Each box drawn as a filled rectangle of identical size. Small Black 1pt arrowheads at each end indicate the 3'-to-5' polarity. Bottom panel — body axis with Hox expression domains: a stylized horizontal embryo silhouette drawn in Black 1pt outline, head-left tail-right. Above the embryo, colored bands matching the chromosomal Hox-box colors run across body segments — the Blue band over the anterior head region, the Sky Blue band over the cervical region, the Bluish Green band over the thoracic region, and so on through Reddish Purple at the posterior tail. Thin Black 1pt dashed lines connect each Hox-cluster box in the top panel to its corresponding expression-band region in the bottom panel, demonstrating the order-matching. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Top: horizontal chromosome with 8 Hox boxes colored on anterior-to-posterior gradient. Bottom: embryo silhouette with matching colored expression bands along anterior-to-posterior body axis. Dashed lines connect each Hox box to its body region.
[O] Two stacked horizontal panels. Cluster on top, body on bottom, dashed correspondence lines between.
[P] Chromosome backbone Black with 3'/5' arrowheads. Hox-box gradient Blue (anterior) → Sky Blue → Bluish Green → Orange → Vermillion → Reddish Purple (posterior). Embryo outline Black. Expression bands match Hox-box colors. Correspondence lines Black dashed.
[E] No specific Hox gene names rendered, no specific organism, no segment numbers, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, Hox gene names, organism names, segment numbers, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 13.2 — Modular Enhancer Architecture (author-placed)

**Priority: Critical.** The mechanism that makes regulatory evolution possible without catastrophic pleiotropy. Stickleback case rides on this architecture.

### Block 1 — Illustrae paste block

A horizontal composition. A central Black `#000000` 1.5pt gene rendered as a long horizontal rectangle labeled position "coding region" filled in Sky Blue `#56B4E9`. To the left of the gene, four distinct enhancer modules drawn as smaller horizontal rectangles, each separated by Black 1pt spacer lines indicating intervening DNA. Each enhancer in a distinct color: pelvic enhancer Bluish Green `#009E73`, jaw enhancer Orange `#E69F00`, pituitary enhancer Reddish Purple `#CC79A7`, fin enhancer Blue `#0072B2`. Above each enhancer a small cluster of transcription-factor-binding icons drawn as small filled circles in colors matching tissue-specific factors. Below each enhancer a small tissue-icon silhouette: pelvic enhancer → small pelvic-region silhouette in Bluish Green; jaw enhancer → jaw silhouette in Orange; pituitary enhancer → brain pituitary in Reddish Purple; fin enhancer → fin silhouette in Blue. To the right, a duplicate of the same arrangement showing the pelvic enhancer struck through with a Vermillion `#D55E00` X to indicate a deletion. The pelvic tissue silhouette below now grayed out (drawn in Black 30% opacity) while the other three tissue silhouettes remain in color — visualizing that loss of one enhancer affects only one tissue. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Left: gene with four tissue-specific enhancers, each with bound transcription factors and matching tissue silhouette. Right: same arrangement with pelvic enhancer deleted (Vermillion X), pelvic tissue grayed out, other tissues intact.
[O] Two side-by-side configurations of the same gene-enhancer arrangement. Left panel intact, right panel with one enhancer deleted.
[P] Coding region Sky Blue. Enhancers Bluish Green / Orange / Reddish Purple / Blue, one per tissue. Transcription factor icons in matching enhancer colors. Tissue silhouettes in matching enhancer colors. Deletion indicator Vermillion X. Grayed-out tissue Black 30% opacity.
[E] No specific gene name, no specific TF names, no specific DNA sequence, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene names, TF names, DNA sequences, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 13.3 — Stickleback Pitx1 Pelvic Enhancer: Convergent Regulatory Evolution

**Priority: Critical.** The chapter's signature case — same address, different specific deletions, same morphological outcome across independent freshwater lakes.

### Block 1 — Illustrae paste block

A two-panel composition. Top panel — fish phenotypes: two stickleback silhouettes side by side. Left silhouette in Blue `#0072B2` outline labeled position "marine, spine-bearing" with two short pelvic-spine projections drawn as small Black `#000000` 1pt triangles extending downward from the pelvic region. Right silhouette in Sky Blue `#56B4E9` outline labeled position "freshwater, spineless" with the pelvic region drawn smooth, no spines. Bottom panel — Pitx1 locus across four independent lake populations: a horizontal Black `#000000` 1pt genomic backbone shown four times stacked vertically (one row per lake). On each row the Pitx1 coding region appears at right as a Sky Blue filled rectangle; the pelvic enhancer position appears at left as a Bluish Green `#009E73` filled bracket. Each lake row shows a different specific deletion drawn as a Vermillion `#D55E00` filled rectangle of different width and slightly different position within the enhancer bracket: Row 1 large deletion centered; Row 2 narrow deletion offset left; Row 3 medium deletion offset right; Row 4 medium deletion centered. To the right of each row a small Bluish Green checkmark indicating "spineless phenotype achieved". Above the stacked rows a Black 1pt bracket annotating "same enhancer address". Below, an annotation bracket reading "different specific deletions". White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Top: marine stickleback with spines vs freshwater stickleback without spines. Bottom: Pitx1 locus across four lake populations, each with a different specific deletion in the same pelvic enhancer, all reaching the same spineless phenotype.
[O] Two stacked panels. Top: two fish silhouettes side by side. Bottom: four stacked genomic backbones with deletion rectangles, bracketed top and bottom by annotations.
[P] Marine fish Blue outline. Freshwater fish Sky Blue outline. Spines Black triangles. Pitx1 coding region Sky Blue. Pelvic enhancer bracket Bluish Green. Deletions Vermillion rectangles. Phenotype checkmark Bluish Green. Annotation brackets Black.
[E] No specific lake names, no specific deletion coordinates, no specific gene structure detail, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, lake names, deletion coordinates, gene structure detail, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 13.4 — dN/dS Spectrum and the Selective Sweep

**Priority: Critical.** Connects the chapter's central diagnostic (dN/dS) to its signature population-genetic signature (sweep / diversity valley). One figure carries both.

### Block 1 — Illustrae paste block

A two-panel composition. Left panel — dN/dS spectrum bar chart: x-axis with three labeled positions (purifying, neutral, positive). Three vertical reference bars at dN/dS = 0.1 (Blue `#0072B2` filled, labeled position "histones"), dN/dS = 1 (Bluish Green `#009E73` filled, labeled position "pseudogenes"), dN/dS = 5 (Vermillion `#D55E00` filled, labeled position "HIV V3"). A horizontal Black `#000000` 1pt reference line at dN/dS = 1. Right panel — selective sweep diversity valley: x-axis labeled position "chromosomal position", y-axis labeled position "nucleotide diversity". A Sky Blue `#56B4E9` 1pt curve at moderate level across most of the x-axis representing baseline diversity. Sharply dipping to near zero at a central swept-site position drawn as an Orange `#E69F00` filled vertical line. The dip is widened on both sides forming a clear valley. Above the swept-site marker a small Vermillion `#D55E00` filled star labeled position "beneficial fixation". A faint Reddish Purple `#CC79A7` ghost curve overlay shows what a softer / wider sweep would look like with a shallower valley. White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Left: dN/dS bar chart with three exemplar values spanning purifying / neutral / positive selection regimes. Right: nucleotide diversity along a chromosome showing a sharp valley around a swept beneficial site, with a ghost overlay of a softer sweep.
[O] Two side-by-side panels. Left bar chart with three vertical bars. Right line plot with diversity baseline and central valley.
[P] Purifying bar Blue. Neutral bar Bluish Green. Positive bar Vermillion. Reference line Black. Baseline diversity Sky Blue. Swept site marker Orange. Fixation star Vermillion. Softer sweep ghost Reddish Purple.
[E] No specific gene names within image, no specific quantitative axis ticks, no specific population names, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene names, quantitative axis ticks, population names, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## Figure 13.5 — Gene Duplication Fates

**Priority: Important.** Three distinct fates (pseudogenization, subfunctionalization, neofunctionalization) walked as a flowchart. The hemoglobin family is the worked case but the figure should be diagrammatic.

### Block 1 — Illustrae paste block

A branching flowchart composition. Top center — single ancestral gene drawn as a Sky Blue `#56B4E9` filled horizontal box with three small Black `#000000` 1pt expression-domain markers labeled position "tissue A", "tissue B", "tissue C". A Black 1pt downward arrow leads to a duplication event marked by a small Bluish Green `#009E73` filled diamond. Below the diamond, two parallel daughter genes drawn as Sky Blue filled boxes side by side. From the daughter-gene pair, three downward branches diverging into three fate columns. Left column — pseudogenization: daughter gene 2 gradually accumulates Vermillion `#D55E00` filled X marks indicating stop codons and frameshifts; final box drawn in Black 30% opacity (molecular fossil). Middle column — subfunctionalization: daughter 1 retains tissue A and B markers, daughter 2 retains tissue C marker (each daughter loses some regulatory elements, indicated by missing markers); both daughters drawn in full Sky Blue. Right column — neofunctionalization: daughter 1 retains all three original tissue markers; daughter 2 gains a new Orange `#E69F00` filled "tissue D" marker representing a novel function; both daughters drawn in full Sky Blue. Above each column a labeled bracket: "pseudogenization", "subfunctionalization", "neofunctionalization". White background, flat vector, double-column 174mm preferred.

### Block 2 — Full SCOPE prompt

[S] Double-column 174mm preferred, vector, white background.
[C] Ancestor gene with three tissue-expression domains undergoes duplication then diverges into three fate columns: pseudogenization (decay markers), subfunctionalization (split domains), neofunctionalization (new domain added).
[O] Vertical flowchart top to bottom. Single ancestor → duplication diamond → paired daughters → three diverging fate columns.
[P] Ancestor and daughter genes Sky Blue. Duplication event Bluish Green diamond. Expression-domain markers Black, novel marker Orange. Decay X marks Vermillion. Fossil opacity 30% Black. Column brackets Black.
[E] No specific gene family names, no specific tissue names, no specific time scale, no decorative ornament, no shadows.

### Block 3 — Negative prompt

text labels, gene family names, tissue names, time scale, gibberish letters, titles, captions, decorative ornament, photographic elements, realistic 3D textures, drop shadows, gradient fills, gradient backgrounds, hand-drawn styles, sketch lines, decorative borders, colorful backgrounds, visual clutter, fuzzy borders, watermarks, red-green color combinations, rainbow color scales, 3D perspective distortion

---

## What CAJAL Declines to Architect

- **Five toolkit signaling pathways panel (Wnt / Notch / Hedgehog / BMP / FGF).** The pathways are conceptually similar enough that a comparison schematic risks becoming visual filler; better to handle in a dedicated cell-signaling chapter or as a sidebar.
- **FOXP2 worked example.** The dN/dS arithmetic and historical-correction narrative is text-native; a figure would either duplicate Fig 13.4 or rehash math.
- **Syncytin / V(D)J recombination / ERV-derived enhancers.** Three independent cases of transposon co-option; a combined schematic risks oversimplifying. Better as Fig 13.6 if budget allows, or handled in text alone.
- **Heterochrony / heterotopy axolotl and butterfly eyespot illustrations.** Picture-research deliverables; the conceptual mechanism is covered by Fig 13.2 modularity.
- **AI Wayback Machine biographical material on Kimura, King, Wilson.** Picture research.

---

## Video Candidate Pass

**FIGURE 13.1 (Hox collinearity):** **MILD VIDEO CANDIDATE.** Animating the boundary-shift case — sliding the posterior boundary of one Hox expression domain to produce snake-like elongation of the trunk — would make heterochrony / heterotopy visceral.
**FIGURE 13.2 (Modular enhancer):** STATIC SUFFICIENT for the architecture; animation of the deletion event could complement.
**FIGURE 13.3 (Stickleback Pitx1):** STATIC SUFFICIENT.
**FIGURE 13.4 (dN/dS + sweep):** **MILD VIDEO CANDIDATE.** Animating the sweep — beneficial allele arising, escaping drift, rising to fixation, the surrounding diversity valley carving itself out as recombination races against fixation — would dramatize the hitchhiking effect.
**FIGURE 13.5 (Gene duplication fates):** STATIC SUFFICIENT.

**STRONG VIDEO CANDIDATE — anchored on Fig 13.1: Hox gene expression along the embryonic body axis.** This is the chapter's central conceptual hinge. Show an early bilaterian embryo elongating along the anterior-posterior axis; as somites form, color them in real time according to the Hox gene whose expression dominates that segment; demonstrate collinearity by playing the chromosomal Hox cluster left-to-right and the body axis anterior-to-posterior in synchrony; then perturb — shift one Hox boundary and watch the morphology change (snake-like body, additional ribs). Hits both the mechanism-as-learning-target criterion and the dynamic-developmental-process criterion. **Recommended as the chapter's primary animation deliverable.**

**Video candidates identified: 1 strong (Hox expression along body axis) + 2 mild (Fig 13.1 boundary shift variant, Fig 13.4 sweep).** Recommended: **the Hox expression animation** as the chapter's centerpiece video.

---

## Split-point note

Chapter cross-references Ch 11 speciation (selective sweeps) and Ch 12 phylogenetics (molecular clock, dN/dS as branch-and-site diagnostic). The Fig 13.4 sweep schematic should coordinate visually with any sweep figure in Ch 11 or the capstone Ch 14. The stickleback Pitx1 case in Fig 13.3 will be referenced again in Ch 14's lactase persistence section as the parallel "convergent regulatory evolution" precedent — palette and motif should match across both chapters so the parallel reads visually.
