# Chapter 10 — Population Genetics and Natural Selection: How Allele Frequencies Change, and How to Predict Them

**Suggested titles:**
- *Why a Mildly Deleterious Allele Sits at One in Ten — Sickle Cell, Malaria, and the Mathematics of an Equilibrium That Looks Like a Mistake*
- *Hardy, Weinberg, and One Page of Algebra — How a Mathematician and a Physician Independently Wrote the Null Hypothesis for Evolution*
- *Five Forces, One Equation — Why Every Real Population Disobeys Hardy-Weinberg in a Specific, Measurable Way*

---

**TL;DR.** Chapter 09 said evolution is what populations do — variation, differential reproduction, time. This chapter pins down the mathematics. The Hardy-Weinberg equilibrium is the null hypothesis of population genetics: if a population is large, mates at random, and is not subject to mutation, selection, or migration, then allele frequencies stay the same generation after generation and genotype frequencies follow p² + 2pq + q². No real population satisfies all five conditions, which is exactly the point — each violation is one of the five forces of evolution (mutation, natural selection, genetic drift, gene flow, non-random mating), and each force pushes allele frequencies in a specific, quantitatively predictable way. The worked example is sickle cell hemoglobin in malaria-endemic West Africa, where the HbS allele sits at a frequency near 0.10 not because it is good for anyone but because heterozygotes resist falciparum malaria while both homozygotes pay a fitness cost — a balanced polymorphism with an equilibrium frequency you can calculate with one division. By the end of the chapter, you should be able to compute carrier frequencies from disease frequencies, predict how fast an allele changes under selection, distinguish drift in a small population from selection in a large one, and explain why a population bottleneck reduces variation more than the same small population size held steady over generations.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **Compute** allele frequencies (p, q) from observed genotype counts in a population, and **predict** the expected genotype frequencies (p², 2pq, q²) under Hardy-Weinberg equilibrium.
2. **State** the five conditions required for Hardy-Weinberg equilibrium (large population, random mating, no mutation, no migration, no selection) and **identify** which condition is violated in a described biological scenario.
3. **Derive** the Hardy-Weinberg equation from random mating and Mendelian segregation in your own words, in fewer than 100 words.
4. **Use** the Hardy-Weinberg equation to estimate carrier frequency from disease frequency — for example, predicting that a recessive disease present in 1 in 3000 births implies a carrier frequency of about 1 in 28 (≈3.6%).
5. **Define** *fitness* (w), *selection coefficient* (s), *effective population size* (Ne), and *balanced polymorphism* in plain language, and **compute** each from a worked example.
6. **Predict** the equilibrium allele frequency under heterozygote advantage from the selection coefficients against the two homozygotes — q* = sAA / (sAA + sSS) — and **apply** it to the sickle cell case in West Africa.
7. **Distinguish** the four ways selection can act on a recessive allele (selection against rare recessive, selection against dominant, heterozygote advantage, heterozygote disadvantage) and **explain** why selection against a rare recessive is slow.
8. **Explain** why genetic drift is stronger in small populations than in large ones — in particular, that the magnitude of allele frequency change per generation under drift is inversely proportional to the effective population size Ne.
9. **Distinguish** the founder effect (small founding population carries only a subset of alleles) from a bottleneck (large population reduced to small) from sustained small population size, and **explain** why all three reduce genetic variation, but for different reasons that respond to different interventions.
10. **Identify** non-random mating (assortative, disassortative, inbreeding) by its signature — homozygote excess, heterozygote deficit, no necessary change in allele frequency — and **explain** why inbreeding exposes deleterious recessives that random mating hides.
11. **Build** a Hardy-Weinberg + five-forces population genetics simulator (`10-population-genetics.html`) that displays allele frequency over time under user-set selection coefficients, mutation rates, migration rates, and population size, and **use** it to recover (a) Hardy-Weinberg equilibrium when nothing is acting, (b) directional selection toward fixation, (c) balanced polymorphism around q ≈ 0.10 under heterozygote advantage, and (d) drift-dominated stochastic behavior in small populations.
12. **Name** at least three common student misconceptions about population genetics and **explain** what is wrong with each.

**Prerequisites.** Chapter 02 on Mendelian inheritance — you should remember that diploid organisms carry two alleles per gene, one from each parent, and that meiosis segregates them. Chapter 03 on extensions to Mendel, especially the language of dominance, recessivity, and codominance — we will use those terms without re-defining them. Chapter 08 on mutation as the source of new alleles — we will treat mutation rates here as numbers, not as molecular events. Chapter 09 on natural selection — the four ingredients (variation, excess offspring, differential reproduction, time) and the three modes of selection (directional, stabilizing, disruptive) are the *qualitative* version of what this chapter makes *quantitative*. You do not need calculus. You need to be able to multiply, divide, and recognize a quadratic.

---

## A mathematician answers a creationist

In 1908, the British mathematician Godfrey Harold Hardy received an annoying question at a dinner party. Hardy was a number theorist at Cambridge, friend of Ramanujan, professional aesthete on the subject of pure mathematics. He had no interest in biology and considered applied mathematics, where his work touched the real world, faintly embarrassing. The question, posed by his friend the geneticist Reginald Punnett, was nevertheless interesting enough that Hardy ended up writing it down.

The question came from a critique of Mendelism that was circulating in 1908, when Mendel's laws were still being absorbed by the broader biological community after their 1900 rediscovery (Chapter 02). The critic — a statistician named George Udny Yule — had pointed out that if dominant alleles were truly dominant, and dominance had any effect on inheritance, then over generations the dominant phenotype should rise to a 3:1 ratio in the population. Brown eyes are dominant over blue. If Mendel was right, shouldn't brown eyes inexorably take over the population? Why haven't they?

The argument was wrong, but it took a moment to see why. Punnett asked Hardy.

