# Chapter 13 — Molecular Evolution and Evo-Devo: How Sequences Change and How Bodies Get Built From the Same Toolbox

**Suggested titles:**
- *Sticklebacks Lose Their Spines, Lake After Lake, Always at the Same Address — Why Most Morphological Evolution Hides in Regulatory DNA*
- *Kimura's Cancellation, Carroll's Toolkit, and the Sentence Mary-Claire King Got Right in 1975 With Almost No Data*
- *Hox, Hitchhiking, and Histones — A Tour of the Molecular Machinery That Runs Along the Branches of Chapter 12's Tree*

---

**TL;DR.** Chapter 12 built the tree from sequence data, treating the molecular clock as an instrument. This chapter opens the instrument. The first half walks the machinery of molecular evolution — Kimura's neutral theory (which says the rate at which neutral substitutions get fixed equals the mutation rate, with population size cancelling out of the algebra in three lines), the dN/dS ratio (which uses synonymous substitutions as a neutral baseline and nonsynonymous substitutions as the thing selection actually sees, with the ratio of the two reading out whether a gene is constrained, drifting, or being pushed to change), selective sweeps (which carve diversity valleys around beneficial mutations as they hitchhike to fixation), transposable elements (which look like genomic parasites and have repeatedly been domesticated into placentas, immune systems, and tissue-specific enhancers), and gene duplication (which buys the genome a free copy to play with). The second half walks the developmental side — Hox genes whose protein-coding sequence is so conserved that a human HoxB6 can replace its fly counterpart and the fly still patterns its body, but whose regulatory deployment differs from segment to segment and from phylum to phylum and explains why a fly is not a centipede and a snake is not a lizard; toolkit signaling pathways (Wnt, Notch, Hedgehog, BMP, FGF) reused across animals; the modularity of enhancers that lets a single tissue lose a gene's expression without losing it everywhere; heterochrony and heterotopy as the two levers — change in time, change in place — by which regulatory evolution edits morphology. The two halves close together on what Mary-Claire King and Allan Wilson saw in 1975 with no genome and three sentences of intuition: *evolutionary changes in anatomy are more often based on changes in the mechanisms controlling the expression of genes than on sequence changes in proteins.* The worked example takes one well-known protein — FOXP2 — and runs the full dN/dS calculation on the human-chimp comparison, computes the ratio, walks the original Enard 2002 "selective sweep on the human lineage" reading, then walks the Atkinson 2018 reanalysis that says the signal is weaker than first reported, and ends by naming what dN/dS as a tool can and cannot do. The chapter's deep-dive is the stickleback pelvic spine story — *Pitx1* enhancer deletions in dozens of independent freshwater populations, the same morphological outcome at the same regulatory address by different specific mutations — because it ties together the molecular, the regulatory, and the morphological at the same time on one fish. By the end you should be able to compute dN/dS from a small alignment, interpret it for at least four gene classes, predict whether a given morphological difference between species is more likely encoded in a coding change or in a regulatory change, name what neutral theory does and does not claim, and explain why the protein-coding sequence of a Hox gene can be virtually unchanged from a fly to you while still being centrally responsible for the difference between a fly's body and yours.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **State** Kimura's neutral theory in plain language and **derive** the rate-equals-mutation-rate result (`K = 2N_e μ × 1/(2N_e) = μ`) on the page, naming where each factor comes from.
2. **Distinguish** the strict neutral theory (Kimura 1968) from the nearly-neutral theory (Ohta 1973, 1992), and **explain** why small effective population size lets slightly-deleterious mutations accumulate.
3. **Define** synonymous and nonsynonymous substitutions, compute `dN` and `dS` from a small alignment by hand, and **interpret** the `dN/dS` ratio for at least four classes of gene (histones, MHC, HIV envelope, an inactivated pseudogene).
4. **Describe** the signature of a selective sweep in linked sequence diversity, **predict** its width given selection coefficient and recombination rate, and **explain** why selective sweeps are easier to detect when they are recent and strong.
5. **Define** transposable elements; **name** the two dominant classes in the human genome (L1, Alu); and **list** at least three documented exaptations (syncytin, V(D)J/RAG, ERV-derived interferon enhancers).
6. **Distinguish** three fates of a duplicated gene (pseudogenization, subfunctionalization, neofunctionalization), and **trace** the hemoglobin family as a worked example of duplication-plus-divergence over deep time.
7. **State** the conservation property of Hox proteins (homeobox virtually unchanged across animal phyla) and the collinearity property of Hox clusters (chromosomal order matches body-axis expression order).
8. **Define** *cis*-regulatory element, enhancer, and modularity, and **explain** in mechanism why modular regulatory architecture lets evolution change one tissue's expression without disrupting others.
9. **Define** heterochrony and heterotopy and **identify** which mode of regulatory change each refers to.
10. **Explain** the stickleback pelvic spine loss case at the level of the *Pitx1* pelvic enhancer, and **state** why repeated loss in independent freshwater populations is evidence for regulatory evolution rather than coding-sequence evolution.
11. **State** what King and Wilson (1975) proposed about the relative contribution of regulatory versus protein-coding changes to morphological evolution between humans and chimpanzees, and **summarize** where the field's current consensus sits on Carroll's strong "regulatory primacy" reading versus the Hoekstra-Coyne (2007) pushback.
12. **Build** `13-molecular-evolution.html` — a two-panel simulator that (a) accumulates synonymous and nonsynonymous substitutions in evolving sequences under tunable mutation rate and selection, reports `dN/dS` in real time, and visualizes a sweep when a beneficial nonsynonymous variant arises; and (b) shows how shifting one Hox boundary on a vertebrate-style body plan produces a discrete morphological change while a protein-coding knockout of the same gene produces developmental failure.
13. **Name** at least three common student misconceptions about molecular evolution and evo-devo and **explain** what is mechanistically wrong with each.

**Prerequisites.** Chapter 8 introduced mutation as the raw material; you need transition vs. transversion, frameshift vs. point, and germline vs. somatic from that chapter. Chapter 9 introduced the selection coefficient and the meaning of fixation; we will use both as if known. Chapter 10 introduced effective population size *N\_e* and the cancellation `2N_e × 1/(2N_e) = 1` that we will run again here for the neutral-theory derivation. Chapter 11 introduced reproductive isolation and the molecular barriers to gene flow; we will quote a couple of positive-selection examples (sperm-egg recognition proteins, sea urchin bindin) from that chapter without re-deriving. Chapter 12 introduced the molecular clock, the Jukes-Cantor distance correction, and the tree-building methods — all of which we will use as known machinery. You need to be comfortable with `ln`, with elementary probability (the per-generation fixation probability is `1/(2N_e)`), and with reading a codon table. No prior exposure to developmental biology is assumed; the Hox section is built from scratch.

---

## A fish that lost its spines in a thousand lakes, always at the same address

Three-spined sticklebacks (*Gasterosteus aculeatus*) are small armored fish about the length of a thumb. The marine form, which still lives in the cold coastal waters of the northern hemisphere, carries a pair of bony **pelvic spines** projecting downward from the body wall like a folding switchblade. A piscivorous fish trying to swallow a stickleback gets a mouthful of spines. The armor is expensive in calcium and drag but pays off in survival; marine sticklebacks have carried it for millions of years.

After the last ice age, marine sticklebacks repeatedly colonized newly-formed freshwater lakes across the northern hemisphere — Iceland, British Columbia, Alaska, Scotland, the lakes of the Baltic — and in many of these lakes the pelvic spines were lost. Not loosely lost, not partially lost. *Lost.* Some lake populations have only a vestigial pelvic girdle; some have nothing at all. The pattern recurs across continents on a time scale of roughly the last 10,000 to 15,000 years. Once you know to look for it, the same morphological change shows up in lake after lake, on different continents, in genetically distinct fish stocks.

The standard evolutionary reading of this pattern is straightforward. In freshwater, the piscivorous fish predators that the pelvic spines defend against are largely absent; the dominant predators are invertebrates (dragonfly larvae, predaceous diving beetles) that *prefer* prey with grippable spines they can latch on to. Selection has reversed direction. Calcium is also scarce in many freshwater lakes, so the metabolic cost of building bony armor matters more. The spines stop being useful and start being expensive, and the fish that happen to be born without them outreproduce the fish that have them. This is textbook adaptation by natural selection. But it leaves the molecular question open: *what mutation produces a spineless stickleback?*

David Kingsley's lab at Stanford set out to answer this in the early 2000s by crossing marine and freshwater sticklebacks and mapping the trait through their offspring. The phenotype mapped to a single major-effect locus on the chromosome carrying a gene called ***Pitx1*** — a transcription factor known from mouse and chick work to be essential for hindlimb and pelvic-region development in tetrapods. Sequencing the *Pitx1* coding region in marine and freshwater fish came back with a result that probably surprised the authors. *The protein-coding sequence of Pitx1 was identical between the spine-bearing marine fish and the spineless freshwater fish.* Whatever had changed, it was not the protein.

