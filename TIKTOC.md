# TIKTOC.md — Biology +1: Genetics & Evolution
## A Simulation-First Genetics and Evolution Textbook

**Working title:** Biology +1: Genetics & Evolution — Interactive Simulations with Claude and D3
**Series:** Biology +1 Series
**Author:** Humanitarians AI · ni.brown@neu.edu · Bear Brown & Company
**Repo:** biology-plus-one-genetics-and-evolution
**Version:** 1.0
**Status:** TIKTOC complete — ready for research gathering and chapter drafting

---

## Book Concept

This book teaches genetics and evolution — from meiosis and Mendelian inheritance through molecular genetics, gene regulation, biotechnology, and the mechanisms of evolutionary change — to biology majors in introductory genetics and evolution courses, by pairing each conceptual chapter with LLM-generated D3.js simulations that make genetic and evolutionary processes visible. Allele frequencies drift in real time. Natural selection sweeps through populations. Phylogenetic trees assemble from molecular data. Regulatory networks respond to environmental signals.

**The central insight of this book is that genetics and evolution are the same subject at different scales.** Genetics asks how information is stored, copied, expressed, and varied within a generation. Evolution asks how that variation is filtered across generations by natural selection, genetic drift, and other forces. The bridge between them — mutation as the source of variation, Hardy-Weinberg as the null model, selection as the filter — is the conceptual spine of the book.