Hardy worked it out in an afternoon, sent a letter to the journal *Science*, and got back to number theory. The letter — three pages, no graphs, almost contemptuously brief — is one of the foundational documents of twentieth-century biology ([Hardy 1908, *Science* 28:49–50](https://www.science.org/doi/10.1126/science.28.706.49); the original letter; the proof is at the end of the second page and would fit on an index card).

Hardy's argument was this. Imagine a large population in which the frequency of allele A is *p* and the frequency of allele a is *q*, with p + q = 1. Assume mating is random — any two individuals are as likely to mate as any other two. Then the offspring genotypes are produced by drawing two alleles independently from the gene pool. The chance of drawing A and A in succession is p × p = p². The chance of drawing a and a is q × q = q². The chance of drawing one of each (in either order) is 2 × p × q. So in the next generation, the genotype frequencies are p², 2pq, q² — and these sum to 1 because (p + q)² = p² + 2pq + q² = 1² = 1.

Now do it for the generation after that. The new allele frequencies are: frequency of A = p² + (1/2)(2pq) = p² + pq = p(p + q) = p. Frequency of a = q² + pq = q. Nothing changed. Allele frequencies stayed at p and q. Genotype frequencies stayed at p², 2pq, q². The population is in equilibrium. It will sit there, generation after generation, as long as the conditions hold.

What Hardy had proven was that dominance, by itself, does not cause anything to change. A dominant allele will not "take over" a population just because it is dominant; *dominance is a fact about expression, not a fact about frequency*. If a dominant allele rises in frequency, it does so because something is driving it — selection, drift, migration, mutation, or non-random mating. In a population where none of those forces are operating, the brown-eyed and blue-eyed alleles will sit at whatever frequencies they happen to be at, forever.

Weinberg in Germany derived the same result the same year, working from medical-genetics data on twin studies and color blindness ([Weinberg 1908, *Jahreshefte des Vereins für vaterländische Naturkunde in Württemberg* 64:369–382](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1932915/); English translation in Stern 1962). The German biological community knew Weinberg's name; the English community knew Hardy's. For decades the principle was called "Hardy's law" in English-language textbooks and "Weinberg's law" in German ones. By the 1940s the joint attribution settled in. We call it the **Hardy-Weinberg equilibrium**.

I want to be careful about the dinner-party origin story because it makes the principle sound smaller than it is. The Hardy-Weinberg equilibrium is not a curiosity that resolved an 1908 dispute about dominance. It is the null hypothesis of population genetics. It is the reference point against which all departures get measured. Every claim about evolution at the population level — every claim of selection, drift, gene flow, mutation, or non-random mating — is, in its underlying logic, a claim about a deviation from Hardy-Weinberg. The principle is doing the same work that *F* = *ma* does in mechanics or that *PV* = *nRT* does in thermodynamics: it tells you what the system does in the absence of the thing you are trying to study, so you can recognize the thing you are trying to study when it shows up.

Hold the formula. Now we make the population real.

---

## Allele frequencies — what we are counting

A population, in the sense this chapter uses, is a group of interbreeding individuals of the same species — the medium ground finches on Daphne Major, the *E. coli* in one of Lenski's flasks, the Lancaster County Old Order Amish, the people who carry the ABO blood-group gene in Jordan. The members of a population share a **gene pool**: the totality of alleles at every locus, summed across every individual.

For a diploid species — humans, fruit flies, finches, oak trees — each individual carries two copies of every autosomal gene, one from each parent. A population of *N* diploid individuals therefore contains 2*N* copies of any given gene. We can ask, of any particular allele at that gene, *what fraction of those 2N copies are this allele?* That fraction is the **allele frequency**.

Consider a simple gene with two alleles, A and a. Pick a population of 500 medium ground finches. Each finch has two copies of the gene, so the gene pool contains 1,000 copies in total. Suppose we genotype every finch and find:

- 360 finches are AA (each contributing two A copies → 720 A copies)
- 120 finches are Aa (each contributing one A and one a → 120 A copies + 120 a copies)
- 20 finches are aa (each contributing two a copies → 40 a copies)

Total A copies: 720 + 120 = 840. Total a copies: 120 + 40 = 160. Total copies: 840 + 160 = 1,000. ✓

So **p**, the frequency of A, is 840 / 1,000 = 0.84. And **q**, the frequency of a, is 160 / 1,000 = 0.16. Note p + q = 1.00, which it must — every allele is either A or a, and the two frequencies must sum to one.

There is also a shortcut, useful when you have already computed genotype frequencies. Let *f*(AA) = 360/500 = 0.72, *f*(Aa) = 120/500 = 0.24, *f*(aa) = 20/500 = 0.04. Then:

p = *f*(AA) + (1/2) × *f*(Aa) = 0.72 + 0.12 = 0.84

q = *f*(aa) + (1/2) × *f*(Aa) = 0.04 + 0.12 = 0.16

Same answer. The logic is that each AA individual contributes 100% A to the gene pool, each Aa contributes 50%, each aa contributes 0% — and you weight by how common each genotype is.

A point worth being precise about: there is a difference between **allele frequency** and **genotype frequency**, and population genetics tracks the first more carefully than the second. The reason is what Chapter 09 already hinted at: genotypes last one generation. An AA finch produces gametes that each contain a single A. Its diploid identity is undone every meiosis. What gets transmitted to the next generation are the *alleles*, not the genotype-combinations. The genotype frequencies in the next generation will be whatever the random sampling of alleles into new diploid combinations produces. So if you want to know what a population is going to look like next generation, you need to track allele frequencies, not genotype frequencies.

This is, incidentally, why Hardy's argument was the move it was. Yule had been confused because he was tracking genotype frequencies (brown-eyed vs blue-eyed phenotypes) and not seeing that what counts is the allele frequencies underneath them. The 3:1 ratio Yule expected would emerge if you started with 100% Aa heterozygotes and let them self-cross. It does not emerge in a population that has been at equilibrium for many generations, because such a population has already settled into p² : 2pq : q² and stays there.

---

## Deriving Hardy-Weinberg — Mendel meets random mating

The derivation is so short that I want to do it explicitly, because once you have done it once, the formula becomes something you understand rather than something you memorize.

Start with a population at generation *t*, with allele frequencies *p* (for A) and *q* (for a). Assume:

1. The population is large enough that allele frequencies in any sample of gametes are essentially equal to the population frequencies (no sampling error — the "large population" assumption).
2. Mating is random — any two individuals are equally likely to mate. This means the genotypes of mating pairs are determined purely by the gene pool's allele frequencies, not by who-prefers-whom.
3. There is no mutation, so an A allele stays A and an a allele stays a.
4. There is no migration in or out, so no new alleles arrive.
5. All genotypes survive and reproduce equally well — no selection.

Now build the next generation. Each individual gets one allele from each parent. The probability that a given individual gets A from its mother is *p* — because *p* is what fraction of the maternal gene pool is A. The probability it gets A from its father is also *p*, for the same reason. Because we have assumed random mating, the maternal and paternal contributions are independent — knowing what mom contributed tells you nothing about what dad contributed. So:

- Probability of being AA = P(A from mom) × P(A from dad) = p × p = **p²**
- Probability of being aa = q × q = **q²**
- Probability of being Aa = P(A from mom) × P(a from dad) + P(a from mom) × P(A from dad) = pq + qp = **2pq**

That is the Hardy-Weinberg equation:

> **p² + 2pq + q² = 1**

The "= 1" is because every offspring must have one of the three genotypes, and the probabilities must sum to one. You can check: (p + q)² = p² + 2pq + q², which equals 1² = 1 since p + q = 1.

The second half of Hardy's proof, which I asserted without showing, is that allele frequencies do not change generation to generation under these conditions. Show this. The frequency of A in the next generation is the fraction of gametes carrying A. Each AA individual produces gametes that are 100% A; each Aa produces 50% A; each aa produces 0% A. So:

p(next gen) = p² × 1 + 2pq × (1/2) + q² × 0 = p² + pq = p(p + q) = p × 1 = **p**

The new p equals the old p. By an identical argument the new q equals the old q. The population is in equilibrium — it sits at (p, q) with genotype frequencies (p², 2pq, q²), and absent any force acting, it stays there.

Three sentences, and we are done with the derivation. Memorize the conclusion — *p² + 2pq + q²* — but understand that the formula is the consequence of Mendelian segregation plus random mating, nothing more. If those two things hold and nothing else acts, the conclusion follows automatically.

---

## Using Hardy-Weinberg in practice — carriers from cases

The equation becomes useful when you do not have direct access to the gene pool but you do have access to phenotype data, and you want to back out the underlying allele frequencies.

A common application is in medical genetics. Many genetic diseases are recessive — they manifest only in *aa* homozygotes. If you know the incidence of the disease in a population, you know *q²* directly (the fraction of the population that is *aa*). You can then compute *q*, *p*, and the **carrier frequency** *2pq* — the fraction of the population that is heterozygous, asymptomatic, but capable of passing the disease allele on.

Take phenylketonuria (PKU), a recessive metabolic disease in which homozygotes lack functional phenylalanine hydroxylase. Untreated, PKU causes severe intellectual disability; with newborn screening and dietary management, affected individuals can live essentially normal lives ([Blau et al. 2010, *Lancet* 376:1417–1427](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(10)60961-0/fulltext); review of PKU). The disease incidence in many European-ancestry populations is approximately 1 in 10,000 [verify — varies by population, with Ireland higher and Finland lower].

For arithmetic clarity I will use a slightly different number: 1 in 3,000, which is closer to the incidence reported in some populations and produces tidier arithmetic. Suppose then that PKU occurs in 1 of every 3,000 births:

q² = 1 / 3,000 = 0.000333

q = √0.000333 ≈ **0.0183**

p = 1 − q ≈ **0.982**

Carrier frequency (2pq) = 2 × 0.982 × 0.0183 ≈ **0.036**

So in a population where PKU affects 1 in 3,000 births, about 3.6% of the population are silent carriers — heterozygotes who carry one copy of the PKU allele and one functional copy, who are phenotypically unaffected, who are nevertheless at risk of having an affected child if their partner is also a carrier. About 1 in 28 people in this hypothetical population is a carrier.

Stop on the magnitudes for a moment. The disease frequency is 1 in 3,000. The carrier frequency is about 1 in 28. *Carriers outnumber affected individuals by about 110 to 1.* This is a general feature of rare recessive alleles, and it has clinical and ethical implications. Most of the PKU allele's "presence" in the population sits silent in heterozygotes; only a tiny fraction surfaces as disease. The same pattern holds for cystic fibrosis (about 1 in 25 European-ancestry individuals is a CF carrier, about 1 in 2,500 is affected), Tay-Sachs disease in Ashkenazi Jewish populations (about 1 in 27 are carriers, about 1 in 3,500 are affected — substantially elevated from the general population because of historical founder effects we will discuss below), and sickle cell disease in African-American populations (about 1 in 13 are carriers, about 1 in 365 children of two African-American parents are affected) ([CDC 2024, Sickle Cell Data and Statistics](https://www.cdc.gov/sickle-cell/data/index.html); [verify exact rates, which fluctuate slightly with the underlying genetic survey]).

The clinical move that follows is **carrier screening**. If you know the carrier frequency, you can compute the *risk* a random couple from the population face of having an affected child: each parent has a *2pq* chance of being a carrier; if both are carriers, the child has a 1/4 chance of being *aa*. So the unconditional probability of an affected child for an arbitrary couple is *2pq × 2pq × 1/4 = (pq)². Compare that to *q²* — what you get if you do not know the parents' genotypes. The math works out so the unconditional disease probability is *q²* either way (it is the same population baseline). But once you have screened the parents and learned they are both carriers, the conditional risk of an affected child jumps to 1/4, which is the part that is decision-relevant. Genetic counseling lives in that conditional probability ([Edwards et al. 2015, *J Genet Couns* 24:545–552](https://onlinelibrary.wiley.com/doi/10.1002/jgc4.5); on carrier screening).

A final point. The estimate above assumed Hardy-Weinberg held — that the population was large, random-mating, and not subject to recent selection on the locus. For PKU and many other recessive diseases, this is approximately true; the disease is rare enough that selection against the recessive (which exists, mildly, even with treatment) is slow, and gene flow with neighboring populations homogenizes most loci on relevant timescales. For some diseases — sickle cell in particular — the Hardy-Weinberg assumption is *spectacularly* wrong, because heterozygotes have higher fitness than either homozygote in the relevant environment, and the equilibrium allele frequency is being held up by balanced selection. The carrier frequency for HbS in West Africa is not what Hardy-Weinberg-from-disease-incidence predicts; it is what *balanced selection at equilibrium* predicts. Coming up.

---

## The five forces — what makes allele frequencies move

If a population is *not* in Hardy-Weinberg equilibrium, then one (or more) of the five assumptions is being violated, and the violation is what is driving the change. There are exactly five forces of evolution at the population-genetic level, each corresponding to a violated Hardy-Weinberg assumption:

1. **Mutation** — violates "no mutation." New alleles enter the gene pool.
2. **Natural selection** — violates "all genotypes equally fit." Some alleles propagate more reliably than others.
3. **Genetic drift** — violates "infinite population size." In finite populations, allele frequencies wander randomly because of sampling error in who reproduces.
4. **Gene flow** — violates "closed population." Migrants bring alleles in (or take them out).
5. **Non-random mating** — violates "random mating." Who mates with whom is not independent of genotype.

The next five sections take these in turn. For each, I will describe what the force does to allele frequencies, give an equation (or at least a relationship) that predicts the magnitude of the effect, and ground the picture in a worked example. The fifth force (non-random mating) is in some ways the odd one out — it can change *genotype* frequencies without changing *allele* frequencies — and I want you to see why.

After we have all five, we will spend the longest section of the chapter (the next worked example) on a case where natural selection produces a counterintuitive *equilibrium*, not fixation: the sickle cell allele in West Africa. That case is the chapter's deep-dive.

---

## Force 1: Mutation — the ultimate source

Mutation is the only force that creates new alleles. Selection can only act on variation that already exists; drift moves alleles around but does not invent them; migration imports alleles from somewhere else; non-random mating reshuffles. Mutation is where the variation comes from in the first place.

Chapter 08 gave the mechanism — DNA replication errors, polymerase mis-incorporation, repair failure, mutagen exposure. The rates were the punch line: roughly 10⁻⁹ to 10⁻⁸ point mutations per base pair per cell division in human somatic cells, with germ-line rates slightly lower because germ-line cells have stronger repair surveillance ([Lynch 2010, *Trends Genet* 26:345–352](https://www.cell.com/trends/genetics/fulltext/S0168-9525(10)00115-X); rates across species). For a typical protein-coding gene of about 1,000 base pairs, the mutation rate per gene per generation is on the order of 10⁻⁵.

Here is the key point for population genetics: **the per-generation mutation rate is too low for mutation alone to change allele frequencies appreciably**. If a new mutation arises in a single individual, its initial frequency in the population is 1/(2N) — one copy out of the 2N alleles in the gene pool. In a population of a million individuals that is one part in two million. Even if mutation kept generating new copies of the same allele at every locus, the rate of frequency change would be roughly the mutation rate itself — about 10⁻⁸ per generation. That is utterly trivial compared to selection coefficients of 0.01 to 0.5 or drift in populations of size N = 100, both of which can produce frequency changes of percent-per-generation or larger.

What mutation does is *introduce the variation that the other forces then act on*. The peppered moth's *carbonaria* dark allele was created by a single mutation in a single moth in industrial England (we now know the mutation is a transposable element insertion into the cortex gene — [Van't Hof et al. 2016, *Nature* 534:102–105](https://www.nature.com/articles/nature17951)). Once the allele existed, selection drove it from rare to common because of the soot-darkened bark. Without the mutation, no soot-darkened-bark adaptation could occur, because there was no variant for selection to keep. Without the selection, the mutation would have stayed at 1/(2N) ≈ vanishingly rare and gone extinct from drift alone. *Mutation supplied; selection sorted.*

There is a special case where mutation does drive frequency change directly: **mutation-selection balance** for a deleterious allele. If selection is removing copies of an allele at rate *s* (the selection coefficient, defined below), and mutation is introducing them at rate *μ*, then at equilibrium the allele frequency settles at a level where input equals output. For a recessive deleterious allele:

q* ≈ √(μ/s)

This is small. For μ = 10⁻⁵ and s = 0.5 (a substantially harmful recessive), q* ≈ √(2 × 10⁻⁵) ≈ 0.0045. The disease incidence is then q*² ≈ 2 × 10⁻⁵ ≈ 1 in 50,000. That is roughly the incidence of many rare recessive diseases, and mutation-selection balance is part of the explanation for why they are rare but not extinct: every generation a small number of new mutations replace the alleles that selection has just eliminated. The disease persists at low frequency forever, fed by recurrent mutation.

The two practical things to remember about mutation are: (1) it sets the *menu* of variation that the other forces work with; (2) over very long timescales (millions of generations), the cumulative effect of mutation on the molecular composition of the genome is enormous — most of the *neutral* differences between species at the DNA level are mutational accumulation, which is the engine of the **neutral theory of molecular evolution** we will get to in §"The neutral theory preview" below.

---

## Force 2: Natural selection — fitness and the selection coefficient

Chapter 09 introduced natural selection qualitatively. Now we make it quantitative. The two quantities you need are *fitness* and *selection coefficient*.

**Fitness** (written *w*) is *expected relative reproductive success* — the expected number of offspring an individual leaves, divided by the population average. By convention, the fittest genotype in the population is assigned *w* = 1 (or sometimes the population mean is assigned 1; usage varies). Less-fit genotypes get *w* < 1. The number is dimensionless. A genotype with *w* = 0.9 leaves, on average, 90% as many offspring as the reference. *w* = 0 means the genotype leaves no offspring — sterile, or always dies before reproducing.

The **selection coefficient** (written *s*) is just 1 − *w*. It is the *reduction* in relative fitness, measured from the fittest genotype. The fittest has *s* = 0 (no reduction); a genotype with *w* = 0.9 has *s* = 0.1; a lethal genotype has *s* = 1. The selection coefficient is easier to think with in many calculations because it captures "how much is selection working against this genotype" as a single number.

For a single biallelic locus with alleles A and a, we have three possible genotypes (AA, Aa, aa) and three fitnesses (wAA, wAa, waa), and three selection coefficients (sAA, sAa, saa) — one for each. The pattern of selection coefficients determines which way allele frequencies move.

**Directional selection against a recessive.** Suppose *a* is recessive deleterious — *aa* homozygotes have reduced fitness, but Aa and AA are equally fit. So wAA = wAa = 1, waa = 1 − s. After one generation of selection acting on a population at Hardy-Weinberg frequencies, you can compute the new allele frequency exactly:

q' = q(1 − sq) / (1 − sq²)

The full derivation is a brief exercise in conditional probability that I will not run here; the result is in any population-genetics textbook ([Hartl & Clark 2007, *Principles of Population Genetics*, 4th ed., Sinauer](https://global.oup.com/academic/product/principles-of-population-genetics-9780878933082); the standard reference). The qualitative behavior is more important than the algebra: **selection against a rare recessive is slow**. When q is small, most copies of the *a* allele sit hidden in *Aa* heterozygotes (fraction 2pq ≈ 2q), where they are not exposed to selection. Only a small fraction (q²) sits in *aa* homozygotes, where selection acts on it. Halving q from 0.01 to 0.005 takes hundreds of generations even with a strong selection coefficient. This is exactly why eugenic programs aimed at "eliminating" recessive disease alleles from a population by sterilizing affected homozygotes are mathematically futile — even if they were ethically defensible, which they are not, the math doesn't cooperate. Most of the allele is in carriers and selection cannot see it ([Crow 1986, *Basic Concepts in Population, Quantitative, and Evolutionary Genetics*, Freeman](https://www.amazon.com/Basic-Concepts-Population-Quantitative-Evolutionary/dp/0716718049); the historical and quantitative analysis).

**Directional selection against a dominant.** If *A* is dominant deleterious — both AA and Aa are equally less fit, while aa is fittest — selection is much faster, because every copy of A is exposed (in homozygotes and heterozygotes both). Achondroplasia, the most common form of disproportionate dwarfism, is caused by a dominant allele in the FGFR3 gene; it persists in the population at low frequency despite reduced fitness because of recurrent mutation (the allele is one of the most mutable loci in the human genome) ([Wilkin et al. 1998, *Am J Hum Genet* 63:711–716](https://www.cell.com/ajhg/fulltext/S0002-9297(07)61462-1); on the FGFR3 mutational hotspot). Without recurrent mutation, dominant deleterious alleles disappear from a population within tens of generations.

**Heterozygote advantage (overdominance).** When the heterozygote (Aa) has higher fitness than either homozygote, selection produces a stable polymorphism — *both* alleles are maintained at intermediate frequencies forever. The math is below in the sickle cell deep-dive. This is the most subtle and most interesting selection regime, because the *outcome* of selection is not fixation but a *balance*.

**Heterozygote disadvantage (underdominance).** When the heterozygote has lower fitness than either homozygote, you get the opposite — an unstable equilibrium where, depending on starting frequency, one allele or the other goes to fixation. This is rarer in nature but important for some chromosomal polymorphisms.

The general rule: the *pattern* of fitnesses across genotypes determines the *kind* of outcome. Fixation, loss, or stable polymorphism, with the allele-frequency trajectories described by a system of equations like the q' equation above. We will work through the heterozygote-advantage case explicitly in a moment.

---

## Force 3: Genetic drift — sampling error as evolutionary force

Drift is the strangest of the five forces, because it has nothing to do with fitness, adaptation, or any kind of biological-functional pressure. It is statistical sampling error in who reproduces, applied generation after generation. In a finite population, even with no selection at all, allele frequencies wander.

Here is the picture. Consider a population of *N* diploid individuals, with allele *A* at frequency *p*. To form the next generation, the population produces gametes — the gene pool now has frequencies *p* and *q* — and 2*N* of those gametes are sampled to form the *N* offspring of the next generation. *That sampling step is random.* The probability that exactly *k* of the 2*N* offspring's alleles are *A* is given by the binomial distribution. The expected number is 2*N* × *p*, but the actual number will vary around the expectation.

The variance in the new allele frequency is:

Var(p') = p(1 − p) / (2N) = pq / (2N)

The standard deviation is √(pq / 2N). This says that the magnitude of drift per generation scales as **1/√N**. In a population of 10,000, the standard deviation of allele frequency change per generation is about 0.5%. In a population of 100, it is about 5%. In a population of 10, it is over 15%.

Drift has three consequences that matter for population genetics:

**(1) Fixation or loss is the long-term endpoint.** In the absence of mutation, gene flow, or balancing selection, drift eventually pushes every allele to either *fixation* (frequency 1) or *loss* (frequency 0). Once a locus is fixed for one allele, drift cannot move it — there is no variation left. The probability that a particular allele ultimately reaches fixation, given that it starts at frequency *p*, is exactly *p* (for a neutral allele). A new mutation, which starts at 1/(2N), has a 1/(2N) chance of going to fixation. Most mutations are lost almost immediately.

**(2) Drift is inversely proportional to population size.** This is the crucial design fact. In a small population, drift dominates; in a large population, drift is negligible. The boundary between "drift wins" and "selection wins" depends on the size of *Ns*: if *Ns* >> 1 (large population, strong selection), selection drives the outcome. If *Ns* << 1 (small population or weak selection), drift drives the outcome.

**(3) Drift erodes genetic variation.** Each generation of drift loses some alleles to chance. The expected heterozygosity (the probability that two randomly drawn alleles at a locus are different) decays at a rate of 1/(2N) per generation under pure drift. Small populations lose variation fast.

**Effective population size (Ne).** In real populations, the *N* in these equations is not the headcount of individuals but the **effective population size** — written *Ne* — which is the size of an idealized Wright-Fisher population (equal sex ratio, every individual contributes gametes with equal variance to one offspring generation) that would experience the same drift as the real population. For most species, *Ne* is *smaller* than the census size *N*, sometimes much smaller, because of:

- *Unequal sex ratio*: if a population has 100 breeding females and 10 breeding males, *Ne* ≈ 4 × (females × males) / (females + males) ≈ 36, much less than 110. (Polygynous species with a few dominant males monopolizing mating effectively have a much smaller gene pool than their census size suggests.)
- *Variance in reproductive success*: when some individuals leave many more offspring than the average and others leave none, the effective population size is reduced.
- *Generation overlap*: if generations are not discrete, the calculation gets more complex; usually *Ne* is reduced.
- *Past bottlenecks*: the long-term *Ne* is sensitive to the smallest *Ne* the population has passed through; *Ne* is harmonic-mean-like across generations, so a single small generation reduces it disproportionately.

For humans, the effective population size over the last 10,000 generations is estimated at about *Ne* ≈ 10,000, despite a current census size in the billions ([Tenesa et al. 2007, *Genome Res* 17:520–526](https://genome.cshlp.org/content/17/4/520); estimate from linkage disequilibrium). That estimate reflects the bottleneck that anatomically modern humans passed through during the Out-of-Africa migration ~60,000 years ago, plus the slow recovery of variation since. When you do drift math for humans, you use *Ne* = 10,000, not 8 billion. The 8 billion are mostly the descendants of a population that was, in the recent evolutionary past, very small.

**Bottleneck effect.** A bottleneck is a temporary severe reduction in population size — a disease epidemic, a habitat collapse, a chance disaster — that drops *N* (and *Ne*) to a small fraction of its former value for one or a few generations. During the bottleneck, drift is intense; many alleles are lost. When the population recovers, the alleles that were present in the survivors are the only alleles present in the new expanded population. The recovery does not restore variation. The alleles lost during the bottleneck stay lost (unless reintroduced by gene flow or new mutation).

The classic example is the cheetah, which is estimated to have passed through a severe bottleneck about 10,000 years ago, possibly during the late Pleistocene megafaunal extinctions ([O'Brien et al. 1985, *Science* 227:1428–1434](https://www.science.org/doi/10.1126/science.2983425); the foundational paper; [Dobrynin et al. 2015, *Genome Biol* 16:277](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-015-0837-4); modern whole-genome analysis). Modern cheetahs show astonishingly low genetic variation — about 95% lower than typical mammalian species — and one of the strangest signatures: skin grafts between unrelated individuals are not rejected, because the major histocompatibility complex (MHC) is essentially monomorphic. The cheetahs' MHC is so uniform that the immune system cannot distinguish "self" tissue from another cheetah's tissue. The bottleneck destroyed the diversity, and 10,000 years of population recovery has not restored it.

**Founder effect.** A founder effect is a bottleneck-in-miniature, occurring when a small group of individuals colonizes a new habitat and becomes the founders of a new population. Whatever alleles they happen to carry — including rare alleles that may have been at low frequency in the source population — become the *only* alleles in the new population. Rare diseases that drift up in frequency to common levels in the founder population are a classic signature.

The Old Order Amish of Lancaster County, Pennsylvania, are the textbook example. The population descends from about 200 founders who emigrated from Switzerland and Germany in the early 1700s, and has remained largely endogamous (marrying within the community) since. Several rare genetic diseases are dramatically elevated in this population, most famously **Ellis-van Creveld syndrome** — a recessive condition causing short-limbed dwarfism, polydactyly, and congenital heart defects. The disease is caused by mutations in the EVC gene, and its incidence in the Lancaster Amish is about 1 in 200 births, compared to about 1 in 60,000 in the general population ([McKusick et al. 1964, *Bull Johns Hopkins Hosp* 115:306–336](https://pubmed.ncbi.nlm.nih.gov/14211613/); the original genetic-isolate analysis; [Ruiz-Perez et al. 2000, *Nat Genet* 24:283–286](https://www.nature.com/articles/ng0300_283); the gene identification). The carrier frequency in the Lancaster Amish is roughly 7%, compared to about 0.5% in the source European population. The disease allele was almost certainly carried by one or a small number of the original 200 founders, and drift, plus endogamy, raised its frequency by more than an order of magnitude in three centuries.

The founder effect is, in this sense, drift compressed into the founding event. It does not require many generations. The pattern of which rare alleles end up over-represented is essentially random — whatever the founders happened to carry. Different Amish settlements in different parts of North America have different elevated diseases. The Pennsylvania settlement has elevated Ellis-van Creveld; the Ohio settlement has elevated maple syrup urine disease ([Strauss et al. 2006, *Mol Genet Metab* 89:228–236](https://www.sciencedirect.com/science/article/pii/S1096719206001119); on MSUD in the Mennonite/Amish populations). Each settlement's medical profile reflects its founders' particular hand of cards.

**Bottleneck vs. sustained small population — the often-missed distinction.** A common student confusion is to treat "bottleneck" and "small population over many generations" as the same thing. They are not. The bottleneck *loses* alleles in a discrete event — many rare alleles disappear simultaneously when the population crashes, and they are not recovered by subsequent population growth. A sustained small population at, say, *Ne* = 1,000 over many generations has higher drift than a large population would, but it also has mutation flowing in at every generation, so it reaches a *mutation-drift equilibrium* where input balances loss. Variation is reduced but not eradicated. The bottleneck collapses variation faster than the equilibrium would predict, and the post-bottleneck recovery is determined by how fast new variation can be regenerated by mutation — which is slow.

This matters for conservation biology. A population reduced to 50 individuals and held at 50 for 1,000 generations would have *some* genetic variation (at mutation-drift equilibrium for *Ne* = 50, the equilibrium heterozygosity is about 4*Ne*μ ≈ 4 × 50 × 10⁻⁸ ≈ 2 × 10⁻⁶ per base, much lower than the human average around 10⁻³ but not zero). A population that was a million for many generations, crashed to 50 for one generation, then recovered, would lose most of its diversity in a single event and recover it only over hundreds of thousands of generations of mutation. The bottleneck is the worse case. Wildlife managers worry about *both*, and exercise 3 below asks you to walk this distinction.

---

## Force 4: Gene flow — migration as homogenizer

**Gene flow** (often called migration in population-genetic literature) is the movement of alleles between populations. The rate is parameterized as *m*, the fraction of a population's individuals (or gametes) in each generation that arrived from elsewhere. If *m* = 0.1, then 10% of the population (or the breeding population) each generation is recent migrants.

The effect of gene flow on allele frequencies is easy to write down. Suppose two populations have allele frequencies *p₁* and *p₂*, and migrants move at rate *m* from population 2 to population 1. Then the new frequency in population 1 is:

p₁' = (1 − m) × p₁ + m × p₂

This is a weighted average — population 1 retains its old allele frequency in proportion to (1 − m), and gains the migrants' frequency in proportion to *m*. After many generations of migration (without selection or drift), the two populations' frequencies converge.

Gene flow's main effect is **homogenization**. Populations that exchange migrants stay genetically similar to each other. Even small migration rates — *m* = 0.01, one migrant in a hundred per generation — are usually enough to prevent two populations from diverging substantially by drift or selection, *if* the selection differential between them is small. The general result, derived by Sewall Wright in the 1930s, is that if migration rate *m* is much greater than selection coefficient *s*, the populations stay homogeneous; if *s* >> *m*, they diverge.

Gene flow can also rescue a small isolated population from inbreeding depression and drift-driven loss of variation. The **Florida panther** (*Puma concolor coryi*) is the textbook case. By the 1990s, the Florida panther population was reduced to about 20–30 individuals and showed multiple genetic-disease signatures (kinked tails, cardiac defects, low sperm motility), all consistent with inbreeding depression. In 1995, biologists introduced eight female Texas pumas (*P. c. stanleyana*) to restore gene flow with the closest related subspecies. The introgression worked; the Florida panther population has since grown to over 200, the inbreeding signatures have largely disappeared, and the genetic rescue is one of the rare unambiguous conservation success stories ([Johnson et al. 2010, *Science* 329:1641–1645](https://www.science.org/doi/10.1126/science.1192891); on the genetic rescue).

Gene flow can also work *against* local adaptation. If a population is under selection toward a locally favored allele, but migrants from a neighboring population (with different selection regime) keep arriving with the alternative allele, the local population may never reach fixation. This is the **migration load**, and it sets a floor on how locally adapted a population can become in the face of continuous immigration.

For human populations, gene flow has been a dominant force in shaping the modern allele-frequency landscape. The major continental population groups are connected by gradient gene flow, with relatively few hard genetic barriers; **FST**, the standard measure of genetic differentiation between populations, is about 0.10–0.15 for the major continental groups, meaning that 10–15% of human genetic variation is *between* groups and 85–90% is *within* groups ([Rosenberg et al. 2002, *Science* 298:2381–2385](https://www.science.org/doi/10.1126/science.1078311); the foundational microsatellite analysis; [Li et al. 2008, *Science* 319:1100–1104](https://www.science.org/doi/10.1126/science.1153717); with SNP data). This low *FST* means human populations are not biologically discrete races — gene flow has kept us much more homogeneous than the visible phenotypic differences (skin color, hair texture, facial morphology) might suggest. Chapter 14 will return to *FST* in the context of the race-as-biology question.

---

## Force 5: Non-random mating — homozygote excess without allele-frequency change

Non-random mating is the strange one. It changes *genotype* frequencies without (necessarily) changing *allele* frequencies. The Hardy-Weinberg equation assumes individuals mate at random with respect to genotype; if they don't, the genotype frequencies depart from p², 2pq, q², but the allele frequencies themselves can be unchanged from one generation to the next.

There are several types of non-random mating:

**Assortative mating** — individuals preferentially mate with phenotypically (and therefore often genotypically) similar individuals. Tall people marry tall people; people with similar educational attainment marry each other; in many bird species, males and females mate preferentially with partners of similar plumage. Assortative mating increases the frequency of homozygotes for the trait-related loci and decreases the frequency of heterozygotes.

**Disassortative mating** — the opposite, where unlike individuals preferentially mate. This is rarer but important — for instance, in the MHC, where humans (and many other species) preferentially choose mates with dissimilar MHC profiles, possibly via odor cues ([Wedekind et al. 1995, *Proc R Soc B* 260:245–249](https://royalsocietypublishing.org/doi/10.1098/rspb.1995.0087); the famous "smelly T-shirt" study; controversial methods but the qualitative effect is documented in many vertebrates). Disassortative mating maintains heterozygosity.

**Inbreeding** — mating with close relatives — is the most consequential for human medical genetics. Self-fertilization in plants and consanguineous marriage in humans (first-cousin marriage, common in some cultural traditions) elevate the homozygosity at *every* locus, not just trait-related ones. The reason: relatives share many alleles by descent from common ancestors. Two first cousins share 1/8 of their genomes IBD (identical by descent) on average. When they mate, their offspring inherit alleles that are correlated — the two copies at any locus are more likely to be identical than they would be in an outbred mating.

The **inbreeding coefficient** *F* is the probability that the two alleles at a locus in an individual are identical by descent. For a random outbred individual, *F* = 0. For an offspring of first cousins, *F* = 1/16. For an offspring of full siblings, *F* = 1/4. For an offspring of self-fertilization (in selfing plants), *F* = 1/2 (after one generation; rising to 1 after many generations).

When *F* > 0, the genotype frequencies deviate from Hardy-Weinberg:

- *f*(AA) = p² + Fpq
- *f*(Aa) = 2pq(1 − F)
- *f*(aa) = q² + Fpq

The heterozygote frequency drops by *Fpq*, and that loss is split between the two homozygote classes. Allele frequencies are unchanged: p stays p, q stays q. What changes is who-is-paired-with-whom in the diploid combinations.

The consequence is **inbreeding depression**. Most deleterious recessive alleles, in an outbred population, hide harmlessly in heterozygotes. Inbreeding increases the homozygote frequency, which exposes the alleles to selection. Inbred offspring have a higher load of homozygous deleterious alleles and consequently reduced fitness. The effect is well-documented in humans: offspring of first-cousin marriages have about 1.7–2.8% additional risk of severe genetic disease compared to offspring of unrelated parents (baseline risk about 2%, so total risk roughly doubles) ([Bittles & Black 2010, *PNAS* 107 Suppl 1:1779–1786](https://www.pnas.org/doi/10.1073/pnas.0906079106); the meta-analysis of consanguinity studies). In zoological populations, where forced inbreeding has been studied at scale (e.g., experimental *Drosophila* populations), inbreeding depression on fitness can be 30–80% within a few generations ([Charlesworth & Charlesworth 1999, *Genet Res* 74:329–340](https://www.cambridge.org/core/journals/genetics-research/article/abs/genetic-basis-of-inbreeding-depression/F95C7D3F30B6E89A47E1B59B6F77B4F6); review of the genetic basis).

Inbreeding is also the major reason zoo conservation programs maintain studbooks and stringently avoid mating closely related individuals. The Species Survival Plans operated by AZA-accredited zoos for endangered species track every individual's ancestry and recommend specific pairings to minimize the *F* of the next generation ([Lacy 1989, *Zoo Biol* 8:111–123](https://onlinelibrary.wiley.com/doi/10.1002/zoo.1430080203); on genetic management of captive populations). In humans, genetic counselors raise the consanguinity question precisely because the elevated risk is quantifiable and the conversation is worth having.

A side note worth pinning down. **Sexual selection** — the choice of mates based on phenotypic traits — is technically a form of non-random mating, but it is usually treated as a flavor of natural selection because it changes allele frequencies (alleles for the preferred trait propagate faster). Chapter 09 covered the peacock-tail logic. The distinction between "assortative mating" and "sexual selection" is partly a matter of where in the analysis you put the change: if you are tracking genotype frequencies (everyone reproduces, but pairings are non-random), it is non-random mating. If you are tracking allele frequencies (alleles for the preferred trait win, alleles for the dispreferred trait lose), it is selection. Both descriptions can apply to the same biology.

---

## Worked example: the sickle cell allele in West Africa — balanced polymorphism end to end

Now we do the chapter's mechanism deep-dive. The aim is to take a single allele — the HbS variant of the β-globin gene — and trace, end to end, why it sits at a frequency near 0.10 in malaria-endemic West Africa rather than going to fixation, going to loss, or wandering randomly. The answer is a specific mathematical model — heterozygote advantage producing a *balanced polymorphism* — and the model's prediction matches the observed frequency to one decimal place.

This is the chapter's deep-dive. It is the example you should be able to do yourself by the end.

### The allele and the disease

The HbS allele is a single point mutation in the β-globin gene (*HBB* on chromosome 11), changing the codon for glutamate at position 6 to a codon for valine — the A→T transversion at the second base of codon 6, GAG → GTG, that we worked end-to-end in Chapter 05. The protein consequence is the substitution Glu6Val. The functional consequence: the substituted valine creates a sticky hydrophobic patch on the surface of deoxygenated hemoglobin, and under low oxygen the HbS molecules polymerize into long fibers that distort the red blood cell into the characteristic sickle shape. Sickled cells are rigid, fragile, and prone to occlude small blood vessels.

The three genotypes have very different clinical phenotypes:

- **HbAA (normal)**: two copies of the wild-type β-globin allele. Normal hemoglobin. Susceptible to falciparum malaria (the most lethal of the four human-pathogenic *Plasmodium* species), with about 10% childhood mortality from severe malaria in unsupplemented endemic areas [verify — historical estimate; modern public health interventions have reduced this substantially in many regions] ([Snow et al. 2017, *Lancet* 390:2284–2295](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(17)31303-3/fulltext); on historical malaria mortality).

- **HbAS (sickle trait, heterozygous)**: one wild-type, one HbS allele. About 40% of the hemoglobin is HbS, the rest is normal. Cells contain enough normal hemoglobin to function under physiologic oxygen conditions; sickling occurs only under extreme stress (high altitude, extreme dehydration). Critically, *the partial sickling provides resistance to falciparum malaria*: the parasite cannot complete its intra-erythrocytic life cycle as efficiently in HbAS red cells. HbAS carriers have substantially reduced severe-malaria mortality compared to HbAA — by perhaps 90% in some estimates ([Allison 1954, *BMJ* 1:290–294](https://www.bmj.com/content/1/4857/290); the foundational paper showing the correlation between sickle trait and malaria resistance; [Williams et al. 2005, *J Infect Dis* 192:178–186](https://academic.oup.com/jid/article/192/1/178/824748); modern estimate).

- **HbSS (sickle cell disease, homozygous)**: two HbS alleles. Severe chronic anemia, painful vaso-occlusive crises (Chapter 05), splenic infarcts, stroke, organ damage. Untreated childhood mortality is very high — historical estimates from sub-Saharan Africa suggest up to 80% mortality before reproductive age, though modern medical care (hydroxyurea, transfusion, and now gene therapy with Casgevy as of December 2023, see Chapter 07) has dramatically improved survival ([Piel et al. 2017, *Lancet* 390:311–323](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(17)30193-9/fulltext); review of global SCD mortality; [verify exact historical pre-treatment mortality, which varies by region and study].

So the three genotypes face very different fitness environments in a malaria-endemic region:

- HbAA: high mortality from malaria (~10% childhood mortality from severe malaria) → wAA ≈ 0.9, sAA ≈ 0.1
- HbAS: low mortality from either malaria or sickling → wAS ≈ 1.0, sAS ≈ 0 (the reference fitness)
- HbSS: high mortality from sickle cell disease (~80% childhood mortality without treatment) → wSS ≈ 0.2, sSS ≈ 0.8

The heterozygote has higher fitness than either homozygote. This is the textbook condition for heterozygote advantage.

### The equilibrium frequency — derived

Let *q* be the frequency of the HbS allele and *p* = 1 − *q* the frequency of HbA. Under Hardy-Weinberg, the genotype frequencies pre-selection are p², 2pq, q² for HbAA, HbAS, HbSS respectively.

After selection acts in one generation, the contribution of each genotype to the next generation's gene pool is its frequency × its fitness. So:

- Post-selection HbAA: p² × wAA = p² × (1 − sAA)
- Post-selection HbAS: 2pq × wAS = 2pq × 1 = 2pq
- Post-selection HbSS: q² × wSS = q² × (1 − sSS)

The mean fitness of the population is:

w̄ = p²(1 − sAA) + 2pq + q²(1 − sSS)

The new frequency of the HbS allele is the fraction of post-selection alleles that are HbS, which is:

q' = [pq + q²(1 − sSS)] / w̄

At equilibrium, q' = q. Setting this up and solving (a few lines of algebra I will not run on the page; the standard derivation is in Hartl & Clark 2007 ch 6), the equilibrium frequency of HbS is:

> **q* = sAA / (sAA + sSS)**

This is one of the most useful equations in population genetics. The equilibrium allele frequency under heterozygote advantage is determined purely by the *relative* selection coefficients against the two homozygotes. Plug in numbers:

q* = sAA / (sAA + sSS) = 0.10 / (0.10 + 0.80) = 0.10 / 0.90 = **0.111**

So the model predicts the HbS allele should sit at a frequency of about 11.1% in malaria-endemic West Africa.

The observed frequency? In the malaria belt of West Africa, the HbS allele frequency runs about 0.08–0.12 in unselected samples — close to 0.10 ([Piel et al. 2010, *Nat Commun* 1:104](https://www.nature.com/articles/ncomms1104); the geostatistical map of HbS frequencies). The match between prediction and observation is within the rounding error of the selection coefficients.

That is the chapter's deep-dive. *One division — sAA / (sAA + sSS) — predicts the equilibrium frequency of a clinically significant allele in a real human population to within a percentage point.* The math works because the biology is exactly what the model describes: heterozygotes have a fitness advantage in the malarial environment, both homozygotes pay a cost, and selection balances the costs at the predicted equilibrium.

### What the equilibrium does — and what changes when malaria leaves

The balanced polymorphism is *stable* — if the allele frequency is perturbed away from 0.111 (by drift, founder effect, gene flow), selection pushes it back. If *q* drifts above 0.111, then HbSS frequency rises faster than HbAA frequency falls, more SS homozygotes die, *q* drops back. If *q* drifts below 0.111, then HbAA frequency rises faster than HbSS frequency falls, more AA homozygotes die from malaria, *q* rises back. The frequency 0.111 is an attractor in the dynamical system.

Now change the environment. Eradicate falciparum malaria. The malaria-related selection coefficient *sAA* drops to zero. The equation becomes:

q* = 0 / (0 + sSS) = 0

There is no longer any equilibrium that maintains the HbS allele. With *sAA* = 0, every copy of the HbS allele is purely deleterious — heterozygotes have the same fitness as HbAA homozygotes, and HbSS homozygotes are at severe fitness disadvantage. The HbS allele is now under classical directional selection against a (mostly) recessive deleterious. The expected trajectory is slow decline toward extinction.

How slow? With *sSS* = 0.8 and starting *q* = 0.10, the change per generation is roughly Δq ≈ −*sSS* × q² × p ≈ −0.8 × 0.01 × 0.9 ≈ −0.007. The HbS allele frequency drops by about 0.7% per generation. To halve from 0.10 to 0.05 takes about 10–15 generations; to reach 0.01 takes about 50–80 generations. Slow but real.

Test the model against a real-world population that has recently moved out of malaria endemicity. **African Americans** are descended primarily from West Africans who came to North America via the transatlantic slave trade, with most of the gene flow in the 17th–19th centuries (about 10–15 generations ago). North America has had much less endemic falciparum malaria than West Africa, especially in the last 5–10 generations. The selection pressure that maintained HbS at 0.10 in West Africa has been mostly absent for the African-American population.

The observed HbS allele frequency in African Americans today is about 0.04 ([CDC 2024](https://www.cdc.gov/sickle-cell/data/index.html); newborn screening data; [verify exact frequency, which varies by region and sample]). That is about 40% of the West African ancestral value, declining roughly as the directional-selection-against-recessive equation predicts for 10–15 generations of relaxed *sAA* with continuing *sSS* against HbSS homozygotes.

The math, in this case, makes a prediction beyond West Africa and the prediction is roughly right. The HbS allele frequency has dropped in the African-American population over the centuries since the migration, by approximately the amount expected if selection against HbSS has been operating with reduced compensation from heterozygote advantage in the new (low-malaria) environment.

### Lesson and limit

**Lesson.** The math of heterozygote advantage explains both *why* sickle cell disease persists at the frequency it does in West Africa — selection maintains it through the heterozygote advantage in malaria-endemic environments — and the *geographic distribution* of the allele, which mirrors the historical distribution of falciparum malaria. It is one of the cleanest worked examples of natural selection at the molecular level, and one of the few cases where a single-locus population-genetic model fits a real human population well enough that the equilibrium frequency can be predicted from selection coefficients alone.

**Limit.** The selection coefficients I used (sAA = 0.1, sSS = 0.8) are approximate. The actual fitness estimates depend on the specific endemic region, the era (pre-modern vs. post-modern medicine), the specific *Plasmodium* burden, and many other factors. Modern estimates of *sAA* (the malaria mortality cost in HbAA homozygotes) range from about 0.05 to 0.2 across studies; estimates of *sSS* range from about 0.5 to 0.9 ([Hedrick 2011, *Heredity* 107:283–304](https://www.nature.com/articles/hdy201116); the careful modern review of sickle cell selection coefficients). The predicted *q\** therefore ranges, depending on which estimates you use, from about 0.05 to 0.25. The actual *q* in West Africa, 0.08–0.12, sits in the middle of that band — consistent with the model, but not a knife-edge confirmation. The selection coefficients matter, and they are hard to measure precisely.

Also, the sickle cell case is special in being **one locus, two alleles, large effects, well-characterized environment**. Most cases of balancing selection in nature are messier — frequency-dependent (your fitness depends on what alleles other individuals have, not just the absolute environment), context-dependent (the heterozygote advantage holds in some environments but not others), or multi-locus (the relevant fitness landscape involves interactions between several genes). Sickle cell is the *clean* case. It works as a worked example because it is uncharacteristically clean, not because all of population genetics is this tractable.

What sickle cell shows is that *the framework is right* — selection coefficients, equilibrium equations, predicted vs. observed allele frequencies — even when the parameters are hard to pin down. The framework predicts the right *kind* of behavior even when the specific numbers are approximate, and the cases where the parameters are well-measured (like sickle cell) confirm the framework.

---

## The neutral theory preview (full treatment in Chapter 13)

A puzzle, set up briefly and resolved in Chapter 13. The 1960s brought two pieces of empirical work that did not fit the natural-selection-explains-everything picture. First, in 1966 Richard Lewontin and Jack Hubby used a new technique (protein gel electrophoresis) to look at how much enzyme variation existed in natural populations of *Drosophila* and other organisms ([Lewontin & Hubby 1966, *Genetics* 54:577–594](https://academic.oup.com/genetics/article/54/2/577/5990091); the foundational paper). They found *much* more variation than anyone had expected — at most loci, populations carried multiple alleles at moderate frequencies. Second, molecular sequence data was beginning to accumulate, and the rate at which homologous proteins diverged between species seemed remarkably *constant* across lineages and across time — the "molecular clock" pattern ([Zuckerkandl & Pauling 1965, *Evolving Genes and Proteins*](https://www.sciencedirect.com/book/9781483227344/evolving-genes-and-proteins); the original molecular-clock argument).

Both observations were hard to explain with selection alone. If most variation were adaptively maintained, why so much of it? If divergence rate were driven by varying selection pressures across lineages, why so constant?

In 1968, Motoo Kimura published "Evolutionary rate at the molecular level" in *Nature*, proposing what became the **neutral theory of molecular evolution** ([Kimura 1968, *Nature* 217:624–626](https://www.nature.com/articles/217624a0); the original paper). The neutral theory's claim: *most* molecular variation within and between species is selectively neutral or nearly so — it has no fitness consequence — and its frequency is driven primarily by mutation and drift, not by selection. Selection still operates, but on a minority of mutations (the small fraction that have meaningful fitness effects); the bulk of observed variation is mutation × drift, and the apparent constancy of the molecular clock reflects the approximately constant rate at which neutral mutations enter a population and drift to fixation or loss.

The neutral theory's most striking prediction is that, for strictly neutral mutations, the *rate of fixation of new mutations in a population equals the per-individual mutation rate*. This is a remarkable result that holds independently of population size. The derivation: new mutations enter at rate 2*N*μ per generation (in a diploid population of *N* individuals with mutation rate μ per gamete per generation). Each new mutation has a probability of 1/(2*N*) of ultimately fixing (because for neutral alleles, fixation probability equals frequency, and the new mutation starts at 1/(2*N*)). So the rate of fixation = 2*N*μ × 1/(2*N*) = μ. The 2*N* in the input cancels the 1/(2*N*) in the fixation probability. The population-size dependence vanishes. *Every population, regardless of size, accumulates neutral substitutions at rate μ per generation.*

This is the molecular clock — at least for the neutral fraction. The neutral theory makes the clock a *consequence* of the math rather than a mysterious empirical regularity.

I am not going to push further on the neutral theory here. Chapter 13 is the chapter that lives inside it — molecular evolution, evo-devo, the substitution rate of synonymous vs. nonsynonymous changes, the population-genetic signatures of recent selection. What I want you to carry away from this preview is: (1) **not all evolution is selection** — drift is doing as much, or more, of the work at the molecular level than selection is; (2) **mutation rate sets the timescale** for neutral molecular change in a way that population size does not affect; (3) **Kimura 1968 is one of the most important papers in 20th-century biology** because it overturned the assumption that everything in genomes must be doing something adaptive.

---

## How the forces interact — which one wins where

Five forces, each pushing allele frequencies. In any real population they all act at once. The question is which dominates.

**Selection vs. drift.** The decisive parameter is **Ns** — effective population size × selection coefficient. When Ns >> 1, selection dominates and produces deterministic frequency changes. When Ns << 1, drift dominates and produces stochastic wandering. For humans (Ne ≈ 10,000), an allele with selection coefficient s = 10⁻⁵ (one part in 100,000) has Ns = 0.1 — drift dominates; the allele is effectively neutral. An allele with s = 0.01 has Ns = 100 — selection dominates; the allele goes to fixation or loss as the selection direction dictates.

This explains the apparent paradox of the neutral theory: most molecular variation has very small fitness effects (or none), so for any realistic population size, drift is the controlling force. Only the rare strongly-selected variants behave the way classical selection theory describes.

**Selection vs. gene flow.** The competition is between *s* and *m*. If a local population is under selection toward a favored allele but migrants keep arriving with the unfavored allele, the local frequency stabilizes at a balance. Roughly, if *m* >> *s*, migration prevents local adaptation; if *s* >> *m*, selection produces local adaptation despite migration. The peppered moth populations in regions of intermediate pollution had intermediate frequencies of the dark allele — selection in one direction, gene flow from neighboring populations diluting it.

**Selection vs. mutation.** For deleterious recessive alleles, mutation-selection balance produces an equilibrium at q* ≈ √(μ/s). For *s* = 0.5 (substantially harmful), μ = 10⁻⁵ (typical per-locus mutation rate), q* ≈ 4.5 × 10⁻³, and disease incidence ≈ q*² ≈ 2 × 10⁻⁵, or 1 in 50,000. This is a useful intuition: many rare recessive diseases sit at frequencies consistent with mutation-selection balance, because the alleles cannot be eliminated faster than recurrent mutation regenerates them.

**Drift vs. gene flow.** A small isolated population loses variation to drift; gene flow from a larger population restores it. The Florida panther example (above) shows the rescue effect in action. The general principle: very small populations should not be allowed to remain isolated if their conservation matters.

**Drift vs. mutation.** Under mutation-drift balance (no selection), a population reaches an equilibrium heterozygosity proportional to 4*Ne*μ (for autosomes in diploid species). For humans, with *Ne* ≈ 10,000 and μ ≈ 10⁻⁸ per base per generation, the predicted average heterozygosity per base is about 4 × 10⁻⁴, and the observed value is about 10⁻³ — same order of magnitude. The factor-of-two discrepancy comes from many things, including the fact that *Ne* has been variable over human history (probably larger in the more distant past), but the rough match is reassuring.

The summary picture: **large populations are dominated by selection (when there is any) and gene flow; small populations are dominated by drift and inbreeding; the boundary between regimes is set by Ne × s for selection vs. drift and by Ne × m for drift vs. gene flow.** Most real-world cases sit somewhere in between, with multiple forces contributing and the outcome reflecting the balance.

---

## Common student misconceptions

Population genetics is taught densely in most curricula and several misunderstandings recur. I want to name them explicitly.

**Misconception 1: "Natural selection is the only force of evolution."** No. Selection is one of five forces, and at the molecular level, drift probably accounts for more of the observed variation than selection does. A population can change its allele frequencies through drift (random fluctuation), gene flow (migration), mutation (recurrent input of new alleles), or non-random mating (changing genotype frequencies even without changing allele frequencies). When you see an allele frequency change in a real population, the first question is *which force?* — and the answer is usually a combination.

**Misconception 2: "Hardy-Weinberg equilibrium means the population is not evolving."** Hardy-Weinberg is the *null model*. It is what a population *would do* if no force were acting. Real populations are never exactly at Hardy-Weinberg, because some forces are always operating. When we say a particular locus is "in Hardy-Weinberg equilibrium," we mean the observed genotype frequencies are close enough to p², 2pq, q² that we cannot detect departure — which is consistent with no detectable evolution at that locus on the relevant timescale, not with "no evolution ever happening." The framework is a tool for *measuring deviations*, not a description of static populations.

**Misconception 3: "Dominant alleles increase in frequency over time because they are dominant."** This is exactly the misunderstanding Hardy's 1908 letter was answering, and it persists. *Dominance is about expression, not frequency.* Brown eyes are dominant over blue. Brown-eyed alleles are at lower frequency than blue-eyed alleles in many European populations. The dominant allele *expresses* the brown-eye phenotype when paired with a recessive blue-eye allele; it does not *propagate* faster because of dominance. Allele frequencies change because of selection, drift, gene flow, mutation, or non-random mating — and dominance is irrelevant to all five. The dominant allele rises only if selection favors the brown-eye phenotype or some other force is pushing on it.

**Misconception 4: "Genetic drift only matters for small populations."** Drift acts in all populations; its magnitude is just smaller in large ones. For nearly-neutral alleles (Ns near 1 or below), drift can dominate even in fairly large populations. Most molecular variation in humans behaves nearly-neutrally even though *Ne* is on the order of 10,000 — because the per-locus selection coefficient is usually very small. Drift is a continuum, not a regime that switches on only when N drops below some threshold.

**Misconception 5: "Inbreeding causes mutations."** No. Inbreeding does not change mutation rates. Inbreeding increases the *homozygosity* of existing alleles — including existing recessive deleterious alleles that were hiding in heterozygotes. The diseases that emerge in inbred populations are pre-existing alleles being expressed homozygously, not newly mutated alleles. The deleterious mutations were already there at low frequency; inbreeding just made them visible by pairing them with themselves more often than random mating would.

**Misconception 6: "If a population is in Hardy-Weinberg, all its loci are."** Hardy-Weinberg is a per-locus condition. A population can be in equilibrium at most loci but out of equilibrium at one or two where selection (or another force) is acting strongly. The MHC complex in humans, for instance, shows substantial departure from Hardy-Weinberg due to balancing selection for diversity — even though most other loci in the same individuals are close to equilibrium. When you test Hardy-Weinberg, you test one locus at a time, and finding equilibrium at one locus does not mean every locus is at equilibrium.

---

## Synthesis and the bridge to Chapter 11

Step back. The chapter did four things.

First, it derived the Hardy-Weinberg equilibrium from random mating and Mendelian segregation — three sentences of algebra, p² + 2pq + q² = 1, allele frequencies stable across generations if five conditions hold. This is the null hypothesis of population genetics. It is not a description of real populations; it is the reference point against which the behavior of real populations is measured.

Second, it cataloged the five forces — mutation, natural selection, genetic drift, gene flow, non-random mating — each corresponding to a violated Hardy-Weinberg assumption. Each force has a characteristic signature in the data and a characteristic equation governing its magnitude. Mutation supplies the variation; selection sorts among variants; drift moves frequencies randomly in finite populations; gene flow homogenizes neighboring populations; non-random mating reshuffles diploid combinations without changing the allele pool.

Third, it worked through one extended case — the HbS allele in West Africa — where heterozygote advantage produces a balanced polymorphism at the predicted equilibrium frequency. The math is brutal in its simplicity: q* = sAA / (sAA + sSS) ≈ 0.111, observed q ≈ 0.10. One equation, one division, one match between prediction and observation. The geographic distribution of HbS mirrors the historical distribution of falciparum malaria. The decline of HbS in African-American populations over 10–15 generations of relaxed selection is roughly what the directional-selection equation predicts when the malaria selection pressure is removed. The framework works.

Fourth, it named the misconceptions that students reliably arrive with — the conflation of dominance with frequency, the belief that selection is the only force, the assumption that Hardy-Weinberg implies stasis. Each was named and dismantled.

The bridge to Chapter 11. This chapter described population-genetic forces operating *within* a population — how allele frequencies change inside a single interbreeding group. The next chapter asks what happens when populations *split* — when gene flow drops to zero and two formerly connected populations become genetically isolated. Speciation is the long-term consequence of population genetics: the same five forces acting independently in two populations, over thousands or millions of generations, produce divergence; eventually the divergence becomes large enough that the populations cannot interbreed even if reunited; the populations have become separate species. Chapter 11 walks the mechanisms (allopatric vs. sympatric speciation, reproductive isolating barriers, polyploidy in plants), the famous adaptive radiations (cichlids, Darwin's finches, Hawaiian honeycreepers), and the tempo question (gradualism vs. punctuated equilibrium) we hand-waved past in Chapter 09.

Population genetics is the engine. Speciation is the product. The math is the same math, run for longer and in parallel in two places at once.

---

## Exercises

**Warm-up**

1. A population of 200 plants is sampled for flower color, controlled by a single gene with two alleles. The dominant allele (R) produces red flowers; the recessive (r) produces white. The sample contains 80 RR plants, 80 Rr plants, and 40 rr plants. (a) Compute the allele frequencies p and q. (b) Predict the expected genotype frequencies under Hardy-Weinberg equilibrium. (c) Does the observed distribution match Hardy-Weinberg? If not, qualitatively, which force might be responsible? *Tests: basic computation of allele frequencies from genotype counts; comparison of observed vs. expected; introduction to deviation as evidence.*

2. Cystic fibrosis is a recessive disease present in approximately 1 in 2,500 births in a European-ancestry population. Assuming Hardy-Weinberg equilibrium, (a) calculate q (the frequency of the CF allele), (b) calculate p (the frequency of the wild-type allele), (c) calculate the carrier frequency (2pq). (d) About what fraction of the population are silent carriers? *Tests: applying Hardy-Weinberg to estimate carrier frequency from disease frequency, a common medical-genetics application.*

3. Define each of the following in one sentence, in plain language: (a) allele frequency, (b) genotype frequency, (c) fitness (w), (d) selection coefficient (s), (e) effective population size (Ne), (f) balanced polymorphism. *Tests: vocabulary recall as a check that the central concepts have been pinned down.*

**Application**

4. **Heterozygote advantage worked example.** Consider a hypothetical population in which heterozygotes (Aa) have the highest fitness, with wAA = 0.7, wAa = 1.0, waa = 0.5. (a) Compute the selection coefficients sAA and saa. (b) Use the equilibrium equation q* = sAA / (sAA + saa) to predict the equilibrium frequency of the *a* allele. (c) At this equilibrium, what fraction of the population are heterozygotes? (d) Suppose the environment changes so that wAA rises to 0.9 (heterozygote advantage shrinks). Recompute q*. Does the *a* allele go up or down? Explain in one sentence why. *Tests: quantitative application of the heterozygote advantage model; understanding how changes in selection coefficients move the equilibrium.*

5. **Estimating Ne and predicting drift.** A wildlife biologist is monitoring a population of 1,000 panthers. She determines that only 200 of them are reproducing (the rest are pre-reproductive juveniles or post-reproductive). Of the 200 reproducing adults, the sex ratio is 40 males to 160 females (some males monopolize matings). (a) Estimate the effective population size *Ne* using the formula *Ne* ≈ 4 × (Nm × Nf) / (Nm + Nf) for unequal sex ratios. (b) For a neutral allele at this *Ne*, what is the standard deviation of allele frequency change per generation if p = 0.5? (c) Compare your answer to (b) to the per-generation change predicted in a panmictic population of 1,000 (i.e., if Ne = 1,000). What does this say about why census population size can mislead about evolutionary risk? *Tests: working with effective population size in a conservation scenario; understanding the inverse-square-root relationship between Ne and drift magnitude.*

6. **Sickle cell decline in African Americans.** The HbS allele frequency in West Africa is approximately 0.10. In African Americans (descended primarily from West Africans 10–15 generations ago in an environment with much less falciparum malaria), the current HbS allele frequency is approximately 0.04. (a) Walk through, qualitatively, the population-genetic forces that could explain the decline. (b) Which force(s) would you expect to dominate? Justify in one paragraph. (c) The reduction is about 60% over 10–15 generations. Does this rate strike you as fast or slow, in the context of selection-against-recessive-with-relaxed-heterozygote-advantage? *Tests: integration of multiple forces operating on a real population; quantitative estimation of expected rates of change.*

**Synthesis**

7. **Bottleneck vs. sustained small population.** Population A is reduced from 1 million to 50 individuals in a single generation by a habitat collapse, then expands over the next 50 generations back to 1 million. Population B starts at 1 million, drops gradually to 50 individuals over many generations, and stays at 50 for 1,000 generations. (a) Which population is expected to retain more genetic variation at the end? (b) Why? Address both the rate of allele loss and the rate of allele regeneration through mutation. (c) What practical implication does this have for conservation biology when comparing species that have recently bottlenecked vs. species that have been at chronically low population sizes for many generations? *Tests: distinguishing two superficially similar mechanisms of variation loss; conservation implications.*

8. **Hardy-Weinberg as forensic tool.** A forensic geneticist examines a population sample at a SNP locus with two alleles, T and C. She observes 49 TT, 6 TC, and 45 CC individuals out of 100. (a) Compute the allele frequencies p (frequency of T) and q (frequency of C). (b) Compute the expected genotype frequencies under Hardy-Weinberg. (c) Compare observed and expected. Which genotype is over-represented and which is under-represented? (d) Propose at least three biological hypotheses that could produce this pattern, and explain how you would distinguish among them. *Tests: detection of departure from Hardy-Weinberg; interpretation of departure as evidence; multiple hypotheses for the same data.*

9. **Carrier screening and the eugenics question.** In a hypothetical society, a recessive disease has disease incidence q² = 1/2,500 and carrier frequency 2pq ≈ 0.04 (4% carriers). A government proposes a program to eliminate the allele by preventing all affected (qq) individuals from reproducing. (a) Compute what fraction of the next generation's gene pool of this allele is currently carried by carriers (Aa) vs. affected (aa) homozygotes. (b) If selection against aa is perfect (saa = 1) and operates only on the homozygotes (no impact on Aa), compute the predicted change in q in one generation. (c) Approximately how many generations would the program need to operate to halve q? (d) On the basis of (a)-(c), evaluate the program's mathematical feasibility, separately from any ethical considerations. *Tests: quantitative application of selection against recessive; the historical eugenics context where such math was relevant; numerical futility of programs that ignore the carrier-frequency arithmetic.*

**Challenge**

10. **Designing a study to distinguish drift from selection.** An ornithologist studying a population of 200 island birds finds that an allele at a particular locus has risen from frequency 0.05 (estimated from a 1950 museum-specimen sample) to frequency 0.35 today, 75 years later. Average generation time is 3 years, so this represents about 25 generations. (a) Compute the per-generation rate of frequency change. (b) Is this rate consistent with drift alone in a population of *Ne* = 200? Use the formula for drift variance to argue quantitatively. (c) Is the rate consistent with directional selection? If so, estimate the required selection coefficient. (d) Propose a study design that would distinguish whether the change is due to drift or to selection — what data would you collect, and what pattern would you look for? *Tests: ability to distinguish two mechanistically different explanations for the same observed pattern; quantitative reasoning about expected magnitudes; experimental design.*

11. **Inbreeding coefficient in a real pedigree.** In a small isolated village, a couple of first cousins (parents are siblings to each other's parents) marry. (a) Compute the inbreeding coefficient F of their child. (b) For a recessive disease allele with population frequency q = 0.02, compute the expected disease frequency in offspring of (i) two unrelated individuals from this village, (ii) first cousins. Use the formula *f*(aa) = q² + Fpq. (c) By approximately what factor does first-cousin marriage elevate the risk of this disease? (d) Repeat for q = 0.01 and q = 0.001. What does the dependence of the elevation factor on q tell you about why first-cousin marriage is most consequential for rare diseases? *Tests: working with the inbreeding coefficient; numerical application across multiple allele frequencies; reasoning about why inbreeding's effects are concentrated at rare-allele loci.*

12. **The neutral theory's prediction.** Kimura's neutral theory predicts that for strictly neutral mutations, the rate of substitution (fixation of new mutations) equals the per-individual mutation rate, *independently of population size*. (a) Walk through the derivation: rate of input × probability of fixation = ? (b) Why does this prediction seem paradoxical at first — large populations have more individuals and therefore more new mutations per generation, yet have the same substitution rate as small populations? (c) Find the resolution: identify the term that cancels. (d) The molecular clock observed in real proteins (cytochrome c, hemoglobin) is approximately constant per generation across lineages with very different population sizes. Does this support or refute the neutral theory? *Tests: working through a non-obvious derivation; understanding what the molecular clock empirically supports; engaging with theory at a level deeper than memorization.*

---

## What the student builds

`10-population-genetics.html` — Hardy-Weinberg + five-forces simulator. The aim is a tool that makes the five forces visible and lets the student dial each one up or down to see how allele frequencies respond.

**Controls.** Starting allele frequency p₀ (default 0.5). Effective population size Ne (slider: 10 to 100,000, logarithmic). Three selection coefficients — sAA, sAa, sSS — each independently adjustable from 0 to 1 (allows directional selection, heterozygote advantage, heterozygote disadvantage). Mutation rate μ per allele per generation (default 10⁻⁵). Gene flow rate m from an external population with fixed allele frequency p_external (default 0). Number of generations to simulate (default 200). Number of replicate runs (default 10, to make drift visible).

**Display.** Primary panel: line plot of allele frequency *p* vs. generation, with one line per replicate (semi-transparent for visual layering). Solid black line: deterministic prediction from the selection equation (the expected trajectory in the absence of drift). Dashed horizontal line: theoretical equilibrium frequency under heterozygote advantage (q* = sAA / (sAA + sSS)) if applicable. Secondary panel: observed genotype frequencies vs. Hardy-Weinberg predictions, plotted side by side at user-selected time points. Tertiary panel: a small "force-balance" indicator showing which force is currently dominant (selection / drift / gene flow / mutation), based on the parameter values.

**Three scenario presets.**

1. *Pure drift in a small population.* Ne = 50, all selection coefficients 0, mutation rate 0, gene flow 0. Run 10 replicates for 200 generations. Students should see allele frequency wandering randomly in each replicate, with some replicates fixing at 1 and others at 0; the mean across replicates remains roughly p₀ but the variance grows over time.

2. *Directional selection in a large population.* Ne = 10,000, sAA = 0, saa = 0.1, mutation 0, gene flow 0, p₀ = 0.1. Students should see the *A* allele rise smoothly toward fixation along the deterministic trajectory; replicate variation is small (drift overwhelmed by selection in a large population).

3. *Heterozygote advantage producing balanced polymorphism.* Ne = 10,000, sAA = 0.1, sAa = 0, sSS = 0.8 (the sickle cell parameters). p₀ = 0.5. Students should see the allele frequency converge to q* = 0.1/0.9 ≈ 0.111 regardless of starting point; the population settles into balanced polymorphism; the genotype frequency panel shows the characteristic AA:Aa:aa distribution.

The simulator should let the student combine forces. The clearest pedagogical demonstration is running heterozygote advantage with two different Ne values: at Ne = 10,000, the balanced polymorphism is stable; at Ne = 50, drift can drag the frequency away from 0.111 and even drive the population to fixation or loss of the HbS allele despite the heterozygote advantage. The lesson: even strong balancing selection cannot maintain polymorphism in a very small population. Conservation implication: small isolated populations lose the polymorphisms that selection would otherwise maintain.

A stretch goal for the simulator: a "sickle cell in a changing environment" preset that runs heterozygote advantage for 200 generations (settling near q ≈ 0.10), then sets sAA to zero (malaria eradicated) and continues for another 200 generations. Students should see the HbS allele decline toward extinction at the predicted slow rate, matching the qualitative trajectory observed in the African-American population over the last 10–15 generations.

---

**What would change my mind.** A demonstration that the heterozygote advantage model for sickle cell systematically fails — that, when selection coefficients are measured carefully in specific African populations and the predicted equilibrium frequency is computed, the observed allele frequency deviates from the prediction in ways that cannot be accounted for by drift, gene flow, or measurement error. Such a finding would not overturn the population-genetic framework as a whole, but it would show that the cleanest worked example used here is not actually clean — that the apparent fit between prediction and observation reflects coincidence or undocumented covariates. Recent careful work ([Hedrick 2011](https://www.nature.com/articles/hdy201116); [Elguero et al. 2015, *PNAS* 112:7051–7054](https://www.pnas.org/doi/10.1073/pnas.1505665112)) has refined the parameter estimates without overturning the qualitative conclusion. If new work showed the relationship breaks down, I would need to revise this chapter's deep-dive.

**Still puzzling.** The exact relationship between effective population size (Ne) and census size (N) for real populations remains hard to pin down empirically. The estimates of Ne ≈ 10,000 for humans over recent history come from indirect methods (linkage disequilibrium decay, coalescent analysis of polymorphism data) that involve substantial modeling assumptions. Different methods give somewhat different answers; the ratio Ne/N is variable across species and across loci within species; and the "long-term harmonic mean" interpretation of Ne is itself an idealization. I have used Ne ≈ 10,000 in this chapter as a working number, but the right answer depends on what question is being asked and on which timescale.

---

**Tags:** Hardy-Weinberg, allele-frequency, natural-selection, genetic-drift, gene-flow, mutation, non-random-mating, fitness, selection-coefficient, effective-population-size, balanced-polymorphism, heterozygote-advantage, sickle-cell, malaria, founder-effect, bottleneck, Amish, Ellis-van-Creveld, cheetah-bottleneck, Florida-panther, neutral-theory, Kimura, mutation-selection-balance, inbreeding, FST
