# Chapter 08 — Mutation, DNA Damage, and Cancer Genetics: The Hinge Between Disease and Evolution

**Suggested titles:**
- *The Same Letter Wrong, the Same Letter New — How Mutation Is Disease in One Cell and Raw Material in Another*
- *Three Generations of MSH2 — A Family in Which the Inherited Mistake Becomes the Cancer*
- *Cancer Is Evolution in Fast-Forward — Why the Math of a Tumor and the Math of a Species Are the Same Math*

---

**TL;DR.** Mutation has two faces, and this chapter exists to make both visible at once. In every chapter you have read so far, mutation has been an error — the GAG→GTG that turns hemoglobin A into hemoglobin S, the deletion that breaks CFTR, the BRCA1 frameshift that runs in a family. In every chapter you are about to read, mutation will be raw material — the input to natural selection that, multiplied across millions of years and billions of organisms, produced the diversity of life. The same molecular events, read through different lenses. The bridge case that makes this concrete is cancer: when somatic mutations accumulate in a dividing cell lineage, that lineage becomes a small evolving population, inside the body, on a timescale of decades. Mutations vary (heritable, by mitosis); some confer faster growth (differential reproduction); selection acts (some clones expand, others die out). That is the full Darwinian recipe, applied to cells. By the time you finish this chapter, the math you used to interpret a Mendelian pedigree in Chapters 1–3 and the math you will use to interpret allele-frequency change in Chapters 10–14 will be revealed as the same math. Cancer is the example; mutation is the concept.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **Classify** a given DNA change as a point mutation (substitution: transition or transversion), an indel, or a chromosomal mutation; and, when the change falls in a coding region, **predict** whether it is silent, missense, nonsense, or frameshift.
2. **Distinguish** spontaneous from induced mutations and **name** the major source of each (replication error, depurination, deamination, tautomeric shift; UV, ionizing radiation, alkylating agents, base analogs, intercalators, APOBEC).
3. **Explain** the logic of the Ames test and **predict** how a mutagen-detection screen would distinguish a frameshift-only mutagen from a base-substitution mutagen.
4. **Cite** order-of-magnitude mutation rates for RNA viruses (~10⁻⁶/bp/replication), bacteria (~10⁻¹⁰/bp/replication), and humans (~10⁻⁸/bp/generation), and **compute** the expected number of *de novo* point mutations in a human child.
5. **Distinguish** germline from somatic mutations and **explain** why the same molecular event has very different fates in those two contexts.
6. **Apply** Knudson's two-hit hypothesis to predict the laterality, age of onset, and family-history pattern of a hereditary cancer (retinoblastoma; BRCA1; Lynch syndrome).
7. **Distinguish** proto-oncogene gain-of-function (dominant at the cellular level, one hit sufficient) from tumor suppressor loss-of-function (recessive at the cellular level, two hits required), and **explain** why this dominance asymmetry falls out of gene function rather than being an arbitrary convention.
8. **Walk** the Fearon–Vogelstein multi-step colorectal cancer model from normal epithelium through APC loss → KRAS activation → SMAD4 loss → TP53 loss, **estimate** the timescale (10–30 years), and **explain** why the model maps cleanly onto a five- to seven-hit accumulation problem.
9. **Read** a tumor's mutational signature spectrum and **infer** the likely environmental cause (SBS4 = tobacco; SBS7 = UV; SBS2/13 = APOBEC; SBS1 = clock-like; SBS3 = HR deficiency).
10. **State** the three Darwinian ingredients (variation, differential reproduction, heredity) and **check off** each ingredient for a cell population inside a body, and **explain** why this makes "cancer is somatic evolution" a literal claim rather than a metaphor.
11. **Build** a mutation-accumulation simulator (`08-mutation-accumulation.html`) that tracks cell divisions, accumulates random point mutations, occasionally hits driver loci, and produces a time-to-cancer distribution; **vary** the per-division mutation rate (baseline vs. smoker vs. Lynch syndrome) and **predict** the effect on the distribution before running it.
12. **Articulate** the bridge claim of this chapter — that mutation in a somatic cell becomes cancer mechanism and mutation in a germ cell becomes evolutionary raw material, and that the molecular event is the same in both — in your own words, with at least one worked example for each face.

**Prerequisites.** Chapter 04 (DNA structure, semiconservative replication, polymerase proofreading, the BER/NER/MMR/HR/NHEJ repair pathways). Chapter 05 (the reading frame, the codon table, start and stop codons, the sickle-cell substitution traced end to end). Chapter 06 (regulatory regions, splicing, why noncoding changes can matter). Chapter 07 (sequencing, especially the distinction between germline and tumor sequencing). I will assume you can take a given codon table substitution and call it silent / missense / nonsense / frameshift without help. I will assume you remember that DNA repair pathways exist and roughly what each does. I will not assume you have ever computed a mutation rate end to end, or that you have seen the two-hit math worked.

---

## A family the textbook keeps coming back to