**The narrative arc runs from cellular mechanism to population dynamics to deep time.** The book begins with meiosis (why offspring differ from parents), moves through molecular genetics (what genes are and how they work), crosses the bridge of mutation and cancer (Chapter 8), and enters evolutionary biology (how populations change, how species form, how life's history is reconstructed). A student who finishes this book can explain how a new antibiotic resistance gene spreads through a bacterial population, why some genetic diseases are more common in isolated populations, and how we know that whales evolved from land mammals.

**Series position:** Core genetics and evolution volume. Assumes Biology +1: The Cell (especially cell division, DNA structure, and protein synthesis). Bridges to Biology +1: Animal Physiology (evolution shapes physiological diversity) and to the Cancer +1 series (cancer as somatic evolution). Chapter 1 (Meiosis) overlaps with Biology +1: The Cell Chapter 13 — students from that volume will recognize the material; the framing here is inheritance rather than cell division.

---

## Book Type and Deployment

**Primary type:** Course textbook — adopted for a semester, chapter = roughly one week.

**Target course:** Introductory genetics and evolution for biology majors. Sophomore/junior level. Can serve as a combined genetics-evolution course or as the evolution component of an introductory biology sequence.

**Prerequisites assumed:** Biology +1: The Cell or equivalent (cell division, DNA as genetic material, basic protein synthesis). High school biology. No prior genetics or evolution course required.

**Prerequisites explicitly not required:** Organic chemistry. Calculus (algebra and basic probability sufficient). Statistics beyond introductory level.

**Semester format:** 15 weeks. Chapter 0 Week 1 alongside Chapter 1. Chapters 1–14 map to Weeks 1–14. Week 15 flex.

**What this book is not:** A graduate genetics text. A molecular biology laboratory manual. A phylogenetics software tutorial. A medical genetics reference.

---

## The +1 System

Each chapter ends with an **LLM Exercise** block:
1. **The simulation prompt** — four-move prompt producing a working D3 visualization
2. **Exploration tasks** — specific parameter changes answered by observation
3. **Extension prompt** — bridges to the next chapter

Chapter 0 generates `CLAUDE.md`, `DESIGN.md`, and `PROJECT.md`.

**Genetics & Evolution simulation character:** Simulations visualize genetic processes (allele segregation, pedigree analysis, DNA replication) and evolutionary dynamics (allele frequency change over time, population bottlenecks, phylogenetic tree building). Many simulations are stochastic — running the same simulation twice gives different results, which is the point. D3 is used for animated genetic diagrams, population allele frequency charts, and phylogenetic tree visualizers.

---

## Three-Act Learning Arc

**ACT ONE — Inheritance and Molecular Genetics (Chapters 1–7)**
*From "offspring resemble but differ from parents" to "I understand the molecular mechanisms that store, copy, and express genetic information."*
Meiosis → Mendelian genetics → extensions of Mendel → DNA structure and replication → transcription and translation → gene regulation → biotechnology. The molecular foundation of heredity.

**ACT TWO — Variation, Mutation, and the Bridge to Evolution (Chapter 8)**
*The pivot chapter: mutation connects molecular genetics to evolutionary change.*
Mutation, DNA damage, repair, and cancer genetics. How errors in the molecular machinery become the raw material of evolution — and when they become disease.

**ACT THREE — Evolutionary Mechanisms and Deep Time (Chapters 9–14)**
*From "I understand genetic variation" to "I can explain how populations evolve, how species form, and how life's history is reconstructed."*
Evolution and natural selection → population genetics → speciation → phylogenetics → molecular evolution and evo-devo → capstone synthesis.

---

## Chapter List

---

### CHAPTER 00 — How to Use the Simulations
**Filename:** `00-how-to-use-the-simulations.md`
**Arc position:** Pre-chapter / setup
**Source:** New

**One-line:** Students build the three Brutalist governing files and produce their first genetics simulation — a Punnett square generator that scales to any number of traits — before reading any new content.

**Chapter description:**
One job: get the student to a working, modifiable D3 genetics simulation before any new biology. The first simulation is a Punnett square — the most recognizable tool in genetics — because every student has seen one and because extending it to dihybrid and trihybrid crosses immediately shows the power of the computational approach. A 4×4 Punnett square by hand is tedious. A 16×16 one is impossible. The simulation makes both trivial.

**Core concepts:**
- The Brutalist system: CLAUDE.md, DESIGN.md, PROJECT.md
- The four-move prompt structure: Show / Say / Constrain / Verify
- D3 v7 for genetics: SVG grids, allele frequency charts, stochastic simulations, phylogenetic trees
- Punnett square as first simulation: gamete combinations, genotype ratios, phenotype ratios
- The verification stack: biology check (does a monohybrid Aa × Aa give 1:2:1 genotype ratio?), format check, browser test

**What the student builds:**
- `CLAUDE.md` — genetics simulation coding constitution (D3 v7, SVG canvas, grid-based genetic diagrams, stochastic population simulations, allele frequency line charts, phylogenetic tree rendering)
- `DESIGN.md` — visual constitution (dominant allele: dark blue #1a5276; recessive allele: light blue #85c1e9; heterozygous: medium blue #2980b9; wild-type: green #27ae60; mutant: red #c0392b; population allele frequency: dark line on white; genetic drift: multiple colored lines; selection: arrow overlays; phylogenetic branches: gray #7f8c8d; dark mode support)
- `PROJECT.md` — project state
- `00-punnett-square.html` — Punnett square generator: input fields for parent genotypes (up to trihybrid); generates correctly sized grid; colors cells by genotype (dominant homozygous, heterozygous, recessive homozygous); calculates and displays genotype ratios and phenotype ratios; slider to add more loci

**Simulation physics:**
For N loci, each heterozygous parent produces 2^N gamete types. Grid is 2^N × 2^N. Each cell is filled by combining row gamete and column gamete. Count cells by genotype class. Display as colored grid with ratio summary.

**Color conventions for DESIGN.md:**
- Dominant homozygous genotype: dark blue (#1a5276)
- Heterozygous genotype: medium blue (#2980b9)
- Recessive homozygous genotype: light blue (#85c1e9)
- Wild-type phenotype: green (#27ae60)
- Mutant/disease phenotype: red (#c0392b)
- Carrier (genetics pedigree): half-filled symbol
- Population allele frequency p: solid dark line (#2c3e50)
- Population allele frequency q: solid gray line (#7f8c8d)
- Genetic drift replicates: multiple thin colored lines
- Phylogenetic branches: gray (#95a5a6); bootstrap values: orange (#e67e22)
- Dark mode: backgrounds to #1a1a1a

**Connection to Chapter 1:** Punnett squares show the outcomes of crosses. Chapter 1 explains why those outcomes occur — the behavior of chromosomes during meiosis.

---

### CHAPTER 01 — Meiosis and the Basis of Inheritance
**Filename:** `01-meiosis-basis-of-inheritance.md`
**Arc position:** Act One, Chapter 1
**Source:** `14-meiosis-and-sexual-reproduction.md`

**One-line:** Students learn how meiosis halves chromosome number and generates genetic variation through crossing over and independent assortment — establishing why offspring differ from parents and from each other.

**Chapter description:**
The genetics framing of meiosis differs from the cell biology framing in Biology +1: The Cell. There, meiosis was introduced as a type of cell division. Here, meiosis is introduced as the mechanistic explanation for Mendel's laws — which Mendel himself never knew. Independent assortment of homologs explains the Law of Independent Assortment. Separation of alleles at anaphase I explains the Law of Segregation. Crossing over explains why linked genes are not always inherited together. Students who have seen meiosis in The Cell volume are now seeing why it matters for inheritance; students encountering it for the first time get the cell biology and the genetics simultaneously.

**Core concepts:**
- Why sexual reproduction requires chromosome number reduction: diploid + diploid = tetraploid without meiosis; meiosis restores diploid number each generation
- Homologous chromosomes: same genes, same loci, possibly different alleles; one from each parent
- Meiosis I — the reductive division:
  - Prophase I: chromosomes condense; homologs synapse (synapsis); crossing over at chiasmata; synaptonemal complex
  - Crossing over (recombination): non-sister chromatids of homologs exchange segments; creates recombinant chromosomes; increases genetic diversity; ~1–3 crossovers per chromosome per meiosis
  - Metaphase I: bivalents align at metaphase plate; independent assortment — each bivalent orients randomly
  - Anaphase I: homologs separate; 2n → n (but still 2 chromatids per chromosome)
  - Result: two haploid cells, each with replicated chromosomes
- Meiosis II — the equational division: sister chromatids separate; four haploid cells
- Genetic variation from meiosis:
  - Independent assortment: 2²³ ≈ 8 million possible gamete types in humans from this mechanism alone
  - Crossing over: effectively unlimited combinations; recombination frequency as a measure of genetic distance
  - Random fertilization: further multiplies variation
- Connecting meiosis to Mendel:
  - Law of Segregation: alleles on homologs separate at anaphase I → each gamete gets one allele
  - Law of Independent Assortment: non-homologous chromosomes orient independently at metaphase I → alleles on different chromosomes assort independently
- Errors in meiosis: nondisjunction → aneuploidy; trisomy 21, Turner syndrome, Klinefelter syndrome; maternal age effect on nondisjunction

**Key vocabulary:** homologous chromosomes, allele, locus, diploid, haploid, synapsis, crossing over, chiasma, independent assortment, Law of Segregation, Law of Independent Assortment, recombination frequency, nondisjunction, aneuploidy, trisomy

**What the student builds:**
`01-meiosis-genetics.html` — meiosis and genetic variation simulator. Controls: number of chromosome pairs (2–5 for clarity); crossing over frequency slider; run simulation button (stochastic). Display: animated meiosis showing homolog pairing, crossing over events (shown as color exchanges), independent assortment (random orientation at metaphase I), and final four gametes; each gamete's chromosome composition shown color-coded by parental origin; genetic diversity counter showing number of unique gamete types produced across N runs; Law of Segregation panel: for a heterozygous locus Aa, show that exactly 50% of gametes carry A and 50% carry a across many runs.

**Key references for research agent:**
- OpenStax Biology Chapter 11 (Meiosis and Sexual Reproduction)
- Crossing over mechanism: Szostak et al. (1983) *Cell* double-strand break model
- Independent assortment and Mendel's laws: connection established by Sutton (1902) and Boveri
- Nondisjunction and maternal age: Hook (1981) *Science*; CDC birth defect data
- Recombination frequency as genetic distance: Morgan and Sturtevant (1913)

**Bridge to Chapter 2:** Meiosis explains why offspring inherit combinations of parental traits. Chapter 2 examines the patterns those inheritance combinations produce — Mendel's laws in action.

---

### CHAPTER 02 — Mendel's Laws and Mendelian Inheritance
**Filename:** `02-mendels-laws-mendelian-inheritance.md`
**Arc position:** Act One, Chapter 2
**Source:** `15-mendels-experiments-and-heredity.md`

**One-line:** Students learn Mendel's experimental approach, derive the Laws of Segregation and Independent Assortment from crossing data, and build a virtual genetics experiment simulator that replicates Mendel's pea plant crosses.

**Chapter description:**
Mendel's experiments are the foundation of genetics — and a masterclass in experimental design. He chose the right organism (peas, which self-fertilize and have easily distinguishable traits), the right traits (seven pairs of contrasting characters, each controlled by a single gene on a different chromosome — extraordinarily lucky), and the right approach (large sample sizes, quantitative analysis, multiple generations). This chapter works through Mendel's logic: how he inferred the existence of discrete heritable factors from phenotypic ratios, how he distinguished dominant from recessive, and how he derived both laws. The simulation replicates Mendel's actual crosses with realistic sampling variation — students discover the 3:1 ratio themselves before it is stated.

**Core concepts:**
- Mendel's experimental design: pea plant advantages; true-breeding lines; P, F1, F2 generations; reciprocal crosses
- Monohybrid cross: one trait; P: AA × aa → F1: all Aa (dominant phenotype) → F2: 3 dominant : 1 recessive (phenotype); 1:2:1 (genotype)
- Law of Segregation: two alleles for each trait; alleles separate during gamete formation; each gamete carries one allele
- Testcross: cross unknown genotype with homozygous recessive; reveals genotype of unknown parent
- Dihybrid cross: two traits on different chromosomes; F2: 9:3:3:1 phenotype ratio
- Law of Independent Assortment: alleles of different genes assort independently (when on different chromosomes)
- Probability in genetics: product rule (independent events); sum rule (mutually exclusive events); applying probability to predict cross outcomes
- Chi-square test: comparing observed to expected ratios; determining whether deviations from expected are due to chance
- Pedigree analysis: autosomal dominant, autosomal recessive, X-linked dominant, X-linked recessive patterns; determining genotypes of individuals from pedigree

**Key vocabulary:** true-breeding, monohybrid cross, dihybrid cross, dominant, recessive, genotype, phenotype, homozygous, heterozygous, F1, F2, testcross, Law of Segregation, Law of Independent Assortment, pedigree, chi-square test

**Common misconceptions:**
- "Dominant means more common in the population" — dominance is about phenotypic expression, not frequency
- "The 3:1 ratio is exact" — it is a probability; small sample sizes will deviate significantly
- "Recessive alleles disappear over generations" — Hardy-Weinberg (Chapter 10) shows they are maintained

**What the student builds:**
`02-mendel-experiments.html` — virtual Mendel experiment simulator. Controls: trait selector (choose from 7 pea traits: seed color, seed shape, pod color, pod shape, flower color, flower position, plant height); cross type (monohybrid, dihybrid); number of offspring slider (10 to 10,000). Display: parent phenotypes and genotypes; F1 cross setup; F2 offspring generated stochastically (each offspring independently assigned by probability); bar chart of phenotype counts; expected vs. observed ratio comparison; chi-square value calculated with p-value; students run N=20 and see variation; run N=1000 and see convergence to expected ratio.

**Key references for research agent:**
- OpenStax Biology Chapter 12 (Mendel's Experiments and Heredity)
- Mendel's original paper (1866): Versuche über Pflanzenhybriden — translation and commentary
- Mendel's luck: all 7 traits happened to be on different chromosomes — Fisher's analysis
- Rediscovery of Mendel: de Vries, Correns, Tschermak (1900)
- Chi-square test in genetics: Fisher's application to Mendel's data (and the controversy)

**Bridge to Chapter 3:** Mendel's laws explain simple single-gene inheritance. Chapter 3 examines the extensions and complications — incomplete dominance, codominance, multiple alleles, polygenic traits, and gene interactions.

---

### CHAPTER 03 — Extensions of Mendelian Genetics
**Filename:** `03-extensions-mendelian-genetics.md`
**Arc position:** Act One, Chapter 3
**Source:** `16-modern-understandings-of-inheritance.md`

**One-line:** Students learn the patterns of inheritance that extend beyond Mendel's simple dominant-recessive model — incomplete dominance, codominance, multiple alleles, polygenic traits, epistasis, and linkage — and build a trait distribution simulator showing how polygenic inheritance produces continuous variation.

**Chapter description:**
Most traits do not follow simple Mendelian ratios — not because Mendel was wrong, but because most traits are controlled by multiple genes with multiple alleles, and because genes on the same chromosome violate independent assortment. This chapter extends the Mendelian framework to cover the full range of inheritance patterns observed in real organisms, with emphasis on how each extension modifies the expected phenotypic ratios and why. The chapter also introduces linkage and recombination mapping — using the frequency of recombinant offspring to estimate the physical distance between genes, a technique that predated DNA sequencing and remains conceptually important.

**Core concepts:**
- Incomplete dominance: heterozygotes have an intermediate phenotype (e.g., red × white → pink); ratio 1:2:1 phenotype in F2
- Codominance: both alleles expressed simultaneously in heterozygotes (e.g., AB blood type); distinguishing from incomplete dominance
- Multiple alleles: more than two alleles exist in the population for a locus (e.g., ABO blood group — I^A, I^B, i); individual still has only two alleles
- ABO blood types: complete system; I^A and I^B codominant; i recessive; antigens and antibodies; transfusion compatibility
- Pleiotropy: one gene affects multiple phenotypic traits (e.g., sickle cell anemia — hemoglobin structure affects RBC shape, oxygen transport, susceptibility to malaria)
- Epistasis: alleles at one locus mask the expression of alleles at another locus; modified 9:3:3:1 ratios; types (dominant, recessive, duplicate dominant)
- Polygenic inheritance: multiple genes each contribute to a continuous quantitative trait; bell-curve distribution; skin color, height, intelligence; QTL mapping
- Environmental effects on phenotype: norm of reaction; phenotypic plasticity; temperature-sensitive alleles (Himalayan rabbit coat color); the genotype-phenotype distinction
- Linkage: genes on the same chromosome tend to be inherited together; violates independent assortment
  - Parental types: more common; recombinant types: less common
  - Recombination frequency = (recombinants / total offspring) × 100; 1 centimorgan (cM) = 1% recombination
  - Genetic maps: relative distances between linked genes; not physical distances
- Sex-linked inheritance: X-linked recessive (color blindness, hemophilia); X-linked dominant; Y-linked; sex-influenced traits
- Maternal effect genes: cytoplasmic inheritance from mother; Drosophila bicoid gradient (preview of gene regulation)

**Key vocabulary:** incomplete dominance, codominance, multiple alleles, ABO blood group, pleiotropy, epistasis, polygenic inheritance, quantitative trait, norm of reaction, linkage, recombination frequency, centimorgan, genetic map, sex-linked, maternal effect

**What the student builds:**
`03-polygenic-traits.html` — polygenic inheritance and trait distribution simulator. Controls: number of contributing loci (1–8); allele effect size slider; environmental variance slider; population size (100–10,000). Display: distribution of phenotypes shown as a histogram; with 1 locus: shows discrete Mendelian classes; with 2 loci: 5 phenotypic classes; with 8 loci: approaches normal distribution; environmental variance adds noise, broadening the distribution; ABO blood type panel: show all possible genotypes and their phenotypes; linkage panel: show parental vs. recombinant class frequencies for two linked genes at different map distances.

**Key references for research agent:**
- OpenStax Biology Chapter 13 (Modern Understandings of Inheritance)
- ABO blood group history: Landsteiner (1900) Nobel lecture
- Sickle cell and malaria: Allison (1954) *British Medical Journal*
- Polygenic inheritance: Nilsson-Ehle (1909) wheat color experiment
- Linkage mapping: Morgan (1911); Sturtevant (1913) first genetic map

**Bridge to Chapter 4:** Genes are inherited according to these patterns. Chapter 4 examines what genes actually are at the molecular level — the structure of DNA and how it is replicated.

---

### CHAPTER 04 — DNA Structure, Replication, and Repair
**Filename:** `04-dna-structure-replication-repair.md`
**Arc position:** Act One, Chapter 4
**Source:** `17-dna-structure-and-function.md`

**One-line:** Students learn the double helix structure of DNA, understand the semiconservative mechanism of DNA replication, and build a DNA replication fork simulator showing leading and lagging strand synthesis.

**Chapter description:**
DNA is the molecule that bridges classical genetics (Mendel's abstract "factors") and molecular biology (specific sequences of nucleotides). This chapter covers the historical experiments that identified DNA as the genetic material (Griffith, Avery, Hershey-Chase), the structure of the double helix (Watson, Crick, Franklin, Wilkins), the semiconservative mechanism of replication (Meselson-Stahl), and the enzymatic machinery of DNA replication (helicase, primase, DNA polymerase, ligase). DNA repair is introduced here because it is mechanistically connected to replication — the same enzymes participate in both — and because repair failures are the link to mutation and cancer (Chapter 8). The simulation shows a replication fork advancing with all enzymes animated in their correct roles.

**Core concepts:**
- DNA as the genetic material:
  - Griffith (1928): transformation — heat-killed smooth bacteria transformed rough bacteria into smooth
  - Avery, MacLeod, McCarty (1944): the transforming principle is DNA, not protein
  - Hershey and Chase (1952): phage infection — DNA (not protein) enters bacteria and directs phage production
- DNA structure (Watson and Crick, 1953):
  - Nucleotide: deoxyribose sugar + phosphate + nitrogenous base (A, T, G, C)
  - Base pairing rules: A-T (2 hydrogen bonds); G-C (3 hydrogen bonds); complementary and antiparallel strands
  - Double helix: major and minor grooves; B-form DNA; 10 bp per turn; 3.4 nm per turn
  - Chargaff's rules: [A] = [T] and [G] = [C]; provided clue to base pairing
  - Franklin's X-ray crystallography (Photo 51): provided critical structural data
- DNA replication:
  - Semiconservative model: each daughter molecule has one parental and one new strand (Meselson-Stahl 1958)
  - Origin of replication: bacteria — single origin; eukaryotes — multiple origins; ORC complex
  - Replication fork: bidirectional; helicase unwinds; SSB proteins stabilize; topoisomerase relieves torsional stress ahead of fork
  - RNA primer: primase synthesizes short RNA primer (~10 nt); required because DNA polymerase cannot initiate
  - Leading strand: synthesized continuously in 5'→3' direction toward fork
  - Lagging strand: synthesized discontinuously away from fork; Okazaki fragments; RNA primers removed by RNase H; gaps filled by DNA pol I; ligase seals nicks
  - DNA polymerase III (prokaryotes) / Pol δ and ε (eukaryotes): high fidelity; 3'→5' proofreading exonuclease; ~1 error per 10⁷ bases
- DNA repair mechanisms:
  - Mismatch repair: recognizes and corrects replication errors after the fact; MSH and MLH proteins; HNPCC (Lynch syndrome) when mutated
  - Base excision repair: removes damaged single bases; AP endonuclease
  - Nucleotide excision repair: removes bulky lesions (UV-induced thymine dimers); xeroderma pigmentosum when defective
  - Double-strand break repair: homologous recombination (high fidelity, uses sister chromatid); NHEJ (error-prone but fast)
  - BRCA1/BRCA2: HR repair of double-strand breaks; breast and ovarian cancer risk when mutated

**Key vocabulary:** nucleotide, base pairing, antiparallel, double helix, Chargaff's rules, semiconservative replication, origin of replication, replication fork, helicase, primase, DNA polymerase, leading strand, lagging strand, Okazaki fragment, proofreading, mismatch repair, nucleotide excision repair, double-strand break repair, BRCA

**What the student builds:**
`04-replication-fork.html` — DNA replication fork simulator. Controls: replication speed slider; proofreading fidelity toggle (on/off); repair mechanism selector (mismatch, NER, DSB). Display: animated replication fork showing: parental strand unwinding (helicase shown as a wedge); SSB proteins binding; RNA primer laid down by primase; DNA polymerase extending the leading strand continuously; lagging strand: Okazaki fragments shown forming in the opposite direction; primer removal and gap filling; ligase sealing; error introduced (mismatch shown as a color change) → repair pathway activated → error corrected; error rate counter with and without proofreading.

**Key references for research agent:**
- OpenStax Biology Chapter 14 (DNA Structure and Function)
- Watson and Crick (1953) *Nature*; Franklin's Photo 51 history
- Meselson and Stahl (1958) *PNAS* — the most beautiful experiment in biology
- Hershey and Chase (1952) *Journal of General Physiology*
- DNA polymerase fidelity: Kunkel (2004) *Journal of Biological Chemistry*
- BRCA1/2 and homologous recombination: Moynahan and Jasin (2010) *Nature Reviews Molecular Cell Biology*

**Bridge to Chapter 5:** DNA is replicated faithfully. Chapter 5 examines how the information in DNA is used — the two-step process of transcription (DNA → RNA) and translation (RNA → protein).

---

### CHAPTER 05 — From Gene to Protein: Transcription and Translation
**Filename:** `05-gene-to-protein.md`
**Arc position:** Act One, Chapter 5
**Source:** `18-genes-and-proteins.md`

**One-line:** Students learn how genetic information flows from DNA to RNA to protein through transcription and translation, understand the genetic code, and build a translation simulator showing ribosome movement along mRNA.

**Chapter description:**
The central dogma of molecular biology — DNA → RNA → protein — is the most fundamental information-flow principle in biology. This chapter covers transcription (how RNA polymerase reads the DNA template and produces a complementary RNA), RNA processing in eukaryotes (5' cap, poly-A tail, splicing of introns), the genetic code (the triplet codon system that maps nucleotide sequences to amino acid sequences), and translation (how ribosomes decode mRNA with the help of tRNA and aminoacyl-tRNA synthetases). The genetic code's properties — redundancy, non-overlapping, universal — are discussed as molecular fossils of early life. The simulation shows a ribosome moving codon by codon along an mRNA, with tRNAs arriving and peptide bonds forming.

**Core concepts:**
- The central dogma: DNA → (transcription) → RNA → (translation) → protein; reverse transcription (retroviruses) as a legitimate exception
- Transcription:
  - RNA polymerase: reads template strand 3'→5'; produces RNA 5'→3'; no primer needed; less accurate than DNA polymerase
  - Promoter: DNA sequence where RNA polymerase binds; TATA box in eukaryotes; -10 and -35 in prokaryotes
  - Transcription factors: required for eukaryotic RNAP II binding; general vs. specific transcription factors
  - Termination: Rho-dependent and Rho-independent (prokaryotes); polyadenylation signal (eukaryotes)
  - Three RNA polymerases in eukaryotes: Pol I (rRNA), Pol II (mRNA), Pol III (tRNA, 5S rRNA)
- RNA processing (eukaryotes only):
  - 5' 7-methylguanosine cap: added cotranscriptionally; protects mRNA from degradation; needed for ribosome binding
  - 3' poly-A tail: 100–250 adenines added post-transcriptionally; stability and export
  - RNA splicing: introns removed; exons joined; spliceosome (snRNPs); alternative splicing — one gene, many proteins
  - Pre-mRNA → mature mRNA: processed in nucleus; exported to cytoplasm
- The genetic code:
  - Triplet codons: 3 nucleotides code for one amino acid; 4³ = 64 codons for 20 amino acids
  - Redundancy (degeneracy): most amino acids encoded by multiple codons; third position wobble
  - Start codon: AUG (methionine); initiation signal
  - Stop codons: UAA, UAG, UGA; no corresponding tRNA
  - Non-overlapping, comma-free; universal (nearly — minor exceptions in mitochondria)
  - Cracking the code: Nirenberg, Khorana, Holley Nobel 1968
- Translation:
  - Ribosomes: large (50S/60S) + small (30S/40S) subunits; rRNA catalyzes peptide bond formation (ribozyme); A, P, E sites
  - tRNA: adaptor molecule; anticodon recognizes codon; aminoacyl-tRNA synthetases charge tRNA with correct amino acid (the real genetic code readers)
  - Initiation: small subunit binds mRNA; initiator tRNA (Met-tRNA) binds start codon; large subunit joins
  - Elongation: aminoacyl-tRNA binds A site → peptide bond (transpeptidation) → translocation (ribosome moves 3 nt) → repeat; EF-Tu and EF-G in prokaryotes
  - Termination: stop codon in A site → release factor → polypeptide released; ribosome disassembles
  - Polysomes: multiple ribosomes on one mRNA simultaneously

**Key vocabulary:** central dogma, transcription, translation, RNA polymerase, promoter, TATA box, transcription factor, 5' cap, poly-A tail, RNA splicing, intron, exon, spliceosome, genetic code, codon, anticodon, tRNA, aminoacyl-tRNA synthetase, ribosome, A/P/E sites, polysome

**What the student builds:**
`05-translation-simulator.html` — ribosome translation simulator. Controls: mRNA sequence input (or random sequence generator); speed slider; show/hide molecular details toggle. Display: mRNA sequence shown with codons color-coded; ribosome shown as two subunits at the start codon; animation: tRNA with correct anticodon enters A site; peptide bond forms (bond shown forming between P-site amino acid chain and A-site amino acid); translocation (ribosome shifts 3 nt, tRNA moves E→P→A); growing polypeptide chain shown; stop codon: release factor shown, polypeptide released; amino acid sequence decoded and displayed; codon table shown for reference.

**Key references for research agent:**
- OpenStax Biology Chapter 15 (Genes and Proteins)
- Cracking the genetic code: Nirenberg and Matthaei (1961); Nirenberg Nobel lecture (1968)
- Ribosome as ribozyme: Steitz and Moore Nobel lecture (2009)
- Alternative splicing: Pan et al. (2008) *Nature Genetics* — 95% of human multi-exon genes alternatively spliced
- tRNA structure: Holley Nobel lecture (1968)
- Central dogma: Crick (1970) *Nature*

**Bridge to Chapter 6:** Genes are transcribed and translated. Chapter 6 examines how gene expression is regulated — how cells decide which genes to turn on and off, when, and how much.

---

### CHAPTER 06 — Gene Expression and Regulation
**Filename:** `06-gene-expression-regulation.md`
**Arc position:** Act One, Chapter 6
**Source:** `19-gene-expression.md`

**One-line:** Students learn how gene expression is regulated at multiple levels from transcription to translation, understand operons in prokaryotes and enhancer-based regulation in eukaryotes, and build a gene regulatory network simulator showing how feedback loops control expression.

**Chapter description:**
Every cell in a human body has the same genome, yet a neuron and a muscle cell look and function completely differently. The difference is gene regulation — which genes are expressed, when, where, and at what level. This chapter covers prokaryotic gene regulation (the lac operon as the model system), eukaryotic transcriptional regulation (enhancers, transcription factors, chromatin remodeling), post-transcriptional regulation (RNA stability, miRNA), and epigenetic regulation (DNA methylation, histone modifications). The lac operon is the pedagogical masterpiece of molecular biology — a simple genetic switch that responds to environmental conditions through elegant molecular logic. The simulation models the lac operon as a regulatory circuit that students can perturb.

**Core concepts:**
- Why gene regulation matters: differential gene expression underlies cell differentiation, development, and responses to environment
- Prokaryotic gene regulation — the lac operon:
  - Operon: cluster of functionally related genes under shared promoter control; lacZ, lacY, lacA
  - lac repressor: binds operator and blocks transcription; allolactose (inducer) binds repressor → conformational change → repressor releases operator → transcription ON
  - Negative control (repressor): default OFF; inducer removes repressor
  - Positive control (CAP/CRP): cAMP-CAP complex binds CAP site → increases transcription; glucose ↓ → cAMP ↑ → CAP active; catabolite repression
  - Combined control: full induction requires BOTH lactose present (removes repressor) AND glucose absent (activates CAP)
  - trp operon: opposite logic; default ON; tryptophan (co-repressor) binds repressor → repressor active → transcription OFF; attenuation as additional control
- Eukaryotic transcriptional regulation:
  - Enhancers and silencers: cis-regulatory elements; can be thousands of bp from promoter; work in either orientation; tissue-specific expression
  - Transcription factors: sequence-specific DNA-binding proteins; activators and repressors; combinatorial control
  - Mediator complex: bridge between enhancer-bound TFs and the basal transcription machinery
  - Chromatin remodeling: nucleosomes block DNA access; SWI/SNF complex repositions nucleosomes; HATs (acetylation → open) and HDACs (deacetylation → closed)
- Epigenetic regulation:
  - DNA methylation: 5-methylcytosine at CpG sites; associated with gene silencing; heritable through cell division; X-chromosome inactivation; genomic imprinting
  - Histone modifications: acetylation, methylation, phosphorylation, ubiquitination of histone tails; histone code hypothesis; H3K4me3 (active) vs. H3K27me3 (silent)
- Post-transcriptional regulation:
  - mRNA stability: 5' cap and poly-A tail protect; AU-rich elements in 3' UTR → rapid degradation; half-lives from minutes to hours
  - miRNA: ~22 nt non-coding RNA; base pairs with 3' UTR of target mRNAs → translational repression or mRNA degradation; ~60% of human protein-coding genes regulated by miRNAs
  - siRNA: similar mechanism; used as experimental tool (RNAi) and therapeutic (e.g., inclisiran)
- Translational regulation: iron response element (IRE) and IRP — translation of ferritin mRNA regulated by iron levels

**Key vocabulary:** operon, lac operon, repressor, operator, inducer, allolactose, CAP/CRP, catabolite repression, trp operon, enhancer, silencer, transcription factor, chromatin remodeling, epigenetics, DNA methylation, histone modification, miRNA, siRNA, RNAi

**What the student builds:**
`06-lac-operon.html` — lac operon regulatory circuit simulator. Controls: lactose concentration slider (0 → high); glucose concentration slider (0 → high); toggle between wild-type and mutant versions (constitutive, repressor-negative, operator-negative). Display: molecular diagram of the operon showing promoter, CAP site, operator, lacZ/Y/A genes; repressor shown bound/unbound to operator based on allolactose level; CAP-cAMP shown bound/unbound based on glucose level; transcription rate shown as a gauge and as mRNA production rate; β-galactosidase activity shown (downstream of lacZ expression); truth table showing all four combinations of lactose/glucose and the resulting transcription state.

**Key references for research agent:**
- OpenStax Biology Chapter 16 (Gene Expression)
- lac operon: Jacob and Monod (1961) *Journal of Molecular Biology*; Nobel lecture 1965
- Enhancers: Banerji et al. (1981) *Cell*
- miRNA discovery: Lee et al. (1993) *Cell*; Fire and Mello Nobel 2006
- Epigenetics: Bird (2007) *Nature* review
- X-chromosome inactivation: Lyon (1961) *Nature*

**Bridge to Chapter 7:** Gene expression can be regulated. Chapter 7 examines how molecular tools allow us to read, copy, edit, and reprogram genetic information — biotechnology and genomics.

---

### CHAPTER 07 — Biotechnology and Genomics
**Filename:** `07-biotechnology-genomics.md`
**Arc position:** Act One, Chapter 7
**Source:** `20-biotechnology-and-genomics.md`

**One-line:** Students learn the molecular tools of modern biotechnology — restriction enzymes, PCR, gel electrophoresis, cloning, CRISPR, DNA sequencing — and understand how genome-scale data is analyzed and applied.

**Chapter description:**
Biotechnology is applied molecular genetics — using the cell's own molecular machinery to read, copy, cut, paste, and edit DNA. This chapter covers the toolkit chronologically and conceptually: restriction enzymes (1970s) → gel electrophoresis → Southern blotting → PCR (1983) → recombinant DNA and cloning → DNA sequencing (Sanger 1977 → Next-Gen sequencing 2005) → CRISPR-Cas9 (2012). Each tool is motivated by the problem it solves. Genomics is the application of these tools at scale: whole-genome sequencing, comparative genomics, functional genomics (RNA-seq, ChIP-seq). The clinical and agricultural applications — insulin production, GM crops, forensic DNA analysis, prenatal genetic testing, CRISPR therapeutics — connect molecular biology to real-world impact.

**Core concepts:**
- Restriction enzymes: type II; recognize specific palindromic sequences (4–8 bp); cut at or near recognition site; sticky ends vs. blunt ends; EcoRI, HindIII, BamHI as examples; biological role (restriction-modification system)
- Gel electrophoresis: separate DNA fragments by size; agarose gel; ethidium bromide (or safer alternatives); DNA ladder; Southern blotting: transfer to membrane + probe hybridization
- PCR (polymerase chain reaction):
  - Denaturation (94°C) → annealing (50–65°C) → extension (72°C) → repeat; exponential amplification; 2ⁿ copies after n cycles
  - Requirements: template, two primers (flanking target), dNTPs, Taq polymerase (thermostable), thermal cycler
  - Applications: diagnosis (COVID tests), forensics, cloning, sequencing
  - RT-PCR: reverse transcription + PCR; detect RNA (gene expression, RNA viruses)
  - Real-time PCR (qPCR): quantify gene expression
- DNA cloning: insert DNA into vector (plasmid or bacteriophage); transform into host bacteria; select for colonies containing insert; screen for correct insert
  - Restriction digest + ligation; or Gibson assembly
  - Expression vectors: promoter + insert → protein production; insulin, growth hormone, erythropoietin
- DNA sequencing:
  - Sanger sequencing: chain-terminating ddNTPs; reads ~800 bp; gold standard for single-gene sequencing
  - Next-generation sequencing (NGS): massively parallel; billions of short reads; whole-genome sequencing in days
  - Third-generation sequencing (PacBio, Oxford Nanopore): long reads (>10 kb); real-time; direct detection
- CRISPR-Cas9:
  - Guide RNA directs Cas9 to specific DNA sequence; Cas9 creates double-strand break; repair by NHEJ (disruption) or HDR (correction)
  - Applications: gene knockout, gene correction, base editing, prime editing, CRISPRi/CRISPRa
  - Doudna and Charpentier Nobel 2020
  - Ethical issues: germline editing (He Jiankui case); somatic vs. germline distinction
- Genomics and bioinformatics:
  - Whole-genome sequencing: Human Genome Project (2003); ~3.2 billion bp; ~20,000 protein-coding genes
  - Comparative genomics: synteny; identifying conserved regions; inferring gene function
  - RNA-seq: quantify gene expression transcriptome-wide; differential expression analysis
  - GWAS: genome-wide association study; SNPs associated with traits/diseases

**Key vocabulary:** restriction enzyme, palindrome, sticky ends, PCR, primer, Taq polymerase, thermal cycler, RT-PCR, qPCR, DNA cloning, expression vector, Sanger sequencing, next-generation sequencing, CRISPR-Cas9, guide RNA, HDR, NHEJ, genomics, RNA-seq, GWAS

**What the student builds:**
`07-pcr-simulator.html` — PCR and gel electrophoresis simulator. Controls: template sequence (choose a target gene or enter custom); primer design interface (drag to select primer binding sites); number of cycles slider (1–40); annealing temperature slider (shows primer efficiency). Display: animated PCR cycles — denaturation (strands separate), annealing (primers bind, shown as colored bars), extension (new strand synthesized); cycle count and copy number shown (exponential growth graph); after completion, virtual gel electrophoresis: bands appear at correct sizes; DNA ladder shown for comparison; students vary primer positions to amplify different-sized fragments.

**Key references for research agent:**
- OpenStax Biology Chapter 17 (Biotechnology and Genomics)
- PCR: Mullis Nobel lecture (1993)
- CRISPR: Doudna and Charpentier Nobel lecture (2020); He Jiankui case ethics
- Human Genome Project: Lander et al. (2001) *Nature*; Venter et al. (2001) *Science*
- Next-generation sequencing: Mardis (2008) *Annual Review of Genomics and Human Genetics*
- CRISPR therapeutics: Frangoul et al. (2021) *New England Journal of Medicine* (sickle cell)

**Bridge to Chapter 8:** Biotechnology allows us to read and edit genomes. Chapter 8 examines what happens when the genome changes without our intervention — mutation, DNA damage, and the cancer that can result.

---

### CHAPTER 08 — Mutation, DNA Damage, and Cancer Genetics
**Filename:** `08-mutation-dna-damage-cancer.md`
**Arc position:** Act Two — the bridge chapter
**Source:** New (no direct source chapter; synthesizes Chapters 4–7 and bridges to evolution)

**One-line:** Students learn the types and causes of mutation, understand how DNA damage leads to cancer through multi-step carcinogenesis, and build a mutation accumulation simulator showing how cancer evolves as a somatic evolutionary process.

**Chapter description:**
Mutation is the hinge between genetics and evolution. In the genetics context (Chapters 1–7), mutation is an error — a change in DNA sequence that may impair gene function and cause disease. In the evolutionary context (Chapters 9–14), mutation is the ultimate source of all genetic variation — without it, evolution would be impossible. This bridge chapter covers both faces: the molecular mechanisms that cause mutation, how mutations accumulate to cause cancer (somatic evolution), and how mutation rate and type differ across species and contexts. Cancer is introduced here as the evolutionary process it fundamentally is — natural selection acting on somatic cells with heritable variation in growth rate. This connects to the Cancer +1 series for students who want to go deeper.

**Core concepts:**
- Mutation types:
  - Point mutations: substitutions (transitions — purine↔purine or pyrimidine↔pyrimidine; transversions — purine↔pyrimidine); insertions and deletions (indels)
  - Frameshift mutations: insertions or deletions not in multiples of 3; shift reading frame; usually severe
  - Synonymous (silent) vs. nonsynonymous (missense) vs. nonsense (stop codon created) mutations
  - Chromosomal mutations: deletion, duplication, inversion, translocation; aneuploidy (from meiotic errors)
- Causes of mutation:
  - Spontaneous: replication errors (~1 per 10⁹ bases despite proofreading); tautomeric shifts; depurination; deamination of cytosine → uracil
  - Induced (mutagens): chemical (alkylating agents, base analogs, intercalating agents); physical (UV → thymine dimers; ionizing radiation → DSBs); biological (transposons, viral insertion)
  - Ames test: using bacteria to screen for chemical mutagens
- Mutation rate: varies enormously across organisms; RNA viruses highest (no proofreading); bacteria ~10⁻⁹ per bp per replication; humans ~10⁻⁸ per bp per generation; mutation rate × genome size = ~100 new mutations per human per generation
- DNA repair (recap from Ch 4, expanded):
  - When repair fails: mutations fixed in genome; when repair fails in dividing cells → cancer
  - Repair deficiency diseases: xeroderma pigmentosum (NER failure); Lynch syndrome (MMR failure); BRCA mutations (HR failure)
- Cancer as somatic evolution:
  - Somatic mutations accumulate in dividing cells; most are neutral; rare ones affect growth regulation
  - Two-hit hypothesis (Knudson): tumor suppressors require loss of both alleles; first hit (germline or somatic) + second hit (somatic) → cancer
  - Proto-oncogenes → oncogenes: gain-of-function mutations; one mutant allele sufficient; RAS, MYC, EGFR
  - Tumor suppressor genes: loss-of-function mutations; p53 (guardian of the genome); Rb; APC
  - Multi-step carcinogenesis: colorectal cancer model (Vogelstein) — APC → RAS → SMAD4 → p53; ~5–7 driver mutations over decades
  - Mutational signatures: patterns of mutations reveal underlying causes; APOBEC signature; tobacco signature; UV signature; used in cancer diagnosis
  - Clonal evolution: cancer cells compete; selection favors faster-growing, more invasive clones; same logic as population genetics (Chapter 10)
- Germline vs. somatic mutations: germline = inherited (affects all cells of offspring); somatic = acquired (affects only that cell lineage); cancer is always somatic (except rare hereditary syndromes)

**Key vocabulary:** point mutation, frameshift mutation, transition, transversion, silent mutation, missense mutation, nonsense mutation, mutagen, Ames test, mutation rate, two-hit hypothesis, proto-oncogene, oncogene, tumor suppressor gene, multi-step carcinogenesis, mutational signature, clonal evolution, somatic mutation, germline mutation

**What the student builds:**
`08-mutation-accumulation.html` — somatic mutation accumulation and cancer evolution simulator. Controls: cell division rate slider; mutation rate per division slider; selection coefficient for driver mutations slider; number of cell divisions (years of life) slider. Display: single cell at top; cells divide and accumulate mutations (shown as colored marks on cell icons); neutral mutations accumulate; when a driver mutation occurs (rare), that clone expands faster (shown visually); after N driver mutations, "cancer" threshold crossed; time to cancer shown as a distribution across many simulation runs; vary mutation rate (smoking → higher rate; repair deficiency → higher rate) and watch time to cancer decrease.

**Key references for research agent:**
- Two-hit hypothesis: Knudson (1971) *PNAS*
- Multi-step colorectal cancer: Fearon and Vogelstein (1990) *Cell*
- Mutational signatures: Alexandrov et al. (2013) *Nature*; COSMIC signatures database
- Cancer as evolution: Nowell (1976) *Science*; Greaves and Maley (2012) *Nature*
- Ames test: Ames et al. (1973) *PNAS*
- p53: Lane (1992) *Nature* "guardian of the genome"

**Bridge to Chapter 9:** Mutation is the source of variation. Chapter 9 examines how natural selection and other evolutionary forces sort that variation — the mechanisms that transform genetic variation into evolutionary change.

---

### CHAPTER 09 — Evolution and the Origin of Species
**Filename:** `09-evolution-origin-of-species.md`
**Arc position:** Act Three, Chapter 9
**Source:** `22-evolution-and-the-origin-of-species.md`

**One-line:** Students learn the evidence for evolution, understand Darwin's mechanism of natural selection, and build a natural selection simulator showing how fitness differences drive allele frequency change.

**Chapter description:**
Evolution by natural selection is the central organizing theory of biology — the framework that makes sense of everything from antibiotic resistance to the diversity of life. This chapter establishes the evidence for evolution (fossil record, comparative anatomy, biogeography, molecular evidence), Darwin's mechanism (natural selection requires heritable variation + differential fitness), and the modern synthesis that integrates Mendelian genetics with Darwinian selection. The simulation makes natural selection concrete and quantitative: students set selection coefficients and watch allele frequencies change generation by generation, discovering that even small fitness differences produce dramatic evolutionary change over time.

**Core concepts:**
- Evidence for evolution:
  - Fossil record: transitional forms (Tiktaalik — fish-tetrapod transition; Archaeopteryx — dinosaur-bird); stratigraphic succession; index fossils; molecular clocks
  - Comparative anatomy: homologous structures (same origin, different function — bat wing, whale flipper, human arm); analogous structures (convergent evolution — dolphin fin and shark fin); vestigial structures (human coccyx, whale pelvic bones)
  - Biogeography: distribution of species reflects evolutionary history; island biogeography; continental drift; Darwin's finches
  - Molecular evidence: DNA sequence similarity correlates with relatedness; universal genetic code; conserved genes (Hox genes, ribosomal RNA); endogenous retroviruses as shared markers
- Darwin's mechanism of natural selection:
  - Conditions required: heritable variation; variation affects fitness; differential reproduction
  - Artificial selection: domestication; plant and animal breeding; demonstrates selection works
  - Natural selection: environment is the selecting agent; fitness = reproductive success in that environment
  - Adaptation: evolved trait that increases fitness in current environment; not "purpose" — result of past selection
  - Fitness: relative reproductive success; not strength or health per se
- The modern evolutionary synthesis:
  - Combines Darwin's natural selection with Mendelian genetics and population genetics
  - Mutation provides raw variation; selection, drift, migration sort variation; speciation produces diversity
- Sources of evolutionary evidence today: comparative genomics; experimental evolution (LTEE — Lenski's E. coli 35+ years); ancient DNA; evo-devo

**Key vocabulary:** natural selection, fitness, adaptation, homologous structures, analogous structures, vestigial structures, transitional fossil, biogeography, molecular clock, modern synthesis, artificial selection, experimental evolution

**What the student builds:**
`09-natural-selection.html` — natural selection simulator. Controls: initial allele frequency p₀ slider (0.01–0.99); selection coefficient s slider (-1 to +1, where positive = A advantaged); dominance (dominant, recessive, codominant); number of generations slider (1–1000); population size (to show drift effects). Display: allele frequency p vs. generation number as a line chart; selection for dominant allele: fast initial increase; selection for recessive: slow until frequency high; heterozygote advantage (overdominance): stable equilibrium; directional selection sweeps allele to fixation or loss; overlay multiple runs with drift to show stochastic variation around deterministic expectation.

**Key references for research agent:**
- OpenStax Biology Chapter 18 (Evolution and the Origin of Species)
- Darwin (1859) *On the Origin of Species* — key passages
- Modern synthesis: Huxley (1942) *Evolution: The Modern Synthesis*
- Tiktaalik: Daeschler et al. (2006) *Nature*
- LTEE (Long-Term Evolution Experiment): Lenski et al. (1991); Blount et al. (2008) *PNAS*
- Endogenous retroviruses as evolution evidence: Lander et al. (2001) *Nature*

**Bridge to Chapter 10:** Natural selection is one mechanism of evolutionary change. Chapter 10 examines all the mechanisms — selection, genetic drift, gene flow, mutation, non-random mating — through the lens of population genetics.

---

### CHAPTER 10 — Population Genetics and Natural Selection
**Filename:** `10-population-genetics.md`
**Arc position:** Act Three, Chapter 10
**Source:** `23-the-evolution-of-populations.md` (population genetics sections)

**One-line:** Students learn the Hardy-Weinberg equilibrium as the null model of evolution, understand how selection, drift, gene flow, and mutation alter allele frequencies, and build a population genetics simulator showing all five forces simultaneously.

**Chapter description:**
Population genetics is the mathematical foundation of evolutionary biology — it quantifies exactly how allele frequencies change under the influence of evolutionary forces. The Hardy-Weinberg equilibrium is the key conceptual tool: it specifies what would happen if nothing were causing evolution. Any deviation from Hardy-Weinberg indicates that at least one evolutionary force is acting. This chapter covers the five conditions required for Hardy-Weinberg equilibrium and the five corresponding evolutionary forces that violate each condition, with special emphasis on genetic drift (random change in finite populations) and its consequences (founder effect, bottleneck effect) for small populations and conservation biology.

**Core concepts:**
- Hardy-Weinberg equilibrium: allele and genotype frequencies remain constant across generations if:
  - Very large (effectively infinite) population (no genetic drift)
  - Random mating (no sexual selection, no inbreeding)
  - No mutation (or equal rates)
  - No gene flow (closed population)
  - No natural selection (all genotypes equally fit)
  - Equations: p + q = 1; p² + 2pq + q² = 1 (for two alleles)
  - HWE as null hypothesis: test whether observed genotype frequencies match expected; χ² test
- Microevolution: change in allele frequency in a population over time
- Genetic drift: random fluctuations in allele frequency; stronger in small populations; can fix or eliminate alleles by chance
  - Founder effect: small founding population; reduced genetic diversity; high frequency of rare alleles; Amish (Ellis-van Creveld syndrome); Afrikaner (Huntington's disease)
  - Bottleneck effect: severe population reduction; loss of genetic diversity; cheetah (near extinction ~10,000 years ago); northern elephant seal
  - Effective population size (Ne): the size of an ideal population that would lose genetic diversity at the same rate
- Natural selection modes:
  - Directional selection: one extreme phenotype favored; shifts mean; antibiotic resistance; industrial melanism (peppered moth)
  - Stabilizing selection: intermediate phenotype favored; reduces variance; human birth weight
  - Disruptive selection: two extreme phenotypes favored; increases variance; can lead to speciation; African seedcracker beak size
  - Balancing selection: maintains multiple alleles; heterozygote advantage (sickle cell/malaria); frequency-dependent selection (self-incompatibility in plants)
- Gene flow: movement of alleles between populations (migration); homogenizes allele frequencies between populations; can introduce new alleles; prevents local adaptation
- Mutation: ultimate source of new alleles; very low rate per locus; important over long time scales; maintains variation by counteracting fixation by drift
- Non-random mating: inbreeding (increases homozygosity; exposes recessive alleles; inbreeding depression); sexual selection (intersexual and intrasexual)
- Measuring genetic diversity: heterozygosity (observed and expected); FST (genetic differentiation between populations)

**Key vocabulary:** Hardy-Weinberg equilibrium, microevolution, genetic drift, founder effect, bottleneck effect, effective population size, directional selection, stabilizing selection, disruptive selection, balancing selection, heterozygote advantage, gene flow, inbreeding, inbreeding depression, FST, heterozygosity

**What the student builds:**
`10-population-genetics.html` — Wright-Fisher population genetics simulator. Controls: population size N (10–10,000); initial allele frequency p₀; selection coefficient s; dominance h; migration rate m; mutation rate μ; number of generations; number of replicate populations to run simultaneously. Display: allele frequency p vs. generation for all replicates shown as colored lines; mean trajectory shown as thick black line; theoretical deterministic expectation shown as dashed line; fixation probability and time to fixation shown; students compare large vs. small N to see drift; add selection and see drift overcome; founder effect panel: show a small subset of starting alleles being sampled for a new colony.

**Key references for research agent:**
- OpenStax Biology Chapter 19 (The Evolution of Populations)
- Hardy-Weinberg: Hardy (1908) *Science*; Weinberg (1908)
- Founder effect in human populations: Cavalli-Sforza and Bodmer *The Genetics of Human Populations*
- Cheetah bottleneck: O'Brien et al. (1985) *Science*
- Peppered moth: Cook and Saccheri (2013) *Heredity* — modern reanalysis
- Balancing selection: Charlesworth (2006) *PLOS Genetics*

**Bridge to Chapter 11:** Population genetics explains how allele frequencies change within species. Chapter 11 examines how those changes accumulate to produce new species — the process of speciation.

---

### CHAPTER 11 — Speciation
**Filename:** `11-speciation.md`
**Arc position:** Act Three, Chapter 11
**Source:** `23-the-evolution-of-populations.md` (speciation sections)

**One-line:** Students learn how reproductive isolation evolves to produce new species, compare allopatric and sympatric speciation mechanisms, and build a speciation simulator showing how geographic isolation and selection drive divergence.

**Chapter description:**
Speciation is evolution's product — the multiplication of lineages that generates biodiversity. This chapter covers the biological species concept and its limitations, the mechanisms of reproductive isolation (prezygotic and postzygotic), allopatric speciation (geographic isolation → independent evolution → reproductive isolation), and sympatric speciation (reproductive isolation evolving without geographic separation). The case studies are vivid: cichlid fish radiation in African rift lakes (>1,000 species from a single ancestor in ~100,000 years); Apple maggot fly speciation in progress; polyploidy in plants (instant speciation). The simulation shows a population splitting into two isolated subpopulations, accumulating genetic and phenotypic differences, and testing whether reproductive isolation has evolved.

**Core concepts:**
- Species concepts:
  - Biological species concept (Mayr): groups of actually or potentially interbreeding natural populations that are reproductively isolated from other groups; most widely used; fails for asexual organisms, fossil species, hybridizing species
  - Morphological species concept: species defined by morphological characters; practical for fossils and bacteria
  - Phylogenetic/lineage species concept: smallest monophyletic group; consistent with cladistics
- Reproductive isolation — prevents gene flow between incipient species:
  - Prezygotic barriers: habitat isolation (different microhabitats), temporal isolation (different breeding times), behavioral isolation (courtship signals), mechanical isolation (incompatible morphology), gametic isolation (sperm-egg incompatibility)
  - Postzygotic barriers: hybrid inviability, hybrid sterility (mule — horse × donkey), hybrid breakdown (F2 sterile)
- Allopatric speciation: geographic barrier divides population → independent evolution → reproductive isolation evolves → if populations reunite, may or may not interbreed
  - Vicariance: habitat change divides existing range
  - Dispersal: colonization of new habitat
  - Examples: Darwin's finches (geographic isolation on different islands); squirrels on opposite rims of Grand Canyon
- Sympatric speciation: reproductive isolation evolves without geographic separation
  - Polyploidy: chromosome number doubles → immediate reproductive isolation from diploid parents; most common in plants; allopolyploidy (hybrid + polyploidy) — wheat, cotton, strawberry
  - Ecological speciation: divergent natural selection in same habitat; apple maggot fly (host race formation on hawthorn and apple)
  - Sexual selection: rapid divergence in mate recognition systems; cichlid fish color patterns
- Hybrid zones: areas where two species interbreed; can lead to reinforcement (selection strengthens isolation) or fusion (populations merge)
- Adaptive radiation: rapid speciation from a single ancestor into multiple niches; cichlids; Darwin's finches; Hawaiian honeycreepers; mammals after K-Pg extinction
- Rate of speciation: gradualism vs. punctuated equilibrium (Eldredge and Gould 1972)

**Key vocabulary:** biological species concept, reproductive isolation, prezygotic barrier, postzygotic barrier, allopatric speciation, sympatric speciation, polyploidy, allopolyploidy, adaptive radiation, hybrid zone, reinforcement, punctuated equilibrium, vicariance

**What the student builds:**
`11-speciation-simulator.html` — allopatric speciation simulator. Controls: initial population size; geographic barrier strength (probability of gene flow between populations); selection coefficients in each environment (can be same or different); mutation rate; number of generations. Display: two subpopulations shown evolving independently; allele frequency trajectories for each population on same chart (diverging when selection differs, diverging randomly when only drift); genetic distance between populations shown increasing over time; reproductive isolation test: at selected time points, show what fraction of matings between populations would produce viable offspring (based on number of incompatible loci accumulated); polyploidy panel: show instant speciation from chromosome doubling.

**Key references for research agent:**
- OpenStax Biology Chapter 18 (speciation sections)
- Biological species concept: Mayr (1942) *Systematics and the Origin of Species*
- Cichlid radiation: Seehausen et al. (2008) *Nature Reviews Genetics*
- Apple maggot fly: Feder et al. (1994) *Evolution*
- Polyploidy in plants: Soltis et al. (2009) *Trends in Plant Science*
- Punctuated equilibrium: Eldredge and Gould (1972) in *Models in Paleobiology*

**Bridge to Chapter 12:** Speciation produces new lineages. Chapter 12 examines how those lineages are related to each other — the science of phylogenetics and reconstructing life's history.

---

### CHAPTER 12 — Phylogenetics and the History of Life
**Filename:** `12-phylogenetics-history-of-life.md`
**Arc position:** Act Three, Chapter 12
**Source:** `24-phylogenies-and-the-history-of-life.md` (phylogenetics sections)

**One-line:** Students learn how evolutionary relationships are inferred from molecular and morphological data, read and interpret phylogenetic trees, and build an interactive phylogenetic tree constructor showing how different data types affect tree topology.

**Chapter description:**
Phylogenetics is the scientific reconstruction of evolutionary relationships — the tree of life. This chapter covers how phylogenetic trees are built (parsimony, distance methods, maximum likelihood), how to read and interpret them (what a node means, what branch length means, why trees are rooted), the difference between homology and analogy (why similar structures don't always indicate close relationship), and the major lineages of life. The molecular revolution in phylogenetics — using DNA sequences to reconstruct evolutionary relationships — has fundamentally revised our understanding of life's history, with surprises like the close relationship between fungi and animals, the three-domain tree (Bacteria, Archaea, Eukarya), and the placement of whales within artiodactyls.

**Core concepts:**
- What a phylogenetic tree represents:
  - Nodes: common ancestors; internal nodes are hypothetical ancestors
  - Branches: lineages; branch length can represent time, number of changes, or be arbitrary
  - Tips (leaves): extant taxa or sampled sequences
  - Root: the common ancestor of all taxa in the tree
  - Clade (monophyletic group): an ancestor and all its descendants
  - Paraphyletic group: an ancestor and some but not all descendants (not valid in cladistics)
  - Polyphyletic group: taxa that do not share a recent common ancestor (never a natural group)
- Characters and homology:
  - Homologous characters: shared by common ancestry; synapomorphies (shared derived characters) — informative for phylogenetics
  - Analogous characters (homoplasy): convergent evolution; not informative for phylogenetics; need to distinguish from homology
  - Molecular characters: DNA and protein sequences; most widely used; mutational models available
- Phylogenetic inference methods:
  - Parsimony: minimize total number of evolutionary changes; computationally simple; may fail when evolution is non-parsimonious (long branch attraction)
  - Distance methods (UPGMA, neighbor-joining): convert pairwise distances into a tree; fast
  - Maximum likelihood: find the tree that maximizes the probability of the data given a model of evolution; statistically rigorous; computationally intensive
  - Bayesian inference: posterior probability of trees; incorporates prior information; increasingly standard
  - Bootstrap: resampling method to assess node support (>70% = moderate support; >95% = strong)
- Molecular clocks: rate of molecular evolution approximately constant → molecular divergence time ∝ calendar time; calibrated with fossil record; variation in rate (relaxed clocks)
- Major revisions from molecular phylogenetics:
  - Fungi + animals = Opisthokonta (closer to each other than to plants)
  - Whales within Artiodactyla (cetaceans + hippos = Whippomorpha)
  - Three-domain tree: Archaea more closely related to Eukarya than to Bacteria
  - Birds = avian dinosaurs; crocodilians are birds' closest living relatives among reptiles
- The history of life: major events and their timing — origin of life (~3.8 bya); LUCA; eukaryotes (~2 bya); multicellularity (~0.8 bya); Cambrian explosion (~540 mya); colonization of land; mass extinctions (5 major; K-Pg at 66 mya)

**Key vocabulary:** phylogenetic tree, node, branch, clade, monophyletic, paraphyletic, polyphyletic, synapomorphy, homoplasy, parsimony, maximum likelihood, Bayesian inference, bootstrap, molecular clock, convergent evolution, three-domain tree

**What the student builds:**
`12-phylogeny-builder.html` — interactive phylogenetic tree constructor. Controls: taxon selector (choose 5–8 organisms from a list including humans, chimps, mice, birds, frogs, sharks, sea urchins, yeast); character matrix toggle (morphological characters vs. molecular distance); tree-building method selector (parsimony, distance). Display: character matrix or distance matrix shown; tree built from the data shown as a cladogram; bootstrap values shown at nodes; alternative tree topologies shown with their parsimony scores; students change taxon set and watch tree rearrange; molecular clock panel: show divergence times estimated from branch lengths calibrated against fossil record.

**Key references for research agent:**
- OpenStax Biology Chapter 20 (Phylogenies and the History of Life)
- Phylogenetic methods: Felsenstein (2004) *Inferring Phylogenies*
- Whale evolution: Thewissen et al. (2007) *Nature*
- Three-domain tree: Woese et al. (1990) *PNAS*
- Cambrian explosion: Conway Morris (2006) review
- Bootstrap: Felsenstein (1985) *Evolution*

**Bridge to Chapter 13:** Phylogenetics reconstructs evolutionary history. Chapter 13 examines the molecular mechanisms underlying evolutionary change — how mutations in developmental genes produce morphological evolution.

---

### CHAPTER 13 — Molecular Evolution and Evo-Devo
**Filename:** `13-molecular-evolution-evo-devo.md`
**Arc position:** Act Three, Chapter 13
**Source:** `24-phylogenies-and-the-history-of-life.md` (molecular evolution sections) + New

**One-line:** Students learn how DNA sequences evolve over time, understand how changes in developmental gene regulation produce morphological diversity, and build a molecular evolution simulator showing neutral evolution and positive selection.

**Chapter description:**
Molecular evolution examines how DNA sequences change over evolutionary time — what kinds of changes are neutral, which are selected, and how the pattern of change reveals evolutionary history and function. Evo-devo (evolutionary developmental biology) examines how changes in developmental gene regulation — rather than in protein-coding sequences — explain much of morphological evolution. The Hox gene discovery was the paradigm shift: the same master regulatory genes control body patterning in flies and humans. Small changes in when, where, and how much these genes are expressed — not changes in the genes themselves — explain why a fly has segments and limbs in different places than a vertebrate. The simulation shows molecular evolution in real time — sequence divergence under neutral evolution and selective sweeps.

**Core concepts:**
- Molecular evolution rates:
  - Rate of neutral molecular evolution = mutation rate (Kimura's neutral theory)
  - Synonymous vs. nonsynonymous substitutions: dS (synonymous = neutral) vs. dN (nonsynonymous = under selection); dN/dS ratio: <1 (purifying selection), ~1 (neutral), >1 (positive selection)
  - Highly conserved genes: rRNA (used for universal phylogenetics); histones; HOX genes
  - Rapidly evolving genes: immune genes (arms race with pathogens); sperm and egg recognition proteins (sexual conflict); genes under positive selection
- Neutral theory of molecular evolution (Kimura 1968):
  - Most molecular variation is neutral — neither beneficial nor harmful
  - Molecular evolution rate ≈ mutation rate (independent of population size and environment)
  - Explains molecular clock; most protein polymorphism is neutral
  - Not all evolution is neutral: adaptive evolution occurs but may be a minority of changes
- Selective sweeps: positive selection drives beneficial allele to fixation; reduces diversity at linked loci; signature in genome data
- Transposable elements: selfish DNA; ~45% of human genome; Alu (primate-specific SINE); L1 (LINE); can create new regulatory elements and exons; source of evolutionary novelty
- Evo-devo (evolutionary developmental biology):
  - Hox genes: transcription factors controlling anterior-posterior body axis; highly conserved from flies to humans; collinear expression; mutations cause homeotic transformations; changes in Hox expression explain limb diversity
  - Toolkit genes: small set of signaling pathways (Wnt, Notch, Hedgehog, BMP, FGF) reused in different developmental contexts across animal phyla
  - Modularity: regulatory elements (enhancers) control gene expression in specific tissues and times; can evolve independently
  - Heterochrony: evolutionary change in timing of developmental events; neoteny (retention of juvenile features); human skull resembles juvenile chimp skull
  - Heterotopy: evolutionary change in location of developmental events
  - Regulatory evolution: most morphological evolution involves changes in gene regulation (cis-regulatory elements), not protein-coding sequences; stickleback pelvic spine loss: Pitx1 enhancer deletion
- Gene duplication and divergence: a major source of evolutionary novelty; after duplication, one copy can evolve new functions (subfunctionalization or neofunctionalization); hemoglobin gene family; olfactory receptor gene family

**Key vocabulary:** synonymous substitution, nonsynonymous substitution, dN/dS ratio, neutral theory, selective sweep, transposable element, Hox gene, toolkit gene, heterochrony, neoteny, cis-regulatory element, enhancer evolution, gene duplication, neofunctionalization

**What the student builds:**
`13-molecular-evolution.html` — molecular evolution simulator. Controls: sequence length (100–1000 bp); mutation rate slider; selection coefficient for each codon type (synonymous = neutral; nonsynonymous = slider from -1 to +1); number of generations; number of lineages. Display: starting sequence shown; mutations accumulate at each generation (shown as colored marks at changed positions); synonymous changes accumulate faster than nonsynonymous (when under purifying selection); positive selection: a beneficial nonsynonymous change sweeps to fixation, shown as a sweep reducing diversity at linked sites; dN/dS ratio calculated in real time; phylogenetic tree built from final sequences shows divergence between lineages.

**Key references for research agent:**
- Neutral theory: Kimura (1968) *Nature*; Kimura (1983) *The Neutral Theory of Molecular Evolution*
- Hox genes: Lewis Nobel lecture (1995); McGinnis and Krumlauf (1992) *Cell*
- Evo-devo synthesis: Carroll (2005) *Endless Forms Most Beautiful*
- Stickleback regulatory evolution: Shapiro et al. (2004) *Nature*
- dN/dS and positive selection: Yang and Bielawski (2000) *Trends in Ecology and Evolution*
- Transposable elements: Chuong et al. (2017) *Science*

**Bridge to Chapter 14:** Molecular and developmental mechanisms explain how genotypes produce phenotypes and how genotypes evolve. Chapter 14 integrates all of the book's themes in a capstone.

---

### CHAPTER 14 — Capstone: From Genes to Evolutionary Change
**Filename:** `14-capstone-genes-evolution.md`
**Arc position:** Act Three, Chapter 14 — Capstone
**Source:** New (synthesizes Chapters 1–13)

**One-line:** Students synthesize the entire book's genetics and evolution content through three integrative case studies — antibiotic resistance evolution, human population genetics, and the molecular basis of human evolution — connecting molecular mechanisms to evolutionary outcomes.

**Chapter description:**
The capstone synthesizes genetics and evolution through three extended case studies that each require concepts from throughout the book. Case 1 — antibiotic resistance — traces the complete path from molecular mutation (Chapter 8) through selection in bacterial populations (Chapter 10) to clinical and ecological consequences, using E. coli and MRSA as models. Case 2 — human population genetics — applies Hardy-Weinberg, drift, selection, and gene flow to explain patterns of human genetic diversity: why Africans have more genetic diversity than non-Africans (out-of-Africa bottleneck), why some disease alleles are common in specific populations (founder effects, balancing selection), and what GWAS reveals about complex traits. Case 3 — the molecular basis of human evolution — uses evo-devo, comparative genomics, and ancient DNA to examine what makes humans genetically distinct from our closest relatives: the FOXP2 language gene, HAR1 (fastest-evolving human sequence), ASPM and MCPH1 (brain size genes), and what we have learned from Neanderthal and Denisovan genome sequences.

**Core concepts synthesized:**

**Case 1 — Antibiotic Resistance as Rapid Evolution:**
- Mutation (Ch 8): point mutations → beta-lactamase, altered PBPs, efflux pumps
- Selection (Ch 9, 10): antibiotic = selecting agent; resistant cells have fitness advantage
- Population dynamics (Ch 10): selective sweep; resistance allele reaches fixation in days to weeks
- Gene flow (Ch 10): horizontal gene transfer (R plasmids) = gene flow without reproduction
- Fitness costs and epistasis (Ch 10): resistance mutations often reduce growth rate; compensatory mutations
- Conservation implications: antibiotic stewardship as evolutionary management; reducing selection pressure

**Case 2 — Human Population Genetics:**
- Out-of-Africa bottleneck (Ch 10, 11): modern humans left Africa ~60–70 kya; non-African populations are a subset of African genetic diversity; African populations have highest heterozygosity
- Founder effects in human populations (Ch 10): Ashkenazi Jews (Tay-Sachs, Gaucher disease); Amish (Ellis-van Creveld); Finnish disease heritage
- Natural selection in human populations (Ch 9, 10): lactase persistence (recent, multiple independent origins in cattle-herding populations); skin color (UV radiation → folate vs. vitamin D trade-off); malaria resistance (sickle cell, G6PD deficiency, Duffy antigen)
- GWAS and complex traits (Ch 7, 10): height, BMI, educational attainment; thousands of small-effect variants; missing heritability problem
- Population structure and FST (Ch 10): human FST ≈ 0.15 (15% of diversity between populations; 85% within); race is not a biological category

**Case 3 — The Molecular Basis of Human Evolution:**
- Comparative genomics (Ch 13): humans and chimpanzees share ~98.8% of protein-coding DNA; most differences in regulatory sequences
- Human accelerated regions (HARs) (Ch 13): genomic sequences that evolved rapidly in the human lineage; HAR1 expressed in developing neocortex; HACNS1 limb enhancer
- FOXP2 (Ch 13): language and speech gene; two human-specific amino acid changes; selected in human lineage; Neanderthals had human FOXP2 sequence
- Ancient DNA revolution (Ch 12, 13): Neanderthal genome (Pääbo Nobel 2022); Denisovans; admixture with modern humans; introgressed alleles in modern populations (Tibetan EPAS1 from Denisovans)
- Brain evolution (Ch 13): ASPM and MCPH1 evolved rapidly; gene duplication events in human lineage; NOTCH2NL duplication → neocortex expansion

**Final project options:**
- (A) Complete annotated simulation gallery for all 14 chapters with written exploration notes
- (B) An evolutionary genetics case study: choose one genetic disease or trait (sickle cell, lactase persistence, cystic fibrosis, Huntington's disease) and trace the complete story from molecular mechanism (what the mutation does) through population genetics (why it is at its current frequency) to evolutionary history (when and where it arose and spread)
- (C) A molecular evolution analysis: choose two species and analyze their genomic differences using the concepts of Chapter 13 — which genes show evidence of positive selection, which are highly conserved, and what does the pattern tell us about the evolutionary pressures each lineage faced

**Key references for research agent:**
- Antibiotic resistance evolution: Laxminarayan et al. (2013) *Science*; Levin and Rozen (2006) *Nature Reviews Microbiology*
- Human out-of-Africa: Li et al. (2008) *Science*; Reich *Who We Are and How We Got Here* (2018)
- Lactase persistence: Tishkoff et al. (2007) *Nature Genetics*
- Human-specific genomic changes: Pollard et al. (2006) *Nature* (HAR1); Prabhakar et al. (2008) *Science* (HACNS1)
- Neanderthal genome: Green et al. (2010) *Science*; Pääbo Nobel lecture (2022)
- FOXP2: Enard et al. (2002) *Nature*
- NOTCH2NL and brain size: Fiddes et al. (2018) *Cell*

---

## Assessment Structure

| Component | Chapters | Notes |
|-----------|---------|-------|
| Weekly simulation builds (13 × 10 pts) | 1–13 | One simulation per chapter |
| Chapter 0 setup (20 pts) | 0 | CLAUDE.md, DESIGN.md, PROJECT.md present |
| Act One exam: genetics (75 pts) | 1–7 | Meiosis through biotechnology |
| Bridge exam: mutation and cancer (50 pts) | 8 | Mutation types, cancer genetics, somatic evolution |
| Act Three exam: evolution (75 pts) | 9–13 | Selection through molecular evolution |
| Simulation exploration reports (3 × 25 pts) | 3, 10, 13 | Written report with biological interpretation |
| Final exam: integration (100 pts) | 14 | All three capstone case studies |
| Final project (150 pts) | 14 | See Chapter 14 options above |

---

## Simulation Stack Reference

All simulations use D3 v7, single HTML files with inline CSS and JS.

**Standard genetics & evolution simulation elements defined in CLAUDE.md:**
- SVG canvas: 700×500px for genetic diagrams and population plots; 700×400px for molecular diagrams
- Stochastic simulations: use Math.random() with fixed seed option for reproducibility; run multiple replicates
- Allele frequency charts: D3 line charts; multiple replicates as thin colored lines; mean as thick black line; HWE expectation as dashed line
- Punnett squares and pedigrees: SVG grid and symbol rendering
- Phylogenetic trees: D3 hierarchical layout; branch lengths proportional to changes
- Population panels: animated dots representing individuals; color-coded by genotype
- Dark mode: `prefers-color-scheme` media query

---

## Consolidation and Expansion Map

| Source file | Maps to | Notes |
|------------|---------|-------|
| `14-meiosis-and-sexual-reproduction.md` | Ch 01 | Genetics framing (inheritance basis), not cell biology framing |
| `15-mendels-experiments-and-heredity.md` | Ch 02 | Direct source |
| `16-modern-understandings-of-inheritance.md` | Ch 03 | Direct source |
| `17-dna-structure-and-function.md` | Ch 04 | Direct source + repair expanded |
| `18-genes-and-proteins.md` | Ch 05 | Direct source |
| `19-gene-expression.md` | Ch 06 | Direct source |
| `20-biotechnology-and-genomics.md` | Ch 07 | Direct source |
| *(no source)* | Ch 08 | New bridge chapter — mutation and cancer genetics |
| `22-evolution-and-the-origin-of-species.md` | Ch 09 | Direct source |
| `23-the-evolution-of-populations.md` | Ch 10 + Ch 11 | Split: population genetics (Ch10), speciation (Ch11) |
| `24-phylogenies-and-the-history-of-life.md` | Ch 12 + Ch 13 (part) | Split: phylogenetics (Ch12), molecular evolution (Ch13 part) |
| *(no source)* | Ch 13 (part) + Ch 14 | Evo-devo (new in Ch13); capstone (new Ch14) |
| *(no source)* | Ch 00 | New — Brutalist setup + Punnett square simulation |

---

*TIKTOC.md v1.0 — 15 chapters (Chapter 0 + Chapters 1–14)*
*Ready for: research gathering (Cowork research prompt), chapter drafting*
*Repo: biology-plus-one-genetics-and-evolution*
*10 source chapters + 3 new chapters (Ch00, Ch08, Ch14) + splits of Ch23 and Ch24*
*Chapter 8 bridges genetics to evolution — mutation as somatic disease AND evolutionary raw material*
*Chapter 14 capstone: antibiotic resistance + human population genetics + molecular human evolution*
*Bridges to: Biology +1: The Cell (Ch01 overlaps), Biology +1: Animal Physiology (evolution shapes physiology), Cancer +1 series (Ch08)*
