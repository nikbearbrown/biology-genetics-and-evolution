# Chapter 01 — Meiosis and the Basis of Inheritance

**Suggested titles:**
- *Sutton's Grasshopper Cells, and the Year Mendel's "Factors" Finally Got a Body*
- *Why Alleles Segregate — A Cell, Two Divisions, and One Movement at Anaphase I*
- *From a 9:3:3:1 Ratio in a Pea Patch to a Bivalent on a Spindle: The Chromosomal Theory of Inheritance*

---

**TL;DR.** Mendel published in 1865 and inferred two "factors" per trait that segregate cleanly into gametes; he could not see them. By the 1880s cytologists could see chromosomes; by 1902–1903 Walter Sutton (a graduate student staring at grasshopper testis cells) and Theodor Boveri (an embryologist working on sea urchins) independently proposed that Mendel's factors *are* the chromosomes, because chromosomes behave at meiosis exactly the way Mendel's factors behave at inheritance — they occur in pairs, the pair members separate cleanly into gametes, and different pairs sort independently. This chapter shows how meiosis is the cellular mechanism that produces every Mendelian ratio: anaphase I separating homologs is Mendel's First Law made physical; the independent orientation of 23 bivalents at metaphase I is Mendel's Second Law made physical; and the one big exception to the second law — genetic linkage — is just what you would expect when two genes ride the same chromosome. Sturtevant in 1913 turned that exception into a measurement tool: recombination frequency between two linked genes is the rate of crossing over between them, and 1% recombination ≈ 1 centimorgan of map distance. Sex-linked inheritance (Morgan's white-eyed fly, 1910) is the same chromosomal logic applied to the X chromosome's special arithmetic in males. The chapter is the bridge from Ch 00's combinatorial Punnett squares to Ch 02's Mendelian crosses: every ratio you computed last chapter has a metaphase-I plate behind it.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **State** the chromosomal theory of inheritance in one sentence (Mendel's factors are chromosomes; the inheritance pattern of a factor is the meiotic behavior of the chromosome carrying it) and **name** the three Sutton–Boveri parallels that the theory rests on.
2. **Identify** the molecular event at anaphase I — homologs separating, sister chromatids staying joined — as the cellular basis of Mendel's First Law (segregation), and **trace** a single heterozygous *Aa* parent through one complete meiosis to show why exactly half the gametes carry *A* and half carry *a*.
3. **Identify** the random orientation of bivalents at metaphase I as the cellular basis of Mendel's Second Law (independent assortment), and **compute** the 2ⁿ gamete count for *n* independently assorting heterozygous loci on *n* different chromosomes.
4. **Predict** the gamete ratios produced by a dihybrid *AaBb* parent under three cases: (a) *A* and *B* on different chromosomes (1:1:1:1 — Mendel's Second Law); (b) *A* and *B* on the same chromosome, no crossing over (1:1 — perfect linkage); (c) *A* and *B* on the same chromosome with recombination frequency *r* (parental gametes at (1−*r*)/2 each, recombinant gametes at *r*/2 each).
5. **Compute** map distance in centimorgans from a recombination frequency between two linked genes (1 cM ≈ 1% recombination, valid up to about 25% where the linear approximation breaks down).
6. **Diagnose** the inheritance pattern of a trait (autosomal dominant, autosomal recessive, X-linked dominant, X-linked recessive) from a small pedigree, and **explain** at the chromosomal level *why* X-linked recessive disorders show the signature pattern of carrier mothers, affected sons, and no father-to-son transmission.
7. **Compute** the probability that a son of a carrier mother and an unaffected father is affected with an X-linked recessive disorder (1/2), and the probability that a daughter is a carrier (1/2) — and **explain** which meiotic event produced the carrier egg.
8. **Distinguish** meiosis I nondisjunction from meiosis II nondisjunction in terms of which chromosomal structure failed to separate, and **predict** which trisomies (21, 18, 13) and sex-chromosome aneuploidies (XXY, XO, XYY, XXX) are compatible with live birth.
9. **Apply** the three sources of human gamete diversity — independent assortment (2²³ ≈ 8.4 million), crossing over (50–200 crossovers per meiosis), and random fertilization — to argue that no two non-identical-twin siblings have ever been genetically identical, and **distinguish** this multiplicative diversity from naive additive counting.
10. **Build** a meiosis-as-inheritance simulator (`01-meiosis-mendel.html`) with two panels: (a) a chromosomal animation of Mendel's laws under independent assortment, perfect linkage, and partial linkage with a recombination-frequency slider; (b) an X-linked-recessive pedigree generator with selectable real diseases (hemophilia, color blindness, Duchenne muscular dystrophy).

**Prerequisites.** Chapter 00 (Punnett squares as bookkeeping; the 2ⁿ gamete count assumed; the 1:2:1, 9:3:3:1, 27:9:9:9:3:3:3:1 ratios). The vocabulary of allele / locus / gene / genotype / phenotype / homozygous / heterozygous / dominant / recessive (Ch 00). No prior cell biology assumed — I will introduce the parts of meiosis you need, briefly, before the inheritance argument is made. If you have read the sibling book *Biology +1: The Cell* Chapter 13 ("Meiosis and Sexual Reproduction"), you have already met the molecular choreography in full; this chapter assumes you have not, and treats meiosis as a service mechanism for genetics rather than as the subject in itself.

---

## A scene from a Kansas graduate student's microscope, 1902

Lawrence, Kansas, in the late autumn of 1901, then through the spring of 1902. A 24-year-old graduate student named Walter Sutton is sitting at a brass binocular microscope in the zoology department of the University of Kansas, looking at slides of testis cells from a large grasshopper, *Brachystola magna* — the lubber grasshopper of the Kansas prairie. He has trapped his own specimens. He has fixed and sectioned and stained the cells with the methods he learned from his teacher, Clarence E. McClung. He is doing the cytology he can do; what he is hoping to see is the *behavior* of chromosomes during the cell divisions that produce sperm.

Sutton has the advantage of unusually large chromosomes. *Brachystola* has 22 autosomes plus an X chromosome in males, and at certain stages of spermatogenesis the chromosomes are large enough and well-separated enough that he can count them, distinguish them by size, and watch what they do across consecutive divisions in adjacent cells of the same testis section. He has seen things that European cytologists working on smaller cells could not see clearly. Specifically, he has seen that the chromosomes during the first meiotic division come in *pairs* — and that the two members of each pair, after pairing up early in the division, separate from each other so that each daughter cell receives one chromosome from each pair, never two of the same pair and never two from different pairs added together. He has also seen that the orientation of one pair relative to another at the metaphase plate is independent — bivalents do not coordinate which member of the pair goes to which pole.

Sometime in early 1902, Sutton writes a short paper that he submits to *The Biological Bulletin*. It will appear in print in December of that year as a six-page note titled *On the morphology of the chromosome group in Brachystola magna* ([Sutton WS. *Biol Bull*. 1902;4:24–39](https://www.journals.uchicago.edu/doi/10.2307/1535510)). At the end of that paper he makes a tentative connection: the behavior of chromosome pairs at meiosis is exactly the behavior one would expect if chromosomes were the physical carriers of Mendel's hereditary factors. In a second, longer paper the following year — *The chromosomes in heredity*, in the same journal ([Sutton WS. *Biol Bull*. 1903;4:231–250](https://www.journals.uchicago.edu/doi/10.2307/1535741)) — he develops the argument in full. The factors that Gregor Mendel had inferred from breeding experiments forty years earlier *are*, Sutton argues, located on the chromosomes that cytologists can see under the microscope.

The same year, the German embryologist **Theodor Boveri**, working in Würzburg on sea urchin eggs fertilized by multiple sperm, arrives at a closely related conclusion from a different direction. By artificially producing sea urchin zygotes with abnormal chromosome compositions, Boveri shows that the chromosomes are not interchangeable — each one carries something distinct, and the loss or duplication of specific chromosomes produces specific developmental abnormalities. Chromosomes are *individuated*, in his language: each member of the diploid set is a different thing, with a different hereditary role ([Boveri T. *Über mehrpolige Mitosen als Mittel zur Analyse des Zellkerns*. Verhandlungen der physikalisch-medicinischen Gesellschaft zu Würzburg. 1902;35:67–90](https://www.degruyter.com/) [verify exact citation]; English summary in [Baltzer F. *Theodor Boveri: The Life and Work of a Great Biologist*. University of California Press; 1967]).

The conclusion that emerges from Sutton's 1903 paper and Boveri's 1902–1904 papers, taken together, is what biology now calls the **chromosomal theory of inheritance**: *Mendel's factors are chromosomes; the inheritance pattern of any factor is the meiotic behavior of the chromosome carrying it.* Three parallels make the case.

**Parallel 1: Pairs.** Mendel's factors come in pairs — one from each parent — at each locus in each individual. So do chromosomes in somatic cells: 23 maternal plus 23 paternal in humans, paired up homologously. Sutton's grasshopper testis cells displayed the pairs visually; you could count them.

**Parallel 2: Segregation.** Mendel's factor pairs separate cleanly into gametes so that each gamete carries one factor from each pair, not both and not neither. Chromosome pairs do the same thing at anaphase I — the two homologs of each pair go to opposite poles, one to each daughter cell. The cytological behavior matches the breeding result exactly.

**Parallel 3: Independence between pairs.** Mendel's factors at different loci, when located on different chromosomes (which Mendel did not know but happened to be true for all seven of his pea traits), assort independently — the inheritance of one is uncorrelated with the inheritance of another. Different chromosome pairs orient independently at metaphase I — bivalent A can have its maternal homolog going to the left while bivalent B has its maternal homolog going to the right, with all four combinations equally likely. Again, cytology matches breeding.

Three parallels, all from cytology that anyone with a microscope could in principle reproduce, between abstract mathematical patterns that had been published in 1865 and physical movements that anyone could watch through the brass eyepiece in 1902. Sutton's contribution was noticing the alignment; he was twenty-four years old and writing his master's thesis.

The chapter that follows turns this alignment into a mechanism. We will pick up each Mendelian law in turn, point to the meiotic event that produces it, and run the inheritance prediction back from the cells to the offspring counts. Then we will look at the case where the chromosomal theory says Mendel's Second Law should *fail* — when two genes are on the same chromosome and refuse to assort independently — and find that this failure is itself a measurable thing that builds the first geometric pictures of the genome. Then we will pick up the X chromosome's special asymmetry, which generates the inheritance pattern that lets a genetic counselor diagnose hemophilia in a family from the pedigree alone. And we will end by counting, on the page, how three meiotic randomization mechanisms multiply together to make every gamete a draw from an essentially infinite lottery.

There is one promise this chapter is making before it starts. The mechanism of meiosis, in all its molecular detail — the synaptonemal complex, the cohesin-protection trick, the Spo11-induced double-strand breaks that initiate recombination, the maternal-age effect on nondisjunction mediated by decaying cohesin in prophase-I-arrested oocytes — is the subject of *Biology +1: The Cell* Chapter 13. That book is where you go for the molecular choreography. This chapter touches each piece of choreography only long enough to make the inheritance argument clear, then moves on. The cell-biology depth is in the other book. The genetics depth is here.

---

## The arithmetic problem, and meiosis as its solution

Before we walk to the inheritance argument, the chromosome bookkeeping has to be made specific. Most of what looks confusing about meiosis is bookkeeping.

A **diploid** cell carries two copies of every chromosome. In humans, 46 in total: 22 pairs of **autosomes** (numbered 1 through 22, ordered roughly by size) plus one pair of **sex chromosomes** (XX in females, XY in males). The two members of each autosomal pair are called **homologous chromosomes** — *homologous* meaning *same gene content in the same order along the chromosome*, where "same gene content" means the same set of loci and "same order" means those loci appear in the same sequence along the DNA. One member of each pair came from the individual's mother; the other came from the individual's father. They carry the same genes — but they may carry different *alleles* at any given locus. Your maternal chromosome 11 has a hemoglobin-beta gene at one specific position on its short arm; your paternal chromosome 11 has a hemoglobin-beta gene at the corresponding position on its short arm; but one of those genes might encode the normal sequence and the other might encode the sickle-cell variant. Same locus, different alleles. *Homologous* is shorthand for "matched in content but allowed to differ in sequence."

A **haploid** cell carries one copy of every chromosome. In humans, 23 chromosomes. The 23 in any one haploid gamete are not all from the mother or all from the father — they are a *mixture*, one chromosome from each homologous pair, drawn at random from maternal or paternal origin. That random draw is the source of Mendel's Second Law, which we will get to.

The arithmetic of the problem is the one Sutton names cleanly in his 1903 paper. If fertilization fuses two cells into one (sperm + egg → zygote), and the diploid count must be conserved across generations (humans have always had 46 chromosomes), then the cells that fuse must each carry half the diploid count. Sperm 23 + egg 23 = zygote 46. If sperm and egg each carried the full 46, the zygote would have 92, its children would have 184, and within ten generations the genome would be unworkable.

Something has to halve the chromosome count before fertilization doubles it. That something is **meiosis**: a specialized variant of cell division that takes one diploid cell (46 chromosomes in humans) and produces four haploid daughter cells (23 chromosomes each), each of which matures into a gamete (sperm, egg, pollen, spore). Meiosis differs from ordinary cell division (mitosis) in three architectural ways: there are *two* divisions instead of one, with only *one* round of DNA replication beforehand; the first division separates *homologous chromosomes* rather than sister chromatids; and the cell spends a long prophase I physically linking homologs by **crossing over** (a topic we will return to in the section on linkage).

The bookkeeping you need to carry through this chapter is the running chromosome count. Let me lay it out as a table:

| Stage | Chromosome number | Chromatids per chromosome | Total DNA double helices |
|-------|------------------|---------------------------|--------------------------|
| Germ-line cell before S phase | 46 (2n) | 1 | 46 |
| After S phase (DNA replication) | 46 (2n) | 2 | 92 |
| After meiosis I (two daughters) | 23 (n) each | 2 | 46 each |
| After meiosis II (four gametes) | 23 (n) each | 1 | 23 each |
| After fertilization (zygote) | 46 (2n) | 1 | 46 |

The two columns that matter for the inheritance argument are the chromosome-number column (which is halved at meiosis I) and the chromatids-per-chromosome column (which is halved at meiosis II). The two divisions split the bookkeeping in two — meiosis I reduces chromosome *count*, meiosis II reduces chromatid *count* per chromosome — and the two operations together produce gametes with one copy of every chromosome, each chromosome a single DNA molecule, ready to fuse with another gamete and restore the diploid count.

The reason meiosis I is called the **reductional division** is that it is the step that reduces ploidy (2n → n). Meiosis II is called the **equational division** because it preserves ploidy (n → n; the chromatids per chromosome change but the chromosome count does not). For the inheritance argument, almost everything interesting happens at meiosis I.

---

## Mendel's First Law, in cells: anaphase I and the segregation of alleles

Mendel's First Law — the **Law of Segregation** — says, in his own framing reconstructed from 1865, *that the two factors at each locus separate cleanly during gamete formation, so each gamete carries exactly one factor from each pair, with the two factors of a heterozygote represented equally in the gamete pool*. In modern allele language: *the two alleles at each locus segregate into different gametes; a heterozygote Aa produces gametes that are exactly 50% A and 50% a*.

Mendel arrived at this by counting offspring. He crossed homozygous AA pea plants (round seeds) with homozygous aa plants (wrinkled seeds), got an F₁ generation that was all heterozygous Aa with round seeds (because A is dominant), then let those F₁ plants self-pollinate to produce F₂. He counted 5,474 round and 1,850 wrinkled seeds, for a ratio of 2.96:1 (close enough to 3:1 for him to call it 3:1). The 3:1 ratio is what you get if Aa × Aa produces gametes A and a from each parent in exactly equal proportions, and those gametes combine randomly: AA (1/4), Aa (1/4), Aa (1/4), aa (1/4), with the three dominant-genotype boxes producing round seeds and the one recessive-genotype box producing wrinkled. The 3:1 phenotype ratio requires that gametes split exactly 50:50. Mendel did not know why — he could not see chromosomes — but the count required it.

Now watch what happens in a cell.

Take a heterozygous *Aa* parent — say a pea plant that received the round-seed allele *A* from one parent and the wrinkled-seed allele *a* from the other. In every somatic cell of this plant, there are two copies of chromosome 7 (peas have seven chromosome pairs; the seed-shape gene happens to be on chromosome 7 in real peas, though that is incidental to the argument). One copy of chromosome 7 carries the *A* allele at the seed-shape locus. The other copy of chromosome 7 carries the *a* allele at the same locus. The two copies are homologous — same locus, different alleles.

The plant enters its reproductive phase. A diploid germ-line cell in the anther begins meiosis. The cell first replicates its DNA in S phase, so that each chromosome now consists of two sister chromatids joined at the **centromere** (a specific region of the chromosome where the chromatids are held together by protein rings called cohesin — same architecture as in mitosis; see cell-book Ch 13 for the molecular details). After replication, the cell contains two homologous copies of chromosome 7 — each now a pair of sister chromatids:

- Maternal chromosome 7: two sister chromatids, each carrying *A*.
- Paternal chromosome 7: two sister chromatids, each carrying *a*.

In **prophase I**, the cell does something that has no counterpart in mitosis: the two homologous chromosomes find each other across the nucleus and pair along their length, forming a **bivalent** (also called a tetrad because the structure contains four chromatids — two sisters from each homolog). The pairing is intimate, base-pair–scale aligned, mediated by a protein scaffold called the synaptonemal complex (cell-book Ch 13). Within the paired bivalent, recombination machinery introduces one or more **crossovers** between non-sister chromatids of the two homologs (we will return to this in the linkage section); for the moment, assume zero crossovers in the region of the seed-shape locus, so the *A* and *a* alleles stay on their original chromatids.

At **metaphase I**, the bivalent — the paired homologs — aligns at the equator of the cell, attached to spindle microtubules from opposite poles. The four-chromatid bivalent is oriented so that the two sister chromatids of the maternal homolog face one pole, and the two sister chromatids of the paternal homolog face the other pole.

At **anaphase I**, the spindle pulls the two homologs apart. The maternal chromosome 7 (with its two *A*-bearing sister chromatids still joined at the centromere) goes to one pole. The paternal chromosome 7 (with its two *a*-bearing sister chromatids still joined at the centromere) goes to the other. *The sister chromatids do not separate at this division.* What separates is the *homologous pair*. After anaphase I, the cell has produced two daughter cells:

- Daughter 1: 23 chromosomes (one from each pair), each consisting of two sister chromatids. The chromosome 7 in this cell carries *A*.
- Daughter 2: 23 chromosomes, each consisting of two sister chromatids. The chromosome 7 in this cell carries *a*.

Each daughter cell is haploid in chromosome number (n = 23) but each chromosome is still doubled. This is the architectural oddity meiosis II will fix.

The two daughters now enter **meiosis II**. This is essentially mitosis on a haploid cell — the centromere cohesin that protected the sister chromatids through meiosis I is now cleaved, the spindle pulls sister chromatids to opposite poles, and each daughter divides once more. The four-chromatid bookkeeping resolves cleanly:

- Daughter 1 (carrying chromosome 7 with *A*) → two gametes, each with a single chromosome 7 carrying *A*.
- Daughter 2 (carrying chromosome 7 with *a*) → two gametes, each with a single chromosome 7 carrying *a*.

The result of one complete meiosis on a single *Aa* parent cell: **four haploid gametes, of which two carry *A* and two carry *a***. The ratio is exactly 1:1. Mendel's First Law in cells.

Notice what just happened. Mendel observed, from breeding experiments, that the two alleles of a heterozygote enter gametes in equal numbers. He posited *factors* that "segregate" without saying what they were or how they did it. Sutton, looking at grasshopper cells, watched homologous chromosomes pair at prophase I, line up as bivalents at metaphase I, and separate at anaphase I — one homolog to each daughter. The cellular behavior produces exactly the breeding result Mendel had counted. The 50:50 segregation Mendel needed is the cytologically obvious consequence of one chromosome from each pair going to each pole.

This is parallel #2 of the chromosomal theory, with the chromosome story now turned into a Mendelian prediction. **Anaphase I is the molecular basis of Mendel's First Law.**

The genotype frequency of an *Aa* × *Aa* cross — 1 AA : 2 Aa : 1 aa — follows immediately from this. Both parents make gametes in a 1:1 ratio of A to a (Mendel's First Law, via anaphase I segregation). Random fertilization combines them: half the eggs are A, half are a; half the sperm/pollen are A, half are a; the four resulting genotype boxes — AA, Aa, Aa, aa — appear in equal proportions; the genotypes combine 1:2:1; with complete dominance the phenotype ratio is 3:1. The Punnett square you built in Chapter 00 is a 2 × 2 grid whose two row labels and two column labels are *exactly the two products of meiosis* in a heterozygous parent. The grid is bookkeeping for the gametes that anaphase I produces.

A clarification worth pausing on, because students conflate it. The Punnett square counts *gametes*, not individual offspring. Each cell of the Punnett square is the genotype that *would* result if a row gamete fused with a column gamete. The 1:2:1 ratio is a statement about *expected proportions across many offspring*, not a recipe that produces exactly one of each. The probabilistic structure is binomial — for *n* independent offspring of an Aa × Aa cross, the count of aa offspring is Binomial(*n*, 1/4), with mean *n*/4 and standard deviation √(*n* · 1/4 · 3/4). With four offspring you might get exactly 1 aa; you might get 0 or 2 or 3. The 1:2:1 is the *expectation*. This is why Mendel's ~28,000 plants matter — large samples produce tight ratios; small samples produce coincidences. (Chapter 02 examines Mendel's data and Fisher's 1936 challenge to it.)

---

## Mendel's Second Law, in cells: independent orientation at metaphase I

Mendel's Second Law — the **Law of Independent Assortment** — says that the two factors at one locus enter gametes independently of the two factors at any other locus. Cross *AaBb* × *AaBb*, with *A* and *B* at different loci, and the F₂ phenotype ratio is 9 A_B_ : 3 A_bb : 3 aaB_ : 1 aabb. Mendel got this from a different pea-plant cross — true-breeding round yellow plants (RRYY) crossed with true-breeding wrinkled green plants (rryy), F₁ all RrYy round yellow, F₂ count of 315 round yellow : 108 round green : 101 wrinkled yellow : 32 wrinkled green = 9.84 : 3.38 : 3.16 : 1, which he rounded to 9 : 3 : 3 : 1 ([Mendel 1866 *Verhandlungen* 4:3–47](https://www.biodiversitylibrary.org/item/124773); see Ch 02 for the full breeding logic).

The 9:3:3:1 ratio requires that the four gamete types from each *RrYy* parent — RY, Ry, rY, ry — appear in exactly equal proportions, 1:1:1:1. If the R/r locus and the Y/y locus assort independently in gametes, then the gamete frequencies factor: P(RY) = P(R) × P(Y) = 1/2 × 1/2 = 1/4, and so on for the other three. *Independence of loci in gametes* is the mechanistic requirement. The 9:3:3:1 phenotype ratio is the consequence.

Mendel did not know why two unrelated traits would assort independently. He could not see chromosomes. He had no language for what "independence" meant at the cellular level. He observed it across all twenty-one combinations of his seven traits ([Mendel 1866, Table III](https://www.biodiversitylibrary.org/item/124773) [verify]) and called it a law.

Now watch what happens at metaphase I.

Take a heterozygous *AaBb* plant, where the A/a locus is on one chromosome (call it chromosome 1) and the B/b locus is on a different chromosome (chromosome 2). After S phase, the germ-line cell entering meiosis has:

- Two copies of chromosome 1 (one carrying *A*, one carrying *a*), each as a pair of sister chromatids.
- Two copies of chromosome 2 (one carrying *B*, one carrying *b*), each as a pair of sister chromatids.

At prophase I, two bivalents form — one for chromosome 1, one for chromosome 2. The two bivalents are physically separate structures in the nucleus; they do not interact.

At metaphase I, both bivalents align at the cell equator. Each bivalent independently chooses which homolog faces which pole. *Each choice is an independent coin flip with equal probability.* For bivalent 1, the *A*-carrying homolog faces the left pole with probability 1/2 and the right pole with probability 1/2. For bivalent 2, the *B*-carrying homolog faces the left pole with probability 1/2 and the right pole with probability 1/2 — independently of bivalent 1's orientation.

There are four equally likely metaphase-I configurations:

1. *A* left, *B* left → after anaphase I, left daughter has *AB*, right daughter has *ab*.
2. *A* left, *B* right → left daughter has *Ab*, right daughter has *aB*.
3. *A* right, *B* left → left daughter has *aB*, right daughter has *Ab*.
4. *A* right, *B* right → left daughter has *ab*, right daughter has *AB*.

Each configuration produces two haploid daughters with specific genotypes. After meiosis II, each daughter divides into two identical gametes (since sister chromatids carry the same alleles, in the absence of crossing over). So configurations 1 and 4 each produce two AB gametes and two ab gametes; configurations 2 and 3 each produce two Ab gametes and two aB gametes.

Averaging across many germ-line cells, with each of the four configurations occurring at frequency 1/4, the *AaBb* parent produces gametes in the ratio:

- AB: 1/4 (1/2 from config 1 + 1/2 from config 4 weighted by their frequencies) = 1/4
- Ab: 1/4
- aB: 1/4
- ab: 1/4

Four gamete types, 1:1:1:1. Exactly what Mendel's Second Law requires.

The mechanism is the *independent orientation of bivalents at metaphase I*. Each chromosome pair makes an independent choice; the choices multiply because they are independent events; the four equally likely outcomes are the four gamete types in equal proportion. Mendel's Second Law, viewed this way, is the statement that *bivalents orient independently at metaphase I.* The chromosome theory bridges Mendel's statistical observation and the cellular mechanism. If you remember nothing else from this section, remember this.

For *n* independently orienting bivalents — *n* heterozygous loci on *n* different chromosomes — the number of distinct gamete types is 2ⁿ. Each bivalent contributes a factor of 2 (which homolog goes which way), and the bivalents are independent, so the choices multiply. This is the 2ⁿ count Chapter 00's Punnett square assumed; now you know where it comes from. The number is the count of distinct *metaphase-I orientations* in the meiosis.

For humans, with 23 chromosome pairs, the number is 2²³. Let me compute it on the page, because this is one of the numbers students remember from biology forever and most do not actually pause to multiply:

2¹⁰ = 1,024 (close to 1,000 — good thing to memorize)
2²⁰ = 1,024² = 1,048,576 (about a million)
2²³ = 2²⁰ × 2³ = 1,048,576 × 8 = **8,388,608**

About **8.4 million distinct gamete types** per human individual, from independent assortment alone, *before crossing over is considered at all*. This is the source of the "independent assortment" half of human gamete diversity — and it is the count of distinct metaphase-I orientations that 23 bivalents can adopt in one meiosis.

Notice the multiplicative structure. The number 8.4 million is not 23 × something. It is 2 × 2 × 2 × ... (twenty-three times). Each chromosome pair multiplies the count by 2. The 8.4-million result is the consequence of independence — if the orientations of different bivalents were correlated, the count would be smaller. The independence of the metaphase-I plate is the multiplicative engine.

For *AaBb* × *AaBb* — two heterozygous loci on different chromosomes, both parents — the gamete combinatorics is straightforward:

- Each parent makes 2² = 4 gamete types in equal proportion: AB, Ab, aB, ab at 1/4 each.
- Random fertilization combines them: the offspring genotype is a row × column choice on a 4 × 4 Punnett square = 16 equally likely cells.
- Under complete dominance at both loci, the phenotype classes are A_B_ (9 cells), A_bb (3 cells), aaB_ (3 cells), aabb (1 cell). The 9:3:3:1 ratio.

This is Mendel's Second Law, in cells, ending where Chapter 00 began. The 9:3:3:1 ratio you computed combinatorially is the consequence of two heterozygous loci on different chromosomes, where each meiosis produces four equally likely gamete types because *two bivalents orient independently at metaphase I*.

A pause on a piece of Mendel's luck, because it matters for the chapter that follows. Mendel chose seven traits in pea plants — seed shape, seed color, pod color, pod shape, flower color, flower position, stem length. By extraordinary luck (or extraordinary unconscious selection, depending on which historian you read), *all seven traits are controlled by genes on different chromosomes, or far enough apart on the same chromosome that they effectively assort independently*. Peas have seven chromosome pairs. Mendel chose seven traits. Each one happens to assort independently of the others. If he had chosen two traits that were tightly linked — both, say, on the short arm of chromosome 4 — he would have seen non-Mendelian inheritance and might have published a much more confusing paper. The 9:3:3:1 ratio held across all twenty-one pairs of his seven traits ([Mendel 1866 Table III](https://www.biodiversitylibrary.org/item/124773) [verify]; the chromosomal locations of the seven Mendel genes were not fully mapped until decades after his rediscovery, but the rough story holds — see [Reid & Ross 2011 *Genetics* 189:3–10](https://academic.oup.com/genetics/article/189/1/3/6068078) for a recent mapping).

This luck was not, in 1866, recognizable. It became recognizable only after the chromosomal theory was articulated (1902–1903) and after T. H. Morgan and his students discovered linkage and started mapping genes to chromosomes (starting around 1910 — coming up next). When Mendel's Second Law was first challenged by exceptions, the exceptions turned out not to break the chromosomal theory but to *confirm* it. Two genes that did not assort independently were on the same chromosome. The exception became a measurement tool.

---

## When the Second Law fails: linkage, and Sturtevant's 1913 maps

The chromosomal theory makes a sharp prediction that Mendel's data could not test, because all of Mendel's traits happened to be on different chromosomes. The prediction: *when two genes are on the same chromosome, they do not assort independently.* Their alleles tend to travel together into gametes, because the chromosome they share segregates as a unit at meiosis. Mendel's Second Law — which assumes independence between any two loci — should *fail* for genes that share a chromosome.

This prediction was tested, found correct, and developed into a quantitative tool in the years 1910–1913 by **Thomas Hunt Morgan**'s group at Columbia University, working on the fruit fly *Drosophila melanogaster*. The argument is worth seeing in its original form, because it shows the chromosomal theory doing something Mendel's framework alone could not — explaining a specific quantitative deviation from the 9:3:3:1 ratio in terms of a physical distance along the chromosome.

Consider two genes on the same chromosome. Call them *A* (with alleles A, a) and *B* (with alleles B, b). Take a parent that is heterozygous at both loci, with the *A* and *B* alleles on the same homolog (the "in cis" or "coupling" configuration: one chromosome carries AB, the other carries ab). The genotype is *AB/ab* — written this way to indicate that A and B are linked on one chromosome, while a and b are linked on the other.

Now run meiosis on this cell. The single bivalent contains the two homologs (AB and ab). At metaphase I, the bivalent orients independently — but there is only one bivalent here for these two genes, not two. The "independent orientation" argument that gave 1:1:1:1 in the unlinked case does not apply, because there is only one chromosome pair carrying both loci.

If no crossover happens in the bivalent between the A locus and the B locus, then the homologs separate at anaphase I exactly as they entered prophase I: the AB chromatids go to one daughter, the ab chromatids go to the other. After meiosis II, the four gametes are: two AB and two ab. *Perfect linkage* — only the parental gamete types appear. The ratio is 1 AB : 1 ab, not 1:1:1:1.

If a crossover does happen between the A locus and the B locus, the picture changes. A crossover is a physical exchange between non-sister chromatids of the two homologs, mediated during prophase I by the synaptonemal complex and the recombination machinery (Spo11 induces a double-strand break, RAD51/DMC1 catalyze strand invasion, the Holliday junction resolves into a reciprocal exchange — molecular details in cell-book Ch 13). The net effect: one chromatid of the AB chromosome trades its B-end for the ab chromosome's b-end, producing a recombinant Ab chromatid; symmetrically, one chromatid of the ab chromosome ends up as a recombinant aB chromatid. After the crossover, the bivalent contains: one parental AB chromatid, one recombinant Ab chromatid, one recombinant aB chromatid, one parental ab chromatid.

After meiosis I and meiosis II, this bivalent produces four gametes: one AB, one Ab, one aB, one ab — *one of each*, in equal proportions, *for this meiosis*. The two parental gamete types (AB and ab) appear once each; the two recombinant gamete types (Ab and aB) appear once each.

Now average over many meioses. In some, no crossover happens between the A and B loci — those meioses produce only AB and ab gametes (parentals), 1:1. In others, a crossover does happen — those meioses produce all four types, 1:1:1:1.

Let **r** be the **recombination frequency** between the two loci — the proportion of gametes that are recombinant. This is a measurable quantity: cross the heterozygous *AB/ab* parent with a homozygous *ab/ab* tester (a testcross, Ch 02 develops the logic), count the offspring of each phenotype, and the ratio of recombinant to total tells you r directly. By construction, r runs from 0 (perfect linkage, no crossovers between the loci) to 0.5 (loci so far apart that crossovers happen in essentially every meiosis, producing 50% parental and 50% recombinant gametes — indistinguishable from independent assortment).

Under partial linkage, the gamete proportions from the *AB/ab* heterozygote are:

- AB (parental): (1 − r)/2
- ab (parental): (1 − r)/2
- Ab (recombinant): r/2
- aB (recombinant): r/2

The two parental types each at (1 − r)/2; the two recombinant types each at r/2. At r = 0, only parentals (1:1, no recombinants). At r = 0.5, all four types in equal 1:1:1:1 proportion — exactly as if the genes were unlinked. At r = 0.25, parentals at 0.375 each and recombinants at 0.125 each — a 3:1:1:3 ratio of (AB : Ab : aB : ab) gametes, sharply different from Mendel's 1:1:1:1 expectation.

This is the cell-level prediction of the chromosomal theory: *the gamete ratio from a doubly-heterozygous parent depends on whether the two loci are on the same chromosome (and how far apart) or on different chromosomes (always 1:1:1:1).* The chromosomal theory predicts a *quantitative spectrum* of deviation from Mendel's Second Law, indexed by physical distance along the chromosome.

In 1911, Morgan and his colleagues published the first evidence that two *Drosophila* genes did not assort independently — yellow body color and white eye color, both on the X chromosome ([Morgan TH. *Random segregation versus coupling in Mendelian inheritance*. *Science*. 1911;34(873):384](https://www.science.org/doi/10.1126/science.34.873.384) [verify]). In 1913, Morgan's twenty-year-old undergraduate student **Alfred Sturtevant**, sitting on his bedroom floor in Manhattan after a meeting with Morgan, made the leap that turned this into a measurement tool: *recombination frequency is a measure of physical distance along the chromosome*.

The leap, made specific. Two loci very close together on a chromosome rarely have a crossover between them — there is not much DNA between the loci, so the chance that a crossover lands in the gap is low. Two loci far apart on a chromosome often have a crossover between them — there is a lot of DNA in the gap, so the chance is high. Recombination frequency should be a *monotonically increasing function of physical distance*. So you can build a *map* of the genome by measuring recombination frequencies between pairs of loci and arranging them in a linear order consistent with all the pairwise distances.

Sturtevant did this in 1913, using six X-linked genes in *Drosophila* — yellow body, white eye, vermilion eye, miniature wing, rudimentary wing, and a sixth allele I cannot retrieve from the paper without re-checking ([Sturtevant AH. *The linear arrangement of six sex-linked factors in Drosophila, as shown by their mode of association*. *J Exp Zool*. 1913;14(1):43–59](https://onlinelibrary.wiley.com/doi/10.1002/jez.1400140104)). From the pairwise recombination frequencies, he constructed the first **genetic linkage map** of any chromosome — a linear arrangement showing the relative order of the six genes and the relative distances between them. The y-w (yellow-white) distance was small. The y-r (yellow-rudimentary) distance was much larger. The intermediate distances arranged consistently in a line.

Sturtevant defined a unit of map distance: *1 map unit = 1% recombination frequency*. This unit was later named the **centimorgan (cM)** in Morgan's honor. 1 cM ≈ 1% recombination. A pair of loci 10 cM apart has roughly 10% recombination frequency. A pair 20 cM apart has roughly 20%. The relationship is approximately linear up to ~25 cM, after which double crossovers start to mask single crossovers and the simple correspondence breaks down (a topic addressed by Haldane's 1919 mapping function and later by Kosambi's, both of which adjust for double-crossover interference).

The centimorgan is not a unit of physical distance — it is a unit of recombination frequency. The conversion between centimorgans and physical base pairs is non-uniform along the chromosome, because crossovers are concentrated at "hotspots" defined by chromatin marks rather than spread evenly. In humans, the rough average is 1 cM ≈ 1 megabase (10⁶ base pairs), but the local conversion can range from 0.1 to 10× this depending on hotspot density. The human genome is roughly 3,300 cM in females and 2,600 cM in males [verify against current deCODE / 1000 Genomes maps; the female-vs-male asymmetry reflects more crossovers in female meiosis], and roughly 3.2 × 10⁹ base pairs in total.

Why does this matter for genetics? Because the chromosomal theory, made quantitative, gives you a tool. Once you can measure recombination frequencies between pairs of marker loci, you can:

1. **Determine whether two genes are linked.** If r ≈ 0.5 (with statistical confidence given the sample size), the genes assort independently and are either on different chromosomes or far enough apart on the same chromosome to have effectively 50% recombination. If r is significantly less than 0.5, the genes are linked.
2. **Order genes along a chromosome.** Three-point crosses (with three linked markers) let you order the genes — if A-B is 8 cM and B-C is 5 cM and A-C is 13 cM, the order is A-B-C (with distances additive within the linear-approximation regime).
3. **Localize a gene of unknown chromosomal location.** Cross the unknown gene against a panel of known markers; whichever markers show non-independent assortment with the unknown gene tell you which chromosome it is on, and the recombination frequencies tell you where.

Sturtevant's 1913 paper is the founding document of **genetic mapping**. The technique it introduced — measuring recombination frequencies to infer chromosomal positions — was the only way to map genes for the next sixty years, until DNA sequencing in the 1970s and the human genome project in the 2000s replaced linkage mapping with direct physical mapping. Even now, linkage analysis remains the standard tool for mapping disease-causing mutations in families, before sequencing pinpoints the variant. The principle that *recombination frequency measures physical distance* is the foundation of family-based genetic studies, including the genome-wide association studies (GWAS) and quantitative-trait-locus (QTL) mapping that dominate modern human genetics. (Chapter 03 develops Mendelian extensions; Chapter 07 covers modern genomics and GWAS.)

A pause on the philosophical move, because it is one of the most powerful in the chapter. The chromosomal theory turned an *exception* to Mendel's Second Law into a *measurement device*. The cases where Mendel's law fails are precisely the cases where you can measure something the law assumed away. The deviation, made quantitative, gives you the *physical structure of the chromosome* — the linear order of genes, the rough spacing between them, the first geometric picture of the genome. This is the move scientific exceptions sometimes do: not "the theory was wrong" but "the theory's assumption can be relaxed in a way that reveals the underlying structure." The 9:3:3:1 ratio is the limit of strong-linkage analysis (r = 0.5) and tightly-linked analysis is the limit (r = 0). Everything in between is a measurement.

---

## A worked example — three cases of the same dihybrid cross, by chromosomal position

Take an *AaBb* parent and a tester *aabb*. Cross them. Predict the gamete ratios from the heterozygote — and therefore the F₁ offspring genotype ratios — under three scenarios for the chromosomal position of the A/a and B/b loci.

I am doing this in detail because the three cases are the chapter's main quantitative result. The lesson is that the chromosomal theory predicts *all three* — Mendel's Second Law, perfect linkage, and partial linkage — from the same single principle (chromosomes segregate as units; crossovers within a chromosome shuffle alleles between homologs at a rate proportional to physical distance).

**Case 1: A/a and B/b on different chromosomes.** Two bivalents form at prophase I. At metaphase I, the two bivalents orient independently — four equally likely configurations (AB-left, Ab-left, aB-left, ab-left, by which alleles end up at the same pole). After anaphase I and meiosis II, the gamete ratio is:

- AB: 1/4
- Ab: 1/4
- aB: 1/4
- ab: 1/4

Cross with *aabb* tester (which makes only ab gametes). Offspring genotype ratio = gamete ratio of the heterozygote:

- AaBb: 1/4
- Aabb: 1/4
- aaBb: 1/4
- aabb: 1/4

Phenotype ratio under complete dominance: 1 (dominant at both) : 1 (dominant at A, recessive at B) : 1 (recessive at A, dominant at B) : 1 (recessive at both). The 1:1:1:1 testcross ratio. This is the chromosomal-theory rendering of Mendel's Second Law.

**Case 2: A/a and B/b on the same chromosome, no crossing over.** One bivalent forms. In the heterozygote, the A and B alleles are in cis (on the same homolog) — the genotype is AB/ab (one chromosome carries A and B, the other carries a and b). At metaphase I and anaphase I, the two homologs separate as units. After meiosis II, the gamete ratio is:

- AB (parental): 1/2
- ab (parental): 1/2
- Ab (recombinant): 0
- aB (recombinant): 0

Cross with *aabb* tester. Offspring genotype ratio:

- AaBb: 1/2 (parental phenotype, dominant at both)
- aabb: 1/2 (parental phenotype, recessive at both)
- Aabb: 0
- aaBb: 0

Phenotype ratio: 1 (dominant at both) : 1 (recessive at both). Only two phenotypes appear; the other two are absent. The 9:3:3:1 ratio that would have appeared in F₂ collapses to 1:1 in the testcross. The two parental classes appear; the two recombinant classes vanish.

This is **perfect linkage** — what you get when two genes are on the same chromosome and no crossover happens between them. Mendel's Second Law fails completely. The two alleles travel together because they ride the same chromosome.

**Case 3: A/a and B/b on the same chromosome, partial linkage with recombination frequency r.** One bivalent forms. At prophase I, crossovers happen in the bivalent at random along its length. The fraction of meioses in which a crossover occurs *between* the A locus and the B locus is determined by the physical distance between the loci — call this distance d (in centimorgans). For small d, r ≈ d/100 (1% recombination ≈ 1 cM). At larger d, the approximation breaks down because double crossovers start to appear, but for d ≤ 25 cM the linear approximation is reasonable.

After meiosis II, the gamete ratio is:

- AB (parental): (1 − r)/2
- ab (parental): (1 − r)/2
- Ab (recombinant): r/2
- aB (recombinant): r/2

Cross with *aabb* tester. Offspring genotype ratio = gamete ratio of the heterozygote.

For a numerical example, take r = 0.20 (the two loci are about 20 cM apart). Then:

- AaBb (parental): 0.40
- aabb (parental): 0.40
- Aabb (recombinant): 0.10
- aaBb (recombinant): 0.10

If you ran the testcross with 1,000 offspring, you would expect about 400 AaBb, 400 aabb, 100 Aabb, 100 aaBb. The parental phenotypes outnumber the recombinant phenotypes by a factor of 4:1 (400:100). The two recombinant phenotypes appear in equal numbers, and the two parental phenotypes appear in equal numbers — a checkerboard of equal pairs.

Compute the recombination frequency from this data: r = (recombinants)/(total) = (100 + 100)/(400 + 400 + 100 + 100) = 200/1000 = 0.20. The recombination frequency is 20%. The map distance between the A and B loci is approximately 20 centimorgans.

That is Sturtevant's measurement. Run the testcross. Count the four offspring classes. Compute the recombinant fraction. The number tells you the map distance.

The lesson of the worked example. The chromosomal theory explains both *why Mendel's Second Law works* (genes on different chromosomes, independent metaphase-I orientation, 1:1:1:1 gametes) *and when it fails* (genes on the same chromosome, single bivalent, parental gametes dominate). The meiotic mechanics determine the inheritance pattern. The exception is not a failure of the theory — it is a window into the chromosomal architecture.

The limit. This is the simple two-gene case. Real linkage analysis with many genes uses statistical methods (logarithm-of-odds scores, multipoint linkage analysis) to estimate map distances and is the foundation of all modern genetic mapping. The simple "count the four classes, compute r" approach works for the bookkeeping example; the statistical machinery for genome-wide mapping is more elaborate and is the subject of human genetics courses past Chapter 03.

---

## The X chromosome's special arithmetic: sex-linked inheritance and Morgan's white-eyed fly

A separate consequence of the chromosomal theory comes from the asymmetry of the sex chromosomes. In humans (and in most mammals, and in *Drosophila*), females have two X chromosomes (XX) and males have one X and one Y (XY). The Y chromosome carries very few genes — fewer than 100 protein-coding genes in humans, mostly involved in male sex determination and spermatogenesis — and shares only short "pseudoautosomal" regions with the X. The X chromosome, in contrast, carries on the order of 800 protein-coding genes [verify against current GENCODE annotation], many of them not involved in sex at all but doing ordinary cellular jobs.

A gene on the X chromosome that has nothing to do with sex — say, a gene for a blood-clotting factor, or a gene for a retinal photopigment, or a gene for the muscle protein dystrophin — has an inheritance pattern that *differs by sex* simply because males and females have different numbers of X chromosomes. This is the cellular basis of **sex-linked inheritance**.

The first evidence came from T. H. Morgan's fly room at Columbia in 1910. Morgan had been breeding *Drosophila melanogaster* — fruit flies — by the tens of thousands, hoping to find genetic variants that would let him test the chromosomal theory. In May 1910, he found one. Among thousands of red-eyed flies, a single male appeared with white eyes. He crossed it with red-eyed females and got an F₁ generation that was uniformly red-eyed — suggesting white was recessive. He let F₁ flies interbreed and counted F₂. The expected Mendelian 3:1 phenotype ratio appeared — but with a striking twist: *all of the white-eyed F₂ flies were male*. None of the female F₂ flies had white eyes. ([Morgan TH. *Sex limited inheritance in Drosophila*. *Science*. 1910;32(812):120–122](https://www.science.org/doi/10.1126/science.32.812.120).)

The chromosomal theory had no explanation for the absence of white-eyed females — *unless* the white-eye gene was on the X chromosome. If the white-eye gene was on the X, the inheritance pattern would be:

- The original white-eyed male had genotype X^w / Y (where X^w means an X carrying the recessive white allele, w).
- The red-eyed females he was crossed with had genotype X^+ / X^+ (two X chromosomes, both carrying the wild-type red allele, +).
- F₁ daughters got an X^w from the father and an X^+ from the mother: X^+ / X^w. They were heterozygous and red-eyed (because red is dominant over white). F₁ sons got a Y from the father and an X^+ from the mother: X^+ / Y. They were red-eyed.
- F₁ females (X^+ / X^w) interbred with F₁ males (X^+ / Y). F₂ daughters got one X from the mother (X^+ or X^w with equal probability) and one X from the father (X^+ from his single X). So F₂ daughters were either X^+ / X^+ (red) or X^+ / X^w (red, heterozygous carrier). No white-eyed daughters appeared, because daughters cannot be homozygous X^w unless the father carries an X^w — but in this cross the father was X^+ / Y, so he could not contribute X^w to his daughters.
- F₂ sons got a Y from the father and either X^+ or X^w from the heterozygous mother. So F₂ sons were either X^+ / Y (red) or X^w / Y (white). Half of F₂ sons were white-eyed.

The prediction snapped to the data. Morgan published the result in *Science* in July 1910, three months after finding the original white-eyed male. The chromosomal theory had its first direct experimental confirmation in *Drosophila*: a gene whose inheritance pattern matched the inheritance of the X chromosome.

The Morgan story is worth pausing on because of what it set off. The fly room became the most productive genetics laboratory of the early 20th century. Morgan and his students (Sturtevant, Bridges, Muller, Painter — collectively the "Morgan school") used *Drosophila* to map dozens of genes to chromosomes, build linkage maps, characterize chromosomal aberrations (deletions, duplications, inversions, translocations), and lay the foundation for all of modern genetics. Morgan won the Nobel Prize in 1933 — the first Nobel awarded for genetics — "for his discoveries concerning the role played by the chromosome in heredity." The chromosomal theory was no longer a thesis; it was a research program.

Now let me make the inheritance arithmetic of X-linked recessive disorders specific, because this is the most important piece of clinical genetics for the chapter. The general setup: a recessive disease allele on the X chromosome. Males have only one X, so a male with the recessive allele has the disease — he has no second allele to "rescue" him. Females have two X chromosomes; a female with one recessive allele is a *heterozygous carrier* (phenotypically normal but able to pass the allele to offspring); a female with two recessive alleles has the disease (rare, requires both parents to contribute the recessive allele).

The vocabulary you need: a male with one recessive allele on his single X is called **hemizygous** — *hemi-* meaning *half*, because he has only half the normal allele complement. Hemizygosity is the X-chromosome–specific genotype that produces the asymmetry between male and female inheritance patterns. (The term applies to any gene where the individual has only one copy — including Y-linked genes in males, where the male is hemizygous for everything on the Y, but the term is most commonly used for X-linked genes in males.)

Three real X-linked recessive disorders the chapter uses as examples:

**Hemophilia A** is caused by mutations in the *F8* gene on the long arm of the X chromosome (Xq28), which encodes coagulation factor VIII. Affected individuals (almost always males) have impaired blood clotting, leading to spontaneous bleeding into joints and tissues. Incidence is about 1 in 5,000 male births [verify against [Mannucci & Tuddenham 2001 *N Engl J Med* 344:1773–1779](https://www.nejm.org/doi/full/10.1056/NEJM200106073442307)]. The most famous historical pedigree is that of Queen Victoria, who was a carrier (her son Leopold had hemophilia and several of her daughters and granddaughters were carriers; the allele entered the royal houses of Russia, Spain, and Germany through her daughters' marriages, producing the famous case of Tsarevich Alexei Romanov in early 20th-century Russia ([Rogaev et al. 2009 *Science* 326:817](https://www.science.org/doi/10.1126/science.1180660) confirmed the Romanov hemophilia allele as F9 Hemophilia B by sequencing exhumed remains)).

**Red-green color blindness** is caused by mutations in the *OPN1LW* and *OPN1MW* genes on the long arm of the X chromosome (Xq28), encoding the long-wavelength and medium-wavelength cone photopigments. Affected individuals have reduced ability to distinguish red and green. Incidence is about 8% of males and 0.5% of females in populations of European descent [verify against [Sharpe et al. 1999 in *Color Vision* MIT Press](https://mitpress.mit.edu/9780262194204/color-vision/)]. The male-female asymmetry — 16× more common in males — is the diagnostic signature of X-linked recessive inheritance.

**Duchenne muscular dystrophy (DMD)** is caused by mutations in the *DMD* gene on the short arm of the X chromosome (Xp21), which encodes dystrophin — a structural protein that links the muscle cell cytoskeleton to the extracellular matrix. *DMD* is the largest known human gene (~2.4 megabases, spanning over 1% of the X chromosome) and consequently has a high mutation rate. Loss-of-function mutations produce DMD, which manifests in early childhood as progressive muscle weakness, usually leading to loss of ambulation by age 12 and severely reduced life expectancy. Incidence is about 1 in 3,500 male births [verify against [Mendell et al. 2012 *Ann Neurol* 71:304–313](https://onlinelibrary.wiley.com/doi/10.1002/ana.23528)]. About 30% of DMD cases arise from new (de novo) mutations rather than inherited from a carrier mother — a consequence of the large gene size and the unusual mutation arithmetic of X-linked recessive disorders (because affected males rarely reproduce, the population frequency of the disease allele is maintained primarily by new mutations rather than by inheritance, in proportions described by [Haldane 1935 *J Genet* 31:317–326](https://www.ias.ac.in/article/fulltext/jgen/031/03/0317-0326) [verify]).

The cellular event behind every inherited case of an X-linked recessive disorder is the same. The carrier mother carries one mutant X and one wild-type X. In her oocytes, the two X chromosomes pair at meiosis I (the X chromosome does have a homolog in females, unlike males) and segregate normally at anaphase I. Half her eggs carry the mutant X; half carry the wild-type X. Random fertilization combines these with sperm from the unaffected father, who has one normal X and one Y. The four equally likely offspring genotypes from this cross are:

- X^+ from mother + X^+ from father → daughter X^+ / X^+ (unaffected, not a carrier)
- X^w from mother + X^+ from father → daughter X^+ / X^w (unaffected, carrier)
- X^+ from mother + Y from father → son X^+ / Y (unaffected)
- X^w from mother + Y from father → son X^w / Y (affected)

Probabilities, in any single pregnancy from a carrier mother × unaffected father:

- P(daughter unaffected non-carrier) = 1/4
- P(daughter unaffected carrier) = 1/4
- P(son unaffected) = 1/4
- P(son affected) = 1/4

Conditional on the offspring being female: P(carrier) = 1/2, P(unaffected) = 1/2. Conditional on being male: P(affected) = 1/2, P(unaffected) = 1/2. (These are the numbers a genetic counselor gives a couple in the consultation room.)

Two diagnostic features distinguish X-linked recessive inheritance from autosomal recessive inheritance in a pedigree:

**(1) No father-to-son transmission.** Because sons inherit a Y from their fathers (not an X), an affected father cannot transmit an X-linked allele to a son. If a pedigree shows an affected father whose son is also affected, the inheritance pattern is *not* X-linked recessive (it is most likely autosomal dominant). This is the cleanest diagnostic test.

**(2) Affected sons of carrier mothers.** The diagnostic checkerboard of an X-linked recessive disorder in a pedigree is a *carrier mother* (heterozygous, phenotypically normal) producing approximately half affected sons and half unaffected sons, with daughters approximately half carriers and half non-carriers (all phenotypically normal under simple complete recessivity). When you see a pedigree with affected males scattered across generations, transmitted through phenotypically normal females, with no affected females and no father-to-son transmission, the diagnosis is essentially confirmed.

The molecular event that produces a carrier egg is anaphase I of meiosis I in the carrier mother. Her two X chromosomes pair as a bivalent (the X-X pair behaves homologously, like any other autosomal bivalent — the X chromosome's special status is only in males, where it lacks a homologous partner). At anaphase I, the two X homologs separate. Half her oocytes go on to carry her wild-type X; half carry her mutant X. The cellular asymmetry — the meiotic event that produces some carrier eggs and some non-carrier eggs — happens in *every meiosis*, every cycle. The clinical asymmetry — half affected sons, half carrier daughters — is the consequence.

A clarification about X-inactivation, because students sometimes get confused about why heterozygous carrier females are unaffected. Females have two X chromosomes, but in any given cell only one X is transcriptionally active — the other is condensed into a transcriptionally silent **Barr body** through a process called **X-inactivation** ([Lyon MF. *Nature*. 1961;190:372–373](https://www.nature.com/articles/190372a0)). The choice of which X to inactivate is random, made early in embryonic development, and clonally inherited. A heterozygous carrier female is therefore a *mosaic* — about half her cells express the wild-type X and half express the mutant X. For most X-linked recessive disorders, the half-normal-expression in the body is enough to produce a normal phenotype. (For some carriers, especially when X-inactivation happens to be skewed against the wild-type X, mild manifestations of the disease appear — "manifesting carriers." This is a wrinkle on the simple recessive model.)

For X-linked *dominant* disorders (rarer than X-linked recessive), the inheritance pattern is different — affected fathers transmit the trait to all daughters and no sons; affected mothers transmit to half of each. X-linked dominant disorders include incontinentia pigmenti and Rett syndrome; they are diagnosed by a pedigree pattern where affected females outnumber affected males (because affected males often have severe phenotypes incompatible with reproduction, or even with live birth). For autosomal dominant disorders (like Huntington's disease or achondroplasia), affected individuals pass the trait to half their offspring of either sex. For autosomal recessive disorders (cystic fibrosis, sickle-cell disease, Tay-Sachs), affected individuals are typically born to two heterozygous carrier parents, and the pedigree shows scattered cases in single sibships with no transmission from parents to children (because the carrier parents are phenotypically normal). The four diagnostic patterns — autosomal dominant, autosomal recessive, X-linked dominant, X-linked recessive — are the standard pedigree-analysis taxonomy you will see in any clinical genetics course.

---

## When meiosis fails: nondisjunction and aneuploidy, briefly

The same chromosomal-segregation machinery that produces healthy haploid gametes when it works produces gametes with the wrong chromosome count when it fails. The failure mode is called **nondisjunction**: chromosomes (in meiosis I) or sister chromatids (in meiosis II) fail to separate properly, both going to the same daughter cell. The result is a gamete with an extra chromosome (n + 1 = 24) or a missing chromosome (n − 1 = 22). When such a gamete fuses with a normal gamete at fertilization, the zygote is **trisomic** (47 chromosomes, three copies of one chromosome) or **monosomic** (45 chromosomes, only one copy of one chromosome).

I am going to be brief on this section, because the cell-biology depth — the molecular mechanism of nondisjunction, the shugoshin/cohesin choreography, the maternal-age effect on Down syndrome — is the central subject of cell-book Ch 13. The genetics-relevant question is which aneuploidies are compatible with live birth and why.

Most autosomal aneuploidies are not viable. A human fetus with the wrong number of any major chromosome usually does not survive past the first trimester; about 50% of first-trimester miscarriages carry an abnormal karyotype, most often an autosomal trisomy [verify against current ESHRE / ACOG data]. The autosomal trisomies compatible with live birth are restricted to the three smallest autosomes — chromosomes 13, 18, and 21 — because the smallest chromosomes carry the fewest genes, and the dosage imbalance produced by a 50% extra copy of those genes is barely tolerable. (Trisomies of larger chromosomes carry too many dosage-imbalanced genes; the developmental program cannot proceed.) The three viable autosomal trisomies are:

- **Trisomy 21 (Down syndrome).** Incidence ~1 per 700 live births in unselected populations [verify]. Phenotype includes intellectual disability of variable severity, characteristic facial features, increased risk of congenital heart defects, and increased risk of early-onset Alzheimer's disease. The maternal-age effect — incidence rising from ~1/1,500 at age 20 to ~1/30 at age 45 — is the strongest age-dependent phenomenon in human reproduction, and is mediated by gradual loss of meiotic cohesin in prophase-I-arrested oocytes (cell-book Ch 13 develops this).
- **Trisomy 18 (Edwards syndrome).** Incidence ~1 per 5,000 live births [verify]. Severe phenotype, most affected infants die in the first year.
- **Trisomy 13 (Patau syndrome).** Incidence ~1 per 16,000 live births [verify]. Severe phenotype, very high mortality.

The sex-chromosome aneuploidies are different. They are mostly compatible with life because of X-inactivation — all but one X in any cell is silenced, so individuals with extra X chromosomes are buffered against the dosage imbalance. The common sex-chromosome aneuploidies:

- **XXY (Klinefelter syndrome).** Incidence ~1 per 600 male live births [verify]. Mostly mild phenotype, often diagnosed only in adulthood during evaluation for infertility.
- **XO (Turner syndrome).** Incidence ~1 per 2,500 female live births [verify], though most XO conceptions are lost as first-trimester miscarriages and the survivors are a heavily selected subset. Phenotype includes short stature, gonadal dysgenesis, sometimes cardiac defects.
- **XYY.** Incidence ~1 per 1,000 male live births [verify]. Mostly subclinical.
- **XXX.** Incidence ~1 per 1,000 female live births [verify]. Often subclinical.

The contrast between autosomal and sex-chromosome aneuploidies — almost all autosomal trisomies lethal in utero except 13/18/21; most sex-chromosome aneuploidies viable and often subclinical — is a clean illustration of how *dosage buffering* (X-inactivation in this case) determines aneuploidy tolerance.

The chapter ends the brief aneuploidy section here. The clinical and molecular depth is cell-book Ch 13.

---

## Three sources of human gamete diversity, multiplied

Now the running count. Sexual reproduction generates genetic variation by three independent mechanisms, operating at different points in the meiosis-fertilization sequence. Each mechanism is a randomization. Together they multiply — and the multiplicative structure is the chapter's largest number.

**Mechanism 1: Independent assortment at metaphase I.** As we worked out earlier, 23 chromosome pairs orienting independently produce 2²³ = 8,388,608 distinct gamete types per human individual — *before* crossing over is considered at all.

**Mechanism 2: Crossing over during prophase I.** Each meiosis introduces approximately 50–200 reciprocal exchanges between non-sister chromatids of homologous pairs ([verify range against [Wang et al. 2012 *Am J Hum Genet* 90:691–700](https://www.cell.com/ajhg/abstract/S0002-9297(12)00148-0); the exact number depends on sex and individual variation — female meiosis has more crossovers than male, with the female genome roughly 4,400 cM and the male about 2,700 cM [verify against [Kong et al. 2002 *Nat Genet* 31:241–247](https://www.nature.com/articles/ng917)]). Every chromosome has at least one crossover; most have several. Each crossover creates a recombinant chromatid that carries maternal sequence in some regions and paternal sequence in others. Two siblings inherit recombinant chromatids with crossovers at *different* locations, so each sibling's chromosome 7 (or any other chromosome) is a *different* mosaic of the parents' two chromosome-7 sequences.

The combinatorial space of possible recombinant configurations of a chromosome is large and not easy to compute exactly, because crossover locations are continuous (any base position is in principle a valid crossover point, though hotspot biology concentrates them at specific positions) and the *number* of crossovers per chromosome is itself variable. For practical purposes, treat crossing over as a multiplier that turns a finite number of possible chromosome combinations (from independent assortment) into a near-continuous space of possible chromosome sequences. A single chromosome can come in thousands of recombinant configurations; 23 chromosomes multiplied is "incomprehensibly large."

**Mechanism 3: Random fertilization.** Any sperm can fuse with any egg. A typical human ejaculate contains roughly 200–300 million sperm [verify against current WHO semen analysis standards]; a typical ovulation releases one egg. The combinatorial calculation for *one couple, one offspring*, considering only independent assortment, is:

8,388,608 (egg genotypes from mother) × 8,388,608 (sperm genotypes from father) = **70,368,744,177,664**

Approximately **7 × 10¹³, or 70 trillion** possible zygote genotypes from one specific couple — before crossing over is considered. With crossing over, the number is effectively unbounded.

Pause on this. There have been roughly 100 billion humans who have ever lived (10¹¹). The number of distinct zygote genotypes any one couple could produce, considering only independent assortment, exceeds the total number of humans who have ever existed by a factor of about 700. Considering crossing over, the excess is by many orders of magnitude more. Two genetically identical full siblings (other than identical twins, who share a zygote that split after fertilization) are not improbable; they are *not possible* in any practical sense.

This is the basis of the statement "you have never existed before." It is not poetry. It is the consequence of three independent randomization mechanisms multiplying together: 8.4 million × 8.4 million × (huge crossover diversity) = unique.

The lesson of the worked-out arithmetic. The combinatorial explosion of sexual reproduction is *not* additive (8.4M + 8.4M + crossovers ≈ 17M-ish). It is *multiplicative* (8.4M × 8.4M × crossover diversity ≈ ∞). Three randomization mechanisms operating at three different points in the process, on three different physical objects, compose. The point of repeating this is that students very often try to add the mechanisms — they say "and the total diversity is the sum of these three." It is not. They multiply. The multiplication is what makes each gamete unique.

The limit. This calculation assumes truly independent mechanisms and uniform combinatorial sampling. Reality is messier — crossover hotspots concentrate recombination at specific locations rather than spreading it uniformly; some chromosome configurations are incompatible with viability and so are filtered out before being observed; allelic combinations can have epistatic interactions that distort selection on the resulting zygote. The 70-trillion figure is a useful order-of-magnitude estimate of the *space* of possible zygote genotypes; the *probability distribution* over that space is not uniform, and post-fertilization selection (mostly via miscarriage of chromosomally abnormal conceptions) trims it. But the order of magnitude is correct, and the multiplicative structure is the right model.

---

## Common misconceptions

**"Mendel knew about chromosomes."** No. Mendel published in 1866. The word *chromosome* was not coined until 1888, by Heinrich Wilhelm Waldeyer-Hartz. The chromosomal theory of inheritance — the proposal that Mendel's factors are chromosomes — was not articulated until 1902–1903, sixteen years after Mendel's death (he died in 1884). Mendel inferred *factors* — abstract entities that came in pairs, segregated cleanly, and assorted independently — entirely from breeding data. He had no microscopic evidence and no molecular model. The chromosomal theory was a *posthumous* identification of Mendel's factors with a physical structure that cytologists had only recently learned to see and stain reliably. This matters historically because it tells you something about how scientific inference works — Mendel's framework was correct at the abstract level (allele frequencies, segregation, independent assortment) before any physical interpretation was available, and the physical interpretation, when it arrived, slotted in exactly because the math had already been right.

**"All genes assort independently."** No. Only genes that are either (a) on different chromosomes or (b) far enough apart on the same chromosome (~50 cM or more) to have effectively 50% recombination behave Mendelianly. Genes on the same chromosome and physically close to each other are *linked* — their alleles travel together at much higher than 50% rates. The vast majority of pairs of genes in a genome are linked to some other gene; complete independence is the exception, not the rule. Mendel's Second Law works as a general principle only because most human textbook genetics examples are deliberately chosen to involve unlinked loci. Real human inheritance, especially for traits that share chromosomes, deviates from Mendel's expectations in characterized ways. Linkage is not a violation of the chromosomal theory — it is one of its predictions.

**"Crossing over is rare and only happens in special circumstances."** No. Every meiosis has crossovers — at least one per chromosome pair, because a crossover is mechanically necessary to hold homologs together at metaphase I (the chiasmata are the physical connections that allow the spindle to keep the bivalent paired until anaphase I; without them, homologs would dissociate and segregate randomly, producing aneuploid gametes). In humans, the typical meiosis has 50–200 crossovers across the genome, distributed roughly proportional to chromosome length. Crossing over is the default state of meiosis, not an exceptional event. The combinatorial implications — every gamete is a recombinant mosaic of maternal and paternal sequence — follow from this universal occurrence.

**"X-linked recessive disorders affect only males."** Almost, but not quite. Females with two recessive alleles at an X-linked locus do show the disease — this requires an affected (or carrier) father and a carrier mother, both contributing a recessive allele. The reason X-linked recessive disorders appear "to affect only males" in most pedigrees is that the disease allele is usually rare enough that the joint probability of inheriting it from both parents is very low. For very common X-linked recessive conditions (red-green color blindness, with population allele frequency ~8% in males of European descent), homozygous affected females do appear at the rate expected under Hardy-Weinberg (about 0.5% — the square of the male frequency, when males and females have the same underlying allele frequency in the population). For rare conditions like hemophilia, female affected individuals are extremely rare but not impossible — and have appeared historically. Additionally, "manifesting carriers" — heterozygous females with skewed X-inactivation against the wild-type X — show mild forms of some X-linked recessive disorders. The "only males" simplification is approximately right for rare disorders but breaks down for common ones.

**"Independent assortment and crossing over are the same thing."** No. They are two different mechanisms operating at two different stages of meiosis on two different physical objects, and their effects compose multiplicatively. Independent assortment is the random orientation of *different* bivalents at metaphase I; it shuffles whole chromosomes between gametes, and it produces 2ⁿ distinct combinations for n chromosomes. Crossing over is the physical exchange of segments between non-sister chromatids *within* one bivalent during prophase I; it shuffles segments *within* a chromosome, and it produces near-continuous variation in recombinant chromatid sequences. Independent assortment operates on chromosomes as units; crossing over operates on chromosomal segments within a chromosome. Both produce gamete diversity, but they produce different *kinds* of diversity, and they multiply.

**"The chromosomal theory was obvious once Mendel was rediscovered."** No. Mendel's work was rediscovered in 1900 (by de Vries, Correns, and Tschermak independently — Chapter 02 develops the rediscovery story). The chromosomal theory was articulated in 1902–1903 by Sutton and Boveri. But it was not widely accepted for at least another decade. The leading geneticist of the era, William Bateson — who coined the word "genetics" in 1906 — was skeptical of the chromosomal theory until well into the 1910s, partly because he favored a model where heredity was carried by some other physical substrate (he was vague about what). The chromosomal theory became dominant only after Morgan's *Drosophila* work in 1910–1915 directly demonstrated the predictive power of mapping genes to specific chromosomes. The intellectual lag between "Mendel was right" (1900) and "Mendel's factors are chromosomes" (consensus by ~1915) was about fifteen years, and it had to be argued through specific experimental confirmations rather than accepted as obvious.

---

## A worked example — running the full inheritance prediction backwards

Take a specific clinical scenario and trace it through every level of the chapter's framework. This is the move the chromosomal theory makes possible — connecting a pedigree pattern observed in a family to the meiotic event that produced it.

**The scenario.** A 32-year-old woman comes to a genetic counseling appointment because her brother died of Duchenne muscular dystrophy at age 22, and she is considering having children. She does not yet know whether she is a carrier of the *DMD* mutation that her brother carried. Her parents' family history: her brother is the only affected individual in the family. Her mother (the patient's maternal lineage) had two brothers, neither of whom had DMD, both of whom died in old age. Her maternal grandmother also had two brothers, unaffected. Her father has no known family history of DMD.

The genetic counselor walks through the analysis with her. The conversation has three parts.

**Part 1: What is the inheritance pattern?** DMD is X-linked recessive. The diagnostic checkerboard: affected males, no father-to-son transmission, carrier mothers, no affected females in the family. The brother was affected. Her parents must therefore have transmitted his X^w from the carrier-mother (X^+ / X^w) side, because his father (X^+ / Y) could only contribute Y to him. The mother was the obligate carrier.

But the mother does not have affected brothers (the patient's maternal uncles), so the carrier status of the mother is *new* — either the mother is a *de novo* carrier (the *DMD* mutation arose in one of the mother's parents' gametes, not inherited from her maternal grandparents' families) or the mother is an inherited carrier but with the mutation arising in her own germ line. Given that *DMD* has about a 30% de novo mutation rate (from the gene's enormous size — 2.4 megabases — and resulting high mutation target), the de novo scenario is plausible.

**Part 2: What is the probability the patient is a carrier?** The mother was definitely a carrier (because her son had the disease). The mother had two X chromosomes — one carrying the mutant *DMD* allele, one carrying the wild-type allele. In each of her meioses, half her eggs carried the mutant X and half carried the wild-type X. The patient was conceived from one such meiosis. With no other information, the patient's prior probability of having inherited the mutant X is 1/2.

But the patient has some information that can update this. She is 32 years old, has had no symptoms of muscle weakness, and has had no other affected children (though we are told she has not yet had children, so this last point does not apply). The lack of symptoms is consistent with being a non-carrier *or* being a carrier with favorable X-inactivation (manifesting carriers are rare but possible for *DMD*). The lack of symptoms therefore does not strongly update the prior. (A *DMD*-specific carrier-detection test — measurement of serum creatine kinase, or direct sequencing of the *DMD* gene, or analysis of dystrophin protein in muscle biopsy — can confirm or refute carrier status definitively, and is part of the counseling workup.)

For the prediction below, let us assume the patient's carrier probability remains close to 1/2 (the prior), pending a definitive *DMD* sequencing test.

**Part 3: What are the offspring probabilities if she is a carrier?** If the patient is a carrier (X^+ / X^w) and her husband is an unaffected man (X^+ / Y), each pregnancy has the four equally likely outcomes:

- X^+ from her, X^+ from him → daughter X^+ / X^+ (non-carrier, unaffected): probability 1/4
- X^w from her, X^+ from him → daughter X^+ / X^w (carrier, unaffected): probability 1/4
- X^+ from her, Y from him → son X^+ / Y (unaffected): probability 1/4
- X^w from her, Y from him → son X^w / Y (affected): probability 1/4

Conditional on the offspring being female, P(carrier) = 1/2, P(non-carrier) = 1/2. Conditional on being male, P(affected) = 1/2, P(unaffected) = 1/2.

The counselor walks her through the chromosomal events. *If you carry the mutant X*, the counselor says, *then in each of your meioses, your two X chromosomes pair as a bivalent at prophase I. At metaphase I, the bivalent aligns at the plate, with one X facing each pole. At anaphase I, the two X chromosomes separate — one goes to each daughter cell. In half your eggs, the mutant X has gone to one side and ends up in the egg that matures and is ovulated. In the other half, the wild-type X is the one that ends up in the egg. The probability that any specific child inherits the mutant X from you is 1/2.* The probability that a child is *affected* depends on whether they also inherit a Y (from the father, son) or an X (from the father, daughter): if they get a Y, they are hemizygous and affected; if they get an X (which is wild-type), they are heterozygous and unaffected but a carrier.

Now combine the two probabilities. The patient's prior probability of being a carrier is 1/2 (because her mother was a carrier and each of her mother's eggs had a 50% chance of carrying the mutant X). Conditional on her being a carrier, the probability of an affected son is 1/2 per pregnancy (per the meiotic argument above). Joint probability of (carrier ∩ affected son), per pregnancy, with no other information: 1/2 × 1/2 = 1/4.

If she gets the *DMD* sequencing test and learns she is *not* a carrier, the joint probability drops to ~0 (apart from the small possibility of *de novo* mutation in her own germ line, which for DMD is roughly 10⁻⁴ per gamete). If she learns she *is* a carrier, the probability per pregnancy of an affected son rises to 1/2.

This is the counseling number — the 1/2 × 1/2 = 1/4 (or 1/2 × 1 = 1/2 after testing), conditional on each pregnancy. The chromosomal mechanism of meiosis I is the cellular event behind this number. The counseling conversation is, ultimately, a translation of a meiotic event into a clinical decision.

The lesson of the worked example. The chromosomal theory does not just explain why Mendel's laws work in pea plants. It explains why a 32-year-old woman in a clinical counseling room has a calculable probability of carrying a mutation, and a calculable probability of transmitting it to a son, with both probabilities traceable to the segregation of homologous X chromosomes at anaphase I of her mother's meiosis and (potentially) her own. Every clinical genetics calculation involving Mendelian traits is, at the cellular level, a calculation about chromosomes separating at anaphase I.

The limit. This is the simple two-allele single-locus case for an X-linked recessive disorder. Real clinical genetics is messier: incomplete penetrance, variable expressivity, mosaicism in carrier females, de novo mutations, and uncertainty about parental genotypes all complicate the calculation. The 1/4 number is the rough answer the patient gets in the first conversation; the refined answer requires DNA testing and a more nuanced probabilistic model. The chromosomal mechanism is the same — the additional complications are layered on top.

---

## Exercises

**Warm-up**

1. A heterozygous *Aa* pea plant enters meiosis. (a) After S phase, how many chromatids are there at the A locus across the cell? (b) After meiosis I, how many chromatids are there at the A locus in *each* daughter cell? (c) After meiosis II, how many chromatids are there at the A locus in *each* gamete? (d) Of the four gametes produced by one complete meiosis of this *Aa* plant, how many carry the *A* allele and how many carry the *a* allele? *Tests: meiotic bookkeeping for the simplest case, and the cellular basis of Mendel's First Law.*

2. An organism has *n* = 4 chromosome pairs and is heterozygous at one locus on each chromosome (call them A/a, B/b, C/c, D/d). (a) How many distinct gamete types can this organism produce by independent assortment alone, ignoring crossing over? (b) How many distinct metaphase-I orientations are possible? (c) Write out all the gamete types as four-letter strings (e.g., ABCD, aBCD, AbCD, …). *Tests: the 2ⁿ rule and its grounding in metaphase-I orientation.*

3. Two genes on the same chromosome show a recombination frequency of r = 0.15 in a testcross. (a) What is the map distance between them in centimorgans? (b) Of 1,000 offspring from a heterozygous *AB/ab* × *ab/ab* testcross, how many are expected to be each of the four phenotype classes (parental AB, parental ab, recombinant Ab, recombinant aB)? Show the calculation. *Tests: the centimorgan = % recombination conversion and the (1-r)/2, r/2 gamete-frequency formula.*

**Application**

4. **Pedigree diagnosis.** A family pedigree shows: a great-grandfather who was unaffected; his wife who was unaffected; their five children — three sons (one affected, two unaffected) and two daughters (both unaffected); the affected son had no children; one of the unaffected daughters married and had four children — two daughters (both unaffected) and two sons (one affected, one unaffected). The other unaffected daughter married and had three sons (all unaffected) and one daughter (unaffected). (a) What is the inheritance pattern? (b) Justify your diagnosis using the two diagnostic features (no father-to-son transmission, affected males through carrier females). (c) What is the probability that the affected great-grandson is a *de novo* mutation versus an inherited mutation from his mother? *Tests: pedigree analysis and diagnostic reasoning.*

5. **Linkage mapping.** Three genes (A, B, C) are linked on the same chromosome. In testcrosses, the pairwise recombination frequencies are: A-B = 8%, B-C = 5%, A-C = 12%. (a) What is the order of the three genes along the chromosome? (b) Are the three measured distances exactly additive (i.e., does A-B + B-C = A-C)? If not, why? (c) What is the map distance in centimorgans between each pair? *Tests: three-point linkage analysis and the consistency of map distances under the single-crossover approximation.*

6. **The X-linked recessive probability calculation.** A woman's brother had hemophilia A (X-linked recessive, F8 gene). Her mother is therefore an obligate carrier. The woman has no signs of hemophilia. She is married to a man without hemophilia. (a) What is the probability that she is a carrier? (b) What is the probability that her first son will have hemophilia, conditional on her carrier status being unknown? (c) After she takes a DNA test that confirms she is *not* a carrier, what is the probability that her first son will have hemophilia (assume *de novo* mutation rate is negligibly small)? (d) Diagram the meiotic event in her mother's oogenesis that produced the egg from which she was conceived, and identify the anaphase I event whose outcome determined her carrier status. *Tests: probabilistic reasoning, Bayesian updating after a test, and the cellular basis of carrier inheritance.*

**Synthesis**

7. **Why Mendel's luck mattered.** Mendel chose seven traits in pea plants, and by chance (or unconscious selection) all seven happened to assort independently. (a) Given that peas have seven chromosome pairs and Mendel chose seven traits, the *naive* probability that he picked one trait per chromosome is some number — compute it under the assumption that he picked traits uniformly at random from among the available pea-genetic traits, and assuming roughly one trait per chromosome arm. (Your answer will be a rough estimate, not a precise number, because the size of the "available trait pool" is hard to define.) (b) The actual mapping turns out that of Mendel's seven traits, two are on the same chromosome (chromosome 4: pod color and stem length, with a recombination frequency of ~15%) but assorted independently in his crosses because his F₂ sample sizes were not large enough to detect the linkage statistically. (See [Reid & Ross 2011 *Genetics* 189:3–10](https://academic.oup.com/genetics/article/189/1/3/6068078) for the modern mapping [verify].) (c) If Mendel had chosen two traits 10 cM apart on the same chromosome, what F₂ phenotype ratio would he have observed instead of 9:3:3:1? Compute the expected ratio. *Tests: integrating chromosomal theory, sample-size statistical limits, and the historical contingency of Mendel's discovery.*

8. **Three-mechanism diversity.** Use the multiplicative arithmetic to argue that two non-identical-twin full siblings cannot be genetically identical. Specifically: (a) Compute the probability that two siblings inherit the same chromosomes (same combination of maternal vs. paternal homologs at each of the 23 pairs) from each parent — assume no crossing over. (b) Show that even with this probability ignored, the conditional probability that two siblings have the same crossover pattern on every chromosome is essentially zero. (c) Combine the two calculations to give an order-of-magnitude argument that genetic identity between non-identical-twin siblings has probability approximately 10⁻⁵⁰ or smaller. *Tests: probabilistic reasoning about meiotic randomization and the multiplicative composition of independent mechanisms.*

**Challenge**

9. **The chromosomal theory tested against a counter-example.** Imagine you are reviewing a paper claiming that "Mendel's factors are not chromosomes — they are protein-particles in the cytoplasm that are inherited independently of chromosomes." The author cites a single experiment in which two traits showed 50% recombination across multiple crosses but were *not* mapped to different chromosomes by cytological staining (the chromosomes in this organism were not distinguishable under available microscopy). (a) Does this experiment refute the chromosomal theory? Why or why not? (b) What additional experiment would you propose to distinguish "two genes on different chromosomes" from "two cytoplasmic factors inherited independently"? (c) How does the absence of cytological resolution in the original experiment limit what conclusions are warranted? *Tests: applying the chromosomal theory to a hypothetical counter-example, and identifying what evidence would actually be diagnostic.*

10. **Build the simulation.** Using the Brutalist file conventions from Chapter 00, write the four-move prompt (Show / Say / Constrain / Verify) for `01-meiosis-mendel.html`. The simulation should have two panels: (a) a meiosis-as-inheritance panel that animates the meiotic chromosome behavior in a heterozygous AaBb parent and lets the user select whether A and B are on different chromosomes (animation shows two bivalents orienting independently), on the same chromosome with no crossing over (perfect linkage), or on the same chromosome with a user-specified recombination frequency 0 ≤ r ≤ 0.5 (animation shows the bivalent with crossovers occurring at the relevant rate); the gamete ratios update in real time as the user adjusts r, and the simulation prints PASS/FAIL verifications for the three boundary cases (1:1:1:1 at r = 0.5; 1:0:0:1 at r = 0; (1-r)/2 : r/2 : r/2 : (1-r)/2 at intermediate r); (b) an X-linked-recessive pedigree generator with selectable real diseases (hemophilia A, color blindness, Duchenne muscular dystrophy), controls for which parent is a carrier or affected, the sex of each child, and a readout that prints the probability of each phenotype for each offspring under the Mendelian-X-linked-recessive model; verification PASS/FAIL on the boundary case of carrier mother × unaffected father producing the 1/4 affected son ratio. *Deliverable:* The four-move prompt, the file (built and run), and a screenshot of the readout panel at r = 0.20 in the first panel. *Tests: the chapter's full mechanism applied through the same simulation-building method introduced in Chapter 00.*

---

## What would change my mind

The chromosomal theory as I have presented it — that Mendel's factors are chromosomes, that the meiotic behavior of chromosomes is the cellular mechanism of Mendelian inheritance — would fail as a general account if, in a well-characterized organism with karyotypable chromosomes and a reasonable mutational repertoire, two genes that demonstrably reside on the same chromosome (confirmed by physical mapping, fluorescent in situ hybridization, or genome sequencing) consistently showed 50% recombination across multiple crosses with adequate sample sizes — that is, behaved as if they were on different chromosomes despite being on the same one. This would imply that some mechanism beyond physical chromosome-pairing-and-segregation is doing the work of inheritance, and that the chromosomal theory's central claim (recombination frequency reflects physical distance) is wrong as a general principle. The evidence to date — sixty-plus years of physical mapping in *Drosophila*, mice, humans, yeast, and countless other species — shows that the chromosomal-physical-distance ↔ recombination-frequency correspondence holds robustly, with characterized deviations (hotspot clustering, sex-specific maps, mutation-rate-dependent effects on cohesin stability) explainable within the same framework. If such a deviation appeared in a clean experimental system, I would expect the chromosomal theory to be amended (additional mechanisms layered onto the framework) rather than overturned — but if it were truly clean and reproducible, I would have to consider that genes might also be carried by some other physical substrate. The fact that this has not been observed in over a century of cytogenetics is the basis on which the theory stands.

## Still puzzling

I do not yet fully understand why the genome-wide distribution of crossover hotspots is so non-uniform — specifically, why crossovers in humans concentrate at a relatively small set of hotspots (defined by the PRDM9 zinc-finger DNA-binding protein), why those hotspots are themselves remarkably species-specific (mouse hotspots are at different locations than human hotspots), and why the PRDM9 zinc-finger array is the most rapidly evolving protein-coding region in the human genome ([Myers et al. 2010 *Science* 327:876–879](https://www.science.org/doi/10.1126/science.1182363); [Baudat et al. 2010 *Science* 327:836–840](https://www.science.org/doi/10.1126/science.1183439)). The picture I find compelling is that crossover hotspots are an evolutionarily unstable population-genetic equilibrium between selection pressures (more crossovers at a hotspot mean more recombination, which can be adaptive in changing environments, but also more mutational damage to the hotspot DNA itself, which can be deleterious), but the model is not fully worked out and the question of why PRDM9 changes so fast — fast enough that closely related primates have largely non-overlapping hotspot locations — remains an active research area. The chapter's quantitative inheritance prediction (recombination frequency measures physical distance, 1 cM ≈ 1% recombination) is robust at the genome-average level, but the local conversion between centimorgans and base pairs is messier than the simple linear approximation suggests, and I am not yet confident I could give a student a fully satisfying mechanistic account of why crossover hotspots exist where they do.

---

## LLM Exercise — Build your meiosis-and-Mendel simulator

This block is the one you actually do. The prompt below is ready to paste at Claude (or ChatGPT, or Gemini) once you have CLAUDE.md and DESIGN.md saved in the same folder from Chapter 00.

### The simulation prompt

```
Show: Read CLAUDE.md and DESIGN.md from this project. Conform to them.

Say: Build 01-meiosis-mendel.html — a meiosis-as-inheritance
simulator with two panels.

Panel 1 — Chromosomal Mendel. Animate one complete meiosis of a
heterozygous parent at one or two loci (A/a and B/b). The user
toggles among three modes:
  (a) "Different chromosomes" — A and B on separate chromosomes.
      Two bivalents form, orient independently at metaphase I, and
      separate at anaphase I. Show four equally likely orientations
      cycling through, and tally the gamete proportions.
  (b) "Same chromosome, no crossing over" — A and B on one
      chromosome in cis (AB/ab). One bivalent forms; at anaphase I,
      the AB homolog goes to one pole and the ab homolog to the
      other. Only AB and ab gametes are produced.
  (c) "Same chromosome, recombination frequency r" — slider for r
      (0.00 to 0.50, step 0.01, default 0.20). The simulation
      visually displays the bivalent at prophase I with crossover
      events occurring at frequency r between the A and B loci, and
      tallies the resulting gamete proportions: AB at (1-r)/2, ab
      at (1-r)/2, Ab at r/2, aB at r/2.

The gamete ratio is displayed as a bar chart (using D3, four bars,
labeled AB, Ab, aB, ab; bars colored by genotype class per
DESIGN.md). The readout panel displays:
- the current mode
- the current value of r (in mode c)
- the four gamete proportions
- the predicted F1 testcross offspring ratio (gamete ratio × ab
  tester)
- a PASS/FAIL line for the boundary cases: r = 0 should give
  1:0:0:1 (parentals only); r = 0.5 should give 1:1:1:1 (as if
  unlinked); intermediate r should give the (1-r)/2 : r/2 : r/2 :
  (1-r)/2 ratio matching the formula.

Panel 2 — X-linked-recessive pedigree generator. The user selects:
- The disease (dropdown: hemophilia A [F8], red-green color
  blindness [OPN1LW/OPN1MW], Duchenne muscular dystrophy [DMD],
  population frequency parameters built in for each).
- The genotype of the mother: dropdown of "non-carrier", "carrier",
  "affected" (rare).
- The genotype of the father: dropdown of "unaffected", "affected"
  (carries the recessive on his single X).
- Number of children to simulate (slider, 1 to 12, default 4).
- Sex of each child (drop-downs for each, default random).

The simulation displays the pedigree as a small tree (squares for
males, circles for females, filled = affected, half-filled = carrier
female, empty = unaffected), and prints the calculated probability
of each phenotype for each child given the parental genotypes:
- For carrier mother × unaffected father: 1/2 daughters carrier,
  1/2 daughters non-carrier, 1/2 sons affected, 1/2 sons unaffected.
- For affected father × non-carrier mother: all daughters carrier,
  no sons affected (no father-to-son transmission).
- For carrier mother × affected father: 1/2 daughters affected, 1/2
  daughters carrier, 1/2 sons affected, 1/2 sons unaffected.
- For non-carrier mother × unaffected father: no offspring at risk
  (except for new mutation, which the simulation ignores).

The readout panel includes a "diagnostic test" toggle that, when
enabled, displays the two pedigree-diagnosis criteria with a
PASS/FAIL: (1) no father-to-son transmission in the displayed
pedigree (PASS if no affected son has an affected father in the
pedigree); (2) affected sons through carrier mothers (PASS if every
affected son has a carrier mother in the pedigree).

Constrain: Two panels side by side; SVG canvas 720 x 480 per panel.
Bivalent drawn as two homologous chromosomes (one blue, one red) of
length 300 px, with sister chromatids shown as parallel lines and
centromeres marked. Crossover events animated as instant exchanges
between non-sister chromatids at random positions along the bivalent
length, weighted to fall within or outside the A-B interval at
frequency r. Color the alleles A, a, B, b using genotype-class
colors per DESIGN.md (homozygous-dominant dark blue #1a5276;
heterozygous medium blue #2980b9; homozygous-recessive light blue
#85c1e9; affected red #c0392b). Single self-contained HTML file,
D3 v7 from CDN, no other dependencies. Add at the top of the
script:
// CLAIM: For two heterozygous loci with recombination frequency r,
// the gamete proportions are (1-r)/2, r/2, r/2, (1-r)/2 for the
// four classes (AB, Ab, aB, ab). At r = 0, only AB and ab gametes
// appear (perfect linkage); at r = 0.5, all four appear in 1:1:1:1
// proportion (Mendel's Second Law).

Verify: Print to the console on every parameter change, as PASS/FAIL
lines with measured values, expected values, and the case:
  (1) Panel 1, mode a (different chromosomes): gamete proportions
      must be {AB: 0.25, Ab: 0.25, aB: 0.25, ab: 0.25}, summing to 1.
  (2) Panel 1, mode b (perfect linkage): gamete proportions must be
      {AB: 0.5, Ab: 0, aB: 0, ab: 0.5}, summing to 1.
  (3) Panel 1, mode c, r = 0.20: gamete proportions must be
      {AB: 0.40, Ab: 0.10, aB: 0.10, ab: 0.40}, summing to 1.
  (4) Panel 1, mode c, r = 0.50: gamete proportions must equal mode
      a (1:1:1:1) to verify the boundary.
  (5) Panel 2, carrier mother × unaffected father: probability of
      affected son must be 0.25 (1/2 son × 1/2 mutant X), affected
      daughter must be 0 (under default rare-disease assumption);
      carrier daughter must be 0.25.
  (6) Panel 2, affected father × non-carrier mother: all daughters
      must be carriers (P = 0.5 per pregnancy), no sons affected
      (P = 0 per pregnancy) — verifying no father-to-son
      transmission.
```

### Exploration tasks

Once the simulation runs:

1. **The linkage spectrum.** Set Panel 1 to mode c. Step r through 0.00, 0.05, 0.10, 0.15, 0.20, 0.25, 0.30, 0.40, 0.50. At each step, write down the four gamete proportions and the predicted F1 testcross offspring ratio. At r = 0, the ratio collapses to 1:1 (parentals only). At r = 0.5, it expands to 1:1:1:1 (as if unlinked). At intermediate r, the ratio is asymmetric (parentals dominate over recombinants in a way that maps directly to r). Plot the predicted offspring ratio as a function of r — you will see the parental-recombinant divergence shrink continuously as r approaches 0.5. *Aside:* this is the experimentally measurable curve Sturtevant used in 1913 to build the first chromosome map.

2. **The pedigree diagnostic.** Set Panel 2 to "color blindness," with the mother as carrier and the father as affected. Generate 12 children. Note that some affected daughters now appear (because the father contributes a recessive X to all his daughters, so half of them — those who get the mutant X from the mother — are affected). Run the diagnostic check — *no father-to-son transmission* should still pass (because sons get a Y from the father, not the recessive X). This is the move that distinguishes X-linked recessive from autosomal recessive in a pedigree: the inheritance is not symmetric between mothers and fathers.

3. **A historical case.** Set Panel 2 to "hemophilia A," with the mother as carrier and the father as unaffected. Generate 9 children. Compare the expected outcomes to the historical pedigree of Queen Victoria's descendants — she had nine children, of whom (recorded) one son (Leopold) was affected and at least two daughters (Alice and Beatrice) were carriers. The simulation should produce a similar distribution on average, though any individual run will fluctuate around the expectation. This is the same statistical sampling issue that made Mendel's small sample sizes potentially mask the chromosome-4 linkage between pod color and stem length. *Sample size is everything* — at n = 9, you get a recognizable but noisy signal of the underlying X-linked recessive pattern.

### Extension prompt

Once the basic meiosis-Mendel simulator works, the obvious extension is to add the *cytological* layer — visualize the bivalent in three-dimensional space, with sister chromatids drawn as paired lines and crossover events shown as actual physical exchanges between non-sister chromatids. Paste this:

```
Extension: Modify 01-meiosis-mendel.html so that Panel 1's bivalent
animation shows the full meiotic choreography in five animated
phases:
  (a) Prophase I — show the two homologous chromosomes pairing
      along their length (synaptonemal complex implied as a thin
      central line). One crossover event per bivalent is drawn as a
      visible exchange between two non-sister chromatids at a
      random position along the length, weighted by r so that the
      crossover lands between the A and B loci with probability r.
  (b) Metaphase I — the bivalent aligns at the cell equator,
      attached to spindle microtubules from opposite poles. The
      orientation of the bivalent (which homolog faces which pole)
      is randomized for each animation cycle.
  (c) Anaphase I — homologs separate; one goes to each pole. Sister
      chromatids remain joined at the centromere.
  (d) Telophase I — two haploid daughter cells form, each with one
      homolog of two sister chromatids.
  (e) Meiosis II — sister chromatids separate in each daughter;
      four gametes result. Each gamete is colored by its genotype
      class.
The animation cycles continuously; the user can pause, step
through, or restart. Each frame is annotated with the phase name
and the chromosomal event (e.g., "anaphase I: homologs separating").
```

This extension is what makes the meiotic mechanism *visible* — and it is the simulation that students often find most clarifying, because the abstract argument of "homologs separate at anaphase I" becomes a concrete animation of two chromosomes moving in opposite directions.

A connection forward. The simulator you just built tells you *how* meiosis produces the gamete ratios that explain Mendel's laws. Chapter 02 takes the next step — what Mendel actually saw in his pea garden, the experimental design that let him infer the laws without ever seeing a chromosome, and the rediscovery of his work in 1900 by three independent investigators who arrived at the same conclusions from different starting points. The chromosomal theory in this chapter is the cellular explanation; Mendel's experimental program in Chapter 02 is the observational basis from which the explanation was inferred. The mechanism and the observation are two sides of the same scientific story — and Chapter 02 will show you what kind of breeding data, in what quantities, was sufficient to make the inference rigorous.

---

**What would change my mind:** If a clean experimental study in a karyotypable organism — say, modern *Drosophila* or *Arabidopsis* with full genome sequencing — showed that two genes physically located on the same chromosome (confirmed by FISH or whole-genome sequencing) consistently displayed 50% recombination across multiple crosses with statistically adequate sample sizes (i.e., behaved as if unlinked despite physically sharing a chromosome), the chromosomal theory's core prediction — that recombination frequency reflects physical chromosomal distance — would be falsified, and I would have to either amend the theory to allow additional inheritance substrates or replace it. To date the evidence is overwhelming that physical chromosome behavior governs inheritance in eukaryotes, but the principle of the chapter is to name what would change my mind.

**Still puzzling:** I do not yet fully understand why crossover hotspots — the specific genomic locations where recombination is concentrated — are so species-specific and so rapidly evolving via the PRDM9 zinc-finger array, and whether the cellular benefit of having hotspots (concentrating recombination machinery efficiently) outweighs the genetic cost (concentrating mutational damage at those same sites). The recombination-distance prediction holds robustly at genome averages, but the local picture — why a particular kilobase of human chromosome 7 has 5× the average crossover rate while a neighboring kilobase has 0.1× — remains an active research area I cannot summarize confidently in a single explanation.

---

**Tags:** chromosomal-theory-of-inheritance, Mendel's-laws, linkage-mapping, X-linked-inheritance, Sturtevant-1913