Let me start with a family you will recognize from the chapters before. Three generations of women in a small town in Pennsylvania carry the same one-letter change — a frameshift in the gene called *MSH2*. *MSH2* is one of the four DNA mismatch repair (MMR) proteins; you met it in Chapter 04 as the protein that finds the mismatched base after the polymerase has missed it and the proofreading exonuclease has missed it too. MMR is the third dam in the leakage cascade. Lose it, and the per-cell mutation rate jumps by about a hundredfold ([Hsieh and Yamane 2008 *Mech Ageing Dev* 129:391–407](https://www.sciencedirect.com/science/article/pii/S0047637408000341); the canonical molecular review).

The grandmother in this family — call her Margaret — was diagnosed with colorectal cancer at age 46. She had an aunt who had died of "stomach cancer" in the 1950s and a cousin who had ovarian cancer in her forties. Margaret's mother in turn — call her Linda — was diagnosed with endometrial cancer at 44 and a metachronous colorectal cancer at 50. Linda's son, the third generation in this story, came to a genetic counselor at age 25 because he had read about Lynch syndrome and wondered whether the family pattern fit. Sequencing of his germline DNA confirmed it: a *MSH2* frameshift, inherited from his mother, inherited from her mother before her. He is a carrier. He has not (yet) developed any cancer. He is about 20 years from the median age at which Lynch syndrome carriers develop their first colorectal cancer ([Win et al. 2017 *Lancet Oncol* 18:e493–e503](https://www.thelancet.com/journals/lanonc/article/PIIS1470-2045(17)30537-8/fulltext); the modern risk estimates).

I want you to look at this family with two eyes at once.

With the first eye — the genetics eye, the eye trained by Chapters 1–7 — the family is a Mendelian pedigree. One allele of *MSH2* is broken. The inheritance is autosomal dominant at the level of "carrier risk passed to offspring" (50% per child) but recessive at the level of "cell phenotype" (one good copy of MSH2 is enough to maintain MMR). Lynch syndrome is one of about a dozen well-characterized hereditary cancer-predisposition syndromes, all of which follow this same Mendelian logic: a germline mutation in a tumor-suppressor or DNA-repair gene, transmitted vertically, conferring a lifetime risk that may approach 70–80% but is not 100%.

With the second eye — the eye this chapter is about to train, the evolution eye — the family is something else. Every cell in every carrier starts life with one defective *MSH2* allele. In the colon epithelium especially — a tissue whose stem cells divide approximately every four days, generating something like 10¹¹ daughter cells per carrier per year — there is constant opportunity for the second allele to be lost. When it is lost in a given cell, that cell has now lost mismatch repair entirely. The mutation rate in that cell's descendants is roughly 100-fold higher than in its neighbors ([Lengauer et al. 1997 *Nature* 386:623–627](https://www.nature.com/articles/386623a0); the foundational paper showing MMR-deficient cell lines accumulate microsatellite mutations at vastly elevated rates). Mutations accumulate. Most are passengers — silent, no effect. A rare one hits *APC*. The cell descended from that hit forms a hyperproliferative crypt. Another mutation later hits *KRAS*. The crypt becomes an adenoma. Another mutation hits *SMAD4*. The adenoma becomes dysplastic. Another mutation hits *TP53*. The dysplastic lesion becomes invasive. Forty years after Margaret's grandson inherited the *MSH2* frameshift — say, when he is 65 — a single cell lineage somewhere in his colon may have run all the way down this path.

That is *somatic evolution*. Inside the body. On the timescale of decades. By exactly the same rules — variation, differential reproduction, heredity — that, scaled up by twelve orders of magnitude in body count and seven in time, produced the diversity of life on Earth.

The same molecular event — a frameshift in *MSH2* — is two different things in this family. In the germline (in Margaret's eggs, in Linda's eggs, in her son's gametes), it is *inherited variation* — the raw material that Mendelian transmission carries from one generation to the next, that selection in the population gene pool acts on, that determines what alleles future generations inherit. In a somatic colonic stem cell that loses its second *MSH2* allele, it is *disease mechanism* — the proximate cause of cancer, the thing the surgeon will eventually have to cut out.

One change. Two fates. The fate is decided not by the chemistry of the change but by which cell lineage carries it forward.

That is the bridge this chapter is built on. The genetics half of the book has been about mutation as error. The evolution half — which begins in the next chapter — will be about mutation as raw material. This chapter says: *they are the same thing, seen through different lenses, with cancer in the middle showing both at once.*

The rest of the chapter is the territory. I will lay out the anatomy of mutation (what kinds of changes there are). I will lay out the causes (what produces them, spontaneously and by exposure). I will pin down the *quantitative scale* — how often mutations happen, in what units, with what cross-species variation. I will return to cancer and show, with arithmetic, why the multi-step picture works. I will show how to read a tumor's mutation spectrum like an archaeological record of exposure. And I will close with the explicit bridge: a section called *The Two Faces of Mutation* where the connection from this chapter to Chapter 9 onwards is made mechanistic, not metaphorical.

If at any point in this chapter you find yourself confused about whether mutation is "good" or "bad," that confusion is the chapter doing its job. Mutation is neither. Mutation is *change*. What change does depends on context.

---

## Anatomy of a mutation — the typology before the physiology

Before causes, before consequences, the chapter needs the vocabulary. There are two axes that matter, and a typology that falls out of crossing them.

### Axis 1: How big is the change?

A **point mutation** is a change to a single base pair. Two flavors:

A **substitution** swaps one base for another. There are exactly twelve possible substitutions (each of the four bases can become each of the other three: 4 × 3 = 12). The twelve sort into two families.

A **transition** is a substitution that swaps a purine for the other purine (A ↔ G) or a pyrimidine for the other pyrimidine (C ↔ T). Chemically, the swap is between two bases that look similar — both purines have two fused rings; both pyrimidines have one ring. Four of the twelve possible substitutions are transitions.

A **transversion** is a substitution that swaps a purine for a pyrimidine (or vice versa): A ↔ C, A ↔ T, G ↔ C, G ↔ T. The chemical structure changes more drastically — a two-ringed base becomes a one-ringed base or the reverse. Eight of the twelve possible substitutions are transversions.

Here is something the symmetry hides. Although there are twice as many *possible* transversions as transitions, in real genomes transitions outnumber transversions by roughly two to one. The transition:transversion ratio (often abbreviated Ts/Tv) in the human genome is around 2.0 in coding regions and around 2.1 in noncoding regions ([Stoltzfus and Norris 2016 *Genome Biol Evol* 8:1934–1949](https://academic.oup.com/gbe/article/8/6/1934/2197505); a careful review). Why? Because the biochemistry that generates substitutions is not uniform across the 12 possibilities. One major source — deamination of 5-methylcytosine at CpG dinucleotides, producing C→T — is a transition. Another — tautomeric mispairing — disproportionately produces transitions. The empirical Ts/Tv > 1 falls out of the chemistry, not from a designer's choice.

An **indel** — *insertion-or-deletion* — adds or removes one or a few base pairs. Indels are typically short (1–50 bp) and often arise at repetitive sequences, where the polymerase slips during replication: the daughter strand briefly unpairs from the template, re-pairs out of register, and the polymerase keeps going. Slippage at a run of, say, six A's might produce a daughter strand with five A's or seven A's. The signature failure mode of mismatch repair — what makes the colons of Lynch syndrome patients full of *microsatellite instability* — is uncorrected slippage at short tandem repeats.

Beyond point mutations are **chromosomal mutations**, changes affecting whole chunks of chromosome:

A **deletion** removes a segment — anywhere from a few base pairs (sometimes counted as an indel) up to entire chromosome arms.

A **duplication** copies a segment, leaving the organism with extra dose. Duplications are mechanistically important in evolution — much of the human genome is descended from duplication events whose copies subsequently diverged in function (Chapter 13 will spend time on this).

An **inversion** flips a segment 180° relative to the surrounding chromosome.

A **translocation** moves a segment from one chromosome to another. Reciprocal translocations swap pieces between two chromosomes. The Philadelphia chromosome — t(9;22)(q34;q11), seen in chronic myeloid leukemia — fuses parts of *BCR* on chromosome 22 with parts of *ABL1* on chromosome 9, producing the constitutively active BCR-ABL kinase whose discovery and pharmacology drive the cell book's cancer chapter ([Druker et al. 2001 *N Engl J Med* 344:1031–1037](https://www.nejm.org/doi/full/10.1056/nejm200104053441401); the imatinib trial).

**Aneuploidy** is the wrong total chromosome count — loss or gain of whole chromosomes. Down syndrome is trisomy 21 (three copies of chromosome 21 instead of two). Many cancers show extensive aneuploidy on karyotyping, which is one reason their genomes are so chaotic.

### Axis 2: What happens to the protein?

When a point mutation falls in a coding region, four outcomes are possible. Each takes its name from the codon table you internalized in Chapter 05.

A **silent (synonymous) mutation** changes the codon but not the amino acid. The genetic code is redundant — 61 sense codons encode 20 amino acids — so many third-base changes are silent. Glycine has four codons (GGA, GGC, GGG, GGU); any change among the third positions of these still codes for glycine. *Silent* does not always mean *invisible* — codon choice affects translation rate, mRNA stability, and splicing-enhancer binding. The strong claim "silent = harmless" is wrong; the weaker claim "silent = no amino-acid change, effect depends on context" is right.

A **missense mutation** changes the codon and the amino acid. The protein gets built with a different residue at that position. Whether this matters depends on which residue is where. A conservative change (one hydrophobic for another, distant from the active site) may be near-neutral; a non-conservative change (a charged residue at the active site) may be devastating. The sickle-cell substitution — GAG→GTG at codon 6 of β-globin, glutamate to valine — is a missense mutation, and you traced its consequences end to end in Chapter 05.

A **nonsense mutation** changes a sense codon to a stop codon (UAA, UAG, or UGA). The protein is truncated at that point. Truncations are usually devastating because the truncated protein is incomplete — it lacks downstream domains, often misfolds, and may be degraded by quality-control pathways (nonsense-mediated decay, or NMD, recognizes most premature stop codons and destroys the mRNA before any protein is made).

A **frameshift mutation** is an indel inside a coding region whose length is *not* a multiple of three. The reading frame shifts at the indel and every codon downstream is read wrong, producing a string of nonsensical amino acids until the polymerase hits a premature stop. Frameshifts are usually worse than missense or nonsense because they destroy the protein from the indel onward. The CFTR ΔF508 mutation (Chapter 02) is *not* a frameshift — it deletes three base pairs in-frame, removing one phenylalanine — but most truncating mutations in tumor-suppressor genes (and the *MSH2* mutation in our Lynch family above) are.

A clean teaching move I'll borrow from Chapter 05: walk a single gene through all four mutation types. β-globin (HBB) is convenient. **G→T at codon 6 first position** → missense (sickle cell, HbS). **AAG → TAG at codon 17** → nonsense (β⁰-thalassemia from premature stop). **A single-base insertion in exon 1** → frameshift (β-thalassemia from truncation). **G→A in the 5' splice site of intron 1** → splice-site mutation (mRNA not made, β-thalassemia from absence). Same gene, four mutations, three diseases, four molecular categories. The gene is innocent of all of them; the chemistry of each change determines the outcome.

### A useful misconception to clear

Students often arrive at this chapter believing that mutation types are themselves "harmful" or "harmless" categories. This is wrong twice over. A silent mutation is *usually* neutral but can disrupt splicing. A missense mutation may be devastating (BRCA1 in a HR-active residue) or benign (a conservative substitution at a tolerant residue). A frameshift is *usually* devastating but in some genes — particularly tumor-suppressor genes the cell would be better off without — may be the trick the cancer is using. The category names the *kind of change at the codon level*, not the *kind of consequence at the organism level*. The consequence depends on which gene, which residue, what tissue, what context. The reader who internalizes the typology should not also internalize a sign — they should internalize a kind.

---

## Causes — spontaneous chemistry, induced damage, and Bruce Ames

Now: where do mutations come from? The categories sort cleanly into *spontaneous* (the body and its chemistry doing it to itself) and *induced* (an external agent doing it).

### Spontaneous mutation — the body damaging itself, every day, all the time

Three dominant sources. Each is worth pinning down because each leaves a fingerprint.

**Replication error.** DNA polymerase makes mistakes. Even with proofreading (the 3'→5' exonuclease activity built into replicative polymerases), and even with mismatch repair behind that, the residual error rate is roughly 10⁻⁹ to 10⁻¹⁰ per base pair per replication round in *E. coli* ([Lee et al. 2012 *PNAS* 109:E2774–E2783](https://www.pnas.org/doi/10.1073/pnas.1210309109); whole-genome sequencing of mutation accumulation lines reports 2.2 × 10⁻¹⁰). In humans, the comparable rate per nucleotide per generation is about 1.2 × 10⁻⁸ ([Kong et al. 2012 *Nature* 488:471–475](https://www.nature.com/articles/nature11396); 78 Icelandic trios). The rate is small. The genome is large. The arithmetic matters; we'll do it below.

**Tautomeric shifts.** The bases A, G, C, T each have rare alternate forms — *tautomers* — in which a hydrogen has shifted to a different position on the ring. In the rare imino form, adenine pairs not with thymine (its usual partner) but with cytosine. In the rare imino form, cytosine pairs not with guanine but with adenine. The tautomers are short-lived (microseconds), but if a base happens to be in the wrong form at the moment the polymerase tries to copy it, the wrong partner gets installed. This is a quantum-mechanical, irreducibly stochastic source of error — no proofreading can prevent it, because the misincorporated base looks correct at the moment it goes in.

**Spontaneous chemical damage.** DNA is not a stable molecule. Two reactions matter most.

*Depurination* — the glycosidic bond between adenine (or guanine) and deoxyribose breaks spontaneously, leaving an abasic site (a sugar with no base attached). Estimated rate: ~10,000 depurinations per cell per day in mammalian cells ([Lindahl 1993 *Nature* 362:709–715](https://www.nature.com/articles/362709a0); the classic review of intrinsic DNA instability). Most are caught by base excision repair, but when the polymerase encounters an unrepaired abasic site at the replication fork, the translesion polymerases typically insert an adenine opposite (the "A rule"), which generates a transversion if the lost base was a G or C.

*Deamination.* Cytosine spontaneously loses its amino group to become uracil. Uracil pairs with adenine. So after one more replication round, what was a C is now a T — a C→T transition. The cell catches most of these because uracil is not a normal base in DNA and a battery of uracil-DNA glycosylases recognize it and excise it. But *5-methylcytosine*, the methylated form that decorates CpG dinucleotides in vertebrate genomes (Chapter 06), deaminates to *thymine*, which is a normal base. The repair machinery cannot tell the deaminated 5-methyl-C from a "real" T. The mutation slips through. This is why CpG → TpG is the single most common substitution in the human genome and why one of the most universal cancer mutational signatures — SBS1, which we'll meet below — is essentially a clock counting 5-methyl-C deaminations.

### Induced mutation — the world doing it to you

External mutagens come in three flavors.

**Chemical mutagens** are reactive molecules that modify DNA bases or insert themselves into the helix.

*Base analogs* like 5-bromouracil look chemically similar to thymine, get incorporated by the polymerase, and then mispair — 5-BrU readily pairs with guanine, producing A:T → G:C transitions.

*Alkylating agents* add small carbon-containing groups to bases. The biggest offender is methylation at the O⁶ position of guanine: O⁶-methylguanine pairs preferentially with thymine instead of cytosine, producing G:C → A:T transitions. Mustard gas (the WWI chemical weapon) is an alkylator. Temozolomide, used to treat glioblastoma, is a designed alkylator — it mutates tumor DNA enough that some tumor cells die. *N-nitroso* compounds, formed when nitrites react with amines in the stomach, are alkylators. So is methyl methanesulfonate (MMS), one of the standard laboratory mutagens.

*Intercalating agents* are flat aromatic molecules that slide between adjacent base pairs and distort the helix. Ethidium bromide (the DNA stain in old gel electrophoresis labs) and acridines are the classic examples. Intercalators cause indels, not substitutions — the polymerase slips at the distorted site and the daughter strand ends up one or two bases too long or too short. Acridines mostly produce frameshifts.

*Reactive oxygen species* are generated by normal metabolism (electron transport chain leaks; respiratory bursts in macrophages; ionizing radiation), and they oxidize bases. The most common product is 8-oxo-guanine, which mispairs with adenine, producing G:C → T:A transversions. Cells have a dedicated repair enzyme (OGG1) that recognizes and excises 8-oxo-G, but escapes happen. The signature of oxidative damage is the G→T transversion.

**Physical mutagens** are forms of energy that damage DNA directly.

*Ultraviolet light* causes covalent crosslinks between adjacent pyrimidines on the same strand — *cyclobutane pyrimidine dimers* and 6-4 photoproducts. The dimerized bases cannot pair properly. The nucleotide excision repair pathway (NER, which you met in Chapter 04 in connection with xeroderma pigmentosum) removes them. When NER fails — either because the patient is XP, or simply because there is more damage than the cell can fix in time — the lesions persist, and translesion synthesis past them produces C→T transitions. The fingerprint of UV damage is C→T at dipyrimidine sites: skin cancers (basal cell, squamous cell, melanoma) are absolutely littered with this signature.

*Ionizing radiation* (X-rays, gamma rays, alpha particles, neutrons) breaks DNA. The most dangerous lesions are double-strand breaks, repaired (when they get repaired) by either homologous recombination (HR; high fidelity, uses a sister chromatid as template) or non-homologous end joining (NHEJ; faster, error-prone, often inserts or deletes a few base pairs at the ligation site). The signature of NHEJ is small indels at break points. Cancer therapy uses ionizing radiation deliberately — focused beams break cancer-cell DNA more than they break neighboring tissue, and the cancer cells (with their broken DNA repair networks) die preferentially.

**Biological mutagens.**

Some viruses integrate into the host genome. If they integrate inside or near a proto-oncogene, the viral promoter can drive constitutive transcription — turning a regulated growth gene into an unregulated one. Hepatitis B virus integration in liver cancer; HPV integration in cervical and head-and-neck cancer; Merkel cell polyomavirus in Merkel cell carcinoma — all are examples ([zur Hausen 2009 *Virology* 384:260–265](https://www.sciencedirect.com/science/article/pii/S0042682208007332)). Harald zur Hausen won the 2008 Nobel Prize for showing that HPV causes cervical cancer; the vaccine that protects against HPV (Gardasil, Cervarix) is the proximate clinical descendant of that discovery.

*Transposable elements* — DNA sequences that move around the genome — can also be mutagens. LINE-1 retrotransposons remain active in the human genome; they occasionally land inside a tumor suppressor and disrupt it ([Cajuso et al. 2019 *Nat Commun* 10:4022](https://www.nature.com/articles/s41467-019-11770-0)).

*APOBEC cytidine deaminases* are part of the innate immune system — they deaminate cytidines in viral RNA and DNA, restricting viral replication. They also leave a fingerprint on cellular DNA at sites of replication stress: C→T and C→G changes at TCW contexts (where W is A or T). The APOBEC signature is one of the most common mutational signatures in human cancers, particularly in epithelial tumors.

### The Ames test — a 60-cent assay that anchors public health

How do you know a chemical is a mutagen? You could expose mice and wait for cancer, but that costs years and millions of dollars per chemical. Bruce Ames's elegant 1973 method does it overnight for 60¢ ([Ames et al. 1973 *PNAS* 70:782–786](https://www.pnas.org/doi/10.1073/pnas.70.3.782); the foundational paper).

The trick: use a panel of bacterial strains (*Salmonella typhimurium*) that carry a specific mutation in the histidine biosynthesis operon — they cannot grow without histidine added to the medium. Crucially, the mutation is one that a *single additional mutation can revert* — a back-mutation restores histidine synthesis. Plate the bacteria on minimal medium *without* histidine, where they cannot grow. Add the test chemical. If the chemical is a mutagen, some bacteria will revert their *his* mutation back to functional, regaining the ability to make their own histidine, and growing into visible colonies. Count colonies. The number scales with the mutagen's potency.

Different bacterial strains detect different mutation types. TA98 carries a frameshift mutation in *hisD*; a mutagen reverts it only if it makes new frameshifts. TA100 carries a base-substitution mutation; a mutagen reverts it only if it makes new substitutions. So if you run a chemical on both strains, you not only tell whether it is a mutagen, you tell what kind.

There is one further brilliance to the assay. Many human carcinogens are not active in their parent form — they require *metabolic activation* by liver cytochrome P450 enzymes to become reactive electrophiles. The metabolite is the mutagen; the parent is not. Bacteria do not have liver enzymes. So Ames added a rat liver homogenate (the *S9 fraction*) to the plate. Now the bacteria are exposed to whatever the rat liver would make from the parent chemical. Suddenly the screen detects pre-carcinogens that activate to mutagens.

Ames and colleagues tested hundreds of chemicals and reported approximately 90% concordance between bacterial mutagenicity and animal carcinogenicity. The phrase "carcinogens are mutagens" was *earned*, not assumed. The Ames test is now a regulatory standard worldwide — any new chemical entering the food supply, the cosmetic supply, or the pharmaceutical pipeline is typically run through an Ames screen as a first-pass mutagenicity check. A 60¢ bacterial assay is the front line of consumer safety.

The pedagogical point is bigger than the assay. The Ames test connects three things this chapter cares about: *mutation rate is a measurable quantity*, *some chemicals raise it*, and *those chemicals tend to cause cancer*. The chain from molecular event to public-health concern is closed by a Petri dish.

---

## Mutation rates — a quantitative tour, with arithmetic

Now we have to do some math, because this is the chapter where the numbers matter most.

A mutation rate is a probability per unit of opportunity. The "per unit of opportunity" can be per base pair per replication round, per base pair per generation, per genome per replication, per gene per cell division. These are not the same. Conversion between them requires knowing genome size, generation time, number of replications per generation, and a few other factors. The literature is full of citations that compare apples to oranges; the careful reader pins down the units.

Here is an order-of-magnitude tour across organisms (per base pair, mostly per replication or per generation as labeled):

- **SARS-CoV-2 (RNA virus):** ~1.3 × 10⁻⁶ per site per replication cycle ([Amicone et al. 2022 *Virus Evol* 8:veac050](https://academic.oup.com/ve/article/8/1/veac050/6608430); reviewed in [Markov et al. 2023 *Nat Rev Microbiol* 21:361–379](https://www.nature.com/articles/s41579-023-00878-2)). The high rate reflects two things: viral RNA-dependent RNA polymerase lacks proofreading, and selection in a quickly-replicating immune-evading virus favors high diversity.
- **HIV-1 (retrovirus):** ~3 × 10⁻⁵ per site per replication, even higher [verify exact figure; standard textbook value], because reverse transcriptase makes copying errors with almost no proofreading at all.
- **Influenza A:** ~3 × 10⁻⁵ per site per replication, similar story.
- **Escherichia coli (bacterium):** 2.2 × 10⁻¹⁰ per base pair per generation ([Lee et al. 2012 *PNAS*](https://www.pnas.org/doi/10.1073/pnas.1210309109), from whole-genome mutation accumulation lines).
- **Drosophila melanogaster:** 2.8 × 10⁻⁹ per site per generation ([Keightley et al. 2014 *Genetics* 196:313–320](https://pmc.ncbi.nlm.nih.gov/articles/PMC3872194/), from deep sequencing of a full-sib family).
- **Homo sapiens:** 1.20 × 10⁻⁸ per nucleotide per generation ([Kong et al. 2012 *Nature*](https://www.nature.com/articles/nature11396), 78 Icelandic trios).

The cross-organism range from *E. coli* at ~10⁻¹⁰ to SARS-CoV-2 at ~10⁻⁶ spans a factor of ten thousand. Why such variation?

There is a beautiful idea here, due originally to Michael Lynch, called the **drift-barrier hypothesis** ([Lynch 2010 *Trends Genet* 26:345–352](https://www.cell.com/trends/genetics/abstract/S0168-9525(10)00097-3)). Mutation rates should evolve as low as they can. Lower mutation rates are favored by selection because most mutations are deleterious — so any allele that improves replication fidelity (a better polymerase, a stronger proofreading exonuclease, a more effective MMR pathway) should be favored. But selection on mutation rate is *second-order* — it depends on the fitness consequences of *future* mutations the allele would prevent. In small effective populations, drift overwhelms second-order selection, and mutation rates cannot fall further. Lynch's prediction: large-population organisms (bacteria, RNA viruses with huge population sizes) should have the lowest rates per base, and small-population organisms (vertebrates) should have higher rates. The data largely fit. The exception is RNA viruses, whose rates are high *despite* large populations — there, the additional consideration is that high mutation rate is itself selected for (it generates escape variants).

Now the arithmetic of *per-human-per-generation*. Take the human rate, 1.2 × 10⁻⁸ per nucleotide per generation. Multiply by the human haploid genome size, ~3 × 10⁹ bp. Multiply by two (the diploid child receives a haploid copy from each parent, each carrying its own freshly-arisen mutations). The answer is **roughly 70 new single-nucleotide variants per human child per generation, on average** ([Kong et al. 2012](https://www.nature.com/articles/nature11396); the exact number depends on parental age but ~63 is the headline figure, with the count rising linearly with paternal age by ~2 mutations per year). Indels and structural variants add several more. The clean rough number to remember is *~70 de novo SNVs per child*, with the full count of de novo changes pushing closer to 100 when everything is counted.

Pause on what this means. Every person you have ever met carries dozens of point mutations that neither of their parents had. Some are silent. Some affect splicing. Some are missense, in genes you might or might not care about. A small fraction land in genes where the missense matters and produce phenotypic effect — a *de novo* dominant disease (autism-spectrum disorders, certain rare developmental syndromes, severe intellectual disability) often traces to such a hit. The headline finding of the past 15 years of clinical genome sequencing is that *de novo* mutations explain a substantial share of severe pediatric disease that does not run in families — because the disease-causing change arose in the parental gamete and is therefore not in either parent's blood.

Cumulatively, across the species, this is the source of all standing genetic variation. Take 8 billion living humans, each carrying ~70 *de novo* mutations. That is 5.6 × 10¹¹ new mutational events per generation in the human population — every base pair in the genome is being mutated, somewhere, in some individual, every generation. Some of those mutations will be lost (drift; deleterious selection). A tiny fraction will increase in frequency (drift; positive selection). This is the input that Chapter 09 onwards will be about.

### The mutation rate at the cellular level — why cancer is inevitable

Now we move from per-generation to per-cell-division, which is the unit that matters for cancer.

A normal human somatic cell, dividing, generates roughly 3 × 10⁹ × 2 × 10⁻⁹ ≈ **3 to 6 single-nucleotide mutations per division** in its daughter genome. (The factor of 2 is because mutations can occur on either strand; the rate per replication round per base pair is ~10⁻⁹ in well-repaired somatic tissue.) Most of these land in noncoding DNA. Most are silent. Most are completely without consequence.

But the human body, over an 80-year lifespan, executes very roughly 10¹⁶ total cell divisions (intestinal epithelium turns over rapidly, neurons hardly at all, but the body-wide sum is on the order of 10¹⁶). At ~3 mutations per division, that is ~3 × 10¹⁶ mutational events in your body over your lifetime. The genome has 3 × 10⁹ bases. **Every base in your genome has been mutated, in some cell of your body, hundreds of times over.** Cancer is not a rare biological accident, full stop. It is *the inevitable consequence of stochastic mutation in cells that keep dividing*. The question is not "why does cancer happen?" — it is "why doesn't cancer happen more often?"

The answer to that question is everything else in this chapter. Most somatic mutations are neutral. Even those that hit a driver gene usually do not do so in the right way (wrong codon, wrong residue, wrong context). Even those that do produce a real driver mutation usually do not accumulate the rest of the drivers in the same cell. Even those that accumulate the full set are usually held in check by the immune system, by neighboring tissue, by the cell's own restraint mechanisms. The path from "mutation occurred" to "clinical cancer" is filtered at every step. The filters are good. They are not perfect.

---

## Repair is the dam — recap from Chapter 04, plus the diseases

Chapter 04 walked the DNA repair pathways — BER, NER, MMR, HR, NHEJ — through their mechanisms. I will not redo that work here. What this chapter adds is the *clinical genetics* of what happens when a repair pathway fails.

Three repair-deficiency syndromes give the chapter its anchors.

**Xeroderma pigmentosum (XP).** Autosomal recessive defect in nucleotide excision repair (NER), the pathway that removes UV-induced pyrimidine dimers. XP patients develop severe sunburn from minimal UV exposure, with freckling and persistent skin damage starting in infancy. The lifetime risk of skin cancer (basal cell carcinoma, squamous cell carcinoma, melanoma) is elevated more than a thousandfold — children commonly develop their first skin cancer before age 10 ([Kraemer et al. 1987 *Arch Dermatol* 123:241–250](https://jamanetwork.com/journals/jamadermatology/article-abstract/553537); the foundational clinical series). The disease is a human experimental confirmation of three things: UV causes mutation; NER removes UV damage; when NER fails, the mutations accumulate and skin cancer follows on a predictable timeline. The chapter on DNA structure and replication opened with a case of XP because XP is the cleanest demonstration in human medicine that *DNA repair is what stands between you and cancer*.

**Lynch syndrome.** Autosomal dominant inheritance of one mutant allele in a mismatch repair gene (*MSH2*, *MSH6*, *MLH1*, or *PMS2*). Lifetime colorectal cancer risk for carriers is approximately 50–70%, with elevated risks of endometrial, ovarian, gastric, and urinary tract cancers as well ([Win et al. 2017 *Lancet Oncol*](https://www.thelancet.com/journals/lanonc/article/PIIS1470-2045(17)30537-8/fulltext)). Tumors in Lynch carriers show *microsatellite instability* (MSI-high): short tandem repeats expand and contract because the failed MMR cannot correct slippage at repetitive sequences. MSI is a forensic fingerprint — a tumor's MSI status can be detected by a simple PCR assay or by sequencing-based detection of indels at a panel of microsatellite loci. The clinical importance of MSI testing is enormous: MSI-high tumors carry an extraordinary mutation burden (thousands to tens of thousands of mutations per tumor) which translates into many neoantigens, which makes the tumors highly responsive to immune checkpoint inhibitors. Pembrolizumab was approved for any tumor that is MSI-high in May 2017 — the first tissue-agnostic cancer-drug approval in history ([Marcus et al. 2019 *Clin Cancer Res* 25:3753–3758](https://aacrjournals.org/clincancerres/article/25/13/3753/82693)). Lynch syndrome turned from "bad luck genetic predisposition" to "good news, your tumor will respond to immunotherapy" because of one molecular characteristic.

**BRCA1/BRCA2-associated hereditary breast and ovarian cancer.** Autosomal dominant inheritance of one mutant allele in *BRCA1* or *BRCA2*, both required for homologous recombination (HR) repair of double-strand breaks. Lifetime breast cancer risk for BRCA1 carriers: approximately 60–70%; ovarian: ~40%. BRCA2 carriers have somewhat lower ovarian risk but elevated risks of male breast, pancreatic, and prostate cancers ([Kuchenbaecker et al. 2017 *JAMA* 317:2402–2416](https://jamanetwork.com/journals/jama/fullarticle/2632503)). The two-hit logic applies — tumors in BRCA carriers nearly always show loss of the wild-type allele. The clinical exploitation: HR-deficient cells depend on the parallel single-strand-break-repair enzyme PARP. Inhibiting PARP in an HR-deficient cell creates a *synthetic lethal* situation — neither pathway works, double-strand breaks accumulate, the cell dies. Olaparib, niraparib, and rucaparib are PARP inhibitors approved for BRCA-deficient cancers ([Lord and Ashworth 2017 *Science* 355:1152–1158](https://www.science.org/doi/10.1126/science.aam7344)). The cell book (Chapter 14) traces this story end to end; I will not redo it here.

These three syndromes are the cleanest evidence that *mutation accumulation drives cancer*. Lose a single repair pathway, and the per-cell-per-division mutation rate jumps. Cancer follows on a predictable timeline. The dam analogy is useful: repair pathways are the dams holding back the mutation flood. Where a dam has a hole, water leaks; where the leak is faster than the cell can compensate, cancer eventually follows.

---

## Cancer as somatic evolution — the central claim of this chapter

If this chapter has one Big Idea, it is this: **cancer is Darwinian selection running inside a body, on cells, in months to decades instead of millennia.** Most readers come to cancer biology imagining it as a special kind of disease — a *thing that happens* to people. The honest mechanistic frame is more interesting and more disturbing: cancer is what evolution does when you scale it down.

The argument is structured. Natural selection requires three ingredients, and only three:

1. **Variation** — heritable differences among individuals in a population.
2. **Differential reproduction** — some variants leave more offspring than others.
3. **Heredity** — offspring resemble parents.

For a population of cells inside an organism:

1. *Variation.* Mutations (somatic, accumulated each division) produce heritable differences among cells. A typical adult tissue is mosaic — different patches descend from different lineages, each with its own complement of accumulated mutations.
2. *Differential reproduction.* Mutations that increase proliferation, decrease apoptosis, or evade immune detection let some clones outgrow their neighbors. A clone that divides twice as fast as the average wins — it gets more daughter cells per unit time.
3. *Heredity.* Mitosis passes DNA from mother cell to daughter cell with high fidelity. The daughter cell inherits the mother's full mutational complement, plus its own newly-arisen mutations. The "heritability" of cell traits across mitotic generations is essentially 1.

That is the full Darwinian recipe. The body is the environment. Mutations are the variation. Selection pressures include nutrient availability, oxygen tension, immune surveillance, and (once treatment begins) chemotherapy and targeted drugs. Resistance to treatment is just selection in another direction — the clones that happen to carry a resistance mutation outgrow the sensitive ones.

The reframe matters because it is not metaphor. It is the same machinery, run with cells instead of organisms and with the body instead of the planet. Peter Nowell wrote the foundational paper articulating this view ([Nowell 1976 *Science* 194:23–28](https://www.science.org/doi/10.1126/science.959840); one of the most-cited single-page papers in cancer biology). His one-paragraph claim — that most tumors arise from a single cell of origin and that progression reflects acquired genetic variability with sequential selection — has held up extraordinarily well. Forty years later, deep sequencing of tumor lineages has confirmed every major Nowell claim ([Greaves and Maley 2012 *Nature* 481:306–313](https://www.nature.com/articles/nature10762); the modern review).

The pedagogical move I want you to make is this: read the next four sections as case studies in somatic evolution. The two-hit hypothesis is selection arithmetic. The oncogene/tumor-suppressor distinction is dominance genetics. The multi-step model is sequential fixation of advantageous variants. The mutational signatures are the molecular archaeology that lets us read which mutagen acted, in which clone, at which stage. Each of these is a piece of population genetics, applied to a population of cells.

When Chapter 10 introduces Hardy-Weinberg, you will be doing the same math you do here. When Chapter 13 introduces molecular clocks, you will be using the same SBS1 mechanism (5-methyl-C deamination, clock-like, age-correlated) on a longer timescale. The continuity is exact. I will return to this point at the end of the chapter.

---

## Knudson's two-hit hypothesis — and the math worked through

Alfred Knudson published in 1971 the statistical paper that became the foundation of tumor suppressor biology ([Knudson 1971 *PNAS* 68:820–823](https://www.pnas.org/doi/10.1073/pnas.68.4.820)). The data were simple: 48 retinoblastoma cases at MD Anderson, of which some were hereditary (with family history) and some sporadic. Knudson noticed that the *hereditary* cases tended to be **bilateral** (both eyes) and **early-onset** (median ~1.5 years), while the *sporadic* cases tended to be **unilateral** (one eye) and **later-onset** (median ~4 years).

He fit the age-of-onset data to mutational kinetics. *Bilateral hereditary cases followed one-hit kinetics*: the rate of tumor onset was linear with the number of retinoblasts at risk. *Sporadic cases followed two-hit kinetics*: the rate was quadratic. He inferred that retinoblastoma required two genetic events at a particular locus.

In hereditary cases, the first event is inherited as a germline mutation present in every cell, including every retinoblast. Only one further somatic event is needed in any retinoblast to lose the locus completely. Given millions of retinoblasts in each eye, this further event is essentially guaranteed to occur in multiple cells across both eyes — and so hereditary patients present bilaterally, multifocally, early.

In sporadic cases, both events must occur somatically in the same retinoblast lineage. The probability of two independent events at the same locus in the same cell line is the product of two small probabilities — vanishingly small per cell. Multiplied across millions of retinoblasts, this product produces, on average, one tumor per affected eye, later in life, in only some children.

The predicted gene — *RB1* — was cloned in 1986 ([Friend et al. 1986 *Nature* 323:643–646](https://www.nature.com/articles/323643a0)). Its protein, Rb, gates the G1/S checkpoint of the cell cycle. The cell-book Chapter 14 traces this biology end to end; I refer you there for the cell-cycle mechanism.

Here is the math. Let me work it explicitly because the arithmetic is the *whole content* of the Knudson argument.

Define:
- *μ* = per-locus mutation rate per cell division, ~10⁻⁶ per gene per division (the order of magnitude obtained when you multiply the per-base rate of ~10⁻⁹ by ~1000 base pairs of relevant coding sequence). A single gene is large enough that, in any given division, the cell has about a one-in-a-million chance of inactivating one allele by a new mutation.
- *N* = number of retinoblasts per eye, ~10⁶ to 10⁷ cells.
- *D* = number of cell divisions during retinal development, ~10 to 30 (depending on how you count; retinal differentiation is mostly complete by age 4 or 5).

**Hereditary case.** Each cell starts with one *RB1* allele already broken (germline). The probability that a given retinoblast loses its second allele during development is roughly *μ × D* ≈ 10⁻⁶ × 30 ≈ 3 × 10⁻⁵ per cell. The total number of retinoblasts that lose both alleles, across the eye, is *N × μ × D* ≈ 10⁶ × 3 × 10⁻⁵ ≈ 30 events per eye. The expected number of independent two-hit cells per eye is on the order of tens. The likelihood of getting at least one (in fact, many) per eye is essentially 1. Hence bilaterality, multifocality, early onset.

**Sporadic case.** Each cell starts with both *RB1* alleles intact. The probability that a given retinoblast loses both alleles during development is roughly *(μ × D)²* ≈ (3 × 10⁻⁵)² ≈ 10⁻⁹ per cell. The total number of retinoblasts that lose both alleles, across one eye, is *N × (μ × D)²* ≈ 10⁶ × 10⁻⁹ ≈ 10⁻³ events per eye. About one in a thousand sporadic retinas develops a tumor. When it does, it usually involves one cell (one tumor, one eye, late in development).

The clinical picture falls out of the arithmetic. Knudson made the prediction in 1971 with a slide rule and a small clinical dataset. Whole-genome sequencing of retinoblastomas thirty years later confirmed every detail.

The generalizable lesson: **any recessive (loss-of-function) tumor suppressor follows two-hit kinetics. Any dominant (gain-of-function) oncogene follows one-hit kinetics.** This distinction is not arbitrary — it falls out of the genetic logic of dominance and recessiveness, the same logic you learned in Mendel's framework in Chapters 1–3. *Cancer genetics is Mendel applied to single cells.* The gene's "phenotype" in a cell is the cell's behavior (proliferate or not, apoptose or not, invade or not). A gain-of-function mutation in a proto-oncogene gives a cell a new "phenotype" (constant growth signal); the cell does not need to lose its wild-type allele because one mutant copy makes enough constitutively active protein to override the regulated wild-type. A loss-of-function mutation in a tumor suppressor only changes the cell's phenotype if all copies of the suppressor are lost; one functional copy provides the protein, and the cell behaves normally.

---

## Oncogenes versus tumor suppressors — the dominance asymmetry

A common student error at this point is to imagine oncogene mutations and tumor suppressor mutations are *different kinds of mutations*. They are not. They are the same molecular events — substitutions, indels, frameshifts, deletions, translocations — falling in different functional categories of gene.

What makes a mutation "oncogenic" or "tumor-suppressive" is *which gene it falls in and what it does to that gene's product*.

**Proto-oncogenes** encode proteins that *promote growth*: growth factors, receptor tyrosine kinases, cytoplasmic kinases, transcription factors, anti-apoptotic regulators. The classic examples are:
- **The RAS family** (HRAS, KRAS, NRAS) — small GTPases that relay signals from receptor tyrosine kinases to downstream cascades (MAPK, PI3K). Specific point mutations at codons 12, 13, or 61 lock RAS in its GTP-bound active form. KRAS G12D is the single most common driver mutation in pancreatic cancer (~90% of cases); KRAS G12C is enriched in lung adenocarcinoma in smokers.
- **MYC** — a transcription factor that drives cell-cycle entry and ribosome biogenesis. Amplification or translocation (Burkitt lymphoma's t(8;14), placing MYC under the IgH locus enhancer) produces overexpression that drives proliferation.
- **EGFR** — a receptor tyrosine kinase; activating mutations (e.g., L858R in the kinase domain) drive lung adenocarcinoma, particularly in never-smokers and East Asian populations.

A proto-oncogene becomes an **oncogene** by *gain of function*. One mutated allele is sufficient — the gas pedal is jammed on. The other allele is irrelevant because the dominant mutant protein produces enough constitutive signal to override the regulated wild-type. *One hit; dominant at the cellular level.*

**Tumor suppressor genes** encode proteins that *restrain growth*: cell-cycle checkpoint proteins, inhibitors of growth signaling, DNA repair components, pro-apoptotic regulators. The classics:
- **TP53** ("p53, guardian of the genome," after [Lane 1992 *Nature* 358:15–16](https://www.nature.com/articles/358015a0)) — a transcription factor activated by DNA damage that arrests the cell cycle, drives DNA repair, or triggers apoptosis. Mutated (usually missense, often R175H or R248W in the DNA-binding domain) in approximately half of all human cancers. The cell book covers p53 mechanism in depth (Chapter 11 there, the cell-cycle and DNA-damage chapter).
- **RB1** — the retinoblastoma protein, as covered above.
- **APC** — the colorectal cancer suppressor, a regulator of β-catenin and Wnt signaling. Loss of APC drives the formation of colonic adenomas.
- **BRCA1, BRCA2** — DNA repair (HR pathway); loss enables a hypermutator phenotype.

A tumor suppressor becomes inactivated by *loss of function*. Both alleles must go for the cell to escape the restraint. *Two hits; recessive at the cellular level.*

Now — and this is the important part — *the dominance pattern is not an arbitrary convention*. It falls out of gene function. To gain a new behavior (constitutive activity), one productive allele is enough. To lose a behavior (the suppressive activity), you must eliminate all productive copies, which in a diploid cell means both alleles. Dominance follows function follows mechanism.

This logic has a powerful clinical implication. **Inherited cancer predispositions are almost always germline mutations in tumor suppressors, not oncogenes.** Why? Because if you inherited a constitutively active KRAS in every cell of your body, embryonic development would fail. The few inherited oncogene syndromes that exist (RET in MEN2; HRAS in Costello syndrome) involve tissue-restricted or hypomorphic alleles that the embryo can tolerate; they produce specific phenotypes, not generalized cancer predisposition.

Tumor suppressors, by contrast, are recessive at the cellular level. A carrier with one inactivated *MSH2* allele in every cell is *functionally normal at the cell level* — every cell still has one good MMR system, and most cells stay that way for life. What the carrier has is a dramatically elevated probability of losing the second allele somewhere, at some point, in some dividing tissue. That probability is the carrier's cancer risk. The germline mutation is one hit already taken; the somatic loss of the second allele is the disease event.

This is why the catalog of hereditary cancer syndromes — BRCA1/2 (breast/ovarian), Lynch (colorectal/endometrial), Li-Fraumeni (TP53 — broad spectrum), FAP (APC — colorectal), VHL (von Hippel-Lindau — kidney/CNS hemangioblastoma), NF1 and NF2 (neurofibromatosis), retinoblastoma (RB1), Cowden syndrome (PTEN) — is almost entirely *recessive-at-the-cell tumor suppressor genes*. The pattern is not an accident; it is the dominance logic of gene function.

---

## Multi-step carcinogenesis — Vogelstein's colorectal model

Eric Fearon and Bert Vogelstein's 1990 *Cell* paper synthesized the colorectal cancer literature into the most influential model of multi-step carcinogenesis ([Fearon and Vogelstein 1990 *Cell* 61:759–767](https://www.sciencedirect.com/science/article/pii/009286749090186I)). I will lay out the model as a sequence, then return to its meaning.

**Step 1: Normal colonic epithelium.** Stem cells at the base of each colonic crypt divide. Daughter cells migrate up the crypt walls, differentiating into goblet cells, absorptive enterocytes, and other lineages. They die at the surface and are sloughed into the gut. The tissue turns over every few days. Homeostasis.

**Step 2: APC loss → small adenoma.** A cell loses both copies of *APC* (germline mutation plus somatic second hit in FAP families; two somatic hits in sporadic cases). APC normally binds β-catenin and targets it for degradation. Without APC, β-catenin accumulates, enters the nucleus, and turns on Wnt-pathway target genes — including c-MYC, cyclin D1, and the stem-cell gene LGR5. The cell behaves as a stem cell that does not stop dividing. The crypt becomes a hyperproliferative dysplastic crypt and grows into a small polyp.

**Step 3: KRAS activation → large adenoma.** On top of APC loss, a single point mutation at codon 12 (most often G12D) activates KRAS. The cell now has both constitutive proliferative signaling (RAS) and unregulated cell-cycle entry (Wnt). The polyp grows into a larger adenoma with more dysplasia.

**Step 4: SMAD4 (or other 18q) loss → late adenoma.** Loss of TGF-β pathway components, especially SMAD4 (on chromosome 18q), removes a growth-restraining signal that normally limits epithelial expansion. The polyp becomes more dysplastic and starts showing histologic features of preinvasive lesion.

**Step 5: TP53 loss → invasive carcinoma.** Loss of p53 removes the apoptosis-and-checkpoint backstop. Cells with damaged DNA no longer die; they continue dividing. This transition is associated with the histologic step from adenoma to invasive carcinoma — cells now break through the basement membrane and invade the underlying tissue.

**Step 6: Further mutations → metastasis.** Additional events (varying by patient — chromosomal instability, additional driver hits, immune-evasion mutations) enable invasion into blood vessels, survival in the circulation, and seeding of distant organs (most often liver).

The timeline: approximately 10–30 years from initial APC loss to clinical cancer in most cases. Hence the public-health recommendation for colonoscopy screening starting at age 45–50: most adenomas can be detected and removed during the long latent phase before they become invasive. Polypectomy is curative when done early; the same disease, undetected for ten more years, may be terminal.

Bert Vogelstein's 2013 *Science* review, [Cancer Genome Landscapes](https://www.science.org/doi/10.1126/science.1235122), generalized the model. Across pan-cancer whole-genome data, the typical adult solid tumor carries **2 to 8 driver mutations** — events that confer growth advantage — embedded among hundreds to thousands of *passenger* mutations that confer no advantage. The driver count varies by tumor type: pediatric cancers often have only 1–3 drivers; smoking-related cancers can have 10+; pancreatic and colorectal usually 4–7. The structure is consistent. A handful of driver hits are required; they accumulate sequentially under selection; the rest of the mutational burden is noise.

The 2020 Pan-Cancer Analysis of Whole Genomes (PCAWG) consortium analyzed 2,658 tumors across 38 cancer types and confirmed and extended the picture ([ICGC/TCGA PCAWG 2020 *Nature* 578:82–93](https://www.nature.com/articles/s41586-020-1969-6)). Most tumors fit a model of sequential driver accumulation. The signatures of mutational processes are recoverable from the data. The clonal structure within tumors can be reconstructed by subclonal variant frequencies.

The pedagogical point: cancer is not "one mutation, then cancer." Cancer is mutation as *accumulation in a dividing lineage*, under selection. Each hit changes the cell's growth dynamics. Each change exposes the cell to new selective pressures. Each pressure favors the next hit. The process is iterative, stepwise, evolutionary.

---

## Mutational signatures — reading exposure from pattern

Here is the most beautiful recent development in cancer genetics. I want to celebrate it because once you see it, it changes how you think about a cancer genome.

Different mutagens leave different chemical fingerprints. UV light produces C→T changes preferentially at dipyrimidine sites — wherever two pyrimidines (CC, CT, TC, TT) are adjacent, UV crosslinks them, and the resulting lesions resolve to C→T transitions. Tobacco smoke contains polycyclic aromatic hydrocarbons that, after metabolic activation in the lung, form bulky adducts on guanine; translesion synthesis past these adducts produces C→A transversions preferentially in particular sequence contexts. APOBEC cytidine deaminases act at TCW (W=A/T) contexts and produce C→T and C→G changes. Mismatch repair failure produces a characteristic spectrum at homopolymer runs and dinucleotide repeats. Each cause leaves a different *spectrum of mutation type by sequence context*.

In 2013, Ludmil Alexandrov, Mike Stratton, and colleagues at the Wellcome Sanger Institute asked: can we extract these signatures *from cancer data alone*, with no prior knowledge of exposure history? They took 4,938,362 mutations from 7,042 tumors and used non-negative matrix factorization to find recurring patterns ([Alexandrov et al. 2013 *Nature* 500:415–421](https://www.nature.com/articles/nature12477); the foundational paper). They classified every point mutation by its trinucleotide context — the mutated base plus the bases immediately 5' and 3'. There are 96 possible categories (6 substitution types — C>A, C>G, C>T, T>A, T>C, T>G — times 16 trinucleotide contexts). They asked which linear combinations of 96-dim spectra explain the data.

They found more than twenty distinct signatures. The follow-up 2020 paper expanded the catalog to 49 single-base substitution (SBS) signatures, 11 doublet-base substitution signatures, and 17 small-indel signatures ([Alexandrov et al. 2020 *Nature* 578:94–102](https://www.nature.com/articles/s41586-020-1943-3)). The signatures are now maintained as a public reference at the COSMIC database ([https://cancer.sanger.ac.uk/signatures/](https://cancer.sanger.ac.uk/signatures/)). For most of the major signatures, a specific environmental or biological cause has been identified.

**Key signatures, with named causes:**

- **SBS1** — C>T transitions at CpG sites. Clock-like; accumulates at a roughly constant rate per cell per year. Cause: spontaneous deamination of 5-methylcytosine at CpG dinucleotides. Present in every cell, every tissue, in proportion to age. SBS1 burden is essentially the molecular clock of cell-division history.

- **SBS4** — C>A transversions throughout the genome. Cause: tobacco smoke carcinogens. Dose-dependent on pack-years. Found in lung cancers of smokers; absent in lung cancers of never-smokers. The C→A transversions arise because polycyclic aromatic hydrocarbon-guanine adducts, when read past by translesion polymerases, get mispaired with adenine, producing G→T on the original strand (read as C→A on the complementary strand).

- **SBS7a/b/c/d** — C>T transitions at dipyrimidine sites. Cause: UV light → pyrimidine dimers → translesion errors. Pervasive in skin cancers (melanoma, squamous cell carcinoma).

- **SBS2 and SBS13** — C>T and C>G changes at TCW contexts. Cause: APOBEC cytidine deaminase activity. Common in many epithelial cancers (bladder, breast, cervical, head-and-neck).

- **SBS6, SBS15, SBS20, SBS26** — broad point-substitution patterns plus small indels at microsatellites. Cause: mismatch repair deficiency. Diagnostic of MSI-high tumors (Lynch syndrome and sporadic MMR-deficient tumors).

- **SBS3** — broad genome-wide pattern. Cause: homologous recombination deficiency (BRCA1/2 loss; "BRCAness"). Predicts PARP-inhibitor responsiveness.

Why is this profound? Because *the tumor's history is written in its mutations*. You can sequence a tumor with no clinical information at all and infer from the mutational spectrum: whether the patient smoked, what their UV exposure was, whether they have HR deficiency, whether they have MMR deficiency, which treatments are likely to work. Cell book Chapter 14 emphasized the *targeted-therapy* utility — I will not redo that here. Here I want to emphasize the *conceptual* shift: a tumor genome is an *archaeological record* of the exposures that produced it. The same conceptual move that lets evolutionary biologists infer ancestral environments from mutation patterns in extant species lets oncologists infer carcinogen exposure from mutation patterns in tumors. The chapter on molecular evolution (Chapter 13) will return to this — the clock-like SBS1 signature *is* the molecular clock that lets us date evolutionary divergences.

A clinical example will help anchor the idea. A 62-year-old former smoker (30 pack-years, quit 10 years ago) presents with a 3 cm lung adenocarcinoma. Tumor sequencing returns:
- ~22,000 total point mutations (very high — typical for smoker lung cancers).
- ~60% of mutations attributable to SBS4 (tobacco).
- ~15% to SBS1 (clock-like, age).
- ~10% to SBS2/SBS13 (APOBEC).
- Driver mutations: KRAS G12C, TP53 R175H, STK11 truncation.

Two things this profile teaches:

First, *the tumor remembers*. Quitting smoking ten years before diagnosis does not erase the SBS4 signature. Those mutations were installed when the patient was smoking, were copied along through every cell division since, and remain in the cancer that emerged from one of those persistently mutated lineages. Smoking cessation reduces *new* cancer risk over time but does not reverse risk from accumulated damage. The graph of risk versus years since quitting is exponentially decaying but never reaches zero.

Second, *the mutagen specified the driver*. KRAS G12C is the mutation in which the codon-12 glycine becomes cysteine — and the underlying nucleotide change is a C→A transversion (GGT → TGT), exactly the kind of change SBS4 produces preferentially. Smokers enrich for KRAS G12C in their lung cancers because tobacco smoke generates C→A transversions; non-smokers enrich for EGFR mutations (which arise from different substitutions) in their lung cancers. The exposure shaped the spectrum of *possible* driver hits. The clinical relevance: KRAS G12C is now druggable (sotorasib and adagrasib are approved KRAS G12C inhibitors), so the patient's mutation signature predicts both the cause and the targeted therapy.

---

## A surprise from healthy tissue — Martincorena's findings

Before I push the somatic-evolution claim to its conclusion, I want to flag a recent finding that complicates the simple "mutation → cancer" picture in an interesting way.

In 2015, Iñigo Martincorena and colleagues at the Wellcome Sanger Institute sequenced eyelid skin biopsies from four middle-aged donors with the depth normally reserved for cancers ([Martincorena et al. 2015 *Science* 348:880–886](https://www.science.org/doi/10.1126/science.aaa6806)). The skin was *normal* — no cancer, no precancerous lesion. They found something remarkable. The normal sun-exposed skin had 2–6 mutations per megabase, comparable to mutation burdens in many cancers. Eighteen to thirty-two percent of cells carried driver mutations in known cancer genes — NOTCH1, TP53, FAT1, and others. The skin showed clear evidence of positive selection on these driver-carrying clones: NOTCH1 mutations were enriched far above what neutral mutation alone would predict. About 140 driver mutations per square centimeter of sun-exposed skin.

The follow-up 2018 paper looked at normal esophageal tissue ([Martincorena et al. 2018 *Science* 362:911–917](https://www.science.org/doi/10.1126/science.aau3879)). Esophageal biopsies from nine donors aged 20–75 showed that NOTCH1 mutations colonized 12% to 80% of cells by middle age. NOTCH1 mutations in *normal* esophagus were *more common* than in esophageal *cancers*, where NOTCH1 mutates in only ~10% of tumors.

What does this mean? It means the simple model — "you acquire a driver mutation, you get cancer" — is wrong in a deep way. You acquire driver mutations *all the time*. Your skin is full of them. Your esophagus is full of them. Some clones (NOTCH1+ in esophagus) seem to expand and stay benign, perhaps even *preventing* the development of cancer by occupying space that more aggressive clones would otherwise colonize. Selection in normal tissue produces clonal expansions constantly. Most of those expansions reach a fitness peak that is *not* "invasive cancer" — they are just bigger than their neighbors.

For the somatic-evolution framing, this is reinforcement rather than refutation. Selection is acting. Variation is being produced. Clones are being differentially favored. The "fitness landscape" of the normal tissue has many peaks. Most clonal expansions settle on benign peaks. Only the rare combination of mutations that produces a clone with *invasive growth, metastatic potential, immune evasion, replicative immortality, and the rest of the cancer phenotype* corresponds to a peak we call "cancer."

The clinical implication is humbling: distinguishing the clonal expansions that will become cancer from those that will not is a hard, currently-unsolved problem. The genomic data alone do not suffice. Microenvironment, immune surveillance, additional mutations, tissue context — all matter. This is why precision-cancer-prevention strategies (treat the pre-cancer before it becomes cancer) have been less successful than precision-cancer-therapy strategies (treat the cancer once it has emerged). The signal-to-noise problem in distinguishing imminent danger from benign clonal expansion is severe.

For this chapter's purposes, the lesson is: *mutation is necessary but not sufficient for cancer*. The path from mutation to clinical disease has many filters. We are still learning what they are.

---

## A worked example — a Barrett's segment over twenty years

Let me trace one somatic evolutionary trajectory end to end. The point is to make the somatic-evolution claim quantitative.

Start with a hypothetical 50-year-old man with a chronic Barrett's esophagus segment. Barrett's esophagus is a metaplastic change in the lower esophagus — the normal squamous epithelium is replaced by intestinal-type columnar epithelium, as an adaptive response to chronic acid reflux. The new epithelium is more resistant to acid but more susceptible to dysplastic progression. About 0.5% of Barrett's patients per year progress to esophageal adenocarcinoma ([Hvid-Jensen et al. 2011 *N Engl J Med* 365:1375–1383](https://www.nejm.org/doi/10.1056/NEJMoa1103042)).

The Barrett's segment is roughly 3 cm long. It contains on the order of 10⁹ epithelial cells. The stem cells at the crypt bases divide approximately weekly — call it 50 divisions per year per stem cell. Over 20 years (the typical time the man has had Barrett's), that is 1000 divisions per stem cell lineage.

**Per-division mutation accumulation.** At a normal somatic mutation rate of ~10⁻⁹ per bp per replication and a genome size of 3 × 10⁹ bp, each cell division produces roughly 3 mutations in each daughter cell. Over 1000 divisions, a stem cell lineage accumulates approximately *3,000 mutations*. Most are in noncoding DNA, silent, neutral.

**How many land in driver genes?** Of the ~20,000 protein-coding genes, the cancer driver gene set is estimated at ~200–300 ([Vogelstein et al. 2013](https://www.science.org/doi/10.1126/science.1235122)). The driver gene set covers something like 0.1–1% of the genome's coding sequence. Probability that any given mutation lands in a driver gene: roughly 1%. Out of 3,000 mutations, expected ~30 land in driver genes. Most of those 30 are *passengers within driver genes* — silent, or at residues that don't matter for function. The fraction of mutations within a driver gene that actually *activates* (for an oncogene) or *inactivates* (for a tumor suppressor) is much smaller — perhaps 1–10% for tumor suppressors (any frameshift or nonsense works) and <1% for oncogenes (only specific residues at specific positions matter).

**Expected driver hits per cell.** A typical Barrett's stem cell lineage by age 70 might accumulate, on average, 1 to 3 "real" driver mutations after 1000 divisions. Most stem cell lineages do not get to the 5-or-more drivers needed for invasive cancer.

But there are 10⁹ cells in the Barrett's segment. The product distribution is what matters. Across 10⁹ cells, even rare combinations occur. Let *p* be the probability that any given cell has accumulated exactly the right set of 5 driver mutations to be cancerous. If *p* is 10⁻⁸ (one in a hundred million per stem cell lineage), then in 10⁹ cells we expect about 10 cells with the full driver set. The first such cell to arise has a growth advantage — say, 20% faster division than neighbors. It expands clonally. Within a few years, its descendants dominate a region of the Barrett's segment. Some of those descendants acquire additional drivers (the population has more cells now, more chances for further hits). The lesion progresses through dysplasia to carcinoma.

This is somatic evolution, made arithmetic. Variation produced by mutation. Heritable (the first cancer cell's mutations are inherited by all its mitotic descendants). Selection acts (faster-growing clones outgrow slower-growing ones). The timescale (20 years in this case) is set by the *product* of cell division rate, mutation rate, and driver landscape.

If the man had a mutator phenotype — say a germline MSH2 mutation, like the Lynch family we opened with — the mutation rate per division would be roughly 100-fold higher (~300 mutations per cell per division instead of 3). The expected driver hits per lineage would scale up correspondingly. The time-to-cancer would compress from 20 years to a couple years for the same target tissue. *That is why Lynch syndrome cancers occur 20–30 years earlier than sporadic cancers in the same tissues.* The mutation rate sets the clock.

If the man had been a heavy smoker for those 20 years, the lung tissue (different organ, similar logic) would experience an elevated rate of C→A transversions specifically — say doubling the relevant mutation rate. The time-to-cancer would compress proportionally. *That is why smokers develop lung cancers 10–15 years earlier than non-smokers on average.* The exposure sets a different clock.

This is the clinical relevance of the somatic-evolution framework: the rate at which cancer evolves in a given tissue depends on the per-division mutation rate, the cell division rate, the size of the cell population at risk, and the driver landscape. Each of those parameters can be altered — by mutagen exposure (raises mutation rate), by tissue turnover (raises division rate), by repair-deficiency (raises mutation rate). And so can the clinical interventions: screening (catches lesions during the long latent phase); chemoprevention (lowers driver-mutation-acquisition probability); targeted therapy (kills the driver-positive clones once they emerge); immunotherapy (lets the immune system see the antigens the driver mutations produce).

**Limits of the calculation.** This is the simplified mathematical view. Real cancers have:
- *Epigenetic dysregulation* — silenced tumor suppressors via promoter hypermethylation (Chapter 06's territory), without any DNA sequence change at all.
- *Tumor microenvironment effects* — fibroblasts, vasculature, immune cells, hypoxia, mechanical stress — that the simple "cell-autonomous mutation accumulation" model ignores entirely.
- *Immune editing* — the immune system selectively kills neoantigen-expressing clones, shaping the surviving population in ways that may make the tumor more or less aggressive depending on context.
- *Clonal interaction* — clones do not just compete; they sometimes cooperate, with one clone secreting a factor that helps a neighboring clone proliferate.

The arithmetic is the skeleton. The biology is the flesh. Both matter. The chapter's role is to make the arithmetic visible. The cell book, the medical school, and the next 30 years of cancer research are about the flesh.

---

## The Tomasetti–Vogelstein controversy — "bad luck" and what it means

I want to take one detour into a public-health controversy because it illustrates how the somatic-evolution view interacts with policy questions in ways that are not always tidy.

Cristian Tomasetti and Bert Vogelstein published two papers ([Tomasetti and Vogelstein 2015 *Science* 347:78–81](https://www.science.org/doi/10.1126/science.1260825); [Tomasetti et al. 2017 *Science* 355:1330–1334](https://www.science.org/doi/10.1126/science.aaf9011)) arguing that random replication errors in stem cells contribute more to cancer incidence than was commonly recognized. Their argument: across human tissues, lifetime cancer risk correlates strongly (correlation ~0.80 in the 2017 update) with the total number of stem cell divisions in that tissue over a lifetime. Tissues with many stem cell divisions (colon, breast) have high cancer risk; tissues with few (cartilage, adult brain) have low. The 2017 paper estimated that ~two-thirds of mutations in tumors come from replication errors, with the remaining third from environmental and hereditary causes.

The phrase "bad luck cancer" went viral. The pushback was severe. Critics — including most public-health epidemiologists — argued that:

1. The correlation does not establish the *fraction* of cancer attributable to replication errors. A tissue can have many stem cell divisions *and* be heavily exposed to environment (the colon sees the gut microbiome and dietary mutagens; the lung sees inhaled toxins). Disentangling is genuinely hard.
2. *Etiology* and *preventability* are different questions. Even if a mutation arose from stochastic replication error, prevention via reducing exposure (smoking cessation, HPV vaccination, sunscreen) still reduces overall cancer rates because environmental mutagens act on top of the baseline.
3. Many cancers are highly preventable (HPV-driven cervical cancer; tobacco-driven lung cancer; HBV-driven liver cancer) regardless of how much of their *baseline* mutation burden comes from replication errors.

My honest reading: Tomasetti & Vogelstein established a correlation that should not be ignored. The interpretive language ("bad luck") oversimplified and offended people whose job is to reduce cancer through prevention. The mature view is that *stochastic replication errors are an unavoidable baseline; environmental mutagens add to that baseline; both matter; the policy implications come from the avoidable component, which remains large*. Approximately 40% of cancer cases in high-income countries are attributable to modifiable lifestyle and environmental factors (tobacco, UV, alcohol, HPV, obesity, occupational exposures) — that is a public-health intervention target the size of a continent.

Where the somatic-evolution framing helps is in keeping both halves of the picture visible. Mutation rate is what determines cancer incidence in dividing tissue. Mutation rate has a *stochastic component* (replication errors, irreducible) and an *environmental component* (mutagens, modifiable). Lowering the environmental component lowers the rate; we cannot lower the stochastic component (yet); both effects are real. The question "is cancer mostly bad luck?" is the wrong question. The question "how much of this cancer would not have happened if exposure had been lower?" is the right question. The answer varies by tumor type and population.

---

## The Two Faces of Mutation — making the bridge explicit

This is the section the chapter has been building toward. I want to make the genetics-to-evolution transition mechanical, not metaphorical.

The same molecular event — a substitution at base *N* in gene *G* — has two completely different fates depending on which cell carries it forward.

**Face 1: Mutation in a somatic cell.** The mutation occurred in a dividing cell of an adult tissue. It is copied to that cell's daughter cells via mitosis. The daughter cells, in turn, copy it to their daughters. If the mutation confers a growth advantage (driver mutation), the lineage carrying it expands. If it confers a growth disadvantage, the lineage shrinks. Either way, the mutation's spread is bounded — by the body the cell lives in, by the lifespan of that body, and by the immune system, tissue architecture, and other constraints. The mutation dies when the body dies. (Exception: the rare transmissible cancers in dogs and Tasmanian devils, where a tumor cell line has gone airborne — literally — and now propagates between organisms. These are zoological curiosities, not mainstream biology.)

If the somatic mutation lands in the right gene, in the right cell type, in combination with enough other drivers, it produces cancer. The mutation is the *disease mechanism*. The genetics half of this book has been preparing you for this view: mutation as error, mutation as cause of disease.

**Face 2: Mutation in a germline cell.** The mutation occurred in a cell of the gonad — a spermatogonial stem cell, an oocyte, an early embryonic precursor — that ultimately gives rise to a sperm or egg. The mutation is copied via meiosis into the gamete. If that gamete fertilizes another gamete, the resulting zygote carries the mutation in every cell. Every tissue, every organ, every cell in the new organism's body. The mutation is now part of the next generation's genome.

If the offspring reproduces, half their gametes will carry the mutation. If those gametes fertilize, the mutation is now in the third generation. With sufficient generations, this mutation either drifts to fixation (everyone in the population has it), drifts to loss (no one has it), or settles into some intermediate frequency, depending on its fitness effect and the population's demographic history.

The mutation is now *evolutionary raw material*. It is one of the alleles the next chapter (and the next five chapters) will treat as the input to selection. The same mutation, in this lineage, can drive adaptation, balanced polymorphism, speciation. It is the variation Mendel did not have a mechanism for but inferred existed; the variation Darwin needed but could not derive; the variation that the modern synthesis (Chapter 09) finally connected to both.

**The connecting machinery is the same.** Mitosis (in the somatic case) and meiosis (in the germline case) both copy DNA with high fidelity. Mutations happen at characteristic rates in both. Selection acts in both — at the cellular level in the soma; at the organismal level in the germline. The math of clonal expansion in a tumor is the math of allele frequency increase in a population — both have the form *p(t+1) = p(t) × (1 + s)* for small selection coefficients *s*, both produce exponential growth when *s > 0*, both saturate when the favored variant approaches fixation.

The differences are quantitative, not qualitative:

- *Timescale.* Somatic evolution runs over months to decades — cell generations of hours to days. Germline evolution runs over thousands to millions of generations — organism generations of years to centuries. The same dynamics, the same math, different units on the time axis.

- *Population size.* Somatic populations within a tumor or tissue are typically 10⁶ to 10¹². Germline populations of a sexual species are typically 10³ to 10⁹ effective. Population size affects how strong drift is relative to selection — small populations are more drift-dominated. But the equations are the same.

- *Heritability.* Mitotic heritability of cell phenotypes is essentially 1 (the daughter cell inherits the mother's full genome plus a few new mutations). Meiotic heritability is more complicated because of recombination — half the chromosomes come from each parent. But the *additive genetic variance* — the fraction of phenotypic variation that is heritable — can still be large.

- *Bound.* The somatic population is bounded by the body and dies with the body. The germline population is bounded only by the species' extinction.

When you build the simulator at the end of this chapter (`08-mutation-accumulation.html`), you will be writing code that tracks cells with mutations, computes selection coefficients, watches clones expand. When you write the simulator for Chapter 09 (`09-natural-selection.html`), you will be writing nearly the same code, with organisms instead of cells and generations instead of cell divisions. The simulator from this chapter is the prototype for every population-genetics simulator you will build in the chapters ahead. *The transition between the two halves of this book is the transition from "cells" to "organisms" in the simulator, with the equations unchanged.*

If you remember nothing else from this chapter, remember the following claim: **mutation in a somatic cell is the proximate cause of cancer; mutation in a germ cell is the ultimate source of evolutionary variation; the molecular event is the same in both, and the difference is decided by which lineage of cells carries the mutation forward through time.**

The genetics-evolution divide that this chapter sits on is, at the molecular level, an artificial divide. The bridge is built. The next chapter walks over it.

---

## Common misconceptions worth naming explicitly

Several student misconceptions deserve attention here.

**Misconception 1: "Most mutations are harmful."** Most mutations are *neutral*. Estimates from comparative genomics suggest that the majority of *de novo* point mutations in coding regions are weakly deleterious or neutral, and the vast majority in noncoding regions are essentially without effect. A small fraction are strongly deleterious (this is the fraction medical genetics deals with). An even smaller fraction are beneficial in some environment (this is the fraction evolutionary biology deals with). The neutral mode of mutation is the bulk of the distribution. The "harmful" framing is an artifact of which mutations get studied — medical genetics studies the harmful ones because that is the clinic's business.

**Misconception 2: "Cancer is mostly inherited."** Most cancers are not inherited in any conventional sense. Inherited cancer susceptibility syndromes — BRCA1/2, Lynch, FAP, Li-Fraumeni, retinoblastoma, von Hippel-Lindau, MEN, and so on — account for somewhere around 5–10% of all cancers [verify; figure varies by tumor type and inheritance definition]. The remaining 90–95% arise from somatic events accumulated in a particular tissue during a person's lifetime. The genetic events are real and central — cancer is genetic in the sense that genes are mutated — but the mutations almost always happened in some cell of the patient's body, not in the sperm and egg that made them.

**Misconception 3: "Mutations are random in their location."** Half right. Mutations occur randomly in the sense that the specific cell, position, and timing of each mutational event is not predictable from biology alone — it is stochastic. But the *spectrum* of mutations across a genome is far from uniform. CpG sites mutate 10-fold faster than non-CpG sites because of 5-methylcytosine deamination. Replication timing matters — late-replicating regions accumulate more mutations than early-replicating regions. Sequence context matters — APOBEC prefers TCW; UV prefers dipyrimidines. Mutation is *random in occurrence* but *non-random in spectrum*. Selection then acts to shape which mutations we observe in surviving cells or surviving organisms. The mutation pattern in a tumor or a species genome reflects the *product* of biased mutational input and selection — not pure neutral expectation.

**Misconception 4: "More mutations means more cancer."** Roughly true for the accumulation phase (each additional mutation in a dividing cell increases the chance of hitting a driver), but counterintuitively false at the tumor level once cancer is established. Tumors with extremely high mutation burdens often respond *better* to immunotherapy because they produce more neoantigens — mutant proteins that look foreign to the immune system. The MSI-high tumors of Lynch syndrome carry vastly more mutations than typical tumors, but they are also the most checkpoint-inhibitor-responsive tumors known. This is why pembrolizumab is approved for *any* MSI-high tumor regardless of organ of origin. More mutations = more cancer when you are *not yet sick*; more mutations = more treatable cancer when you *are sick*. The relationship between mutation burden and outcome flips when treatment is added.

**Misconception 5: "If you have a mutation in a cancer gene, you will get cancer."** No. Driver mutations occur in healthy tissue constantly (the Martincorena findings above). The path from "this cell now has a driver mutation" to "this person now has cancer" requires the right combination of drivers in the right cell type with the right microenvironment and the right amount of accumulated time, plus a failure of immune surveillance to clear the abnormal clone. Each step is a filter. Most driver-mutation-bearing clones do not become cancer.

---

## Exercises — graduated, end-of-chapter

### Warm-up: classify these mutations

For each of the following, classify the mutation type (point: transition/transversion; indel; chromosomal) and the protein-level consequence (silent / missense / nonsense / frameshift / in-frame / regulatory):

1. *HBB* codon 6: GAG → GTG.
2. *HBB* codon 17: AAG → TAG.
3. *CFTR* exon 11: in-frame deletion of CTT (codes for F at position 508).
4. *BRCA1* exon 11: insertion of a G after position 5382 of the cDNA.
5. *TP53* codon 175: CGC → CAC.
6. *MLL* / *KMT2A* (chromosome 11q23): translocation t(4;11) producing an *MLL-AF4* fusion in infant ALL.
7. The G→A change in the 5' splice site of *HBB* intron 1, position +1.

For each, also predict whether the change is dominant or recessive at the cellular level if it falls in a *tumor suppressor* gene versus a *proto-oncogene*.

### Application 1: per-generation mutation arithmetic

The human haploid genome is ~3 × 10⁹ bp. The mutation rate is ~1.2 × 10⁻⁸ per nucleotide per generation. A child receives two haploid copies, one from each parent, each with its own freshly-arisen mutations.

(a) How many *de novo* single-nucleotide variants does a typical child carry?

(b) Approximately what fraction of those *de novo* mutations land in coding regions, given that coding regions are ~1.5% of the genome?

(c) Of the coding *de novo* mutations, approximately what fraction would be expected to be silent, missense, and nonsense respectively, assuming a uniform distribution over the codon table (and ignoring base-composition bias)?

(d) If the father is 50 years old at conception, and the per-year additional rate is about 2 mutations per year of paternal age, how many additional mutations does this child carry compared to a child of a 25-year-old father?

### Application 2: Lynch syndrome time-to-cancer

A Lynch syndrome carrier with a germline *MSH2* frameshift has roughly a 100-fold elevated somatic mutation rate in cells where the second *MSH2* allele has been lost. Assume sporadic colorectal cancer requires the accumulation of ~5 specific driver mutations and arises with a median age of 65 in the general population (with a long latency starting in early adulthood).

(a) Holding cell division rate and selection coefficients constant, predict by how many years earlier a Lynch carrier should develop colorectal cancer on average, given the 100-fold mutation-rate elevation and the fact that cancer probability scales as the *n*-th power of the per-division mutation probability for an *n*-hit cancer.

(b) Compare your prediction to the observed median age of CRC onset in Lynch carriers (~45 years). What might account for any discrepancy?

(c) Why does the actual age-at-onset distribution have a wide spread (some carriers diagnosed at 25, others not until 70) given that all carriers have the same mutation rate elevation?

### Application 3: identify the signature

A patient's tumor has been sequenced. Whole-exome analysis returns the following mutation spectrum: ~85% of the substitutions are C→A transversions distributed broadly through the genome with no strong context preference at trinucleotide level except a slight elevation at NCC trinucleotides. ~10% are clock-like C→T at CpG. ~5% other.

(a) What is the most likely environmental exposure history for this patient?

(b) The patient denies a smoking history. What additional information would you want to know to distinguish active tobacco exposure from secondhand smoke, occupational exposure, or another C→A-producing process?

(c) If KRAS is mutated in this tumor, which specific KRAS variant would be most consistent with the signature? Why?

### Synthesis: explain why cancer is somatic evolution

In your own words, write a 300–500 word essay arguing that cancer is *literally* (not metaphorically) an evolutionary process. Your essay must:

(a) Name the three Darwinian ingredients (variation, differential reproduction, heredity) and explicitly demonstrate that each ingredient is present in a tumor cell population.

(b) Identify the unit of selection (the cell, not the organism) and the unit of fitness (proliferation and survival probability, not reproductive success of the host).

(c) Compare and contrast the timescales (months/decades vs. millennia/eons) and the population sizes (10⁶–10¹² cells vs. typically 10³–10⁹ organisms) of somatic and germline evolution.

(d) Identify at least one prediction the somatic-evolution framework makes that would be hard to derive from a non-evolutionary view of cancer (hint: think about therapy resistance, or about why hereditary cancer syndromes affect specific tissues, or about why immunotherapy works better in MSI-high tumors).

### Challenge: where does the somatic-evolution analogy break?

The framing "cancer is evolution in fast-forward" illuminates a great deal but is not a complete theory. Identify at least three ways in which somatic evolution differs from "ordinary" Darwinian evolution at the species level, and argue whether each difference is a *quantitative* difference (same machinery, different parameter values) or a *qualitative* difference (genuinely different process at a mechanistic level). Possible angles include:

- Recombination — somatic cell populations are largely clonal; sexual organisms shuffle genomes every generation.
- Bound on the population — the tumor is trapped inside the host and dies with the host (except for the very rare transmissible cancers).
- Selection landscape — the body imposes a particular set of selective pressures that does not directly correspond to species-level selective pressures.
- Time horizon — somatic evolution does not need to produce a self-sustaining lineage; an "evolutionary dead end" is the *normal* outcome.

Defend your reading. There is no one right answer; the point is to make the argument carefully.

---

## What student builds: `08-mutation-accumulation.html`

The simulator for this chapter is a mutation-accumulation and cancer-evolution model. The brutalist palette and per-chapter conventions are documented in Chapter 00.

**Controls (sliders):**
- Cell division rate (divisions per month per stem cell).
- Base per-division mutation rate (typical values: 3 × 10⁻⁹ per bp baseline; 3 × 10⁻⁷ for MMR-deficient; ~10⁻⁸ for high-smoker lung).
- Selection coefficient for driver mutations (additional fitness per driver: 0% = neutral, 20% = strong; cumulative across drivers).
- Number of driver mutations required for "cancer" threshold (default 5).
- Total simulation time (years of life).
- Number of independent runs to average for the time-to-cancer distribution.

**Display:**
- A single stem cell at top, drawn with no colored marks.
- As cell divisions occur, daughter cells are drawn below, each with a number of colored dots equal to its accumulated mutations (passenger mutations in gray, driver mutations in red).
- When a cell accumulates the driver threshold, its lineage is highlighted in red and "cancer" is declared.
- Plotted alongside: time-to-cancer distribution across many runs, as a histogram.
- Annotation panel: shows the *expected* time-to-cancer from the user's chosen parameters, alongside the *observed* distribution from the simulation. The two should match within Monte Carlo error.

**Pedagogical sliders to explore:**
- Set the mutation rate to baseline; record the median time-to-cancer (should be very long — most simulations don't reach cancer in 80 years).
- Multiply the mutation rate by 100 (Lynch syndrome). Time-to-cancer compresses dramatically.
- Multiply the mutation rate by 5 (heavy smoker, lung tissue). Time-to-cancer compresses substantially but less dramatically.
- Vary the selection coefficient: with strong selection (large *s*), the few driver-carrying clones expand quickly and the rest of the simulation has more chances for further drivers; with weak selection, drift dominates.
- Vary the number of driver mutations required: cancers requiring 3 drivers (pediatric-like) emerge much earlier than cancers requiring 7 drivers (smoking-related lung).

The simulator is the prototype for population-genetics simulators in Chapters 9–14. The code structure — many independent lineages, mutations accumulated each generation, selection coefficients applied each generation, statistics over runs — will recur. When you build the natural selection simulator in Chapter 09, you are reusing this scaffolding, with "organisms" in place of "cells" and "generations" in place of "cell divisions."

---

## Chapter summary

I will collect the chapter's claims as a short list of what you should now be able to do.

1. *Classify* a given mutation by its scale (point / indel / chromosomal) and, when it falls in a coding region, by its protein consequence (silent / missense / nonsense / frameshift).
2. *Explain* the origin of any specific mutation: spontaneous chemistry (replication error, depurination, deamination, tautomeric shift) or induced damage (chemical / physical / biological mutagens). Name the specific mechanism for each.
3. *Quote* order-of-magnitude mutation rates: ~10⁻⁶ per site per replication in RNA viruses; ~10⁻¹⁰ per bp per generation in bacteria; ~10⁻⁸ per nucleotide per generation in humans; ~70 *de novo* SNVs per human child.
4. *Apply* Knudson's two-hit hypothesis to predict bilaterality, age of onset, and family-history patterns of hereditary cancers, and *work* the underlying arithmetic in your head.
5. *Distinguish* dominantly-acting one-hit proto-oncogenes from recessively-acting two-hit tumor suppressors, and *explain* why the dominance asymmetry follows from gene function rather than convention.
6. *Walk* the Fearon–Vogelstein multi-step colorectal cancer progression, name the order of driver hits, and quote the timeline.
7. *Read* a tumor's mutational signature spectrum and *infer* the likely environmental exposure (tobacco, UV, APOBEC, MMR deficiency, HR deficiency).
8. *State* the three Darwinian ingredients and *demonstrate* their presence in a cell population, justifying the claim "cancer is somatic evolution" as a literal claim rather than a metaphor.
9. *Build* the mutation accumulation simulator and *predict* how varying the mutation rate or selection coefficient changes the time-to-cancer distribution before running the simulation.
10. *Articulate* the bridge claim of this chapter — that mutation in a somatic cell is disease mechanism, mutation in a germ cell is evolutionary raw material, and the molecular event is the same in both — with at least one example for each face.

---

## Bridge to Chapter 9

The next chapter walks across the bridge. It begins with Darwin's mechanism of natural selection — the conditions that make evolution possible, the evidence that it has occurred, the modern synthesis that connected Darwin to Mendel through population genetics. Almost every claim in Chapter 9 will use mutation as the *input* to evolutionary processes. You will recognize the input. You have just spent a chapter inside it.

The population-genetics chapter that follows (Chapter 10) will work the math of Hardy-Weinberg and the deviations from it caused by selection, drift, mutation, gene flow, and non-random mating. The mutation force in those equations is the same *μ* you used in the Knudson math above and in the mutation-accumulation simulator. The selection coefficient *s* you set in the simulator is the same *s* you will use in Wright-Fisher allele frequency dynamics. The math does not change. What changes is which level of biological organization the math is being applied to.

You will return to this chapter again at the end of Chapter 14 (the capstone), when the somatic-evolution framing reappears as the bridge that makes cancer one of the cleanest "evolution in action" stories in modern biology — alongside antibiotic resistance, peppered moths, Darwin's finches, and the Lenski long-term evolution experiment. Cancer joins the canon there. You met it here first.

---

## What would change my mind

If a careful re-analysis of pan-cancer whole-genome data showed that the apparent dominance asymmetry between oncogenes and tumor suppressors is an artifact of detection bias (e.g., we sequence missense in oncogenes more than nonsense in tumor suppressors because of selection on tumor cells in vivo, not because the underlying genetic logic of dominance is what I claim), I would have to re-write the dominance section of this chapter. The Mendelian-logic argument I made depends on the empirical pattern holding up; if it doesn't, the explanation collapses.

## Still puzzling

I do not yet fully understand why some clonal expansions in normal tissue (NOTCH1+ esophageal clones, TP53+ skin clones) appear to *reduce* the risk of overt cancer in the same tissue, when the same mutations in different contexts are clear cancer drivers. The "fitness landscape with multiple peaks" framing names the phenomenon without explaining it. Understanding why clone X stays benign while clone Y in the same tissue becomes invasive is, I think, the next big open problem at the intersection of somatic evolution and cancer biology.

---

**Tags:** mutation, cancer-genetics, somatic-evolution, two-hit-hypothesis, mutational-signatures, Lynch-syndrome, retinoblastoma, clonal-evolution, multi-step-carcinogenesis, bridge-chapter
