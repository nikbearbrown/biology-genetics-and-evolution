# Chapter 02 — Mendel's Laws and Mendelian Inheritance

**Suggested titles:**
- *A Monk, a Garden, and 28,000 Peas — How Counting Became a Theory of Heredity*
- *Three Laws from a Schoolteacher's Notebook: Mendel and the Arithmetic of Inheritance*
- *Why It Took Thirty-Five Years for the World to Notice: Mendel, 1865 → 1900*

---

**TL;DR.** Gregor Mendel published the founding paper of genetics in 1866, in the *Verhandlungen des naturforschenden Vereines in Brünn* — a journal so obscure that copies sat on library shelves across Europe for thirty-five years without being read. He was a self-taught experimentalist running a vegetable garden behind an Augustinian monastery, and he had done two things nobody before him had done together: he had chosen *binary traits* (round vs. wrinkled, yellow vs. green, tall vs. dwarf — seven such traits in the common pea), and he had *counted at scale* (something like 28,000 individual plants over eight years). The combination produced ratios — 3:1 in monohybrid F₂ crosses, 9:3:3:1 in dihybrid F₂ crosses — that were exact enough to demand a mechanism. Mendel proposed one: each organism carries *two* hereditary units (now called alleles) at each character, one from each parent; these units separate cleanly into gametes (the **Law of Segregation**); in heterozygotes one allele's phenotype dominates the other's, which sits hidden but undestroyed (the **Law of Dominance**); and alleles at different characters assort independently in gamete formation (the **Law of Independent Assortment**). The 3:1 and 9:3:3:1 ratios are exact consequences of this model under the **product rule** of independent probability — the same rule a Punnett square represents tabularly. The framework is still the operating arithmetic of clinical genetic counseling for monogenic disorders today: a carrier-couple risk for cystic fibrosis is computed by walking the same gamete-combining grid that Mendel walked for round-and-wrinkled peas, and gets the same numbers. The chapter shows the arithmetic, demonstrates that Punnett squares and the product rule are two views of one operation, and names what Mendel's framework does *not* cover (incomplete dominance, polygenic traits, linkage — taken up in Chapter 03). At the end we look honestly at R. A. Fisher's 1936 statistical analysis of Mendel's published data, which found the ratios suspiciously close to the predicted values — a result still debated, and worth naming as a flag on the data rather than a debunking.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **Describe** Mendel's experimental design — pure-breeding parental lines, controlled hand-pollination, P/F₁/F₂ notation, large sample counts — and **explain** why each design choice mattered for extracting laws from the data.
2. **State** Mendel's three laws (Dominance, Segregation, Independent Assortment) in plain English, and **connect** each to the meiotic event that produces it (anaphase I segregation, independent metaphase I orientation — both from Ch 01).
3. **Predict** F₁ and F₂ phenotype and genotype ratios for any monohybrid cross between two homozygous parents, and for any dihybrid cross where the two genes are on different chromosomes — using **both** the Punnett square and the product rule, and **show** that the two methods give identical answers.
4. **Compute** trihybrid F₂ ratios (27:9:9:9:3:3:3:1) by extending the product rule, and **explain** why building the corresponding 8 × 8 Punnett square is computationally wasteful relative to the product-rule shortcut.
5. **Apply** the test cross to determine whether an organism showing a dominant phenotype is homozygous dominant (AA) or heterozygous (Aa) — and **interpret** the 1:1 vs. all-dominant offspring ratios that distinguish the two cases.
6. **Calculate** carrier-couple recurrence risks for autosomal recessive disorders (cystic fibrosis, sickle-cell disease, Tay-Sachs) using the monohybrid 1:2:1 genotype ratio, and **compute** the probability that *k* of *n* children will be affected using the binomial distribution.
7. **Apply** the chi-square test to F₂ data from a real cross, **compute** χ² with the appropriate degrees of freedom, and **interpret** the resulting *p*-value as evidence for or against Mendelian expectations.
8. **Diagnose** at least three common misconceptions about Mendelian inheritance (e.g., "dominant means common in the population") and **explain** why each is wrong from first principles.
9. **Name** at least four monogenic Mendelian human disorders — Huntington's (autosomal dominant), cystic fibrosis (autosomal recessive), Tay-Sachs (autosomal recessive), achondroplasia (autosomal dominant) — and **state** for each the inheritance pattern and the typical recurrence risk for affected parents.
10. **Build** an extended Punnett-square simulator (`02-mendelian-crosses.html`) that handles 1-, 2-, and 3-gene crosses, computes ratios via both Punnett and product-rule methods, runs sampling experiments showing how observed ratios converge to expected ratios as sample size grows, and includes a chi-square calculator and a small pedigree-pattern recognizer for recurrence-risk problems.

**Prerequisites.** Chapter 00 (Punnett squares as bookkeeping; 1:2:1, 3:1, 9:3:3:1 ratios) and Chapter 01 (meiosis as the cellular mechanism that produces the gamete ratios Mendel needed). The vocabulary of allele, locus, genotype, phenotype, homozygous, heterozygous, dominant, recessive (Ch 00). No statistics background assumed beyond what is built on the page — the product rule, the sum rule, and the chi-square test are all derived where used. The chapter assumes you have seen anaphase I separation as the cellular basis of segregation; if not, the relevant 200-word recap is in §2 below.

---

## A scene in a monastery garden, 1865

Brno, capital of Moravia, in what was then Austria, now the Czech Republic. February 1865. A forty-two-year-old Augustinian friar named Gregor Mendel stands at the front of a small meeting room of the *Naturforschender Verein* — the Natural Science Society of Brünn — and reads a paper. He has spent the previous eight years, summer after summer, growing pea plants in a small plot of land behind his monastery and counting their offspring. He has just finished. He is presenting what he found.

He reads in German for about an hour. He gives tables. He gives ratios. He gives a hypothesis. He proposes that hereditary information is carried in *paired discrete units* — he calls them *Anlagen* (German for "predispositions" or "factors") — that separate cleanly when gametes form and recombine when fertilization happens. He gives the mathematics: a heterozygous parent makes gametes in a 1:1 ratio of the two factors; random fertilization produces 1:2:1 genotype ratios in F₂; with dominance, the phenotype ratio is 3:1. He gives the dihybrid extension: 9:3:3:1. He gives 28,000 individual plant counts to back the predictions up.