The change was a few thousand base pairs upstream, in a non-coding region containing a tissue-specific **enhancer** — a stretch of regulatory DNA that drives *Pitx1* expression specifically in the developing pelvic region of the embryo. In the freshwater fish, this enhancer was *deleted*. Pitx1 protein still got made everywhere else it needed to be — in the jaw, in the pituitary, in the developing fins — because the enhancers controlling those expression domains were intact. But Pitx1 protein no longer got made in the pelvic primordium. With no Pitx1 expression there, the pelvic structures failed to develop, and the spines never formed (Shapiro MD, Marks ME, Peichel CL, Blackman BK, Nereng KS, Jónsson B, Schluter D, Kingsley DM. 2004. "Genetic and developmental basis of evolutionary pelvic reduction in threespine sticklebacks." *Nature* 428:717–723; [DOI 10.1038/nature02415](https://www.nature.com/articles/nature02415); PMID 15085123).

That alone would be a beautiful story. The remarkable part came next. Chan and colleagues sequenced the pelvic enhancer region across many different freshwater populations on different continents and found *different specific deletions* in different lakes — each independently knocking out the same regulatory element (Chan YF, Marks ME, Jones FC, Villarreal G Jr, Shapiro MD, Brady SD, et al. 2010. "Adaptive evolution of pelvic reduction in sticklebacks by recurrent deletion of a Pitx1 enhancer." *Science* 327:302–305; [DOI 10.1126/science.1182213](https://www.science.org/doi/10.1126/science.1182213)). One lake's fish solved the problem with a 1.5-kilobase deletion; another lake's fish solved it with a 600-base-pair deletion; a third lake's fish solved it with a deletion of a slightly different boundary. *The address was the same. The specific letters that got removed were different.* Convergent regulatory evolution at one regulatory element, mediated by the local chromosomal architecture (the locus turns out to sit in a fragile region prone to double-strand breaks) and driven by the strong shared local selection pressure.

I want you to hold this case in mind for the entire chapter, because it answers in one example almost every question the chapter has to ask. *What kinds of DNA changes matter for morphological evolution?* Often regulatory, not protein-coding. *How can selection produce the same phenotype repeatedly?* By attacking the same regulatory element with different specific mutations. *Why doesn't the change have catastrophic side effects?* Because the modularity of enhancers means losing one tissue-specific element doesn't disrupt the others. *Why is the protein conserved if so much evolution happens here?* Because the protein still does the same molecular job — binding the same DNA sequences in the jaw, the pituitary, the fins — and only its deployment to one tissue has been edited away.

The chapter unpacks each of these. First the molecular machinery of how DNA sequences evolve, then the developmental machinery of how regulatory changes turn into morphology, and finally how the two halves meet. The stickleback will return at the end as the cleanest demonstration of the unified picture.

---

## Part 1 — How DNA sequences evolve

### Kimura's neutral theory — what it actually claims

The neutral theory is, in my experience, the most misremembered idea in evolutionary biology. Students remember it as "evolution is mostly neutral," which is both vague and partly wrong, or as "Kimura said natural selection doesn't matter," which is wrong twice. The actual claim is narrower, sharper, and more interesting.

In 1968 Motoo Kimura published a five-page paper in *Nature* titled "Evolutionary rate at the molecular level" (Kimura M. 1968. *Nature* 217:624–626; [DOI 10.1038/217624a0](https://www.nature.com/articles/217624a0); PMID 5637732). The argument went roughly like this. By the mid-1960s, sequence comparison of the same protein across species — hemoglobin in different mammals, cytochrome c in different vertebrates, fibrinopeptides across many taxa — was producing a striking pattern. Each protein accumulated amino acid changes at a roughly constant rate per year, across very different lineages, over hundreds of millions of years. Zuckerkandl and Pauling had called this the "molecular clock" and noted that the constancy was hard to reconcile with the standard Darwinian picture in which substitutions get fixed because they are beneficial in particular environments. Different lineages live in different environments; why would the rate be constant?

Kimura's resolution: maybe most of the substitutions aren't beneficial. Maybe most of them are *neutral* — neither beneficial nor harmful — and they go to fixation by genetic drift, the random sampling process you met in Chapter 10. If so, the fixation rate would be set by mutation, not by environment, and the clock would tick at roughly the same rate everywhere.

Here is the algebra. It is three lines and it is one of the cleanest results in population genetics.

Take a diploid population of effective size *N\_e*. Each individual has two copies of each gene, so the total number of gene copies in the population is `2N_e`. Let the per-gene mutation rate per generation be μ. Then the number of new mutations entering the population each generation is:

```
new mutations per generation = 2N_e × μ
```

Each new mutation starts at frequency `1/(2N_e)` — a single copy among 2*N\_e*. If the mutation is selectively neutral, its eventual fate is decided entirely by drift, and from Chapter 10 you know that the probability a neutral allele eventually goes to fixation by drift equals its current frequency. So:

```
P(any specific new neutral mutation fixes) = 1/(2N_e)
```

The rate at which neutral mutations *go to fixation* in the population per generation is therefore the rate at which they enter times the probability each one eventually fixes:

```
K = 2N_e × μ × 1/(2N_e) = μ
```

The two `2N_e` factors cancel exactly. **The rate at which neutral molecular evolution proceeds equals the mutation rate.** It does not depend on population size. It does not depend on environment. It does not depend on selection — by assumption, there is none on neutral sites. This is the result that explains the molecular clock. Different lineages tick at the same rate because the rate is set by mutation, which is broadly similar across closely related lineages, not by environment, which differs.

Several things follow that are easy to miss.

**The neutral theory is a null model, not a denial of adaptation.** Adaptive evolution at the molecular level is real — sometimes a beneficial mutation arises and is driven to fixation by positive selection, and the fixation rate for those mutations is *not* `μ`. But the neutral theory says: most substitutions you see in a genome are neutral, and you should not invoke selection without evidence. The burden of proof falls on the claim that requires more, which is the same logical posture Popper recommends for any scientific hypothesis. When someone says "this gene shows positive selection," that is a claim *against* the neutral expectation, and it needs evidence.

**"Neutral" is conditional, not absolute.** A nucleotide change is neutral *in the current environment, at the current population size, against the current genetic background*. Change any of those and a previously neutral site can become selected. The neutral theory's empirical claim is that, summed over the genome and over time, neutral substitutions dominate the fixation record — not that selection is rare in some absolute metaphysical sense.

**"Nearly neutral" is the modern refinement.** Tomoko Ohta proposed in the 1970s and developed across decades (Ohta T. 1973. *Nature* 246:96–98; Ohta T. 1992. *Annu Rev Ecol Syst* 23:263–286; [Annual Reviews link](https://www.annualreviews.org/doi/10.1146/annurev.es.23.110192.001403)) that many mutations are not strictly neutral but **slightly deleterious** — they have a small negative selection coefficient *s* on the order of `1/N_e`. For these, drift and weak selection both matter, and the population-size dependence comes back. Small populations fix slightly-deleterious mutations more often than large populations do, because in small populations drift can overwhelm the weak negative selection. This is part of why island-endemic species, parasites with small effective population sizes, and lineages that have gone through bottlenecks tend to accumulate deleterious mutation loads — the **nearly-neutral theory** says small *N\_e* is its own genetic hazard.

A clean teaching framing I want to give you: *the neutral theory wins the methodological battle even when it loses individual cases.* It is the null hypothesis against which every claim of "selection acted here" must be tested. Adaptive evolution exists; demonstrating it in a specific case requires evidence beyond what the neutral expectation predicts.

### dN/dS — measuring selection by exploiting the genetic code

Most of what is interesting about selection on a protein-coding gene comes out of one structural feature of the genetic code, which is that the code is **degenerate**. Sixty-four codons encode twenty amino acids plus a stop. The redundancy is not uniform — leucine has six codons, methionine has one, most amino acids have two to four — but on average, a single random nucleotide change at a random position in a random codon has roughly a 1-in-4 chance of being silent at the amino-acid level. The codon `GAA` and the codon `GAG` both encode glutamic acid; a substitution at the third position changing `GAA` to `GAG` doesn't change the protein at all.

A substitution that doesn't change the encoded amino acid is called a **synonymous substitution** (sometimes "silent"). A substitution that does change the amino acid is called a **nonsynonymous substitution** (sometimes "replacement"). The two categories are different things to natural selection. Selection can see a nonsynonymous substitution through the function of the changed protein — the new amino acid might affect folding, binding, catalysis, stability. Selection generally cannot see a synonymous substitution, because the protein produced is identical. Synonymous sites are therefore, to a good first approximation, **selectively neutral**, and they act as a kind of internal control — the rate at which they accumulate substitutions tells you what neutral evolution looks like in this gene.

For a given protein-coding gene compared between two species (or two lineages), you compute:

- **dS** = number of synonymous substitutions per synonymous site
- **dN** = number of nonsynonymous substitutions per nonsynonymous site

The "per site" normalization matters. Different codons have different numbers of synonymous-vs-nonsynonymous *opportunities* — the third position of a leucine codon has up to three synonymous changes available, while the second position of any codon almost always has only nonsynonymous changes available. A raw count of substitutions wouldn't be comparable across codons. The Nei-Gojobori method and Yang's maximum-likelihood methods (PAML) handle this bookkeeping carefully. The conceptual review is Yang Z and Bielawski JP. 2000. "Statistical methods for detecting molecular adaptation." *Trends Ecol Evol* 15:496–503; [DOI 10.1016/S0169-5347(00)01994-7](https://www.sciencedirect.com/science/article/pii/S0169534700019947).

The interpretive rule:

- **dN/dS ≈ 1 → neutral evolution.** Nonsynonymous changes accumulate about as fast as synonymous ones, which means selection isn't filtering them out and isn't pushing them in. Rare for functional protein-coding genes; common in **pseudogenes** that have lost their function and are now free to drift.
- **dN/dS < 1 → purifying (negative) selection.** Most nonsynonymous changes get eliminated because they disrupt function. This is the *modal* pattern for protein-coding genes — most genes most of the time are under purifying selection. Strongly constrained genes (histones, ribosomal proteins, cytochrome c, the Hox homeodomains) sit at dN/dS values around 0.01 to 0.1 — fewer than one in ten nonsynonymous opportunities makes it through the filter.
- **dN/dS > 1 → positive (Darwinian) selection.** Beneficial amino acid changes are being fixed faster than neutral synonymous ones can drift in. This is *rare* over whole genes — even genes well known to be under positive selection usually show dN/dS > 1 only over specific codons or specific branches of the tree. Branch-and-site models in PAML partition the gene and the tree to detect localized episodes that an average-over-everything analysis would miss.

A few clean examples are worth naming because they show the spectrum.

**Histones (H3, H4).** Among the most conserved proteins known. H4 differs by only two amino acids between cows and peas — separated by roughly 1.5 billion years of evolution. The dN/dS for H4 between any pair of mammals is essentially zero; the protein has no room to change because the histone-DNA wrapping geometry is unforgiving. This is purifying selection at its strongest.

**Cytochrome c.** Margaret Dayhoff's pioneering protein-sequence atlas in the 1960s used cytochrome c precisely because it changes slowly enough to align across most of life. dN/dS between rat and human cytochrome c is around 0.05. The protein is under strong purifying selection — almost every nonsynonymous change is eliminated — but enough have been allowed through over hundreds of millions of years to make the molecular clock readable.

**HIV envelope (Env / gp120), V3 loop.** Within a single infected patient, the V3 loop of the HIV envelope protein evolves to escape host antibody responses. The dN/dS at the V3 codons is often well above 1, sometimes above 5. The antibody-targeted epitope is being actively pushed away from whatever shape the immune system has just learned to recognize. This is positive selection at its strongest, happening inside one person's bloodstream on a scale of months.

**MHC class I and II peptide-binding sites.** The antigen-recognition residues of MHC class I and II proteins show dN > dS — Hughes & Nei (1988) *Nature* 335:167–170 was the foundational paper. The pattern is consistent with **balancing selection** in which heterozygotes — individuals carrying two different MHC alleles and therefore presenting a broader range of peptides to T cells — are favored, sustaining many alleles at intermediate frequencies. Plus there is positive selection at the peptide-binding residues themselves, where any change that lets the MHC bind a peptide the local pathogen population is not yet equipped to evade is favored. The MHC region is one of the most polymorphic regions of any mammalian genome.

**Sperm-egg recognition proteins.** Lysin in abalone, bindin in sea urchins, ZP3 in mammals. The proteins that mediate the species-specific binding between sperm and egg show strong dN/dS > 1, driven by sexual conflict, reinforcement of species barriers between incipient species pairs, and the rapid co-evolution of egg-coat receptors and sperm-protein ligands within species. Swanson & Vacquier 2002 *Nat Rev Genet* 3:137–144 reviewed the pattern.

**Olfactory receptors.** A large gene family with rapid turnover. Humans have about 400 functional olfactory receptors and another 600 pseudogenes — the pseudogenes have dN/dS near 1 because they no longer encode functional proteins and selection no longer cares what they do. The contrast between the functional receptors (dN/dS < 1) and the pseudogenes (dN/dS ≈ 1) in the same gene family is one of the cleanest demonstrations that dN/dS responds to actual function. Niimura & Nei 2007 *PLoS ONE* 2:e708.

Before we move on, three honest caveats the chapter has to make explicit, because they catch students:

1. **dN/dS > 1 over a whole gene is uncommon even for genes "under positive selection."** Most positive selection acts on a handful of codons on specific branches. Averaging over the entire gene drowns the signal. Branch-and-site tests are the modern refinement.
2. **dS is not strictly neutral.** Codon-usage bias affects translation speed and protein folding; some synonymous changes alter splicing or mRNA stability; synonymous sites caught up in a sweep at a linked nonsynonymous site can have their diversity reduced by hitchhiking. Treat dS as a *practical* neutral baseline, not a metaphysical one.
3. **Demography can mimic selection.** A population bottleneck followed by expansion can produce haplotype patterns that look like a selective sweep. Modern selection tests (composite likelihood ratio, iHS, XP-EHH) work hard to separate demography from selection, and several early-2000s "human selective sweep" claims did not survive that test once better demographic models were available.

The summary sentence I want you to memorize: *dN/dS is the answer to a single question — among the substitutions that have already gone to fixation, what fraction changed the protein? The answer tells you whether the protein has been free to drift, forced to stay still, or pushed to change.*

### Selective sweeps — the local signature of positive selection

When a beneficial mutation arises in a population and is driven to fixation by positive selection, it does not arrive alone. The mutation sits on a specific chromosome at a specific location, and the rest of that chromosome — the alleles at nearby loci on the same haplotype — comes along for the ride. As the beneficial allele rises in frequency, the alleles it sits next to also rise in frequency, simply because they have not yet been broken up by recombination. The hitchhiking allele pile-up was named by Maynard Smith and Haigh in their classic paper (Maynard Smith J, Haigh J. 1974. "The hitch-hiking effect of a favourable gene." *Genet Res* 23:23–35).

The result is a **selective sweep**: a local valley of reduced polymorphism around the selected site, embedded in a sea of normal genetic diversity. The width of the valley scales with the strength of selection and the local recombination rate. Stronger selection drives the beneficial allele to fixation faster, and the faster the rise, the less time recombination has to break up the linked haplotype. A strong sweep at low recombination rate carves a wide, deep valley; a weak sweep at high recombination rate carves a narrow shallow one.

Two flavors matter for the chapter.

**Hard sweep.** A single new beneficial mutation rises to fixation. The local signature is dramatic: a long shared haplotype around the selected site reaching high frequency in the population, elevated linkage disequilibrium between nearby loci, and a dip in nucleotide diversity. The lactase persistence sweep in northern Europeans is a textbook example. A single regulatory variant (the −13910*T mutation in the *MCM6* gene upstream of *LCT*) appears on a long shared haplotype reaching roughly 80% frequency in northern Europeans, with the sweep dated to the last 5,000–10,000 years (Bersaglieri et al. 2004 *Am J Hum Genet* 74:1111–1120).

**Soft sweep.** Selection acts on standing variation — an allele that was already polymorphic in the population before becoming favored — or on multiple independent mutations rising in parallel. The local signature is less dramatic; multiple haplotypes carry the favored allele, no single long shared haplotype dominates, and the diversity dip is shallower or absent. Soft sweeps are harder to detect but probably more common in many contexts than hard sweeps (Pritchard JK, Pickrell JK, Coop G. 2010. "The genetics of human adaptation: hard sweeps, soft sweeps, and polygenic adaptation." *Curr Biol* 20:R208–R215).

For the simulator you will build, the point lands cleanly. When a beneficial nonsynonymous variant arises and the selection coefficient is strong, the simulator will show that variant rising to fixation rapidly while other variation in the simulated lineage has not had time to drift in. The result is a flat region around the swept site. This is the genome-scan signature in miniature; the same logic, applied to real human population data, is how lactase persistence, malaria-resistance alleles, the EDAR variant in East Asians, and EPAS1 in Tibetans were identified.

The honest caveat, again: a "positive selection" call from a selective-sweep signature is a *hypothesis*, not a *measurement*. The earliest genome-scan claims of human selective sweeps in the 2000s were often built on demographic models that have since been refined; reanalysis with better models has weakened or overturned a number of those calls. Some sweeps are robust (lactase persistence is solid; the malaria-resistance loci are solid). Others, including some originally claimed for PCSK9 and a few other cardiovascular and immune loci, did not survive better demographic modeling and are now interpreted as bottleneck-and-expansion artifacts rather than selection. The field corrects itself, but the lesson for the student is that the methodology requires care, not just a script.

### Highly conserved versus rapidly evolving — the spectrum

Different gene classes occupy different positions on the dN/dS spectrum, and the position is a measurement of *what the function tolerates*. The pattern is consistent enough that you can predict where a gene will sit if you know what it does.

**Strongly constrained (dN/dS ≪ 1).** Histones; ribosomal RNAs (used by Woese, as Chapter 12 set up, precisely because they conserve enough to align across all three domains); the homeodomain of Hox proteins (more on this in Part 2); cytochrome c; actin; tubulin. These genes encode molecular machines whose function depends on tight three-dimensional geometry, and most amino acid substitutions break the geometry.

**Moderately constrained (dN/dS around 0.1–0.5).** Most metabolic enzymes; most transcription factors away from their DNA-binding domain; most signaling proteins away from their active sites. Selection eliminates many but not all nonsynonymous changes.

**Rapidly evolving (dN/dS approaching or exceeding 1).** Immune system genes facing Red Queen pressure (MHC, antibody V regions, antiviral restriction factors like TRIM5α and APOBEC3G — Sawyer et al. 2005 *PLoS Biol* 3:e275); sperm-egg recognition proteins; some duplicated genes immediately after duplication during their window of relaxed purifying selection; and the pseudogenes that result when one duplicate copy loses function entirely.

The clean teaching frame: a gene's position on this spectrum tells you about its function. Histones tolerate almost nothing because the wrapping geometry is unforgiving. Olfactory receptors tolerate almost anything because losing one is offset by the other 400. Immune receptors are *required* to change because the pathogens are changing.

### Transposable elements — selfish DNA that the genome has repeatedly domesticated

About 45–54% of the human genome consists of recognizable transposable elements — DNA sequences that can move from one chromosomal location to another (International Human Genome Sequencing Consortium 2001 *Nature* 409:860–921 for the original 45% figure; Hoyt SJ, Storer JM, Hartley GA, et al. 2022. *Science* 376:eabk3112 for the T2T-CHM13 telomere-to-telomere assembly that pushed the estimate to ~54% by counting previously unalignable repeats; [DOI 10.1126/science.abk3112](https://www.science.org/doi/10.1126/science.abk3112)). Two classes dominate in humans:

**LINE-1 (L1).** Long interspersed nuclear element. About 17% of the genome. An *autonomous* retrotransposon — it encodes its own reverse transcriptase and endonuclease, which is enough machinery to copy itself out as RNA, reverse-transcribe back to DNA, and insert the copy somewhere else in the genome. Some L1s are still active in human germ cells today, occasionally producing disease — an L1 insertion into the factor VIII gene was the first documented case of de novo retrotransposition causing human disease (Kazazian et al. 1988 *Nature* 332:164–166).

**Alu.** A primate-specific SINE (short interspersed nuclear element), about 300 base pairs long, with roughly a million copies in the human genome (~11% of the total). Alu is *non-autonomous* — it can't move on its own, but it borrows L1's reverse transcriptase to retrotranspose. Alu elements are derived from a signal recognition particle RNA that got captured into the genome and turned into a copyable insertion.

The reflex many students bring in is that all this "junk DNA" is, well, junk. The actual picture is more interesting and now well-established. The current consensus paper is Chuong EB, Elde NC, Feschotte C. 2017. "Regulatory activities of transposable elements: from conflict to benefit." *Nat Rev Genet* 18:71–86; [DOI 10.1038/nrg.2016.139](https://www.nature.com/articles/nrg.2016.139); PMID 27867194. The argument: transposable elements look like genomic parasites — and many of them are, at the moment of insertion — but the genome has *repeatedly* exapted (co-opted) them for useful function. Three exaptations are worth naming because each is a textbook case.

**Syncytin and the placenta.** Placental mammals form a fused multinucleated layer of trophoblast cells called the **syncytiotrophoblast** at the maternal-fetal interface. The fusion is mediated in humans and great apes by a protein called **syncytin-1**, encoded by *ERVW-1* — and *ERVW-1* is the **envelope gene of a human endogenous retrovirus**. The gene is an old retroviral envelope sequence that the host genome captured, lost the rest of the virus around, and put to work. Retroviral envelope proteins naturally encode fusogenic activity (it is what the virus uses to fuse with target cell membranes during infection); the mammalian placenta needed a cell-fusion machinery, and rather than evolving one from scratch, it co-opted a retroviral one floating around in the genome (Mi S, Lee X, Li X, et al. 2000 *Nature* 403:785–789; [DOI 10.1038/35001608](https://www.nature.com/articles/35001608)).

The remarkable part is the comparative pattern. Different placental mammal lineages have **independently captured different ERV envelope genes for the same function**. Humans and great apes use syncytin-1 (HERV-W family) and syncytin-2 (HERV-FRD family). Mice use syncytin-A and syncytin-B from a different ERV family entirely. Carnivores use syncytin-Car1. Rabbits, lemurs, and various other lineages each have their own independently captured syncytin (Cornelis et al. 2017 *PNAS* 114:E4671–E4679; Dupressoir et al. 2009 *Reproduction* 138:719–731). The convergent evolution is at the *function* — placental cell fusion — and the source material is whichever endogenous retrovirus happened to be available when the placenta was evolving in that lineage. Without ERV envelope genes lying around in the genome, placental mammals would have had to evolve cell-fusion machinery from scratch; with them, mammals had ready-made fusogenic protein cassettes repeatedly available for domestication.

**V(D)J recombination from a transposon.** The vertebrate adaptive immune system rearranges immunoglobulin and T-cell receptor gene segments during lymphocyte development by an enzymatic process called **V(D)J recombination**. The enzymes that cut and rejoin the DNA are RAG1 and RAG2. The discovery that RAG1 and RAG2 are derived from an ancient **Transib-family DNA transposase** (Kapitonov VV, Jurka J. 2005. *PLoS Biol* 3:e181; later confirmed by structural and biochemical work from Schatz and colleagues) ties the entire vertebrate adaptive immune system to a single domesticated transposon. This is one of the cleanest cases in biology of transposable elements as a source of novelty, because the function — programmed somatic DNA rearrangement — is one a vertebrate immune system simply could not have without somebody having invented a way to cut and rejoin DNA. A transposon already had.

**ERV-derived enhancers in innate immunity.** Endogenous retroviruses have donated thousands of tissue-specific regulatory elements across mammalian genomes. A particularly clean case: in mammalian cells, a large fraction of the interferon-stimulated genes (the genes turned on in response to viral infection) are driven by enhancers derived from a specific ERV family. Different mammalian lineages have co-opted different ERV families for this purpose — primate immune cells use one set, mouse immune cells use another (Chuong EB, Elde NC, Feschotte C. 2016. "Regulatory evolution of innate immunity through co-option of endogenous retroviruses." *Science* 351:1083–1087; [DOI 10.1126/science.aad5497](https://www.science.org/doi/10.1126/science.aad5497)). The pattern fits a long-running picture: when a virus integrates into the germline, the host eventually silences most of the inserted sequence, but occasionally the regulatory elements inside the virus's promoter region are useful — they drive expression in response to interferon, say — and they get retained and connected to host genes nearby. The result is regulatory rewiring driven by viral DNA.

The honest framing: transposable elements are neither pure parasites nor purely useful regulatory contributors. They are both, at different times, in different contexts. The long-running story is one of conflict — the host suppresses most TEs with DNA methylation, KRAB-zinc-finger proteins, and piRNAs — punctuated by occasional domestications when a particular TE's machinery turns out to be exploitable. The genome's relationship to its TEs is more like a city's relationship to immigration than like a factory's relationship to its inputs. Most arrive, most assimilate or get pushed to the margins, and a small fraction reshape the place in ways no one would have predicted.

### Gene duplication — the genome buys itself a free copy

A single-copy essential gene cannot accumulate function-altering mutations, because every function-altering mutation gets weeded out by purifying selection. The gene is busy doing its essential job, and any change that breaks the job kills the carrier. This is why histones look the way they look — they are stuck.

But suppose, by accident of recombination or replication slippage or unequal crossing over, the gene gets *duplicated* — and now there are two copies of it on the chromosome. One copy can keep doing the original job. The other copy is, for a while, free to drift. Selection no longer cares whether it is functional, because the original copy is covering for it. The duplicated copy is, in Susumu Ohno's phrase from his 1970 book *Evolution by Gene Duplication* (Springer-Verlag, ISBN 3-540-05079-7), evolutionary raw material.

Three fates are possible for the duplicate.

**Pseudogenization.** The most common outcome. The duplicate accumulates inactivating mutations — stop codons, frameshifts, deletions of critical residues — and becomes a **pseudogene**, a sequence that looks like a gene but doesn't encode a functional protein. The human genome contains thousands of identifiable pseudogenes, the molecular fossils of duplicates that didn't make it.

**Subfunctionalization.** The ancestral gene was expressed in multiple tissues (A, B, C) under the control of multiple regulatory elements. After duplication, each copy can lose some of its regulatory elements by random mutation. If copy 1 loses the regulatory element for tissue C and copy 2 loses the regulatory element for tissue A, the two copies together still cover all three tissues — but neither copy alone does. Both are now required, and both are now preserved by purifying selection. This is the **duplication-degeneration-complementation** model (Force A, Lynch M, Pickett FB, et al. 1999. *Genetics* 151:1531–1545), and it is the most common route by which a duplicate is *preserved* without invoking adaptation. It explains why so many duplicates survive in genomes despite the rarity of beneficial new functions.

**Neofunctionalization.** The duplicate evolves a function the ancestor did not have. In any specific case this is rare — most duplicates pseudogenize before they have time to invent something — but cumulatively, over hundreds of millions of years, it is the route by which gene families expand into new functional territory.

The textbook worked case is the **hemoglobin gene family**. Vertebrate hemoglobins evolved from a single ancestral globin gene present in some early deuterostome ancestor. Successive duplications followed by divergence produced the **α-cluster** on human chromosome 16 (containing ζ, α₂, α₁) and the **β-cluster** on human chromosome 11 (containing ε, ᴳγ, ᴬγ, δ, β). Each paralog is expressed at a different developmental stage. Embryonic hemoglobin (using ε and ζ chains) dominates in the early embryo. Fetal hemoglobin (using γ chains) takes over from about 8 weeks of gestation. Adult hemoglobin (using β and δ chains) takes over after birth. The fetal form binds oxygen more tightly than the adult form, which is how the fetus extracts oxygen from the maternal bloodstream across the placenta — fetal hemoglobin out-competes adult hemoglobin for the available oxygen. The whole family is one long story of duplication, subfunctionalization across developmental stages, and tuning of each paralog's oxygen-binding curve to the niche it occupies (Hardison RC. 2012. *Cold Spring Harb Perspect Med* 2:a011627 is a clean modern review).

A second worked case worth mentioning: **olfactory receptors**. Olfactory receptors are G-protein-coupled receptors, each detecting a different range of volatile molecules. Mice have about 1,000 functional OR genes; dogs about 800; humans about 400 functional plus 600 pseudogenes; cetaceans (whales and dolphins) have lost nearly all of theirs because airborne odorant detection is useless underwater. The OR family is the largest gene family in mammalian genomes, and its expansion-contraction history tracks lineage-specific ecology. *What an organism smells, you can see written in its olfactory receptor gene complement.*

The deep evolutionary mechanism behind some of this is **whole-genome duplication** — not duplication of one gene but of *every* gene in the genome at once, by polyploidization. Susumu Ohno proposed in 1970 that vertebrates have undergone two rounds of whole-genome duplication early in their lineage (the **2R hypothesis**), and modern genomic analysis supports it (Dehal P, Boore JL. 2005. "Two rounds of whole genome duplication in the ancestral vertebrate." *PLoS Biol* 3:e314; [DOI 10.1371/journal.pbio.0030314](https://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.0030314)). This is why vertebrates have **four Hox clusters** where invertebrates have one — the original cluster got duplicated twice. Teleost fish underwent a third whole-genome duplication and have seven Hox clusters. Whole-genome duplications are rare events, but when they occur they create thousands of paralog pairs simultaneously, fueling subsequent rounds of subfunctionalization and neofunctionalization. The pattern at the base of most major radiations of complex animals — vertebrates, teleosts, flowering plants — is one of whole-genome duplication followed by lineage-specific exploitation of the new paralog inventory. It is probably not coincidence.

---

## Part 2 — How regulatory change builds bodies

### Hox genes — conserved DNA-binding machine, divergent deployment

In 1984, William McGinnis and colleagues were trying to find vertebrate equivalents of the Drosophila *homeotic* genes — the genes Edward Lewis had shown control segment identity in the fly, mutations in which produced bizarre phenotypes like *Antennapedia* (a leg growing where the antenna should be) and *Ultrabithorax* (a halter transformed into a wing, producing a four-winged fly). They used a piece of fly DNA as a probe and screened mouse and frog genomic libraries under low-stringency conditions, expecting that any vertebrate homologs would have diverged significantly from their fly counterparts and would require a generous mismatch tolerance to find.

They found vertebrate homologs immediately. The hybridization signal was strong; the sequence similarity was high. The 60-amino-acid DNA-binding domain — what we now call the **homeodomain**, encoded by the **homeobox** — was essentially unchanged from flies to mice to frogs (McGinnis W, Garber RL, Wirz J, Kuroiwa A, Gehring WJ. 1984. "A homologous protein-coding sequence in Drosophila homeotic genes and its conservation in other metazoans." *Cell* 37:403–408; [DOI 10.1016/0092-8674(84)90370-2](https://pubmed.ncbi.nlm.nih.gov/6327065/); PMID 6327065). The proteins are so similar that experiments in subsequent years showed they are functionally interchangeable across staggering evolutionary distances — a mouse HoxB6 protein, when expressed in a *Drosophila* embryo, can substitute for the fly's *Antennapedia* and rescue mutants (Malicki J, Schughart K, McGinnis W. 1990. *Cell* 63:961–967). The DNA-binding specificity has not measurably diverged in the roughly 600 million years since the last common ancestor of flies and vertebrates.

Define what we are talking about. A **Hox gene** is a specific class of homeobox-containing transcription factor that controls **anterior-posterior body axis** identity in animals. Each Hox protein binds short specific DNA sequences in the regulatory regions of downstream target genes and turns those targets on or off depending on the context. In flies there are eight Hox genes arranged in two clusters (the *Antennapedia* complex and the *Bithorax* complex). In humans there are 39 Hox genes arranged in four clusters (HoxA, HoxB, HoxC, HoxD) on four different chromosomes, the product of the 2R whole-genome duplications.

The most striking structural feature of Hox clusters is **collinearity** — the order of the genes on the chromosome matches the order of their expression along the body. The 3'-most genes are expressed in the anterior (head) of the embryo; the 5'-most genes are expressed in the posterior (tail). Edward Lewis's Nobel-lecture work on the Bithorax complex (Lewis EB. 1978. "A gene complex controlling segmentation in *Drosophila*." *Nature* 276:565–570; [DOI 10.1038/276565a0](https://www.nature.com/articles/276565a0); PMID 103000) established this property in flies, and it turns out to hold in vertebrates as well — the HoxA cluster's 3' genes pattern the cervical vertebrae, the 5' genes pattern the lumbar and sacral regions, with all the intermediate genes patterning intermediate regions in chromosomal order. The structural property is so robust it has earned its own name; the proximate mechanism involves successive chromatin opening along the cluster from 3' to 5' during embryogenesis, which is genuinely elegant and a frontier of current developmental biology research. Lewis shared the 1995 Nobel Prize in Physiology or Medicine with Christiane Nüsslein-Volhard and Eric Wieschaus for the segmentation and pattern-formation work. The canonical review is McGinnis W, Krumlauf R. 1992. "Homeobox genes and axial patterning." *Cell* 68:283–302; [DOI 10.1016/0092-8674(92)90471-N](https://pubmed.ncbi.nlm.nih.gov/1346368/); PMID 1346368.

Here is the question that organizes everything. *If the Hox protein is virtually unchanged between a fly and a vertebrate, how on earth does it produce such different bodies?*

The answer is that **the protein is the same, but where, when, and how much each Hox protein is expressed differs across phyla**. The fly *Drosophila* has segments that grow walking legs at the thorax but not at the abdomen, because the Hox gene **Ultrabithorax (Ubx)** is expressed in abdominal segments and represses the limb-promoting target genes (Distalless, decapentaplegic). A centipede has limbs on most segments because the Ubx ortholog in the centipede is deployed differently — its expression boundaries are different and its regulatory connection to the limb-promoting genes is different. A snake has lost limbs because the limb-bud-inducing expression of HoxC6/HoxC8 has *expanded* along the body axis, producing a long thoracic field with no transition to a limb-bearing region (Cohn MJ, Tickle C. 1999 *Nature* 399:474–479; the picture was refined by Woltering et al. 2009 and Head & Polly 2015 *Nature* 520:86–89). The protein is the same. The regulatory deployment is different. The morphology follows the deployment.

This is the central evo-devo insight in one sentence: **morphological evolution among animals happens largely through changes in regulatory deployment of a conserved toolkit, not through changes in the toolkit itself.**

### The toolkit — a small set of conserved signaling pathways, reused everywhere

Hox genes are one element of what is now called the **animal developmental toolkit**, but they are not the only one. The toolkit consists of a handful of conserved transcription-factor families (Hox, Pax, T-box, Sox, the broader homeodomain class) and a small number of intercellular signaling pathways. The pathways are:

**Wnt** — secreted glycoproteins that bind Frizzled-family receptors on neighboring cells, ultimately stabilizing β-catenin, which enters the nucleus and turns on target genes. Wnt signaling patterns the primary body axis in nearly every bilaterian animal, controls stem cell maintenance in adult tissues like the intestinal crypt, and is involved in dozens of developmental decisions.

**Notch** — a membrane receptor that, when bound by a Delta or Jagged ligand on a neighboring cell, gets cleaved, releasing its intracellular domain to enter the nucleus and activate target genes. Notch mediates short-range cell-to-cell communication and is centrally involved in distinguishing cell fates between adjacent cells — for example, picking out which cell in a cluster will become a neuron versus a glial cell.

**Hedgehog** — a secreted lipid-modified protein that binds the Patched receptor, releasing the Smoothened co-receptor from inhibition, ultimately activating the Gli/Ci family of transcription factors. Hedgehog patterns the ventral neural tube, the limb digit field, the developing gut, and many other structures. Sonic Hedgehog (Shh) is the vertebrate name; in *Drosophila* it is just *hedgehog*. Riddle RD, Johnson RL, Laufer E, Tabin C. 1993. "Sonic hedgehog mediates the polarizing activity of the ZPA." *Cell* 75:1401–1416 is the foundational paper identifying Shh as the limb-patterning morphogen in vertebrates.

**BMP/TGF-β** — secreted growth factors that bind serine-threonine kinase receptors, signaling through SMAD transcription factors. BMP patterns the dorsal-ventral axis (in flies and frogs), regulates bone formation, controls germ-cell specification, and many other processes.

**FGF** — secreted growth factors binding tyrosine kinase receptors, signaling through Ras-Raf-MAPK. FGF controls limb outgrowth, neural induction, mesoderm patterning, and is reused in dozens of contexts.

These five pathways were already present in the last common ancestor of bilaterian animals — they are universal across animals from sponges through humans, with the same core components in each. What changes across animal phyla is *how* the pathways are wired into the regulatory networks that pattern any given structure. The same toolkit; different connections.

The toolkit framing is most cleanly articulated in Sean Carroll's *Endless Forms Most Beautiful* (Carroll SB. 2005. W. W. Norton; ISBN 0-393-06016-0). The picture: a small set of genetic instruments, used in different combinations and contexts across phyla, can produce arbitrary morphological diversity. Evolution of new body plans does not require inventing new genes — it requires re-wiring the regulatory connections among existing ones. This is part of why the same Hox protein can pattern a fly thorax and a mammalian cervical vertebra: the protein is doing the same molecular job in both, and the regulatory architecture downstream interprets the Hox signal differently in different lineages.

### Modularity — how an enhancer lets evolution edit one tissue at a time

A typical metazoan gene is regulated by *multiple* enhancers, each driving expression in a specific tissue or at a specific developmental stage. *Pitx1* in fish has separate enhancers driving its expression in the pelvic primordium, in the jaw, in the pituitary, and in the developing fin. A mutation that knocks out the pelvic enhancer eliminates Pitx1 expression in the pelvis without disrupting Pitx1 expression anywhere else. This is what made the stickleback story work.

The general principle is **modularity of cis-regulatory architecture**. **Cis-regulatory elements** (the prefix *cis* meaning "on the same molecule") are DNA sequences on the same chromosome as the gene they regulate — promoters, enhancers, silencers — that control transcription by binding transcription factors. **Trans-regulatory** factors are the proteins (transcription factors, RNA polymerase) that act on those cis-elements from elsewhere in the cell. An **enhancer** is a stretch of cis-regulatory DNA, typically a few hundred base pairs long, that binds a combination of transcription factors and drives expression of a target gene in a specific context — a specific tissue, a specific developmental window, a specific environmental condition.

The mechanism that makes enhancers act modularly: each enhancer binds a distinct combination of transcription factors. The combination of factors present in a given cell at a given time determines which enhancers are active. The pelvic enhancer of *Pitx1* binds factors that are present in the pelvic primordium and absent elsewhere. The jaw enhancer of *Pitx1* binds factors that are present in the jaw primordium and absent elsewhere. The two enhancers are physically separate stretches of DNA, often kilobases apart from each other, and a mutation in one does not affect the other.

This is the structural feature that makes evolution by regulatory change possible without massive collateral damage. Without modular cis-regulation, every change to a gene's expression would have to come from changes to the protein itself (which usually break the protein) or changes to the transcription factor that regulates it (which usually break dozens of downstream genes simultaneously). With modular cis-regulation, evolution can edit one expression domain at a time, leaving the rest intact. The cost in pleiotropy — the spillover effect of one change on many traits — is reduced by orders of magnitude.

This is why the King-Wilson conjecture from 1975 worked out. King MC, Wilson AC. 1975. "Evolution at two levels in humans and chimpanzees." *Science* 188:107–116 ([DOI 10.1126/science.1090005](https://www.science.org/doi/10.1126/science.1090005); PMID 1090005) computed from the available protein-electrophoresis data that humans and chimpanzees share roughly 99% of their protein sequences and proposed that the morphological differences between us must therefore lie primarily in *regulatory* sequences controlling when and where each shared protein is expressed. The proposal was speculative in 1975 — they had no way to look at the regulatory sequences directly. Forty years of sequence-and-functional-genomics work have largely vindicated it: most large morphological differences between closely related vertebrate species map to changes in cis-regulatory elements rather than to changes in the coding sequences of the genes those elements regulate. The strong-form claim that *all* morphological evolution is regulatory has been pushed back on (Hoekstra HE, Coyne JA. 2007. "The locus of evolution: evo devo and the genetics of adaptation." *Evolution* 61:995–1016; they argue that protein-coding changes have been underestimated and that many morphological differences involve coding changes too). The modern consensus is mixed — both kinds of change matter, the balance varies by trait, and regulatory change probably dominates for tissue-specific morphological differences while protein-coding change dominates for biochemical and physiological differences.

### Heterochrony and heterotopy — when and where

Two pieces of evo-devo vocabulary that turn out to mean something concrete.

**Heterochrony** is evolutionary change in the **timing** of developmental events. If a particular developmental process runs longer in a descendant lineage than in an ancestral one, structures end up larger or more elaborate. If it runs shorter, structures stay simpler or more juvenile-looking. The special case where a sexually mature adult retains juvenile features is called **neoteny**. The axolotl (*Ambystoma mexicanum*) is the textbook neotenic vertebrate: it reaches sexual maturity while keeping its larval gills and aquatic body, because its thyroid hormone signaling fails to drive the metamorphic switch that other Ambystomatid salamanders go through. The change is in timing — the metamorphic transition just never happens — not in the genes responsible for adult morphology.

Heterochrony is the lever on which a lot of morphological evolution moves. Stephen Jay Gould's *Ontogeny and Phylogeny* (1977) made the case at book length that the human face and skull retain juvenile chimp-like proportions into adulthood — the human skull is, on this reading, a neotenized great-ape skull, with rounding of the cranial vault, reduction of the brow ridge, and shortening of the snout reflecting retention of juvenile geometry. The "human neoteny" hypothesis has been argued and re-argued for decades and is best treated as a useful framing with partial empirical support rather than a settled fact. Mitteroecker P, Gunz P, Bernhard M, Schaefer K, Bookstein FL. 2004. *J Hum Evol* 46:679–697 worked the comparative skull morphology in modern morphometric detail and found support for some, not all, of Gould's claims. The chapter should treat human neoteny as a partially supported evo-devo hypothesis, not a final word.

**Heterotopy** is evolutionary change in the **location** of developmental events. A gene that is normally expressed in tissue A acquires expression in tissue B, producing a new structure where none existed before. Butterfly wing eyespots are the showcase. Sean Carroll's lab traced eyespot evolution to a heterotopic deployment of the *Distalless* gene network — the same genes that pattern appendage outgrowth in arthropods, redeployed at specific points on the wing surface to mark eyespots (Brakefield PM, Gates J, Keys D, et al. 1996. *Nature* 384:236–242). The eyespot is not built by a new gene network; it is an old gene network used in a new place.

The two together — heterochrony (when) and heterotopy (where) — are the levers by which regulatory evolution turns a conserved toolkit into divergent morphologies. The toolkit is the same. What changes is the schedule and the address.

### The deep-dive case — back to the stickleback

I want to walk the stickleback story one more time, slowly, now that the vocabulary is in place. This is the deep-dive of the chapter, and it ties together every concept in Part 1 and Part 2.

Marine sticklebacks colonize freshwater lakes after the last glaciation, roughly 10,000–15,000 years ago. In freshwater, the predator regime changes — piscivorous fish are scarce, invertebrate predators that prefer prey with spines become important — and the cost of bony armor goes up because calcium is scarce. Selection favors fish with reduced pelvic armor.

The trait — pelvic spine presence or absence — maps to a single major-effect locus containing the *Pitx1* gene. The *Pitx1* coding sequence is identical between marine and freshwater fish. What differs is a **pelvic-specific enhancer** about 30 kilobases upstream of the *Pitx1* coding region. In freshwater fish, this enhancer is **deleted**.

The deletion is recurrent. In dozens of independently colonized freshwater lakes on different continents, *different specific deletions* knock out the same enhancer. One Icelandic lake's fish have a 1.5-kb deletion; one British Columbia lake's fish have a 600-bp deletion; one Alaskan lake's fish have a slightly different boundary. Convergent regulatory evolution at the same regulatory address by different specific mutations.

Why this works at the level of selection: the pelvic enhancer deletion eliminates Pitx1 expression specifically in the pelvic primordium while leaving Pitx1 expression intact everywhere else the gene is needed — the jaw, the pituitary, the developing fin. The fish loses its pelvic spines without losing the rest of Pitx1's functions. Pleiotropy is avoided. The cost of the trait change is local.

Why the same mutation arises repeatedly: the pelvic enhancer sits in a region of the chromosome that is prone to deletion. The chromosomal architecture predisposes the locus to lose this particular regulatory element more often than other places in the genome. Strong shared local selection in freshwater × elevated local mutation rate at this locus = repeated parallel evolution.

Now let me name every concept this case illustrates.

1. **Regulatory evolution as the mode of morphological change.** The Pitx1 protein is unchanged; the regulatory element is deleted; the morphology follows the regulatory deployment.
2. **Modularity of enhancers.** The pelvic enhancer is one of multiple Pitx1 enhancers, each tissue-specific. Losing the pelvic one does not disrupt the others.
3. **Convergent evolution.** The same morphological outcome reached repeatedly in independent populations, at the same regulatory address, by different specific mutations.
4. **The Carroll thesis.** *Cis*-regulatory change dominates over protein-coding change for this kind of large-effect morphological transition.
5. **Selective sweep.** Each independent deletion sweeps to fixation in its local population on a time scale of thousands of generations.
6. **Local mutation rate matters.** The chromosomal fragility of the locus predisposes it to recurrent deletion.
7. **Selection coefficient is large in the freshwater environment.** This is why the sweep happens at all and why it happens fast.

The chapter could have used dozens of other cases — *Drosophila* wing pigmentation spots through the *yellow* enhancer (Prud'homme et al. 2006 *Nature* 440:1050–1053), Hox gene re-wiring in arthropods (Averof M, Patel NH. 1997. "Crustacean appendage evolution associated with changes in Hox gene expression." *Nature* 388:682–686; [DOI 10.1038/41786](https://www.nature.com/articles/41786)), lactase persistence in human pastoralist populations (Tishkoff et al. 2007, below), maize domestication through *tb1* enhancer changes. The reason to spend the space on sticklebacks is that the experimental ladder is fully climbed — the phenotype is named, the locus is mapped, the responsible enhancer is identified, the specific deletions are sequenced across populations, and the developmental mechanism is understood. There is no point on the chain where you have to take it on faith. This is what an evolutionary explanation looks like when it works.

---

## Worked example — running dN/dS on FOXP2 and asking what the answer actually means

Let me walk one full dN/dS analysis end to end, on a case where the answer is contested and the contest is instructive. The gene is **FOXP2**, a transcription factor expressed in developing brain, lung, and gut tissue. The question is whether the protein-coding changes on the human lineage since the chimp-human split show evidence of positive selection.

### The data

The human FOXP2 protein is 715 amino acids long. The human and chimpanzee FOXP2 proteins differ at **two amino acid positions** on the human lineage — that is, two amino acid substitutions occurred between the human-chimp common ancestor (~6 million years ago) and modern humans, on the branch leading to humans. The mouse FOXP2 protein differs from primate FOXP2 at additional positions, allowing us to polarize the changes onto specific branches by comparison with the outgroup. (Enard W, Przeworski M, Fisher SE, Lai CSL, Wiebe V, Kitano T, Monaco AP, Pääbo S. 2002. "Molecular evolution of FOXP2, a gene involved in speech and language." *Nature* 418:869–872; [DOI 10.1038/nature01025](https://www.nature.com/articles/nature01025).)

### Counting substitutions and sites

The two amino acid substitutions are both **nonsynonymous**. Looking at the underlying codon changes, there is also one synonymous substitution on the human branch in this gene. So:

- Nonsynonymous substitutions on the human branch: N = 2
- Synonymous substitutions on the human branch: S = 1

To compute dN and dS, we need to know how many nonsynonymous and synonymous **sites** there are in the gene — the denominators. A protein-coding gene of 715 codons has 2,145 nucleotide sites. The Nei-Gojobori method counts each site as a fraction "synonymous" or "nonsynonymous" depending on what fraction of mutations at that site would be synonymous. As a rough rule, about 25% of sites in a typical coding gene are synonymous and 75% are nonsynonymous. For 2,145 sites, that gives:

- Synonymous sites: ~ 0.25 × 2,145 ≈ 536
- Nonsynonymous sites: ~ 0.75 × 2,145 ≈ 1,609

(The actual values depend on the codon composition of the specific gene; this is a textbook approximation.)

### Computing the rates

```
dN = N / (nonsynonymous sites) = 2 / 1,609 ≈ 0.00124
dS = S / (synonymous sites) = 1 / 536 ≈ 0.00187
dN/dS = 0.00124 / 0.00187 ≈ 0.67
```

For a whole-gene average, dN/dS ≈ 0.67 is **less than 1** — consistent with the broad pattern of purifying selection on the gene as a whole. FOXP2 is a tightly conserved transcription factor; most of its sequence is not free to change.

But this is averaging over 715 amino acids. The question is whether two specific changes localized to specific regions of the protein represent positive selection — and the average over the whole gene is not the right test for that question.

### The original Enard 2002 claim

What Enard and colleagues did in 2002 was not just compute dN/dS on the whole gene. They used patterns of **intronic variation** in modern human populations to look for the haplotype-tree signature of a recent selective sweep on the human FOXP2 locus. They observed reduced polymorphism in the intron immediately downstream of the relevant coding substitutions and an excess of rare variants — consistent with a recent positive-selection sweep around the time the two amino acid changes were fixed. They estimated the sweep occurred within roughly the last 200,000 years and argued that FOXP2 may have been a target of positive selection during the emergence of modern human language capacity.

The story got told widely as "the gene for human language."

### What complicated the story

Three subsequent findings complicated it.

**Neanderthals had the same two FOXP2 substitutions.** Krause J, Lalueza-Fox C, Orlando L, et al. 2007. "The derived FOXP2 variant of modern humans was shared with Neandertals." *Curr Biol* 17:1908–1912. The two amino acid changes are therefore older than the modern-human–Neanderthal split, which is roughly 500,000 to 800,000 years ago, not unique to modern humans. The selective sweep — if it occurred — happened before anatomically modern humans appeared.

**Modern selective-sweep tests do not robustly confirm a recent FOXP2 sweep.** Atkinson EG, Audesse AJ, Palacios JA, et al. 2018. "No evidence for recent selection at FOXP2 among diverse human populations." *Cell* 174:1424–1435.e15 reanalyzed the FOXP2 region using larger and better-curated datasets and updated demographic models, and found that the original signal of recent positive selection on FOXP2 may have been a methodological artifact — possibly attributable to a different nearby variant or to demographic structure that the 2002 analysis did not adequately model. The molecular evidence for an *adaptive* fixation of the two amino acid substitutions on the human lineage is **weaker than initially reported**. **[contested]**

**FOXP2 is not "the language gene."** It is a transcription factor expressed broadly in brain, lung, and gut during development. Its targets in the brain include hundreds of downstream genes. The KE-family patients carrying a missense FOXP2 mutation have a complex phenotype that includes orofacial motor coordination deficits, syntactic and comprehension impairments, and reduced nonverbal IQ — not a pure language deficit. Mouse Foxp2 knock-ins of the human form modestly alter striatal medium spiny neuron dendritic morphology and motor learning (Enard W, Gehre S, Hammerschmidt K, et al. 2009 *Cell* 137:961–971), but the phenotype does not look like "language" — it looks like a broader motor and circuit-formation modification.

### What the case actually shows

I want to be careful here. The two amino acid substitutions in human FOXP2 are *real*. The Neanderthal sharing of those substitutions is *real*. The original 2002 selective-sweep claim has *weakened* under reanalysis, but it has not been firmly refuted; the field is in a state where the strong-form "recent positive selection on FOXP2 in modern humans" reading is no longer well-supported, while the weaker-form "FOXP2 underwent some molecular change on the hominin lineage" reading is supported.

The case is in the chapter for a specific pedagogical reason. It is a worked example of *how a molecular-evolution claim self-corrects*. The original analysis was state-of-the-art in 2002; better data and better methods in 2018 produced a different answer. **This is what good methodology looks like — it is willing to revise its claims when the evidence shifts.** A student who walks away from this chapter believing "FOXP2 is the language gene" has not learned the chapter. A student who walks away saying "FOXP2 underwent two amino acid changes on the hominin lineage, and what those changes mean is an active research question with the original strong claim no longer well-supported" has learned the chapter.

The methodological lesson generalizes. dN/dS is a powerful but assumption-laden tool. A single number averaged over a whole gene is not a finding; it is a starting point. Branch-and-site models that partition the analysis by branch and by codon are the modern refinement, and they are what you would use today to ask whether specific codons on the human branch show elevated dN/dS rather than asking whether the whole-gene average does. Demographic alternatives (bottleneck, expansion, structure) need to be excluded before a sweep signal can be confidently called selection. And the link from a selection signal to a *functional* claim — from "this gene was selected" to "this gene does X in the trait we care about" — requires independent functional evidence beyond the sequence comparison.

The summary: dN/dS detects past episodes of selection by exploiting the genetic code. It works. But like any inferential tool, it requires care.

---

## Common misconceptions, named explicitly

### Misconception 1 — "Neutral theory says all evolution is neutral."

No. Kimura's neutral theory says that most *molecular substitutions that have gone to fixation* in protein-coding genes are neutral, not that all evolution is neutral. Adaptive evolution exists and is detected by methods that compare against the neutral expectation (dN/dS, McDonald-Kreitman tests, selective-sweep scans). The neutral theory is the *null model* — the baseline against which adaptive claims must be made. When dN/dS > 1 at a specific codon, the neutral expectation has been violated and the data are pushing you to invoke positive selection.

The reason the misconception is common is that "neutral evolution" and "natural selection" sound like they should be alternatives, and so students assume Kimura was arguing against Darwin. He wasn't. He was arguing that *most of what happens to genomes day-to-day at the sequence level* is drift, not because Darwin was wrong but because most of the genome is not under appreciable selection at most moments. The morphological evolution Darwin cared about is a different question, addressed by the regulatory-evolution machinery this chapter has spent half its length on.

### Misconception 2 — "Hox genes determine body plans."

Hox genes *pattern* body plans, but they do not *determine* them in isolation. Hox proteins are transcription factors; they turn other genes on and off. The morphology that results from a given Hox expression pattern depends on which downstream targets are active in which tissue at which time, which depends on the entire regulatory network downstream of the Hox protein. A Hox protein in a fly thorax produces a fly leg because the fly's downstream regulatory network responds to that Hox protein by building a fly leg. The same Hox protein in a vertebrate cervical segment produces a vertebra because the vertebrate's downstream regulatory network responds to it by building a vertebra. The "determination" lives in the network, not in the Hox gene alone.

The reason this matters: students who think Hox genes "determine" body plans will be confused when the same Hox protein produces different structures in different organisms. The answer is that Hox proteins set a *coordinate label* on each segment — "you are anterior thorax," "you are posterior abdomen" — and the rest of the developmental machinery interprets the label according to its own wiring. The label is conserved. The interpretation is not. This is why regulatory rewiring of *downstream* networks, not changes to Hox proteins themselves, drives much of the morphological diversity between phyla.

### Misconception 3 — "More mutations means more morphological change."

No. The relationship between sequence change and morphological change is not monotonic. A protein-coding change in a Hox gene's homeodomain is usually lethal — the embryo fails to develop, or fails to develop a specific segment, and dies. A regulatory change in a tissue-specific enhancer can produce a dramatic morphological difference (lose your pelvic spines) without lethality, because it edits only one expression domain. Hundreds of synonymous changes scattered across a genome may produce no morphological effect whatsoever. *Where* the mutation falls, in the modular architecture of the genome, matters far more than *how many* mutations there are.

The corollary: morphological evolution does not require a high mutation rate. It requires the *right kinds* of mutations in the *right places* — mostly in tissue-specific regulatory elements where their effects can be localized. This is part of why morphological evolution can outpace molecular sequence evolution in some lineages (the Hawaiian silverswords radiated into dozens of morphologies in 5 million years without exotic sequence change) and lag in others.

### Misconception 4 — "If two species share 99% of their DNA they are basically the same."

The humans-and-chimps-are-98% sequence-identical statistic gets cited often, and it tends to produce the conclusion that the differences between humans and chimps must be trivial. The conclusion does not follow. The 1–2% sequence difference includes tens of millions of base-pair changes; some are in regulatory elements that control which proteins are made in which tissues at which times; some are in coding sequences of proteins whose function does depend on those specific residues. King and Wilson's 1975 point was exactly this — the sequence-identity statistic understates the morphological difference because it does not weight regulatory changes by their downstream effects. *The fraction of identical bases* is not *the fraction of identical organisms*.

---

## Exercises

### Exercise 1 — Classify a substitution

Given this DNA alignment of a coding-region segment between two species (with the codon boundaries marked, reading frame 5' to 3'):

```
Species A:  ATG | GCC | GAA | TGG | CGT | AAC | TAA
Species B:  ATG | GCC | GAG | TGG | CGT | ACC | TAA
```

For each codon position where the two species differ, identify (a) whether the substitution is synonymous, nonsynonymous, or in a regulatory region; (b) what amino acid change (if any) occurred; (c) what dN/dS-style classification this single substitution would contribute to. Then compute the rough dN/dS for the gene segment assuming each codon has on average 1 synonymous and 2 nonsynonymous sites.

(Hint: GAA and GAG both encode glutamic acid. AAC encodes asparagine; ACC encodes threonine. Look up the codon table.)

**Goal:** Practice the synonymous/nonsynonymous distinction at the level of individual codons.

### Exercise 2 — Interpret a dN/dS value

Each of the following genes has been measured by dN/dS across mammals. For each, predict the likely dN/dS class (≪ 1, < 1, ≈ 1, > 1) and explain why in one sentence based on the gene's function:

- Histone H4
- HIV envelope V3 loop (within-patient evolution)
- A pseudogene with three premature stop codons
- An MHC class I peptide-binding residue
- An olfactory receptor in dolphins
- Cytochrome c

Then state, for the two values most distant from 1, what kind of evidence beyond dN/dS you would want before claiming positive or purifying selection at a specific codon.

**Goal:** Internalize that dN/dS reflects function.

### Exercise 3 — Apply: Diagnose a regulatory-vs-coding mutation

For each of the following morphological differences between species or populations, predict whether the underlying mutation is more likely in a **protein-coding sequence** or in a **tissue-specific cis-regulatory element**, and explain the reasoning in 2–3 sentences:

(a) Loss of pelvic spines in freshwater stickleback populations.
(b) Persistence of lactase expression into adulthood in northern European and East African pastoralist populations.
(c) Sickle-cell hemoglobin in West African populations (HbS allele).
(d) The appearance of eyespots on butterfly wings.
(e) The four-winged *Drosophila* phenotype produced by *Bithorax* loss-of-function mutations.

For each, name what would be lost or disrupted if the change were instead in the protein-coding sequence — why the regulatory route is the route that *survives* selection.

**Goal:** Build intuition for when regulatory evolution is the parsimonious explanation and when protein-coding evolution is.

### Exercise 4 — Run the simulator under three scenarios

Open your `13-molecular-evolution.html` simulator and run three configurations:

1. **Pure neutral evolution.** Mutation rate high, no selection on any codon. Run for 1,000 generations. Record final dN/dS.
2. **Strong purifying selection on nonsynonymous changes.** Selection coefficient −1 (lethal) for all nonsynonymous changes. Run for 1,000 generations. Record final dN/dS.
3. **Positive selection on a single nonsynonymous variant.** Set one codon to provide a strong fitness advantage (selection coefficient +0.5) when a particular nonsynonymous variant arises. Run for 1,000 generations. Record final dN/dS, the trajectory of the favored variant, and the local pattern of diversity around it after the sweep completes.

Write a 200-word interpretation of each run, naming what you observed and explaining it in terms of the chapter's framework.

**Goal:** Make the abstract claims (neutral rate = mutation rate; dN/dS responds to selection; sweeps reduce linked diversity) concrete by seeing them in your hands.

### Exercise 5 — Find the homeobox

Take the following sequence fragment (Drosophila *Antennapedia* homeobox, 60 amino acids):

```
RKRGRQTYTRYQTLELEKEFHFNRYLTRRRRIEIAHALCLTERQIKIWFQNRRMKWKKEN
```

BLAST this sequence against the human protein database (NCBI BLAST). Identify the human Hox gene that comes up as the top hit. Compute the percent identity between the fly and human sequences across this domain. Write a paragraph explaining what this percent identity tells you about (a) how long ago the last common ancestor of flies and humans lived, (b) what the conservation implies about the function of this domain, and (c) why the rest of each Hox protein (the regions flanking the homeodomain) is *not* this strongly conserved.

**Goal:** See the homeodomain conservation directly in a sequence comparison.

---

## What you should be able to do now

You should be able to:

- Derive the neutral-rate-equals-mutation-rate result from `K = 2N_e μ × 1/(2N_e)` and explain why population size cancels.
- Compute dN/dS from a small alignment by hand and interpret the answer in terms of purifying, neutral, or positive selection.
- Name the signature of a selective sweep in linked variation and explain why sweep width depends on selection strength and local recombination rate.
- Define transposable elements, name the two major classes in the human genome, and name at least three documented exaptations.
- Distinguish pseudogenization, subfunctionalization, and neofunctionalization as fates of a duplicated gene.
- State the conservation property of Hox proteins (homeodomain unchanged across animal phyla) and the collinearity property of Hox clusters.
- Define cis-regulatory element, enhancer, and modularity, and explain how modular architecture enables tissue-specific regulatory evolution.
- Walk the stickleback pelvic spine story as a worked case of regulatory evolution.
- State what King and Wilson (1975) proposed and where the modern consensus sits on the regulatory-versus-coding question.
- Read a published claim of "positive selection on a gene" and ask the right skeptical questions (whole-gene average or codon-specific? has demography been controlled for? has the finding been replicated with better data?).

---

## Bridge to Chapter 14

Chapter 13 has built the molecular and developmental machinery of evolutionary change — what kinds of DNA changes get fixed, how the rate of fixation depends on selection and population size, how regulatory changes turn into morphological differences, and how a small toolkit of conserved genes is redeployed to build the diversity of animal bodies. The capstone (Chapter 14) integrates this machinery with the population genetics of Chapter 10 and the speciation framework of Chapter 11 to walk three extended case studies that exercise the whole book: **antibiotic resistance** as evolution in real time at the population-genetic and molecular-mechanistic level; **human population genetics** including the out-of-Africa bottleneck, founder effects in specific groups, and balancing selection at the sickle-cell and other malaria-related loci; and **the molecular basis of human evolution** — FOXP2, the Human Accelerated Regions (HAR1 expressed in developing neocortex, *Pollard et al. 2006 Nature 443:167–172*; HACNS1 limb enhancer, *Prabhakar et al. 2008 Science 321:1346–1350 with the Sumiyama-Saitou 2011 caveat that some of the "human-specific accelerated substitutions" may reflect biased gene conversion rather than positive selection*), brain-size genes (ASPM, MCPH1), gene duplication in the human lineage (NOTCH2NL), and the ancient-DNA revolution that produced Neanderthal and Denisovan genomes (Svante Pääbo, 2022 Nobel in Physiology or Medicine; the Tibetan EPAS1 high-altitude adaptation introgressed from Denisovans is the worked case for selection on archaic ancestry). Everything the capstone does, this chapter has prepared you for. Hold onto the dN/dS framework, the regulatory-evolution mode, and the methodological skepticism — the capstone uses all of them.

---

**What would change my mind.** The strong claim that *cis*-regulatory change dominates over protein-coding change as the mode of morphological evolution would be substantially weakened if a large-scale comparative-genomics study found that, across well-resolved morphological differences between closely related vertebrate species, protein-coding changes account for the majority of the cases when both regulatory and coding candidates are tested with comparable rigor. Hoekstra & Coyne (2007) made a version of this argument; the next decade of comparative genomics, with much better data, has not, on balance, vindicated the strong protein-coding-primacy view, but a careful meta-analysis showing that the field has been over-weighting regulatory cases for reasons of publication bias would update my reading. I would also update if a sustained re-examination of the stickleback Pitx1 story revealed that the pelvic morphology difference depends on coding changes elsewhere on the chromosome that previous mapping had missed — the case is the keystone, and a keystone shifting matters.

**Still puzzling.** The relationship between *how much* sequence change accumulates in a lineage and *how much* morphological change accumulates remains the loose end I cannot make precise. Lineages with high mutation rates do not consistently produce more morphological diversity than lineages with low mutation rates; lineages that have radiated into striking morphological diversity (Hawaiian silverswords, cichlid fish, the Cambrian metazoans) do not seem to be unusual in their sequence-level evolution. The two clocks tick at different rates, sometimes in different directions, and the proximate reason — that regulatory architecture decouples sequence change from morphological change in ways that depend on the local modularity of cis-regulation — is true but does not let me predict, given a sequence-level mutation rate and a population size, how much morphological evolution I should expect. I would like that mapping to be tighter than I currently understand it to be.

---

**Tags:** #molecular-evolution #evo-devo #neutral-theory #Kimura #dN-dS #selective-sweeps #transposable-elements #Hox-genes #cis-regulatory-evolution #stickleback-Pitx1 #FOXP2 #King-Wilson-1975 #regulatory-primacy-debate #gene-duplication #heterochrony #neoteny #toolkit-genes #modularity #syncytin #HARs