The audience listens politely. They ask no substantive questions. The paper is published the following year ([Mendel G. *Versuche über Pflanzen-Hybriden*. Verhandlungen des naturforschenden Vereines in Brünn. 1866;4:3–47](https://www.biodiversitylibrary.org/item/124773)) in a journal that the Brno society distributes by exchange to about 130 institutional libraries across Europe. Forty offprints are sent to specific botanists, including the most prominent Swiss plant physiologist of the era, Carl Nägeli at Munich — who reads it, exchanges a few unenthusiastic letters with Mendel, and recommends he try the same experiments on hawkweed (*Hieracium*), a plant whose breeding turns out to be reproductively bizarre in a way nineteenth-century botany did not yet understand. Mendel's hawkweed experiments produce confusing results, and the hawkweed correspondence with Nägeli ends inconclusively. By 1868 Mendel is elected abbot of the monastery, administrative duties consume his time, and he never finishes another set of breeding experiments.

He dies in 1884, age sixty-one, of kidney failure. His successor as abbot orders his papers and notebooks burned. No major obituary in any scientific journal of the day notes the loss. His paper sits in the Brno proceedings, on library shelves across Europe, *cited* in passing in a handful of bibliographies, but not *read* in any productive sense, for the next thirty-five years.

Then, in 1900, three botanists working independently on plant hybridization arrive at the same ratios in their own crosses, each tracks down Mendel's 1866 paper while writing up his results, each acknowledges priority, and all three publish in the spring of 1900. **Hugo de Vries** in Amsterdam ([de Vries H. *Sur la loi de disjonction des hybrides*. Comptes rendus de l'Académie des sciences. 1900;130:845–847](https://gallica.bnf.fr/ark:/12148/bpt6k30844)). **Carl Correns** in Tübingen ([Correns C. *G. Mendel's Regel über das Verhalten der Nachkommenschaft der Rassenbastarde*. Berichte der Deutschen botanischen Gesellschaft. 1900;18:158–168](https://www.biodiversitylibrary.org/item/103956)). **Erich von Tschermak** in Vienna ([Tschermak E. *Über künstliche Kreuzung bei Pisum sativum*. Berichte der Deutschen botanischen Gesellschaft. 1900;18:232–239](https://www.biodiversitylibrary.org/item/103956)). The year 1900 is the founding year of modern genetics. The William Bateson coinage *genetics* itself arrives six years later in 1906 ([Bateson W. *Inaugural address: progress of genetic research*. Report of the Third International Conference on Genetics. 1907:90–97](https://www.biodiversitylibrary.org/item/85036) [verify]).

So the puzzle the chapter opens on is not "what did Mendel discover?" — the laws are stated in any high school biology text. The puzzle is *what did Mendel actually do that nobody else had done?* Hybridization experiments were not new in 1865. People had been crossing plants for centuries — Joseph Kölreuter at Tübingen had published systematic hybridization studies in the 1760s; Charles Naudin in Paris had published similar work in 1862, three years before Mendel's talk, with similar but unanalyzed ratios in his data. None of them had extracted laws. What did Mendel do differently? The answer is going to be unromantic: he chose his materials carefully, he counted at scale, and he was trained as a physicist — he expected nature to produce numerical regularities and he treated his garden as an experimental apparatus designed to reveal them. The hint that this chapter develops: Mendel's discovery was *not* fundamentally about pea plants. It was about experimental design, sample size, and the recognition that hereditary patterns are statistical regularities — and the moment he counted enough offspring to see the ratios sharply, the inference followed almost by itself.

The chapter that follows works through what he did, the laws he extracted, the mathematics of their application, the rediscovery in 1900, and the modern clinical setting where the same arithmetic — Punnett squares descended unchanged from his 1866 paper — produces the recurrence-risk numbers that genetic counselors give carrier couples today. The chromosomal theory we built in Chapter 01 is what we now know to be *underneath* Mendel's laws; Mendel never saw a chromosome. He inferred their behavior from offspring counts. This is the move that made him.

---

## Why the pea was the right organism — the apparatus

The choice of *Pisum sativum* — the common garden pea — was not a folksy preference. It was the apparatus. Mendel needed three properties in his experimental organism, and the pea provided all three.

**Property 1: Reproductive control.** Pea plants are normally **self-pollinating**: each flower's anthers (the male parts) release pollen that lands on the same flower's stigma (the female part) before the flower opens. Left alone, a pea plant fertilizes itself. This sounds like a bug — how do you cross two plants if they fertilize themselves first? — but it is actually a feature, twice. First, because self-pollination is the default, you can grow a population of plants for generations and be confident that none of them have been cross-pollinated by a neighbor; the lineage is *pure*. Second, when you want to make a controlled cross, you can intervene before the flower opens: gently pry it apart with tweezers, snip off the anthers (a procedure called **emasculation**) before any pollen is released, and then deposit pollen from a chosen donor plant on the stigma with a small brush. The pea will faithfully accept the foreign pollen because its own pollen has been physically removed.

This was the experimental control Mendel needed. With emasculation and hand-pollination, he could specify which two plants mated. Without that control he would have been counting offspring from random crosses among his garden plants, and the ratios would have been hopelessly noisy.

**Property 2: Pure-breeding lines for binary traits.** Mendel chose seven characters in pea plants, each appearing in two clearly distinguishable states — what we now call **binary traits** or **discrete characters**, where every individual plant is unambiguously one or the other, no intermediate forms. The seven traits:

| Character | Dominant state | Recessive state |
|-----------|----------------|-----------------|
| Seed shape | Round (R) | Wrinkled (r) |
| Seed color | Yellow (Y) | Green (y) |
| Pod shape | Inflated (I) | Constricted (i) |
| Pod color | Green (G) | Yellow (g) |
| Flower color | Violet/purple (V) | White (v) |
| Flower position | Axial — along the stem (A) | Terminal — at the tip (a) |
| Stem length | Tall, ~6 ft (T) | Dwarf, ~1 ft (t) |

Each character snaps between two states. There is no "slightly wrinkled" seed in Mendel's data, no "medium-tall" stem — every plant is one or the other. This binary classification is what makes counted ratios meaningful. If Mendel had tried to measure stem length as a continuous trait (centimeters, with a distribution), he would have seen a bell curve in F₂ and would never have extracted a clean 3:1.

Before he made a single cross, Mendel spent **two years** establishing pure-breeding lines for each trait — letting plants self-pollinate for multiple generations until the offspring of a tall plant were always tall and the offspring of a dwarf plant were always dwarf, with no exceptions ([Mendel 1866 §1](https://www.biodiversitylibrary.org/item/124773)). These are **pure-breeding** or **true-breeding** lines: populations in which the genetic state has been so thoroughly homogenized that no hidden variation remains to surprise the experimenter. In modern language, a pure-breeding plant is **homozygous** at the locus in question — both copies of the relevant gene carry the same allele. (**Homozygous** comes from Greek *homos*, "same," and *zygote*, "yoked together" — a zygote yoking two identical alleles. **Heterozygous**, the contrasting term, is from *heteros*, "different" — a zygote yoking two different alleles. We will use these terms throughout the chapter.) A pure-breeding tall plant has genotype TT; a pure-breeding dwarf plant has genotype tt. Cross them, and you know exactly what each parent contributed — there is no hidden third allele lurking in the population to mess up the ratios.

**Property 3: Fast generation time, large brood size.** Pea plants flower and set seed in a single growing season, so each cross produces an F₁ generation in one year and an F₂ generation the next. Each pod typically contains 5–9 seeds, and each plant produces dozens of pods. A single F₁ plant self-pollinated can produce hundreds of F₂ seeds, and Mendel grew thousands of F₁ plants per cross. The total counts in his 1866 paper are striking: for the seed-shape cross, he counted 7,324 F₂ seeds (5,474 round to 1,850 wrinkled, ratio 2.96:1); for seed color, 8,023 F₂ seeds (6,022 yellow to 2,001 green, ratio 3.01:1); across all seven traits, his published F₂ totals add up to around 19,959 individual seeds or plants ([Mendel 1866 Table I](https://www.biodiversitylibrary.org/item/124773)). His overall enterprise across the eight years included multiple replications and the dihybrid and trihybrid experiments — historians estimate he handled, sorted, and counted on the order of 28,000 plants and seeds over the lifetime of the project [verify against [Orel V. *Gregor Mendel: The First Geneticist*. Oxford UP; 1996](https://global.oup.com/academic/product/gregor-mendel-9780198547747)].

This sample size matters. The ratios Mendel extracted are not visible at small sample sizes. With ten seeds, you might count 8 round and 2 wrinkled, or 6 round and 4 wrinkled, or any of half a dozen other patterns; the 3:1 prediction is invisible in the noise. With ten thousand seeds, the same prediction is unmissable. Mendel's instinct to count large brought a *signal* out of data that smaller experiments would have produced as *coincidence*. This is the move that distinguishes him from his predecessors.

The combination of these three properties — controllable mating, binary traits with pure-breeding lines, fast and prolific reproduction — turned the pea into a counting apparatus. Mendel had built an experimental system in which ratios could be measured precisely enough to demand a theory. The theory was the easy part. The apparatus was the hard part.

---

## The first experiment: a monohybrid cross, and a 3:1 ratio

Take the seed-shape character. Establish a pure-breeding line of round-seeded plants — call them RR, the "parental generation" or **P generation**, both alleles dominant. Establish a pure-breeding line of wrinkled-seeded plants — rr, both alleles recessive. Cross them: emasculate flowers on an RR plant and hand-pollinate with pollen from an rr plant (or vice versa — Mendel did **reciprocal crosses** to check that the outcome did not depend on which parent was which, and it did not). Collect the seeds. The next year, plant them and observe.

The result Mendel found, in cross after cross across all seven traits, is the foundational empirical observation of genetics: *every F₁ offspring resembles one parent exactly, with no intermediate forms*. For seed shape: every F₁ seed is round. For seed color: every F₁ seed is yellow. For flower color: every F₁ plant has violet flowers. The other parent's trait — wrinkled, green, white — disappears. Not "averaged in," not "blended," not "diluted" — *absent*. Every single F₁ plant looks like one parent.

This was already strange. The dominant theory of inheritance in 1865 was **blending inheritance** — the intuition that offspring are mixtures of their parents' traits, the way mixing red paint with white paint gives pink paint. If you cross a red-flowered plant with a white-flowered plant, blending theory predicts pink. Mendel got *violet* — full violet, indistinguishable from the violet parent, in every F₁ plant. The white trait had not been mixed in. It had been *replaced*.

Two things could be happening. Either the white trait had been *destroyed* during fertilization — somehow eliminated from the F₁ plants altogether — or it had been *hidden*, present but not expressed. Mendel could not tell from F₁ alone. To distinguish the two possibilities, he did the second move: he let F₁ plants self-pollinate and counted the **F₂ generation**.

If the white trait had been destroyed, F₂ would be all violet (because there is no white left to come back). If it had been hidden, F₂ would show *some* white — and the proportion in which it returned would tell you something about the underlying mechanism.

For flower color, Mendel grew 929 F₂ plants. Of these, 705 had violet flowers and 224 had white. The ratio: 705/224 = 3.15. He rounded it to 3:1. For seed shape (a much larger experiment, because seeds are easier to count than mature plants), the F₂ count was 5,474 round to 1,850 wrinkled — 2.96:1. For seed color, 6,022 yellow to 2,001 green — 3.01:1. Across all seven traits, the F₂ ratios cluster around 3:1, with deviations consistent with binomial sampling error at his sample sizes ([Mendel 1866 Table I](https://www.biodiversitylibrary.org/item/124773)).

The white trait was not destroyed. It came back in F₂, *unchanged* (white-flowered F₂ plants are pure white, not pale violet), in a ratio of exactly 1-in-4. The number 1/4 demands a mechanism that produces 1/4.

Here is the model Mendel proposed — and here is where the language has to be precise. Every plant carries *two* hereditary factors for each character, one inherited from each parent. The factor for violet flower color (call it V) is *dominant* — when present, even on only one of the two factors, it determines the visible flower color. The factor for white flower color (call it v) is *recessive* — masked in the presence of V but still present and inheritable. A pure-breeding violet plant is **VV** — two copies of the dominant factor. A pure-breeding white plant is **vv** — two copies of the recessive factor.

When two plants reproduce, each contributes *one* of its two factors to each offspring — randomly, with equal probability, the two factors being chosen independently. (This is Mendel's first conceptual breakthrough: the factors *separate* at gamete formation, one per gamete. We now call this the **Law of Segregation**, and we now know that it is the cellular event of anaphase I in meiosis — Chapter 01, briefly recapped here: at anaphase I, the two homologous chromosomes of a bivalent move to opposite poles, so the two alleles at any locus on those homologs end up in different daughter cells; after meiosis II, each gamete carries exactly one allele.)

VV × vv → every F₁ plant gets one V from one parent and one v from the other. Every F₁ plant is **Vv** — *heterozygous*. Because V is dominant over v, every F₁ plant shows the violet phenotype, even though it carries a v allele that is not expressed.

Now F₁ plants self-pollinate: Vv × Vv. Each parent makes gametes in a 1:1 ratio of V to v (the V allele goes into half the gametes, the v allele into the other half — segregation again). When the gametes combine at random, the four equally likely combinations are:

- V (from one parent) × V (from the other) → VV: probability 1/2 × 1/2 = 1/4
- V × v → Vv: probability 1/2 × 1/2 = 1/4
- v × V → Vv: probability 1/2 × 1/2 = 1/4
- v × v → vv: probability 1/2 × 1/2 = 1/4

The genotype ratio in F₂ is therefore 1 VV : 2 Vv : 1 vv — the **1:2:1 ratio**. Because VV and Vv both show the violet phenotype (V is dominant), the phenotype ratio is (1 + 2) violet : 1 white = **3:1**.

The model produces the ratio that Mendel observed. The ratio that Mendel observed *forces* the model. There is no other way to get exactly 3:1 from two parents that look identical (both heterozygous Vv after the F₁ generation) — it requires that each parent contribute one of its two factors at random and that the contributions be independent. Random fertilization of 50:50 gamete pools is what generates the 1:4 recovery of the hidden recessive phenotype.

The Punnett square is the bookkeeping device that puts the four combinations into a 2 × 2 grid:

|       | V (egg) | v (egg) |
|-------|---------|---------|
| **V (pollen)** | VV (violet) | Vv (violet) |
| **v (pollen)** | Vv (violet) | vv (white) |

Reginald Punnett, an early twentieth-century British geneticist working with William Bateson, introduced this notation around 1907 as a teaching device ([Punnett RC. *Mendelism*. 1st ed. Cambridge: Bowes & Bowes; 1907](https://archive.org/details/mendelism00punn) [verify]). It is just a probability table: each row is one parent's gamete possibility (with equal probability for each row), each column is the other parent's gamete possibility (equal probability for each column), and each cell is the joint outcome (one of four equally likely zygotes). The 1:2:1 genotype ratio is the count of cells: one VV, two Vv (across the two off-diagonal cells), one vv. The 3:1 phenotype ratio is the count of cells under the dominance rule: three violet (VV, Vv, Vv), one white (vv).

This is the central observation of the chapter — and it is exactly the same observation Chapter 01 spent its second section motivating from the meiotic side. Mendel observed it from offspring counts; the chromosomal theory (1902–1903, thirty-six years later) explained *why* it had to be true. Both views are the same operation seen from different angles. The Punnett square is the marriage of the two.

---

## Mendel's three laws — what they say, what they assume

Mendel's 1866 paper does not state his observations as three numbered laws — that formulation is a later pedagogical tidying. But the three patterns the laws now encode are all in his paper, derived from his data and applied in his analysis. I'll state each one in plain English, in the language Mendel actually had (factors and characters), then translate into modern allele language, and connect it to the cellular mechanism we now know lies underneath. The Chapter 01 mechanism stands behind everything.

**Law 1 — Dominance.** *In a heterozygote — an individual carrying one of each of two contrasting hereditary factors — one factor's character dominates the other's; the recessive factor is masked but not destroyed, and reappears unchanged in subsequent generations.* Modern translation: in a heterozygous individual with one dominant allele and one recessive allele at a locus, the phenotype is determined by the dominant allele. The recessive allele's product is overridden, suppressed, or simply unmade — depending on the molecular mechanism — but the recessive allele itself remains in the genome and is transmitted to half of all gametes. Cellular basis: anaphase I segregation (Ch 01) does not destroy alleles. It distributes them. A v allele in a heterozygous Vv parent enters half the parent's gametes intact, exactly as a V allele does.

A clarification, because this is one of the most frequently mangled definitions in introductory biology. **Dominance is a relationship between two alleles, defined by the phenotype of the heterozygote.** It is *not* a statement about how common the allele is in the population. The recessive allele for cystic fibrosis is, in fact, present in roughly 1 in 25 white Americans of European descent — a population frequency of about 4% — which is far rarer than the dominant wild-type CFTR allele at 96% [verify against [CFTR population genetics, Kerem et al. 1989 *Science* 245:1073–1080](https://www.science.org/doi/10.1126/science.2570460) and current ACMG carrier-screening recommendations]. But there are also dominant disorders where the dominant disease-causing allele is rarer than the recessive wild-type allele — Huntington's disease, where the dominant HTT-CAG-repeat-expansion allele has a population frequency of roughly 1 in 20,000, while the wild-type HTT allele is overwhelmingly the common one. **Dominance describes the heterozygote phenotype, not the population frequency.** This will come back in Chapter 10 when we work through Hardy-Weinberg.

**Law 2 — Segregation.** *The two factors at any one character separate cleanly during gamete formation, so each gamete carries exactly one factor — and the two factors of a heterozygote enter the gamete pool in exactly equal proportions.* Modern translation: in a heterozygous individual (Aa), exactly half of all gametes carry the A allele and exactly half carry the a allele. The two alleles segregate independently in each meiosis, with no preferential transmission of one over the other. Cellular basis: this is anaphase I of meiosis (Ch 01 §3). The two homologous chromosomes of the bivalent move to opposite poles; the alleles riding those homologs end up in different daughter cells. Half the eggs (or sperm, or pollen) of a heterozygote carry A; half carry a.

The 50:50 ratio is exact in expectation, not exact in any single meiosis. Any one meiosis produces four gametes, of which two are A and two are a — *that* is exact, because each meiosis is one cell going through one round of segregation. The *expectation* of 50:50 across many gametes from many meioses is exact in the same sense: the average of many fair coin flips is 1/2. Individual offspring counts deviate by sampling fluctuation — which is why Mendel needed his thousands of plants.

**Law 3 — Independent Assortment.** *The pair of factors at one character assort independently of the pair at any other character — there is no correlation between which member of one pair a gamete inherits and which member of another pair it inherits.* Modern translation: in a doubly heterozygous individual (AaBb), the four possible gamete combinations (AB, Ab, aB, ab) appear in exactly equal proportions, 1/4 each. There is no statistical correlation between the A/a allele a gamete carries and the B/b allele it carries. Cellular basis (Ch 01 §4): the independent orientation of different bivalents at metaphase I. Each chromosome pair makes an independent coin-flip choice of orientation; the choices multiply because they are independent events; for two independently assorting heterozygous loci, the four metaphase-I configurations are equally likely, and the four gamete types appear in 1:1:1:1.

The third law has the most important asterisk in the chapter: **it only holds when the two genes are on different chromosomes (or far enough apart on the same chromosome that crossing over effectively randomizes their association).** Chapter 01 worked this out from the cellular side — two loci on the same chromosome are *linked*, their alleles travel together at higher than 50% rates, and the deviation from 1:1:1:1 gametes is the quantitative tool Sturtevant used to map genes in 1913. Mendel did not know this; he never observed linkage; he got lucky that his seven chosen pea traits all assort independently (peas have seven chromosome pairs and Mendel's seven traits are distributed in a way that, statistically across his sample sizes, behaves Mendelianly — even though we now know two of his traits are actually on chromosome 4 and would have shown weak linkage at much larger sample sizes; see [Reid & Ross 2011 *Genetics* 189:3–10](https://academic.oup.com/genetics/article/189/1/3/6068078)). The cell-level reason the third law is more conditional than the second is exactly what Ch 01 was for.

The three laws, summarized in one sentence each: **Dominance** describes how heterozygote phenotypes are determined; **Segregation** describes how alleles enter gametes (50:50); **Independent Assortment** describes how alleles at different loci combine in gametes (independently, when on different chromosomes). The cellular substrate for laws 2 and 3 is meiosis. The substrate for law 1 is whatever the molecular biology of the gene product turns out to be at the heterozygote — which we will not get to until Ch 05.

---

## The product rule, the sum rule, and why the Punnett square is just a table

Mendel's analysis of the dihybrid 9:3:3:1 ratio was the calculation that, more than any other, demonstrated the mathematical character of his framework. The arithmetic he wrote in 1866 is *probability arithmetic* — independent-event probability theory applied to gametes. The Punnett square is one way of representing this arithmetic. The product rule is a more efficient way. They are the same operation.

**The product rule** (for **independent events** — events whose outcomes do not influence each other): *the probability that event A and event B both occur is the product of their individual probabilities.* P(A and B) = P(A) × P(B), when A and B are independent.

In genetics, this rule is used constantly. The probability that a gamete carries the A allele at one locus *and* the B allele at another locus, when the two loci are on different chromosomes and assort independently, is P(A) × P(B) = 1/2 × 1/2 = 1/4. The probability that the offspring of an Aa × Aa cross is aa at the first locus *and* bb at a second locus (where both parents are also heterozygous) is P(aa) × P(bb) = 1/4 × 1/4 = 1/16. The product rule lets us compute multi-locus genotype probabilities without building giant Punnett squares.

**The sum rule** (for **mutually exclusive events** — events that cannot occur simultaneously): *the probability that event A or event B occurs is the sum of their individual probabilities.* P(A or B) = P(A) + P(B), when A and B are mutually exclusive.

In genetics, this rule is used when you want the probability of any of several genotype outcomes that produce the same phenotype. For example, in an Aa × Aa cross, P(dominant phenotype) = P(AA) + P(Aa) = 1/4 + 1/2 = 3/4. The two genotypes AA and Aa are mutually exclusive (an offspring cannot simultaneously be AA and Aa), so their probabilities add.

Combining the two rules gives you all of Mendelian probability arithmetic. The Punnett square is a *table representation* of the same combined operation: each cell is a product of two gamete probabilities, and grouping cells by phenotype is a sum. The Punnett square is a useful pedagogical device for two-locus crosses because the visual layout makes the arithmetic transparent. For three-locus crosses (8 × 8 = 64 cells) and higher, the table becomes unwieldy, and the product rule is much faster.

Watch this. Take a dihybrid cross between two doubly heterozygous parents: AaBb × AaBb, where A/a and B/b are on different chromosomes. Compute the F₂ phenotype ratio two ways — the Punnett square way and the product rule way — and verify they agree.

**Punnett square way.** Each parent makes four gamete types in equal proportion: AB, Ab, aB, ab at 1/4 each. The Punnett square is 4 × 4 = 16 cells, each cell representing one equally likely zygote genotype:

|        | AB (1/4) | Ab (1/4) | aB (1/4) | ab (1/4) |
|--------|----------|----------|----------|----------|
| **AB (1/4)** | AABB | AABb | AaBB | AaBb |
| **Ab (1/4)** | AABb | AAbb | AaBb | Aabb |
| **aB (1/4)** | AaBB | AaBb | aaBB | aaBb |
| **ab (1/4)** | AaBb | Aabb | aaBb | aabb |

Now group the 16 cells by phenotype (assuming complete dominance at both loci):

- *A_B_* (at least one A *and* at least one B → dominant phenotype at both loci): 9 cells — every cell with at least one A in its row or column label AND at least one B in its row or column label. Counting: AABB, AABb, AABb, AaBB, AaBb, AaBb, AaBB, AaBb, AaBb. That is 9 cells (or you can just check that 9 cells contain at least one A and at least one B). Probability 9/16.
- *A_bb* (dominant at A, recessive at B): 3 cells. Probability 3/16.
- *aaB_* (recessive at A, dominant at B): 3 cells. Probability 3/16.
- *aabb* (recessive at both): 1 cell. Probability 1/16.

Phenotype ratio: 9 : 3 : 3 : 1 — the **9:3:3:1 dihybrid ratio**. This is the count Mendel reported for his yellow-round × green-wrinkled cross (315 yellow round : 108 green round : 101 yellow wrinkled : 32 green wrinkled, ratio 9.84 : 3.38 : 3.16 : 1, which he rounded to 9:3:3:1 — [Mendel 1866 Table III](https://www.biodiversitylibrary.org/item/124773)).

**Product rule way.** Treat the two loci independently. At the A/a locus, the F₂ phenotype distribution from an Aa × Aa cross is the familiar 3:1 — P(dominant) = 3/4, P(recessive) = 1/4. At the B/b locus, the F₂ phenotype distribution from a Bb × Bb cross is also 3:1 — P(dominant) = 3/4, P(recessive) = 1/4. Because the two loci assort independently, the joint probabilities multiply:

- P(dominant at A *and* dominant at B) = P(A_) × P(B_) = 3/4 × 3/4 = **9/16**
- P(dominant at A *and* recessive at B) = P(A_) × P(bb) = 3/4 × 1/4 = **3/16**
- P(recessive at A *and* dominant at B) = P(aa) × P(B_) = 1/4 × 3/4 = **3/16**
- P(recessive at A *and* recessive at B) = P(aa) × P(bb) = 1/4 × 1/4 = **1/16**

The four phenotype-class probabilities: 9/16, 3/16, 3/16, 1/16 — exactly the same as the Punnett square. The ratio: 9:3:3:1.

The two methods give identical answers because they are the same calculation in different notation. The product rule is the algebra; the Punnett square is the tabular enumeration of all 4 × 4 = 16 outcomes.

The product rule's advantage shows up at three loci. A **trihybrid** cross — AaBbCc × AaBbCc, with all three genes on different chromosomes — has 2³ = 8 gamete types per parent (ABC, ABc, AbC, aBC, Abc, aBc, abC, abc), so the Punnett square is 8 × 8 = 64 cells. Building that table by hand is tedious and error-prone. The product rule cuts straight through:

- P(dominant at all three) = 3/4 × 3/4 × 3/4 = **27/64**
- P(dominant at two, recessive at one) = 3 × (3/4 × 3/4 × 1/4) = **9/64** for each of three such classes (recessive at C only, B only, A only), so collectively three classes at 9/64 each
- P(dominant at one, recessive at two) = 3 × (3/4 × 1/4 × 1/4) = **3/64** for each of three such classes
- P(recessive at all three) = 1/4 × 1/4 × 1/4 = **1/64**

The trihybrid F₂ phenotype ratio is **27 : 9 : 9 : 9 : 3 : 3 : 3 : 1**. Sum: 27 + 9 + 9 + 9 + 3 + 3 + 3 + 1 = 64 = 4³, which is the total number of cells in the 8 × 8 Punnett square.

Sanity check this against a Punnett-square count if you do not believe it: 27 cells out of 64 have at least one dominant allele at all three loci. That count is easy to verify because the probability of being recessive at a given locus is 1/4 (so the probability of being dominant at a locus is 3/4), and the loci are independent, so P(dominant everywhere) = (3/4)³ = 27/64. Same number, same arithmetic, less table-building.

The pattern generalizes. For *n* independently assorting heterozygous loci in an F₂ cross between two doubly-heterozygous parents (each parent makes 2ⁿ gamete types), the phenotype-class proportions are products of 3/4 and 1/4 according to which loci are dominant and which are recessive in the phenotype class. The dominant-at-all-loci class is (3/4)ⁿ; the recessive-at-all-loci class is (1/4)ⁿ; intermediate classes are products with the appropriate counts. The Punnett-square grid is 2ⁿ × 2ⁿ = 4ⁿ cells; the product-rule calculation has *n* multiplications. The product rule scales linearly; the Punnett square scales exponentially. For *n* ≥ 3, the product rule is the only practical method.

The lesson: **the Punnett square is the operation, written as a table. The product rule is the operation, written as arithmetic.** They give the same answers because they encode the same probability theory. Mendel's genius was recognizing that gamete probabilities multiply when their underlying gametogenic events are independent — a deep mathematical observation he extracted from offspring counts in 1865, two decades before anyone could see chromosomes.

---

## A worked example — yellow round × green wrinkled, both ways

Take a specific dihybrid pea cross and trace it through every level of the framework. This is the worked example Mendel actually reported, and the example that — paired with the monohybrid 3:1 ratios — was sufficient to establish his laws.

**The cross.** Pure-breeding yellow round (YYRR) × pure-breeding green wrinkled (yyrr). Yellow (Y) is dominant over green (y); round (R) is dominant over wrinkled (r). Y/y is on one chromosome (chromosome 1, in modern pea genetics); R/r is on a different chromosome (chromosome 7) [verify against [Reid & Ross 2011](https://academic.oup.com/genetics/article/189/1/3/6068078)]. Two loci, on two different chromosomes, both with a clean dominant-recessive relationship.

**Step 1: F₁.** YYRR × yyrr. Each parent makes only one type of gamete (because it is homozygous at both loci): YYRR makes YR gametes, yyrr makes yr gametes. F₁ is uniformly YyRr — heterozygous at both loci, with one Y, one y, one R, one r each. Phenotype: all F₁ are yellow round, because Y is dominant over y and R is dominant over r.

**Step 2: F₁ × F₁ → F₂.** YyRr × YyRr. Now each parent is doubly heterozygous and can produce 2² = 4 gamete types in equal proportion. The four gametes come from the four equally likely metaphase-I orientations of the two bivalents in meiosis (Ch 01 §4): the Y-bearing homolog can go left or right of the metaphase plate, independently of whether the R-bearing homolog goes left or right. Four configurations, four gamete types:

- YR (Y and R both go to the same gamete): 1/4
- Yr (Y goes with r): 1/4
- yR (y goes with R): 1/4
- yr (y goes with r): 1/4

**Step 3: Build the F₂ Punnett square.** A 4 × 4 grid, 16 cells:

|        | YR (1/4) | Yr (1/4) | yR (1/4) | yr (1/4) |
|--------|----------|----------|----------|----------|
| **YR (1/4)** | YYRR | YYRr | YyRR | YyRr |
| **Yr (1/4)** | YYRr | YYrr | YyRr | Yyrr |
| **yR (1/4)** | YyRR | YyRr | yyRR | yyRr |
| **yr (1/4)** | YyRr | Yyrr | yyRr | yyrr |

Group the 16 cells by phenotype (yellow if at least one Y, round if at least one R):

- *Yellow round* (Y_R_): YYRR, YYRr, YyRR, YyRr (cell 1,1), YYRr, YyRr (cell 2,1 and 2,3), YyRR, YyRr (cell 3,1 and 3,2), YyRr (cell 4,1). Carefully counting: 9 cells. P = 9/16.
- *Yellow wrinkled* (Y_rr): YYrr, Yyrr (cell 2,4), Yyrr (cell 4,2). 3 cells. P = 3/16.
- *Green round* (yyR_): yyRR, yyRr (cells 3,3 and 3,4), yyRr (cell 4,3). 3 cells. P = 3/16.
- *Green wrinkled* (yyrr): yyrr (cell 4,4). 1 cell. P = 1/16.

Total: 9 + 3 + 3 + 1 = 16. Ratio: 9:3:3:1.

**Step 4: Now do the same calculation via the product rule.** Treat Y/y and R/r as independent (because they are on different chromosomes — Mendel's Second Law applies). At the Y/y locus alone, the F₂ ratio from Yy × Yy is 3 yellow : 1 green, so P(yellow) = 3/4 and P(green) = 1/4. At the R/r locus alone, the F₂ ratio from Rr × Rr is 3 round : 1 wrinkled, so P(round) = 3/4 and P(wrinkled) = 1/4. Because the two loci are independent, multiply:

- P(yellow round) = P(yellow) × P(round) = 3/4 × 3/4 = **9/16**
- P(yellow wrinkled) = P(yellow) × P(wrinkled) = 3/4 × 1/4 = **3/16**
- P(green round) = P(green) × P(round) = 1/4 × 3/4 = **3/16**
- P(green wrinkled) = P(green) × P(wrinkled) = 1/4 × 1/4 = **1/16**

The four probabilities — 9/16, 3/16, 3/16, 1/16 — are exactly the same as the Punnett-square count. The ratio is 9:3:3:1.

**Step 5: Compare to Mendel's actual data.** Mendel reported counts of 315 yellow round, 101 yellow wrinkled, 108 green round, 32 green wrinkled, for a total of 556 F₂ plants. The observed ratio: 9.84 : 3.16 : 3.38 : 1, which rounds to 9:3:3:1 within the noise of a 556-plant sample. The chi-square test (developed below) confirms that this deviation from the expected ratio is well within sampling variation — Mendel's data are consistent with 9:3:3:1 at every reasonable significance level.

**The lesson.** Mendelian arithmetic *is* independent-probability arithmetic. The Punnett square is a tabular representation of the product rule. Computing complex multilocus ratios via the product rule scales much better than building giant Punnett squares — for *n* loci, the Punnett square needs 4ⁿ cells, while the product rule needs *n* multiplications. The 9:3:3:1 ratio for a dihybrid cross is (3/4)² and (1/4)² and the two mixed cases, written out — nothing more.

**The limit.** This works for two independent loci on different chromosomes. For *linked* loci on the same chromosome, the four gamete types are not in 1:1:1:1; they are in (1 − r)/2 : r/2 : r/2 : (1 − r)/2, where *r* is the recombination frequency (Ch 01 §5). The dihybrid F₂ ratio in the linked case is *not* 9:3:3:1 — it shifts toward an excess of parental phenotypes and a deficit of recombinants. The chromosomal theory says exactly when Mendel's Second Law applies and when it fails; Mendel got the law right at the population level for his seven traits because all seven happened to behave as if independent. The deeper machinery is in Chapter 01 and will return in Chapter 10 when we move to population-genetic statistics.

---

## The test cross — making the hidden visible

A direct application of Mendel's framework is the **test cross**: a cross between an organism whose genotype is unknown (but whose phenotype is dominant) and a homozygous recessive tester. The test cross was Mendel's diagnostic tool for distinguishing AA from Aa in a plant that showed the dominant phenotype, and it is the same logic that veterinary breeders, plant breeders, and clinical geneticists use today to disambiguate homozygous-dominant from heterozygous individuals.

The setup. Suppose you have a pea plant with round seeds — phenotype dominant — but you do not know whether it is RR (homozygous dominant) or Rr (heterozygous). You cannot tell from looking at the plant; both genotypes produce round seeds. You need an experiment that distinguishes them.

The test cross does this. Cross your unknown plant with a known *homozygous recessive* tester — in this case, a pure-breeding wrinkled-seeded plant (rr). Observe the offspring.

**Case 1: Unknown plant is RR (homozygous dominant).** The cross is RR × rr. RR makes only R gametes; rr makes only r gametes. Every offspring is Rr — heterozygous, dominant phenotype. All round seeds. Zero wrinkled offspring. The genotype is revealed by the *absence* of any recessive offspring.

**Case 2: Unknown plant is Rr (heterozygous).** The cross is Rr × rr. Rr makes half R gametes and half r gametes; rr makes only r gametes. The offspring are half Rr (dominant, round) and half rr (recessive, wrinkled). Phenotype ratio: 1:1 round to wrinkled. The genotype is revealed by the *presence* of recessive offspring at a 1:1 ratio.

The test cross is a *resolution* device: it forces the hidden allele in the heterozygote to express itself in the next generation by removing the masking dominant allele from the other parent. Anything that was concealed under dominance appears phenotypically in the offspring of the test cross.

This is the same logic at the heart of modern carrier-testing and genetic-counseling arithmetic — the test cross gives you a window into the genotype that the phenotype hides.

A subtlety worth pausing on: the test cross does not necessarily give you a clean answer with a small sample. If your unknown plant is Rr and you do a test cross with five rr partners, you might by sampling fluctuation get 5 round offspring and 0 wrinkled — and conclude (wrongly) that the unknown was RR. The probability of this outcome under the Rr-hypothesis is (1/2)⁵ = 1/32 ≈ 3% — small, but not negligible. To distinguish RR from Rr robustly via a test cross, you want enough offspring that the binomial sampling fluctuations cannot fake either result. For practical purposes, 20–50 offspring is usually enough; for a marginal case where you really need confidence, hundreds. This is the same problem of *sample size* that drove Mendel to count tens of thousands of seeds.

---

## A second worked example — cystic fibrosis recurrence risk

The most important modern application of Mendelian arithmetic is **clinical genetic counseling** for monogenic disorders. A couple comes to a counselor because they are concerned about the risk of an inherited disease in their children. The counselor uses Mendelian probability to compute recurrence risk per pregnancy. The arithmetic is exactly the arithmetic of a monohybrid cross.

**The clinical setup.** A woman in her early thirties is a known carrier of a cystic-fibrosis-causing mutation in the *CFTR* gene (Δ508F, the most common CF-causing variant in populations of European descent, accounting for about 70% of CF alleles in such populations [verify against [Kerem et al. 1989 *Science* 245:1073–1080](https://www.science.org/doi/10.1126/science.2570460)]). Her partner has been tested and is also a carrier of a CF-causing mutation (a different variant — but for the present calculation, both carry a recessive disease allele; the mathematics is the same for any autosomal-recessive disorder). Both parents are phenotypically normal (heterozygous carriers do not develop CF). They want to know the probability that any one of their pregnancies will result in a child with cystic fibrosis.

**The cross.** Cf+/Cf⁻ × Cf+/Cf⁻ — both parents heterozygous for a recessive disease allele. This is exactly the Aa × Aa monohybrid cross, with Cf⁺ playing the role of the dominant wild-type allele and Cf⁻ playing the role of the recessive disease allele. The Punnett square (or the product rule, same answer):

|         | Cf+ (1/2) | Cf− (1/2) |
|---------|----------|----------|
| **Cf+ (1/2)** | Cf+/Cf+ (unaffected) | Cf+/Cf− (carrier) |
| **Cf− (1/2)** | Cf+/Cf− (carrier) | Cf−/Cf− (affected, CF) |

Per pregnancy probabilities:

- P(Cf+/Cf+, unaffected non-carrier) = 1/4 = **25%**
- P(Cf+/Cf−, unaffected carrier) = 2/4 = **50%**
- P(Cf−/Cf−, affected with CF) = 1/4 = **25%**

These are the three numbers the counselor gives the couple per pregnancy. The 25% recurrence risk of an affected child is the same 1/4 that Mendel found for white-flowered F₂ peas in 1865. The 50% carrier probability — children who will not have the disease but can transmit it — is the 2/4 heterozygote slot of the Punnett square. The 25% unaffected non-carrier probability is the 1/4 homozygous-dominant slot.

This is *Mendelian arithmetic applied to clinical genetics*. The Punnett square is the same square. The ratios are the same ratios. Only the labels have changed.

A clarification, because students sometimes ask: if the per-pregnancy risk of an affected child is 25%, what is the risk that *two* of four children will be affected? This requires the binomial distribution — a separate piece of arithmetic that combines the per-pregnancy probability with the number of pregnancies.

The binomial probability mass function: for *n* independent pregnancies, each with probability *p* = 1/4 of producing an affected child, the probability of exactly *k* affected children is:

$$P(k \text{ affected of } n) = \binom{n}{k} p^k (1-p)^{n-k}$$

where $\binom{n}{k}$ is the binomial coefficient, *n* choose *k* — the number of ways to choose which *k* of the *n* pregnancies produced affected children. For *n* = 4, *k* = 2, *p* = 1/4:

$$P(2 \text{ of } 4) = \binom{4}{2} (1/4)^2 (3/4)^2 = 6 \times \frac{1}{16} \times \frac{9}{16} = \frac{54}{256} \approx 21.1\%$$

The probability of exactly two affected children in four pregnancies is roughly 21%. The probability of *zero* affected (all healthy) is $(3/4)^4 ≈ 31.6\%$; the probability of exactly one affected is $\binom{4}{1}(1/4)(3/4)^3 \approx 42.2\%$; exactly three is about 4.7%; all four is about 0.4%. The four probabilities should sum to 1: 31.6 + 42.2 + 21.1 + 4.7 + 0.4 = 100.0%. They do.

The binomial distribution is built directly on the product rule. Each pregnancy is independent (assuming no maternal carrier-status confounders, which is typically true for autosomal recessive disorders); the joint probability of any specific sequence of affected and unaffected pregnancies is a product of per-pregnancy probabilities; the number of sequences with exactly *k* affected children is the binomial coefficient. The arithmetic of "what is the chance that this couple's first three children are all healthy?" is $(3/4)^3 = 27/64 \approx 42\%$, and the chance that all five of their five planned children avoid CF is $(3/4)^5 \approx 24\%$. The same Mendelian arithmetic, scaled by the number of pregnancies.

This is the work a genetic counselor does in the consultation room. The Punnett square gives the per-pregnancy probability. The binomial distribution gives the probability over multiple pregnancies. Both are direct consequences of Mendel's Law of Segregation, applied through the product rule.

The catalog of Mendelian human disorders — disorders caused by mutation in a single gene, inherited in patterns predictable from one of the four classical Mendelian inheritance modes — runs to thousands of named conditions. The Online Mendelian Inheritance in Man (OMIM) database, maintained at Johns Hopkins, currently lists more than 7,000 phenotypes with known Mendelian basis ([McKusick-Nathans Institute of Genetic Medicine. *OMIM*. omim.org](https://www.omim.org) [verify count]). Some of the most common, by inheritance mode:

- **Autosomal dominant.** Huntington's disease (HTT CAG-repeat expansion; per-pregnancy 50% risk if one parent is affected); achondroplasia (FGFR3 G380R; the most common form of disproportionate short stature, also 50% transmission); Marfan syndrome (FBN1 mutations; connective tissue disorder with cardiovascular complications). Recurrence-risk arithmetic: cross an affected heterozygote (Aa) × unaffected homozygote (aa) → 1/2 of offspring are Aa (affected), 1/2 are aa (unaffected). This is also a 1:1 testcross-like outcome — same arithmetic as Mendel's monohybrid testcross.
- **Autosomal recessive.** Cystic fibrosis (CFTR mutations); sickle-cell disease (HBB-E6V); Tay-Sachs disease (HEXA mutations); phenylketonuria (PAH mutations); β-thalassemia (HBB mutations). Recurrence-risk arithmetic for a carrier-carrier cross: 1/4 affected, 2/4 carrier, 1/4 unaffected non-carrier — the monohybrid 1:2:1.
- **X-linked recessive.** Hemophilia A (F8) and B (F9); red-green color blindness (OPN1LW/OPN1MW); Duchenne muscular dystrophy (DMD). Recurrence-risk arithmetic: carrier mother × unaffected father → 1/2 of daughters are carriers, 1/2 are non-carriers; 1/2 of sons are affected, 1/2 are unaffected (worked out in Ch 01 §6).
- **X-linked dominant.** Rett syndrome (MECP2; mostly affects girls because most affected boys are not born alive); incontinentia pigmenti (IKBKG). Less common than X-linked recessive.

Every one of these is a Punnett square. The genotypes change, the alleles change, but the arithmetic is the same arithmetic Mendel published in 1866. This is the durability of the framework — it is mathematical, it is mechanical, it generalizes.

---

## Chi-square — measuring whether the deviation is too large to be chance

When you count offspring from a cross and compare them to a Mendelian prediction, the observed counts are almost never *exactly* the expected counts. Random sampling produces fluctuations: from an Aa × Aa cross with 100 offspring, you expect 75 dominant and 25 recessive, but you might observe 73:27, or 78:22, or 70:30. The question is whether any given deviation is within the noise expected from sampling variation, or whether it is large enough to suggest that the underlying model is wrong.

The **chi-square test** (χ², chi-squared) is the standard tool for this question. It measures the discrepancy between observed and expected counts, accounting for the fact that the variance of a count is proportional to its expected value. The formula:

$$\chi^2 = \sum_{i} \frac{(O_i - E_i)^2}{E_i}$$

where *O_i* is the observed count in category *i*, *E_i* is the expected count in category *i*, and the sum runs over all phenotype categories. For a monohybrid 3:1 cross, there are two categories (dominant and recessive); for a dihybrid 9:3:3:1 cross, four categories; and so on.

The chi-square value is then compared to a theoretical distribution (the chi-square distribution) with degrees of freedom equal to the number of categories minus 1 (because once you know all but one category count, the remaining is fixed by the total). The resulting *p-value* is the probability of observing a deviation as large as the measured one *if the null hypothesis (Mendelian expectation) is true*. Small *p* (conventionally *p* < 0.05) is taken as evidence that the deviation is unlikely to be due to chance, suggesting the model may be wrong; large *p* (*p* > 0.05) is taken as evidence that the deviation is within sampling variation, consistent with the model.

Let me work an example. Suppose you observe F₂ counts of 320 yellow round, 105 yellow wrinkled, 95 green round, 35 green wrinkled, from a YyRr × YyRr cross. Total: 320 + 105 + 95 + 35 = 555. Expected under 9:3:3:1: 9/16 × 555 = 312.2 yellow round; 3/16 × 555 = 104.1 yellow wrinkled; 3/16 × 555 = 104.1 green round; 1/16 × 555 = 34.7 green wrinkled.

Now compute χ²:

| Category | Observed (O) | Expected (E) | (O − E) | (O − E)² | (O − E)²/E |
|----------|-----|-----|---------|----------|-----------|
| Yellow round | 320 | 312.2 | 7.8 | 60.8 | 0.195 |
| Yellow wrinkled | 105 | 104.1 | 0.9 | 0.81 | 0.0078 |
| Green round | 95 | 104.1 | −9.1 | 82.8 | 0.795 |
| Green wrinkled | 35 | 34.7 | 0.3 | 0.09 | 0.0026 |

Sum: χ² = 0.195 + 0.0078 + 0.795 + 0.0026 ≈ **1.00**.

Degrees of freedom: 4 categories − 1 = 3.

Look up χ² = 1.00 with 3 degrees of freedom in a chi-square distribution table: the *p*-value is approximately 0.80. This means: if the underlying model (9:3:3:1) is correct, the probability of observing a χ² this large or larger from random sampling is about 80%. The deviation is well within the expected range of sampling fluctuation. The data are *fully consistent* with the 9:3:3:1 model.

In contrast, suppose you observed counts of 280 yellow round, 100 yellow wrinkled, 80 green round, 95 green wrinkled (total 555, same total, very different distribution). Expected values are the same as before. Now:

| Category | O | E | (O − E)²/E |
|----------|-----|-----|-----------|
| Yellow round | 280 | 312.2 | 3.32 |
| Yellow wrinkled | 100 | 104.1 | 0.16 |
| Green round | 80 | 104.1 | 5.58 |
| Green wrinkled | 95 | 34.7 | 104.7 |

Sum: χ² ≈ 113.8 with 3 degrees of freedom. The *p*-value is essentially 0 (vanishingly small). The data are *strongly inconsistent* with 9:3:3:1. Something else is going on — the "green wrinkled" class is dramatically overrepresented (95 observed vs. 34.7 expected), suggesting either linkage between the two genes, some kind of selection against the parental classes, an error in the cross setup, or a deviation from one of Mendel's other assumptions.

The chi-square test is the formal version of the intuition "is the deviation big enough to worry about?" It rewards designs with larger sample sizes (the χ² accumulates the squared deviations across all categories, so larger sample sizes produce sharper discrimination between consistent and inconsistent data), and it gives a quantitative answer that is reproducible across investigators.

The chi-square test has its own assumptions and failure modes — it requires expected counts of at least 5 per category to be approximately valid, and it tests a specific model against the data rather than comparing models against each other — but for evaluating Mendelian ratios in F₂ crosses, it is the standard tool.

---

## The Fisher controversy — was Mendel's data too good?

Now the unromantic part of the chapter, which I have been signaling since the opening section. **R. A. Fisher**, the British statistician and population geneticist (and one of the founders of the modern synthesis between Mendelism and evolutionary biology — Ch 10 will spend time with his population-genetics work), published an analysis in 1936 of Mendel's published F₂ data and reached an uncomfortable conclusion: the deviations from the predicted Mendelian ratios were *systematically smaller* than chance alone would produce ([Fisher RA. *Has Mendel's work been rediscovered?* Annals of Science. 1936;1:115–137](https://www.tandfonline.com/doi/abs/10.1080/00033793600200111)).

Fisher's analytical move. He took every cross Mendel reported in the 1866 paper, computed the chi-square statistic for each, and aggregated. Under the null hypothesis that Mendel's data are honestly drawn from a Mendelian distribution, the aggregate χ² should follow the chi-square distribution with the appropriate degrees of freedom. In particular, *p* should be roughly uniformly distributed on (0, 1) — small *p*'s as common as large *p*'s, just by chance. What Fisher found was that the *p*-values across Mendel's reported crosses were systematically large — clustering near 1 rather than spread uniformly. The combined probability that Mendel's data fit Mendelian expectations as well as they did, by chance alone, was about *p* ≈ 0.00004, or roughly 1 in 25,000 ([Fisher 1936](https://www.tandfonline.com/doi/abs/10.1080/00033793600200111) [verify exact number]).

In plain English: Mendel's data are *too good*. The ratios he reported are systematically closer to the theoretical 3:1 and 9:3:3:1 than random sampling from a truly Mendelian population would produce. With 20,000-plus plants counted, you would expect some crosses to show ratios noticeably off from prediction by chance; Mendel reported almost none.

What does this mean? Fisher's analysis is a *statistical observation*. It is not a claim that Mendel's biological inferences are wrong — the laws are correct; modern genetics confirms them in every conceivable independent test. It is also not a claim of fraud in the strong sense — Fisher himself wrote that he found "no evidence of deliberate falsification," only that "the data of most, if not all, of the experiments have been falsified so as to agree closely with Mendel's expectations." His proposed explanation: an *unconscious bias* in counting, perhaps by Mendel himself or by one or more of his unnamed assistants. When a plant is marginal — a seed not quite obviously round and not quite obviously wrinkled, a flower color not quite obviously violet — the classifier may have a tendency to put the marginal cases into the category that better fits the prediction. Over thousands of marginal cases, this systematic bias would produce data that look "too good."

The controversy that followed Fisher's paper has lasted ninety years and is still not fully resolved. Several lines of response have been developed:

1. **Edwards' defense.** A. W. F. Edwards (a Fisher protégé) re-analyzed the data and confirmed that the discrepancy is real and statistically substantial ([Edwards AWF. *R. A. Fisher's gratuitous defence of Mendel*. Annals of Science. 1986;43:295–303](https://www.tandfonline.com/doi/abs/10.1080/00033798600200251) [verify]). Edwards' interpretation was that some form of bias must be operating, but he was cautious about attributing it to Mendel himself rather than to his assistants.

2. **The selection hypothesis.** Various authors have proposed that Mendel may have *selected* which crosses to publish, omitting those that gave the most discordant results — a form of publication bias rather than data falsification. This is consistent with the "too good" pattern in the published data without requiring that any single experiment be deliberately altered.

3. **The seed-classification ambiguity.** The Reid & Ross modern mapping of Mendel's seven traits found that the seed-shape character (R/r), which Mendel classified visually, has substantial phenotypic ambiguity in heterozygotes — Rr seeds can sometimes appear slightly less round than RR seeds, but the line between "round" and "wrinkled" is not perfectly sharp ([Reid & Ross 2011 *Genetics* 189:3–10](https://academic.oup.com/genetics/article/189/1/3/6068078)). This means unconscious bias in classifying marginal seeds is genuinely plausible.

4. **The "no falsification" hypothesis.** Some authors argue that the chi-square aggregation is overly aggressive and that Mendel's data, considered cross by cross, are individually consistent with Mendelian expectations — only when aggregated does the "too good" pattern emerge, and that aggregation itself can be questioned.

The current consensus, to the extent there is one: Fisher's statistical observation is real, but its interpretation is uncertain. There is something unusual about how closely Mendel's published ratios match his theoretical predictions. Whether this reflects unconscious bias by Mendel or his assistants, publication selection, the inherent ambiguity of phenotypic classification, or some combination is not fully settled.

The broader point for the chapter: this is a flag on the data, not a debunking of the laws. Mendel's laws are correct in their content — confirmed by a century of subsequent work in dozens of model organisms and in humans. The arithmetic predictions of his framework (3:1, 9:3:3:1, monohybrid 1:2:1, recurrence-risk 1/4) match modern data without exception, when the underlying assumptions are met. Mendel's *experimental practice*, on the other hand, may have included a small amount of unconscious selection — a level of bias that does not invalidate the conclusions but does suggest that some of the published numbers should be read as "consistent with the predicted ratio" rather than "exactly the predicted ratio."

The Feynman move here is to *name the wrinkle*. Mendel was a great scientist working in 1865 with no formal statistical apparatus to evaluate his own data. He came to a correct conclusion. Whether his published ratios are 100% honestly drawn from raw counts or 99% honestly drawn with a 1% unconscious bias toward the expected pattern is a historical-statistical question that does not change the laws he discovered. Acknowledging the Fisher controversy is part of intellectual honesty about the discipline's history. It is also, in a small way, a reminder that experimentalists must guard against their own expectations — including their expectations of confirming a beautiful prediction.

---

## Common misconceptions

**"Dominant means more common in the population."** No. *Dominance* is a relationship between two alleles at a single locus, defined by the phenotype expressed in the heterozygote. The dominant allele's phenotype is the one that appears when both alleles are present. This says nothing about how frequent the dominant allele is in the general population. The recessive cystic fibrosis allele has a population carrier frequency of about 1 in 25 in white Americans of European descent, while the dominant wild-type CFTR allele is much more common — but dominance is not about frequency. Conversely, the dominant Huntington's disease allele is far rarer (~1 in 20,000) than the recessive wild-type allele. Dominance is about the heterozygote, full stop. Population frequencies are determined by mutation rates, selection, and history — and we will work through them in Chapter 10's Hardy-Weinberg analysis.

**"Mendel's First Law is the Law of Independent Assortment."** No. The First Law is the Law of Dominance (or, in some formulations, the Law of Segregation). The Second Law is the Law of Segregation (or, depending on which textbook, the Law of Independent Assortment). Numbering conventions actually vary across textbooks — the original 1866 paper does not number the laws — but the most widely used modern convention is: Law 1 = Dominance, Law 2 = Segregation, Law 3 = Independent Assortment. The actual operations are what matter; the numbering is bookkeeping. What is *not* up for debate: Independent Assortment is the law that holds only when the two genes are on different chromosomes (or far enough apart on the same chromosome). It is the most conditional of the three laws.

**"Mendelian inheritance explains all of human genetics."** No. Mendelian inheritance — defined as inheritance of single-gene, complete-dominance, autosomal or X-linked traits — covers a substantial fraction of clinically important rare diseases but a small fraction of overall human genetic variation. Most common diseases — heart disease, type 2 diabetes, schizophrenia, hypertension, height, intelligence as measured by any instrument — are **polygenic**: controlled by many genes (sometimes hundreds), each contributing a small effect, with substantial environmental contributions on top. Polygenic traits do not show 3:1 or 9:3:3:1 ratios; they show continuous distributions, usually approximately bell-shaped. The Mendelian framework is the *foundation* — every polygenic trait can be decomposed into individual loci, each behaving Mendelianly — but the aggregate phenotype distribution is not Mendelian. We will work through polygenic inheritance and quantitative genetics in Chapter 10 and again in Chapter 13.

**"The 3:1 ratio is exact."** No. The 3:1 ratio is the *expected proportion* across an infinite hypothetical sample. Any finite sample shows binomial sampling fluctuation around this expectation. With 100 F₂ offspring from a monohybrid cross, the count of recessive offspring follows Binomial(100, 0.25) — mean 25, standard deviation 4.3. So an observed count of 30 (5 more than expected) is easily within one standard deviation and entirely consistent with the model; an observed count of 50 (25 more than expected, ~6 standard deviations off) would be evidence that something is wrong. Whether a given deviation is "too large" is exactly the question the chi-square test answers. The "3:1" you write in a textbook is shorthand for "the expected proportion, around which observed values fluctuate by amounts governed by the binomial distribution at the relevant sample size." With small samples, fluctuations dominate.

**"Recessive alleles disappear from the population over time."** No. This is the misconception that Hardy and Weinberg refuted in 1908 (and Castle independently in 1903). In a population mating at random, with no selection, no mutation, no migration, and no genetic drift, the allele frequencies do not change generation to generation — they remain at whatever Hardy-Weinberg equilibrium the population was last at. Recessive alleles can persist indefinitely in a population, hidden in heterozygous carriers who never show the recessive phenotype. The CF carrier frequency of ~4% in populations of European descent has been roughly stable over historical time (with the caveat that medicine now keeps affected individuals alive longer and able to reproduce — Chapter 10 discusses how this changes things slowly). The full Hardy-Weinberg analysis is in Chapter 10. For now, the take-home: recessive alleles are *preserved* by their concealment in heterozygotes, not eliminated by it.

---

## Why Mendel succeeded and his predecessors did not

Three things distinguish Mendel's work from earlier hybridization research, and they all interact.

**First, he chose his materials carefully.** Joseph Kölreuter (working in the 1760s and 70s) and Charles Naudin (in the 1860s, just before Mendel) had done extensive cross-pollination studies in many plant species. Both had occasionally noticed patterns suggestive of dominance and segregation. Neither extracted laws because they did not consistently use binary traits with pure-breeding lines, and they worked with species (carnations, tobacco, *Mirabilis*) whose genetics were sometimes considerably more complicated than the pea's. Mendel's choice of *Pisum sativum* with seven cleanly Mendelian traits was a stroke of taxonomic luck combined with deliberate experimental design — he tested multiple species informally before committing to the pea, and chose it because the traits were binary, the lines could be made pure-breeding, and the plant was tractable. The garden was the apparatus.

**Second, he counted at a scale nobody else had.** Naudin's data sets ran in the hundreds; Kölreuter's in tens. Mendel ran his counts into the thousands and tens of thousands. The ratios that are sharp at *n* = 5,474 are statistical mush at *n* = 50. Mendel was a physicist by training, with a physicist's instinct to count repeated measurements until the noise dropped below the signal. Without that scale, the 3:1 and 9:3:3:1 ratios are invisible. With it, they are unmissable.

**Third, he was a mathematical experimentalist working in a biological field that had no mathematical tradition.** Most botanists of the 1860s did not think of inheritance as a mathematical phenomenon. The dominant theoretical framework was *blending inheritance* — a verbal, qualitative description of offspring as mixtures of parents. Mendel approached the same data with the assumption that nature was producing numerical regularities, and that careful counting would reveal them. The 3:1 ratio was, in his head, the kind of clean integer ratio one would expect from a discrete-particle theory of heredity — and the moment he saw it in his data, he had a hypothesis. The hypothesis explained the ratio; the ratio confirmed the hypothesis; the framework was self-consistent and fertile.

Together these three — material choice, sample size, mathematical instinct — produced a discovery that, with any one of them missing, would not have happened. Kölreuter had the material approach but not the scale or the math. Naudin had some of the math but not the binary traits or the scale. Mendel had all three, and the result was a complete theory of inheritance.

The lesson generalizes beyond Mendel. Many fields in science have data that contains the signal but has not yet been counted at the scale that reveals the pattern, or has not yet been classified in the framework that makes the pattern extractable. The move Mendel made — *count more, classify cleanly, expect numerical regularities* — is a move available in any field where the underlying process is producing statistical patterns. The pea was an unusual organism that happened to allow it. The intellectual style that exploited the pea was Mendel's.

A historical irony worth noting. Darwin's *On the Origin of Species* was published in 1859, six years before Mendel's talk. Darwin's theory of natural selection desperately needed a theory of inheritance — without one, the variation that selection acts on cannot be preserved across generations, and the whole framework collapses. Mendel's laws are exactly the missing piece. They explain how variation is preserved (recessive alleles hidden in heterozygotes, popping back up in F₂); how new variation can be combined and recombined (independent assortment); how a population maintains genetic diversity (Hardy-Weinberg, Chapter 10). The two pieces — selection and inheritance — fit together perfectly. They were published within six years of each other, in adjacent intellectual communities, in the same general region of Europe. And the two communities did not talk to each other. Darwin almost certainly never read Mendel's 1866 paper. Mendel read Darwin (and made handwritten notes in his copy of *Origin*, in fact — those notes survive at the Mendel Museum in Brno [verify]), but did not connect his pea-plant results to Darwin's evolutionary framework in a way that gained traction in either direction.

The modern synthesis — the unification of Mendelian inheritance with Darwinian natural selection — took until the 1920s and 30s to construct, work done by Fisher, Haldane, Wright, and others (Chapter 10). The pieces existed in 1866 but the framework that made them visible together did not. Sometimes the bottleneck is not data; it is the conceptual apparatus to recognize that two pieces of data belong to the same problem.

---

## Common misconceptions, revisited via the chapter examples

Three more, briefly, because they come up often enough to be worth naming.

**"Heterozygous Aa parents always produce ¼ aa offspring per pregnancy — not 1 in 4 children, but ¼ each time."** Correct in expectation. The per-pregnancy probability of an aa offspring is 1/4. Crucially, the per-pregnancy probabilities are *independent* — each pregnancy is a fresh draw from the same probability distribution. If you have already had one aa child, the probability of the next child being aa is *still 1/4*, not changed by what happened before. This is the gambler's-fallacy form of the misconception: "we've already had one affected child, so the next must be unaffected." False. Mendelian probability is memoryless. The four equally likely Punnett-square outcomes are sampled independently from each pregnancy.

**"A test cross with three offspring is enough to determine genotype."** Almost never. A test cross with three offspring, all of which are dominant, is consistent with both Rr and RR genotypes for the unknown parent. The probability of seeing three dominant offspring from a Rr × rr cross is (1/2)³ = 1/8 ≈ 12.5% — small, but not negligible. To be confident that the unknown parent is RR (no recessive offspring), you typically want at least 20 dominant offspring, which makes the probability of an Rr-mis-classification (1/2)²⁰ ≈ one in a million.

**"The Punnett square is the only way to compute Mendelian ratios."** It is the most pedagogically transparent way, especially for two-locus crosses where the visual 4 × 4 grid makes the combinatorics obvious. But for any cross involving three or more loci, the product rule is faster, less error-prone, and more general. The Punnett square scales as 4ⁿ for *n* heterozygous loci; the product rule scales as *n*. Real genetics-counseling software almost always uses the product rule (often elaborated to handle linkage and pedigree complications) rather than a Punnett-square calculation.

---

## Three sources of human gamete diversity, revisited from Mendel's side

Chapter 01 closed by counting the three multiplicative mechanisms that generate gamete diversity in human meiosis: independent assortment (2²³ ≈ 8.4 million distinct types per individual), crossing over (50–200 crossovers per meiosis, generating effectively infinite within-chromosome diversity), and random fertilization (compounding the diversity multiplicatively across the two parents). Mendel did not see these mechanisms. He inferred them, in their abstract form, from offspring counts.

What he extracted, from his F₂ ratios, was *precisely the 2² and 2³ counts that underlie the 2²³ count for humans*. The 9:3:3:1 ratio from a dihybrid cross is 2² = 4 gamete types from each parent, recombined randomly. The 27:9:9:9:3:3:3:1 ratio from a trihybrid cross is 2³ = 8 gamete types per parent. By induction, an *n*-hybrid cross between fully heterozygous parents produces 2ⁿ gamete types per parent, recombined randomly to produce 4ⁿ equally likely zygote combinations.

For humans with 23 chromosome pairs, treating each chromosome as a single Mendelian locus (which understates the diversity by ignoring crossing over within chromosomes), the per-individual gamete diversity is 2²³ = 8,388,608. Multiply across two parents: about 7 × 10¹³ possible zygotes per couple. Mendel did not compute this number — he never observed more than three traits at once in his published work — but the framework he established generates it directly. The 2ⁿ count for *n* independent loci is the same combinatorial multiplication, regardless of whether the loci are spread across two chromosomes (Mendel's dihybrid case) or twenty-three (the full human chromosomal complement).

This is the bridge to Chapter 01. Mendel established the *arithmetic* of independent gamete combinations from breeding data, without knowing what was producing those combinations physically. Sutton and Boveri (1902–1903) showed that the physical machinery was the independent metaphase-I orientation of bivalents. The 2ⁿ count is the count of distinct metaphase-I orientations, derived three different ways: from breeding ratios (Mendel), from cytological observation (Sutton), and from combinatorial arithmetic (Punnett, anyone with a multiplication table). All three derivations give the same number.

---

## Exercises

**Warm-up**

1. **The monohybrid Punnett square.** A pea plant heterozygous for seed color (Yy) self-pollinates. Yellow (Y) is dominant over green (y). (a) Build the Punnett square. (b) What is the genotype ratio in the F₁? (c) What is the phenotype ratio? (d) If the heterozygous parent produces 200 seeds, how many are expected to be green? *Tests: mechanical application of the Punnett square; distinguishing genotype from phenotype; converting ratios to expected counts.*

2. **Identifying the inheritance pattern.** For each of the following Mendelian disorders, state (a) the inheritance pattern (autosomal dominant, autosomal recessive, X-linked dominant, X-linked recessive), (b) the per-pregnancy recurrence risk for an affected child if both parents are unaffected carriers (or one parent is heterozygously affected for a dominant), and (c) one defining biochemical or molecular feature: (i) Huntington's disease; (ii) cystic fibrosis; (iii) hemophilia A; (iv) sickle-cell disease; (v) achondroplasia. *Tests: recognition of standard Mendelian inheritance modes and basic medical genetics.*

3. **The product rule, fast.** Two parents are both heterozygous at three independently assorting loci: AaBbCc × AaBbCc. (a) What fraction of F₂ will be homozygous recessive at all three loci (aabbcc)? (b) What fraction will show all three dominant phenotypes? (c) What fraction will be heterozygous at all three loci (AaBbCc)? *Tests: the product rule, the binomial expansion that underlies it, and the difference between a specific genotype and a phenotype class.*

**Application**

4. **The full trihybrid cross — Punnett vs. product rule.** Consider a trihybrid cross AaBbCc × AaBbCc, with all three genes on different chromosomes. (a) How many gamete types does each parent produce? (b) How many cells are in the full F₂ Punnett square? (c) Compute the phenotype-class probabilities using the product rule alone: all three dominant; dominant at A and B only; dominant at A and C only; dominant at B and C only; dominant at A only; dominant at B only; dominant at C only; recessive at all three. Verify that the eight probabilities sum to 1, and verify the 27:9:9:9:3:3:3:1 ratio. (d) Explain why you would not want to build the full Punnett square for a four-gene cross. *Tests: the product rule at scale, and the limits of the Punnett-square method.*

5. **Cystic fibrosis recurrence risk.** A couple are both carriers for cystic fibrosis (both genotypes Cf+/Cf−). (a) What is the per-pregnancy probability that they have an affected child? (b) What is the probability that all four of their planned children are unaffected? (c) What is the probability that exactly two of their four children are affected? (d) Suppose their first child has cystic fibrosis. What is the probability that their second child also has cystic fibrosis? Explain why (d) does *not* depend on (a)'s answer. *Tests: the binomial distribution, the memoryless property of Mendelian probability, and the difference between marginal and conditional probabilities.*

6. **Chi-square test on real-ish data.** A geneticist counts F₂ offspring from a dihybrid yellow round × green wrinkled cross and observes: 320 yellow round, 105 yellow wrinkled, 95 green round, 35 green wrinkled. Total: 555 plants. (a) Compute the expected counts under the 9:3:3:1 hypothesis. (b) Compute the chi-square statistic and the degrees of freedom. (c) Look up (or use a calculator/software for) the *p*-value, and interpret it: is the deviation from 9:3:3:1 statistically significant at *p* = 0.05? (d) What would change about your interpretation if the total sample size were 5,550 instead of 555 (counts proportionally scaled: 3200 yellow round, 1050 yellow wrinkled, 950 green round, 350 green wrinkled)? *Tests: the chi-square machinery, the sensitivity of chi-square to sample size, and the meaning of statistical significance in genetic crosses.*

**Synthesis**

7. **A pedigree problem.** A three-generation family pedigree shows the following pattern. Generation I: a couple (one affected great-grandfather, one unaffected great-grandmother) had three children. Generation II: their three children include one affected son (who married an unaffected woman), one unaffected daughter (who married an unaffected man), and one unaffected son (who married an unaffected woman). Generation III: the affected Gen-II son had three children, of whom two were affected (one male, one female); the unaffected Gen-II daughter had two children, both unaffected; the unaffected Gen-II son had four children, of whom one (a daughter) was affected. (a) What is the most likely inheritance pattern (autosomal dominant, autosomal recessive, X-linked dominant, X-linked recessive)? Justify by listing the diagnostic features visible in the pedigree. (b) For the family of the affected Gen-II son (married to an unaffected woman), what was the per-pregnancy recurrence risk to be affected? (c) For the family of the unaffected Gen-II daughter and her unaffected husband, what was the per-pregnancy recurrence risk that their child would be affected, given that one of them must have been an unrecognized carrier? *Tests: pedigree analysis and the conditional probabilities of Mendelian inheritance.*

8. **A real Mendel mystery.** Mendel's published data for the monohybrid seed-shape cross showed 5,474 round to 1,850 wrinkled F₂ seeds — a ratio of 2.96:1, remarkably close to the predicted 3:1. (a) Under the binomial sampling model, what is the standard deviation of the recessive count for a sample of 7,324 F₂ seeds expected to produce 1,831 recessives at a true 1/4 probability? (b) How many standard deviations away from the expected count is Mendel's observed value of 1,850? (c) Now compute the same for Mendel's flower-color cross (929 F₂ plants, 224 white observed, 232.25 expected at 1/4). How many standard deviations off is that? (d) Aggregating across all seven of Mendel's published monohybrid F₂ counts (provided in [Mendel 1866 Table I](https://www.biodiversitylibrary.org/item/124773)), the data are systematically closer to expectations than chance alone predicts. Compute the overall χ² and the corresponding *p*-value, and discuss what this says about the integrity of Mendel's data — naming the Fisher controversy explicitly. *Tests: binomial standard deviations, aggregated chi-square statistics, and the Fisher controversy from raw data rather than received summary.*

**Challenge**

9. **Reverse engineering the genotype from offspring counts.** Two pea plants of unknown genotype are crossed, both showing the dominant phenotype for two traits (yellow round seeds). Their offspring show: 207 yellow round, 70 yellow wrinkled, 71 green round, 23 green wrinkled. Total: 371. (a) What are the genotypes of the two parents? Justify. (b) Is this consistent with the dihybrid 9:3:3:1 ratio? Apply chi-square. (c) What additional cross would you do to confirm the genotypes? *Tests: reasoning from offspring counts to parental genotypes, and the diagnostic role of follow-up crosses.*

10. **Build the simulator.** Using the Brutalist file conventions from Chapter 00, write the four-move prompt (Show / Say / Constrain / Verify) for `02-mendelian-crosses.html`. The simulation should extend Chapter 00's Punnett-square simulator with new capabilities: (a) **Number of loci selector** (1–4 genes), with the simulation computing both Punnett-square and product-rule predictions and displaying them side by side; (b) **Parent genotype selector** for each locus (homozygous dominant, heterozygous, homozygous recessive); (c) **Trait expression toggle** for complete dominance vs. incomplete dominance vs. codominance (preview for Chapter 03); (d) **Sample-size slider** (10 to 100,000 offspring) with stochastic offspring generation and a real-time bar chart showing observed vs. expected ratios — the student should see how observed ratios converge to expected ratios as sample size grows; (e) **Chi-square calculator** that takes the observed vs. expected counts and outputs χ², degrees of freedom, and *p*-value; (f) **Recurrence-risk calculator** that takes the parental genotypes for a single locus and outputs per-pregnancy genotype and phenotype probabilities, plus binomial-distribution probabilities for "what fraction of *n* children will be affected." *Deliverable:* the four-move prompt, the file (built and run), and a screenshot of the panel showing a 4-locus cross with sample-size slider at *n* = 1000 and *n* = 100,000 and the observed-vs-expected convergence. *Tests: the chapter's full computational framework applied through the same simulation-building method introduced in Chapter 00.*

---

## What would change my mind

The Mendelian framework as presented in this chapter — three laws, derived from offspring ratios in pea plants, generalized to all sexually reproducing organisms — would fail as a complete account if, in a clean experimental system with full molecular characterization, monohybrid F₂ ratios for traits with simple dominant-recessive relationships and full pure-breeding parental lines consistently and reproducibly diverged from 3:1 by amounts that could not be explained by the standard extensions (incomplete dominance, codominance, multiple alleles, sex linkage, linkage, polygenic effects — all covered in Chapter 03 and beyond). The framework as currently understood, augmented by the chromosomal theory (Ch 01) and the molecular details of gene expression (Ch 05 forward), explains essentially every clean Mendelian cross in every species tested. If a cross showed a stable, reproducible, statistically robust deviation that could not be modeled by any combination of these standard mechanisms, I would have to amend the framework. To date this has not happened — every apparent exception has turned out to be one of the named extensions. Mendel's laws are the most thoroughly tested predictive framework in biology, and they have held for one hundred and sixty years.

## Still puzzling

I do not yet fully understand the historical-statistical question raised by Fisher's 1936 analysis: how confidently can we attribute the "too good" fit of Mendel's published data to unconscious classification bias, publication selection, or some other artifact, rather than to genuine data fabrication? Edwards' 1986 re-analysis confirmed the statistical anomaly is real, but the proposed mechanisms — unconscious bias on marginal seeds, selective publication of well-fitting crosses, a combination — are not directly testable from the 1866 paper alone. The historical record is incomplete (Mendel's monastery notebooks were burned after his death), the contemporary classification practices of nineteenth-century botanical experiments are not well documented at the level of detail needed, and the chi-square aggregation that produces the famously low *p* depends on assumptions about which crosses Mendel published and which he might not have. The conclusion I tentatively hold — that some unconscious bias in classifying ambiguous phenotypes is the most plausible explanation, that it does not invalidate the laws but does explain the suspicious closeness of the published numbers, and that publication selection is a plausible but unproven additional contributor — is the best reading I can construct, but I am not confident enough in the historical detail to defend it strongly against an alternative reconstruction. The laws are correct; the question of exactly how Mendel got there in practice is harder than I would like.

---

## LLM Exercise — Build your Mendelian-crosses simulator

This block is the one you actually do. The prompt below is ready to paste at Claude (or ChatGPT, or Gemini) once you have CLAUDE.md and DESIGN.md saved in the same folder from Chapter 00 and the meiosis simulator from Chapter 01.

### The simulation prompt

```
Show: Read CLAUDE.md and DESIGN.md from this project. Conform to
them. The genetics palette: dominant allele dark blue #1a5276;
heterozygous medium blue #2980b9; recessive light blue #85c1e9;
wild-type green #27ae60; mutant red #c0392b; dark mode background
#1a1a1a.

Say: Build 02-mendelian-crosses.html — an extended Punnett-square
simulator for 1- to 4-locus Mendelian crosses with both Punnett-
square and product-rule calculations side by side, plus a stochastic
sampling experiment, a chi-square calculator, and a recurrence-risk
panel.

Panel 1 — Cross setup and ratio computation.
- Number-of-loci selector: 1, 2, 3, or 4 (default 2).
- For each locus, two dropdowns: maternal genotype and paternal
  genotype, each with options homozygous dominant (AA), heterozygous
  (Aa), homozygous recessive (aa).
- A trait-expression toggle for each locus: complete dominance
  (default), incomplete dominance, codominance.
- Display: the cross written out (e.g., "AaBbCc × AaBbCc"); the
  expected genotype ratio computed via the product rule (e.g.,
  "1 AABBCC : 2 AABBCc : ... : 1 aabbcc"); the expected phenotype
  ratio (e.g., "27:9:9:9:3:3:3:1" for a trihybrid with complete
  dominance at each locus); the count of distinct gamete types per
  parent (2^n); the total cells in the corresponding Punnett square
  (4^n).
- For 1 and 2 locus crosses, also display the actual Punnett-square
  grid (2x2 or 4x4) with cells color-coded by genotype class. For
  3 and 4 locus crosses, suppress the grid (too large to be useful)
  and show only the product-rule ratios.

Panel 2 — Sampling experiment.
- Sample-size slider (10 to 100,000 offspring, log scale, default
  1000).
- A "Generate offspring" button that randomly samples N offspring
  from the cross according to the computed gamete-combination
  probabilities (independent draws from the gamete pool, exactly as
  in a real Mendelian cross).
- Display: a bar chart of phenotype counts (D3, bars colored by
  phenotype class per DESIGN.md); the observed ratio printed
  numerically next to each bar; the expected ratio printed for
  comparison; a "convergence-to-expectation" diagnostic showing the
  deviation in each phenotype class as a percentage of the expected
  count.
- A second toggle, "Run 10 replicate experiments at this N," that
  runs 10 independent samples and overlays the histograms — students
  see the spread of observed ratios at any given sample size.

Panel 3 — Chi-square calculator.
- Input: the observed counts from Panel 2 (or manually entered
  counts for analysis of textbook problems).
- Display: the chi-square statistic computed via Σ (O − E)² / E,
  the degrees of freedom (categories − 1), and the corresponding
  p-value (compute from chi-square distribution).
- A horizontal bar showing the p-value, with a vertical line at
  p = 0.05; the bar is colored green (consistent with model) if
  p > 0.05, red (inconsistent with model) if p < 0.05.

Panel 4 — Recurrence-risk calculator.
- Inputs: single locus; mother's genotype (dropdown); father's
  genotype (dropdown); disease model (autosomal recessive,
  autosomal dominant, X-linked recessive).
- Display: per-pregnancy probability of each genotype and phenotype
  outcome; binomial distribution of "fraction of N children
  affected" for N = 1, 2, 3, 4, 5, 10 (small table showing the
  probability of 0 through N affected at each N).
- A "Compare to specific Mendelian disorders" dropdown: cystic
  fibrosis (autosomal recessive, carrier frequency 1/25 in European
  ancestry), Tay-Sachs (autosomal recessive, carrier frequency
  1/30 in Ashkenazi Jewish ancestry), sickle-cell (autosomal
  recessive, carrier frequency varies by ancestry), Huntington's
  (autosomal dominant), hemophilia A (X-linked recessive). When
  selected, populate the recurrence-risk calculator with the
  appropriate parameters and walk through a typical genetic-
  counseling scenario.

Constrain: Four panels stacked vertically on desktop, single-column
on mobile. SVG canvas 720 x 400 per panel where applicable. Use D3
v7 from CDN, no other dependencies. Single self-contained HTML
file. Add at the top of the script:
// CLAIM: For n independently assorting heterozygous loci in an
// F2 cross between two doubly-heterozygous parents, the phenotype-
// class proportions are products of 3/4 and 1/4 according to which
// loci are dominant and recessive in the class. The Punnett-square
// method gives identical answers to the product-rule method but
// scales as 4^n cells while the product rule scales as n
// multiplications.

Verify: Print to the console on every parameter change, as PASS/FAIL
lines with measured values, expected values, and the case:
  (1) Monohybrid Aa × Aa: phenotype ratio = 3:1 (under complete
      dominance) or 1:2:1 (under incomplete dominance/codominance).
  (2) Dihybrid AaBb × AaBb: phenotype ratio = 9:3:3:1 (complete
      dominance both loci); Punnett-square and product-rule
      results must match exactly.
  (3) Trihybrid AaBbCc × AaBbCc: phenotype ratio = 27:9:9:9:3:3:3:1;
      product-rule method must produce the right 8-class
      distribution.
  (4) Sampling experiment at N = 100,000 for a dihybrid cross: the
      observed ratio for each phenotype class must be within ±1%
      of the expected; the chi-square test must give p > 0.05 with
      probability about 95% across replicate runs.
  (5) Recurrence-risk for cystic fibrosis carrier × carrier:
      probability of affected child per pregnancy = 0.25; binomial
      probability of 2 of 4 children affected = (6)(0.25)²(0.75)²
      ≈ 0.2109.
```

### Exploration tasks

Once the simulation runs:

1. **The sampling-size effect.** Set Panel 1 to a monohybrid Aa × Aa cross. Run the sampling experiment in Panel 2 at N = 20, then at N = 200, then at N = 2,000, then at N = 20,000. At each step, look at the observed vs. expected ratios and the chi-square *p*-value. At N = 20, you will frequently see chi-square *p*-values well below 0.05 — apparent "violations" of Mendel's First Law that are nothing but sampling fluctuation. At N = 20,000, the *p*-values will cluster near 1 — the data nearly always fit the model within sampling noise. This is the same effect that made Mendel's 28,000-plant sample size so important. The take-home: ratios are statistical regularities, and you cannot evaluate them on small samples.

2. **The trihybrid product rule.** Set Panel 1 to a trihybrid AaBbCc × AaBbCc cross. Verify by hand that the product rule gives 27/64 for the all-dominant phenotype class, 9/64 each for the three "dominant at two, recessive at one" classes, 3/64 each for the three "dominant at one, recessive at two" classes, and 1/64 for the all-recessive class. Verify that they sum to 64/64 = 1. Now imagine trying to do this with an 8 × 8 Punnett square — you would have to fill in 64 cells, group them by phenotype, and count. The product rule reduces this to four multiplications.

3. **A simulated cystic-fibrosis counseling session.** Set Panel 4 to "cystic fibrosis" with both parents as carriers. Note the per-pregnancy risks (1/4 affected, 1/2 carrier, 1/4 unaffected non-carrier). Look at the binomial table for "fraction of children affected at N = 4." You should see: P(0 affected) ≈ 0.316, P(1 affected) ≈ 0.422, P(2 affected) ≈ 0.211, P(3 affected) ≈ 0.047, P(4 affected) ≈ 0.004. This is the actual table a genetic counselor walks a couple through. The 31.6% probability of no affected children across four planned pregnancies is the optimistic case; the 47% probability of *at least one* affected child (1 minus 0.316) is the more clinically relevant number. The simulator computes the same numbers a counselor would, by direct application of the Mendelian arithmetic we developed in this chapter.

### Extension prompt

Once the basic Mendelian-crosses simulator works, the obvious extension is to add a pedigree-recognizer: a small interactive panel where the user draws a three-generation family pedigree (square = male, circle = female, filled = affected, half-filled = carrier), and the simulator outputs the most-likely Mendelian inheritance pattern (autosomal dominant, autosomal recessive, X-linked dominant, X-linked recessive) and the per-pregnancy recurrence risk. Paste this:

```
Extension: Add a fifth panel to 02-mendelian-crosses.html — a
pedigree-recognizer for three-generation family pedigrees.

The user draws the pedigree by clicking to add individuals (square
or circle), drawing lines to indicate mating and offspring
relationships, and clicking individuals to toggle affected/unaffected
status. The pedigree should support at least three generations and
families of up to ~20 individuals.

Once the pedigree is drawn, the simulator analyzes it and outputs:
- The most likely inheritance pattern. Use the standard diagnostic
  features: no father-to-son transmission of an affected trait
  (X-linked recessive); affected females in most pedigrees with
  every generation affected (autosomal dominant); affected children
  born to unaffected parents (autosomal recessive); etc.
- A goodness-of-fit score for each of the four standard patterns,
  showing which is most consistent with the observed pedigree.
- The per-pregnancy recurrence risk for the next child of the
  bottom-generation couple (assuming standard Mendelian
  inheritance), accounting for the inferred carrier status of
  unaffected parents based on their family history.
```

This extension is what makes the Mendelian framework *clinically usable* — the same arithmetic the chapter has developed, applied to a real family's pedigree, generates the recurrence-risk numbers that genetic counselors give patients.

A connection forward. The simulator you just built handles monohybrid, dihybrid, trihybrid, and quadrihybrid crosses, with chi-square testing, sampling experiments, and recurrence-risk calculations. Every cross it can do is a *Mendelian* cross — single genes, simple dominance, autosomal or X-linked inheritance, independent assortment. Chapter 03 takes the next step: what happens when the Mendelian assumptions break. Incomplete dominance (heterozygote phenotype is intermediate between the two homozygotes — pink snapdragons from red × white). Codominance (both alleles fully expressed simultaneously — AB blood type). Multiple alleles (more than two alleles in the population at one locus — the ABO blood group). Polygenic inheritance (many genes contribute to one continuous trait — human height, skin color). Epistasis (one gene's expression depends on another gene's genotype). Linkage (genes on the same chromosome, refusing to assort independently — the same exception that Sturtevant turned into a measurement tool in Chapter 01). Each of these is a *refinement* of the Mendelian framework, not a refutation. The arithmetic remains the same; the inputs change. Chapter 03 will work through each extension and show how to compute the modified offspring ratios.

---

**What would change my mind:** If a clean experimental study in any sexually reproducing organism showed monohybrid F₂ ratios for a clearly Mendelian-type trait (binary, pure-breeding parental lines, large sample size) that consistently and reproducibly deviated from 3:1 by amounts unexplainable by the standard Mendelian extensions (incomplete dominance, codominance, multiple alleles, sex linkage, polygenic effects), I would have to amend the framework. The published evidence to date is overwhelming that Mendel's laws hold for clean Mendelian traits, with all observed deviations explainable by the standard extensions. The laws are the most thoroughly tested predictive framework in biology.

**Still puzzling:** I do not yet fully understand the resolution of the Fisher controversy — whether Mendel's published F₂ ratios are statistically too close to expectation because of unconscious classification bias by Mendel or his assistants, publication selection of well-fitting experiments, or some combination, and how confident the historical-statistical reconstruction of "what happened in Mendel's garden" can be from the surviving 1866 paper alone. The laws themselves are not in doubt. The experimental practice that produced the published numbers — that is the open historical question.

---

**Tags:** Mendel's-laws, Punnett-square, product-rule, monohybrid-cross, dihybrid-cross
