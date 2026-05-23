# Chapter 03 — Extensions of Mendelian Genetics

**Suggested titles:**
- *Where Mendel Breaks, and How to Patch the Arithmetic*
- *Pink Snapdragons, Yellow Labradors, and the BRCA1 Sisters — Inheritance Past the Three Laws*
- *One Gene, Many Traits; Many Genes, One Trait; and the Word "Penetrance"*

---

**TL;DR.** Mendel's three laws produce clean 3:1 monohybrid and 9:3:3:1 dihybrid ratios *only* when six conditions all hold: complete dominance at every locus, exactly two alleles per gene in the population, exactly one gene per trait, no environmental modification of the phenotype, no interactions between the products of different genes, and autosomal loci on different chromosomes. Real biology breaks every one of these conditions, often several at once. This chapter catalogues the breakage modes — incomplete dominance, codominance, multiple alleles, polygenic inheritance, epistasis, pleiotropy, sex-influenced and sex-limited expression, reduced penetrance and variable expressivity, environmental modification, mitochondrial inheritance, and genomic imprinting — and shows for each one how the arithmetic shifts. The Mendelian skeleton (alleles, gametes, the product rule, the Punnett square) survives every extension; what changes is the rule that turns genotype into phenotype. The clinical anchor is the Bombay phenotype, a real recessive epistatic interaction that explains why a person with genotypically A or B blood can test as O — and why such a person cannot safely receive blood from an ordinary O donor. The conceptual anchor is the recognition that most human traits anyone actually cares about — height, blood pressure, cardiovascular risk, neuropsychiatric disease, cancer susceptibility — are polygenic, environment-sensitive, and only loosely Mendelian. The framework Chapter 02 built does not stop working. It stops being enough on its own.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **State** the six assumptions of strict Mendelian inheritance and **name**, for each assumption, at least one real-world example where it fails.
2. **Distinguish** incomplete dominance from codominance from complete dominance using F₁ phenotypes alone, and **predict** the F₂ genotype and phenotype ratios in each case.
3. **Predict** offspring blood-type probabilities for any two parental ABO genotypes using multiple alleles and codominance arithmetic — the calculation a clinical lab actually performs.
4. **Compute** modified Punnett-square ratios for a system with epistasis (e.g., 9:3:4, 9:7, 12:3:1, 9:3:3:1 → 9:3:4 for recessive epistasis), and **identify** which gene is epistatic to which from F₂ data.
5. **Trace** the Bombay phenotype end to end: cross HhI^A i × HhI^B i, build the 4 × 4 Punnett square, apply the epistasis rule (hh → O regardless of ABO genotype), compute the F₂ blood-type ratio, and **state** the clinical consequence for transfusion.
6. **Diagnose** polygenic inheritance from a phenotype distribution: how the discrete F₂ Mendelian classes (1:2:1 at one locus, 1:4:6:4:1 at two loci, ...) approach a normal distribution as the number of contributing loci grows.
7. **Apply** the concepts of penetrance (the fraction of genotype-carriers showing the phenotype) and expressivity (the severity variation among those who show it) to a pedigree, and **explain** why an autosomal-dominant disorder with reduced penetrance can appear to "skip" generations without violating Mendelian inheritance.
8. **Identify** pleiotropy from a clinical-genetic vignette (one mutation, many tissues affected) and **distinguish** it from polygenic inheritance, which is the opposite arrangement (many mutations, one trait).
9. **Recognize** mitochondrial inheritance from a pedigree (affected mothers transmit to all children; affected fathers transmit to none) and **explain** why this pattern is impossible to fit into the standard Mendelian framework.
10. **Recognize** genomic imprinting from a clinical vignette (same DNA region produces different syndromes depending on parent-of-origin), with Prader-Willi vs. Angelman syndrome as the canonical example.
11. **Diagnose** at least three common misconceptions about non-Mendelian inheritance (e.g., "incomplete dominance means weaker alleles"; "dominant means common"; "BRCA1 means you will get cancer") and **explain** why each is wrong from mechanism.
12. **Build** an extended-inheritance simulator (`03-extended-inheritance.html`) that handles each of the inheritance modes catalogued in this chapter, with side-by-side comparison of standard Mendelian ratios and the modified ratios under each extension.

**Prerequisites.** Chapter 01 (meiosis, segregation, independent assortment, sex chromosomes, linkage and crossover) and Chapter 02 (the three laws, Punnett squares, the product rule, the 3:1 and 9:3:3:1 ratios, pedigree analysis, recurrence-risk arithmetic). The vocabulary of allele, locus, genotype, phenotype, homozygous, heterozygous, dominant, recessive, autosomal, X-linked — all from Chapter 02. No new statistics is introduced; the binomial and product-rule machinery from Chapter 02 carries through. The clinical examples assume no prior medical-genetics background; every disorder named is defined on first use.

---

## Two sisters, one mutation, two different lives

Boston, 2018. A forty-two-year-old woman, mother of two, walks into a high-risk breast-and-ovarian clinic for genetic counseling. Her mother had ovarian cancer at fifty-one. Her maternal aunt had breast cancer at forty-six. She wants to know whether she should be tested for the *BRCA1* mutation that runs in her family. The counselor takes her history, draws her pedigree, walks her through the math, and orders the test. Two weeks later, the result comes back: she carries her mother's pathogenic *BRCA1* mutation. The lifetime risk of breast cancer in *BRCA1* mutation carriers, by age eighty, has been estimated at roughly 60% to 72% in large international cohort studies — varying by exact mutation, family history, and ascertainment ([Kuchenbaecker et al. 2017 *JAMA* 317:2402–2416](https://jamanetwork.com/journals/jama/fullarticle/2632503) [verify]). For ovarian cancer the lifetime risk is roughly 40% to 44% in the same cohort [verify]. She begins an enhanced screening program: annual MRI, biannual mammography, a discussion of risk-reducing surgery.

Her younger sister, age thirty-nine, comes in three months later. The counselor draws the same pedigree, reviews the same family history, orders the same test. Same result. The sister carries the identical *BRCA1* mutation, inherited from the same mother. By the simplest Mendelian reading — autosomal dominant — both sisters carry the dominant disease allele, and both should display the affected phenotype. The mother had ovarian cancer. The aunt had breast cancer. The grandmother (according to family history) died of "stomach trouble" in 1962, which might have been undiagnosed metastatic ovarian disease. The mutation is "dominant." Both sisters carry it.

Eight years pass.

The older sister, by then fifty, develops triple-negative breast cancer — the most aggressive *BRCA1*-associated subtype. She is treated with surgery, chemotherapy, and radiation. She survives.

The younger sister, by then forty-seven, has had nothing. No breast cancer. No ovarian cancer. Annual MRIs clean. She is the same age her mother was at diagnosis. She carries the same mutation. She has had no cancer.

This is not a violation of Mendelian inheritance. It is what Mendelian inheritance *actually looks like* when you stop assuming that "having the dominant disease allele" and "having the disease" are the same thing. The technical term for the gap between them is **penetrance** — the fraction of genotype-carriers who develop the phenotype. *BRCA1* mutations are highly penetrant by population-genetics standards. They are not 100% penetrant. The older sister is in the 60–72% who develop breast cancer by age eighty. The younger sister, at forty-seven, is still in the window where she could enter the affected category — but she might also remain in the unaffected 30–40%. The mutation does not cause cancer the way that having two recessive cystic-fibrosis alleles causes the disease. It loads the dice. The dice still roll.

The clinical implication is not subtle. The genetic counselor who tells the younger sister "your BRCA1 mutation means you will get breast cancer" is doing genetics wrong. So is the counselor who tells her "you might not, so don't worry." The honest counselor walks her through the actual penetrance numbers, the screening options, the risk-reducing surgeries, and lets her decide. The framework that supports that conversation is *not* the strict Mendelian framework of Chapter 02. It is the *extended* framework this chapter builds.

The same conversation — different mutation, different family, different details — happens hundreds of times a day in genetic-counseling clinics around the world. Marfan syndrome, where two siblings with the same *FBN1* mutation have wildly different severity (one with mild lens dislocation; one with a torn aortic root before age thirty). Familial hypercholesterolemia, where heterozygotes have moderately elevated LDL and homozygotes have catastrophic cholesterol levels in childhood. Phenylketonuria, where the same mutation produces severe intellectual disability on a normal diet and near-normal development on a restricted diet. Each of these is "Mendelian" in the sense that a single-gene mutation is the driver. None of them is Mendelian in the sense that the Mendelian framework alone predicts the phenotype.

Chapter 02 told you what Mendel saw. This chapter tells you what Mendel did not see — not because he was wrong, but because peas with binary traits in pure-breeding lines are about the cleanest possible system, and real biology is messier. We are going to walk through twelve extensions to the Mendelian framework. Each one preserves the underlying arithmetic — alleles segregate at meiosis, gametes combine at fertilization, the product rule still gives the gamete frequencies — but each one changes the rule that turns genotype into phenotype. By the end of the chapter, "having the allele" and "having the disease" will be different sentences, and you will know how to compute the gap.

---

## The six assumptions of strict Mendelian inheritance — and where each one fails

Before we start fixing the framework, let us be explicit about what we are fixing. Chapter 02's 3:1 and 9:3:3:1 ratios are not facts of nature. They are *consequences* of a model with six assumptions. List the assumptions cleanly, and you can read each extension in this chapter as a story about which assumption breaks.

**Assumption 1 — Complete dominance.** In a heterozygote, one allele's phenotype is fully expressed and the other's is fully masked. The heterozygote is *indistinguishable* from the homozygous dominant. Mendel's tall × dwarf F₁ peas were six feet tall, not three or four feet tall. → Broken by **incomplete dominance** (heterozygote shows intermediate phenotype) and **codominance** (both alleles fully expressed simultaneously).

**Assumption 2 — Two alleles per gene.** Every individual is one of three genotypes at each locus: AA, Aa, or aa. The Mendelian apparatus produces 1:2:1 genotype ratios. → Broken by **multiple alleles** (more than two alleles segregating in the population, e.g., the three alleles of the ABO blood-group gene; the >200 alleles per locus in the major-histocompatibility-complex HLA system).

**Assumption 3 — One gene per trait.** Each trait is determined by exactly one locus. Stem height in Mendel's peas is determined by one gene; flower color is determined by another gene; they segregate independently. → Broken by **polygenic inheritance** (many genes contribute additively to one trait — height in humans is influenced by hundreds of loci of small effect) and by **epistasis** (one gene's product modifies the expression of another gene's product, so a trait depends on the combined genotype at multiple loci).

**Assumption 4 — One trait per gene.** Each gene affects exactly one trait. The seed-shape gene affects whether seeds are round or wrinkled, full stop. → Broken by **pleiotropy** (one gene affects multiple traits — the sickle-cell hemoglobin allele changes red-cell shape, oxygen-carrying capacity, susceptibility to vaso-occlusive pain crises, organ damage from chronic hemolysis, *and* resistance to *Plasmodium falciparum* malaria, all from a single base substitution).

**Assumption 5 — No environmental modification.** The phenotype is a function of the genotype alone, deterministically. → Broken by **environmental modification** (PKU is severe on a normal-protein diet, near-silent on a phenylalanine-restricted diet; G6PD deficiency manifests only after oxidative challenge; temperature-sensitive coat-color alleles produce dark fur only on cool body extremities). → Broken also, in a softer way, by **incomplete penetrance and variable expressivity**, where the genotype-to-phenotype map is probabilistic rather than deterministic.

**Assumption 6 — Autosomal loci on different chromosomes.** Mendel's third law (independent assortment) requires the loci to be either on different chromosomes or far enough apart on one chromosome that crossing-over randomizes their association. → Broken by **linkage** (treated in Chapter 01, when genes are close on the same chromosome). → Broken by **sex-linked inheritance** (X-linked or Y-linked genes do not follow the same patterns as autosomal genes because males and females have different sex-chromosome dosages — Chapter 01 worked through this from the cytological side; here we add **sex-influenced** traits, where an autosomal gene's expression depends on sex hormones, and **sex-limited** traits, where an autosomal gene is expressed in only one sex). → Broken entirely by **mitochondrial inheritance** (the gene is not on a nuclear chromosome at all; it is on a small circular mitochondrial chromosome that is transmitted only from the mother). → Broken by **genomic imprinting** (the same DNA region produces different phenotypes depending on which parent it came from, because parent-of-origin-specific epigenetic marks silence one of the two alleles).

These are not refutations of Mendel. Every one of them, once specified, can be expressed in Mendelian arithmetic with a slightly modified rule. Mendel's apparatus — gametes carry alleles, gametes combine at random, the product rule gives the joint probabilities — is preserved everywhere. What changes is the *genotype-to-phenotype function*: the rule that, given a genotype like AaBb, tells you what the organism looks like. In strict Mendelian inheritance, the function is "look up dominance per locus and combine." In extended Mendelian inheritance, the function gets more interesting. The rest of the chapter is a tour through how it gets more interesting, and how to do the arithmetic in each case.

---

## Incomplete dominance — pink F₁ snapdragons and a 1:2:1 phenotype ratio

The year is 1900, and Carl Correns — one of the three botanists who rediscovered Mendel that spring — is running his own experiments on *Mirabilis jalapa*, the four-o'clock flower, in Tübingen. Cross a pure-breeding red-flowered plant (genotype R^R R^R) with a pure-breeding white-flowered plant (R^W R^W). The F₁ flowers are not red. They are not white. They are **pink** — uniformly, every F₁ plant, indistinguishably pink. Self-pollinate the F₁ and grow the F₂. The F₂ phenotype distribution is *1 red : 2 pink : 1 white* — a 1:2:1 ratio, not the Mendelian 3:1.

This is **incomplete dominance**: a pattern of inheritance in which the heterozygote shows an intermediate phenotype between the two homozygotes. (I'll define every new technical term at first use through this chapter; this is a hard rule of the workshop.) The 1:2:1 phenotype ratio is *exactly the genotype ratio* of an F₂ cross — because every distinct genotype produces a distinct phenotype, the two ratios collapse onto each other. The Mendelian 3:1 is what happens when the two heterozygous classes "look like" the homozygous dominant class and get counted together. Take away the dominance and the heterozygotes show up as their own class.

Here is the molecular content, the part that is easy to get wrong. **Incomplete dominance does not mean the alleles are weaker.** It does not mean the protein is half-broken. It means *the phenotype depends quantitatively on the amount of functional protein the cell is making.* A homozygous-red snapdragon (R^R R^R) makes a full dose of the enzyme that produces red pigment. A homozygous-white snapdragon (R^W R^W) makes none — the R^W allele encodes a non-functional version of the enzyme (or it has no functional copy at all, depending on the mutation). The heterozygote (R^R R^W) makes one functional copy and one non-functional copy, so it produces *half as much pigment*. With half the pigment, the flower is pink. The model is called **haploinsufficiency**: one functional allele is not sufficient to produce the full phenotype. The recessive allele is not weak. It is simply not contributing pigment, and there is nothing weak about contributing nothing. The arithmetic of pigment dosage is linear; the phenotype is the linear consequence.

The clinical anchor is **familial hypercholesterolemia** (FH), an autosomal-codominant or autosomal-incomplete-dominant disorder of the LDL-receptor gene *LDLR*. Heterozygotes (one functional *LDLR* allele, one non-functional) have LDL cholesterol levels typically in the range of 300–400 mg/dL — about twice the normal upper limit of ~130 mg/dL. They are at substantially elevated risk of premature coronary artery disease, with first myocardial infarction often in the fourth or fifth decade. Homozygotes (two non-functional *LDLR* alleles) have LDL levels above 500 mg/dL, with severe atherosclerosis present in childhood, xanthomas (cholesterol deposits in skin and tendons) visible by age five, and untreated MI in adolescence. The heterozygote is exactly intermediate between the homozygous-normal and the homozygous-affected phenotype, in the *biochemical* phenotype — the LDL number — and roughly intermediate in the *clinical* phenotype (cardiovascular risk). This is the cardiovascular medicine version of pink snapdragons. The mutation is the same mutation. The dosage is what differs ([Goldstein and Brown 1973 *PNAS* 70:2804–2808](https://www.pnas.org/doi/10.1073/pnas.70.10.2804); [Goldstein and Brown Nobel lecture 1985](https://www.nobelprize.org/prizes/medicine/1985/brown/lecture/)).

The Punnett square for an incomplete-dominance monohybrid F₂ cross looks the same as the standard one — what changes is the phenotype legend:

|       | R^R (egg) | R^W (egg) |
|-------|----------|----------|
| **R^R (pollen)** | R^R R^R (red) | R^R R^W (pink) |
| **R^W (pollen)** | R^R R^W (pink) | R^W R^W (white) |

Genotype ratio: 1 R^R R^R : 2 R^R R^W : 1 R^W R^W. Phenotype ratio under incomplete dominance: 1 red : 2 pink : 1 white. Phenotype ratio if you imposed complete dominance (R^R dominant over R^W): 3 red : 1 white. The same four cells; different phenotype-assignment rule. The arithmetic does not care which rule you use. The biology — the actual amount of pigment in the petal — does.

A quick consequence: **with incomplete dominance, the heterozygote can never breed true.** Cross two pink snapdragons (R^R R^W × R^R R^W) and you get a 1:2:1 ratio in F₂ — 1/4 red, 1/2 pink, 1/4 white. To establish a pure-breeding pink line, you would have to maintain a heterozygous population indefinitely, which is impossible by ordinary breeding. This is sometimes used as a marker of incomplete dominance in plant or animal breeding: if a phenotype refuses to breed true no matter how many generations you select, you may be looking at incomplete dominance rather than a simple recessive trait.

---

## Codominance — the ABO blood-group system, the AB heterozygote, and Karl Landsteiner

**Codominance** is incomplete dominance's loud cousin: a pattern in which *both alleles are fully expressed simultaneously* in the heterozygote, producing a phenotype that contains the products of both alleles rather than a blended intermediate. The textbook example is the human ABO blood-group system, worked out by the Austrian physician **Karl Landsteiner** at the University of Vienna in 1900, the same year as the rediscovery of Mendel. Landsteiner won the 1930 Nobel Prize in Physiology or Medicine for this work ([Landsteiner K. *Zur Kenntnis der antifermentativen, lytischen und agglutinierenden Wirkungen des Blutserums und der Lymphe*. Zentralblatt für Bakteriologie. 1900;27:357–362](https://www.nobelprize.org/prizes/medicine/1930/landsteiner/lecture/) [verify]).

Here is the biology. Human red blood cells carry surface carbohydrate antigens that determine the ABO blood type. The relevant gene, **ABO**, sits on chromosome 9 and encodes a glycosyltransferase enzyme — an enzyme that adds a specific sugar to a precursor molecule (called the H antigen — we'll come back to this in the worked example below). There are three common alleles of this gene in the human population:

- **I^A** — encodes a transferase that adds *N-acetylgalactosamine* to the H antigen, producing the **A antigen** on red cells.
- **I^B** — encodes a transferase that adds *galactose* to the H antigen, producing the **B antigen** on red cells.
- **i** — encodes a non-functional enzyme; the H antigen is left unmodified, so no A or B antigen is produced.

There are six possible genotypes from these three alleles, producing four phenotypes (blood types):

| Genotype | Phenotype | Red-cell antigens |
|----------|-----------|-------------------|
| I^A I^A | Type A | A only |
| I^A i  | Type A | A only |
| I^B I^B | Type B | B only |
| I^B i  | Type B | B only |
| I^A I^B | Type AB | Both A and B |
| i i    | Type O | Neither (just H) |

The key fact: in the I^A I^B heterozygote, *both* transferase enzymes are made, *both* sugars get added to the H antigen on different red-cell surface molecules, and the cell expresses *both* A and B antigens simultaneously. The two alleles do not produce a blended phenotype — they produce a combined phenotype. The heterozygote is *not* like the codominant snapdragon (intermediate); it is like a flower with both red and white petals next to each other on the same plant. Both alleles are fully expressed. That is codominance.

The clinical importance is transfusion compatibility. Every person makes antibodies against the ABO antigens *they themselves do not have*. (Type A individuals make anti-B antibodies; type B individuals make anti-A; type AB individuals make neither; type O individuals make both.) Transfuse type A blood into a type B recipient, and the recipient's anti-A antibodies bind to the donor red cells, the cells agglutinate (clump) and lyse, and the recipient enters acute hemolytic transfusion reaction — fever, kidney failure, possible death. The whole framework of safe transfusion practice is built on knowing the donor's and the recipient's ABO type, and the arithmetic of which gametes can produce which genotypes is what genetic counselors and forensic-paternity laboratories use every day.

**Worked example — predicting offspring blood type.** A type A mother (assume genotype I^A i — the safer assumption clinically, since you cannot tell I^A I^A from I^A i without further testing) and a type B father (genotype I^B i). What are the offspring genotype and phenotype probabilities? Build the Punnett square:

|       | I^A (egg) | i (egg) |
|-------|----------|----------|
| **I^B (pollen)** | I^A I^B (AB) | I^B i (B) |
| **i (pollen)** | I^A i (A) | i i (O) |

The four cells, each with probability 1/4. The phenotype ratio in offspring is *1 type A : 1 type B : 1 type AB : 1 type O*. All four ABO blood types appear in equal proportions in the children of this couple. This is the classic example used to explain blood-typing in paternity disputes: a type-O child rules out an I^A I^A or I^B I^B parent; a type-AB child rules out both parents being I^A I^A or both being I^B I^B or either being i i. Blood typing alone cannot *prove* paternity, but it can *rule out* a candidate father whose ABO type is incompatible with the child's, and historically (before DNA testing) this was the standard exclusion test.

A note on terminology that confuses students. **Codominance is not the same as incomplete dominance.** Incomplete dominance produces a *blended intermediate* phenotype (pink, halfway between red and white) — the products of the two alleles mix in dosage. Codominance produces a *both-at-once* phenotype (AB blood: both A and B antigens on the same cell) — the products of the two alleles coexist without mixing. The distinction is biochemical: in incomplete dominance, the products are quantitatively combined (less pigment → pink); in codominance, the products are qualitatively distinct and both present (both surface sugars). The F₂ ratio in both cases is 1:2:1, because in both cases the heterozygote phenotype is distinct from both homozygote phenotypes. The ratio alone cannot distinguish incomplete dominance from codominance; you have to look at *what the heterozygote phenotype actually is.*

---

## Multiple alleles — more than two alleles in the population

The ABO system also illustrates **multiple alleles**: when more than two alleles for one gene exist in the population. Any one individual still has only two alleles (one inherited from each parent — Mendel's law of segregation is intact), but the *population* contains three or more allele types from which an individual's two are drawn. ABO has three (I^A, I^B, i). Other gene systems have far more. The most polymorphic gene system in humans is the **HLA (human leukocyte antigen)** complex on chromosome 6 — the set of genes encoding the major histocompatibility complex proteins that present antigens to T cells. The HLA-B locus alone has been documented with more than 4,000 distinct alleles in human populations [verify against [IPD-IMGT/HLA Database current count](https://www.ebi.ac.uk/ipd/imgt/hla/)]. Two unrelated individuals are very unlikely to be HLA-matched at all six classical loci — which is why bone-marrow transplantation requires extensive donor searches and why graft-versus-host disease is a chronic challenge in transplant medicine.

The Mendelian arithmetic with multiple alleles is the same as with two alleles — the product rule still works gamete-by-gamete — but the number of possible genotypes grows quickly. For *n* alleles at a single locus, the number of possible genotypes is *n(n+1)/2*: *n* homozygotes plus the C(n,2) = n(n−1)/2 heterozygous combinations. For three alleles (ABO): 3(4)/2 = 6 genotypes, as listed above. For four alleles: 10 genotypes. For ten alleles: 55 genotypes. For 4,000 alleles (HLA-B): about 8 million genotypes — though of course only the common alleles dominate in any one population, and most theoretical genotypes never occur because they would combine rare alleles whose joint frequency is essentially zero.

The dominance relationships between the multiple alleles can be complicated. In ABO, I^A and I^B are codominant with respect to each other, but both are *fully dominant* over i. This means we have to track *both* the pairwise dominance hierarchy *and* the genotype. The convention is to write a **dominance series**: for ABO, I^A = I^B > i, meaning I^A and I^B are equal (codominant) and both dominate i. For a system like rabbit coat color, where there are four alleles (C, c^ch, c^h, c) producing different coat patterns (full color, chinchilla, Himalayan, albino), the dominance series is C > c^ch > c^h > c — a strict hierarchy in which each allele dominates the one to its right. The arithmetic of the cross still uses the Punnett square; the phenotype assignment uses the dominance series.

The clinical lesson: when you see a system with more than two alleles, *do not assume strict dominance.* The dominance pattern has to be established empirically for each pair of alleles. The Mendelian apparatus assumes nothing about how many alleles there are or how they interact; it only assumes that segregation, independent assortment, and random fertilization hold. Add as many alleles as the population provides; the apparatus keeps working.

---

## Worked example — the Bombay phenotype, end to end

Now we are going to slow down and trace one example carefully, because it ties together everything in the chapter so far (codominance, multiple alleles) with the next concept (epistasis) and demonstrates how clinical genetics actually uses this machinery.

The setup. Recall that the I^A and I^B transferase enzymes act on a precursor sugar molecule on the red-cell surface called the **H antigen**. The H antigen is itself produced by the action of another enzyme, **fucosyltransferase 1 (FUT1)**, encoded by a separate gene at a different locus — the **H gene** on chromosome 19. The H gene has two alleles in most populations: the functional **H** allele and the rare non-functional **h** allele. Homozygous *hh* individuals produce no functional FUT1 enzyme, *make no H antigen*, and consequently have no substrate for the I^A or I^B transferases to act on. Their red cells display no A antigen, no B antigen, and no H antigen — even if they have a genotype like I^A i or I^B i at the ABO locus that would normally produce blood type A or B.

This is the **Bombay phenotype** (named for its first description in three families in Bombay, India by [Bhende, Deshpande, Bhatia et al. 1952 *Lancet* 259:903–904](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736%2852%2991475-0/fulltext) [verify]). On standard blood-typing reagents, a Bombay individual tests as type O — no agglutination with anti-A serum, no agglutination with anti-B serum. They look like ordinary type-O blood. But they are not. They produce a *fourth* antibody that ordinary type-O individuals do not: **anti-H**, the antibody against the H antigen that ordinary O cells display. A Bombay individual transfused with ordinary type-O blood from a non-Bombay donor will react against the H antigen on the donor's red cells. Acute hemolytic transfusion reaction. The clinical consequence: a Bombay individual can be safely transfused only with blood from another Bombay individual — a population of perhaps one in 10,000 in India and far rarer worldwide. Bombay donor registries exist precisely for this purpose.

This is **recessive epistasis**: a pattern of inheritance in which a homozygous recessive genotype at *one* locus (here, the H locus, *hh*) *masks* the expression of the alleles at *another* locus (the ABO locus). The H gene is **epistatic** to the ABO gene; the ABO gene is **hypostatic** to the H gene. (The Greek roots: *epistasis* means "stoppage" or "standing upon"; the epistatic gene "stands upon" and overrides the hypostatic gene.) The molecular reason for the epistasis is clean: the H-gene product is required for the substrate that the ABO-gene products act on. No substrate, no product, no phenotype — regardless of ABO genotype.

Now we work the arithmetic end-to-end. Consider a cross between two doubly heterozygous parents, each of whom appears as ordinary blood type (because each carries at least one functional H allele, masking the recessive h):

**Parents:** Hh I^A i × Hh I^B i

The mother is genotypically heterozygous at both loci. At the H locus, she is heterozygous H/h — phenotypically she produces H antigen (functional H allele present) and tests as her ABO type. At the ABO locus, she is I^A i — phenotypically she is type A. Same logic for the father: heterozygous at H, type B at ABO.

Each parent produces four gamete types in equal proportion (under independent assortment — note that H is on chromosome 19 and ABO is on chromosome 9, so this assumption holds):

- Mother's gametes: HI^A (1/4), Hi (1/4), hI^A (1/4), hi (1/4)
- Father's gametes: HI^B (1/4), Hi (1/4), hI^B (1/4), hi (1/4)

Building the 4 × 4 Punnett square gives 16 equally likely zygote genotypes. Rather than enumerate all 16, let us use the product rule to compute the distribution by phenotype class.

Step 1 — compute the *standard* dihybrid F₂ ratios at each locus separately, treating dominance as a black box:

- H locus, Hh × Hh: 1 HH : 2 Hh : 1 hh, with 3/4 having at least one H (and producing H antigen) and 1/4 being hh (no H antigen).
- ABO locus, I^A i × I^B i: phenotypes are 1/4 I^A I^B (type AB), 1/4 I^A i (type A), 1/4 I^B i (type B), 1/4 i i (type O).

Step 2 — apply the epistasis rule: hh masks all ABO phenotypes, producing the Bombay phenotype (which serologically looks like type O on standard testing). Combine the per-locus distributions multiplicatively (independent loci, independent assortment):

- P(H_ AND type AB) = 3/4 × 1/4 = 3/16 → type AB
- P(H_ AND type A) = 3/4 × 1/4 = 3/16 → type A
- P(H_ AND type B) = 3/4 × 1/4 = 3/16 → type B
- P(H_ AND type O) = 3/4 × 1/4 = 3/16 → type O (ordinary O — has H antigen, just no A or B added)
- P(hh AND any ABO) = 1/4 × 1 = 4/16 → Bombay phenotype (tests as O, but anti-H positive)

Step 3 — read off the F₂ phenotype distribution by what a blood-typing lab would report:

- **Type AB:** 3/16
- **Type A:** 3/16
- **Type B:** 3/16
- **Apparent type O (true O + Bombay):** 3/16 (true O) + 4/16 (Bombay) = **7/16**

The ratio is 3 : 3 : 3 : 7. *Not* the standard 9:3:3:1 dihybrid ratio. The 9 collapses to 3 (because only 3/16 of the offspring with at least one H allele are AB), the 3:3 stays at 3:3 (because the H_ states with single A or single B remain unmasked), and the 1 of pure i i recessive gets folded into the *4* of Bombay-or-O, totaling 7/16. Reading the phenotype distribution in the order AB : A : B : "type O" gives **3 : 3 : 3 : 7**. (Some textbooks write it as 9:3:3:1 → 9:3:3:4, which is mathematically equivalent: in the standard 9:3:3:1, both the "1" (ii at the second locus) and the "4 in the 9" that are hh get reassigned to the apparent-O class. Either notation is fine; the underlying arithmetic is the same.)

Step 4 — the lesson. The epistatic interaction *modifies the phenotype ratio* without violating Mendelian gametogenesis. Both loci segregate normally. Both loci assort independently. The product rule still gives the gamete frequencies. What changes is *the rule that turns a genotype into a phenotype.* In strict Mendelian inheritance, you read each locus separately and combine. In epistatic inheritance, you read the combination of loci jointly because one locus's state determines whether another locus's state is even visible.

Step 5 — the limit of the model. Real epistasis can be more complex than the all-or-nothing recessive epistasis of the Bombay phenotype. Many quantitative traits show *quantitative* epistasis, where one gene partly modifies another rather than entirely masking it. Multiple modifier genes can act simultaneously, producing complex interaction patterns that no simple ratio captures. Statistical genetics, when working with these traits, fits models with explicit interaction terms (G × G interactions in genome-wide association studies, treated in Chapter 10) rather than discrete Mendelian-style ratios. The Bombay phenotype is unusually clean because its molecular biology is unusually clean: a precursor-product chemistry where the upstream enzyme is strictly necessary. Most epistasis in real populations is messier than this.

The clinical follow-up — the practical reason this matters. A Bombay-phenotype patient walks into a trauma bay with a hemoglobin of 6 g/dL after a car accident. The blood bank types her cells as O. The transfusion order is for O-negative blood. The transfusion begins. The patient develops fever, back pain, hemoglobinuria, hypotension. Acute hemolytic transfusion reaction. The post-transfusion workup reveals an anti-H antibody. The patient's blood is sent for confirmatory testing — Ulex europaeus lectin reagent fails to bind her cells, confirming Bombay phenotype. The remaining transfusion is canceled; the blood bank initiates a search for Bombay-compatible blood, which may need to be flown in from a regional Bombay donor registry. This is the price of the epistasis you computed above: a single allele state at the H locus (hh) can override the ABO genotype entirely, and ordinary serological screening will not see it. The lab knows to look for Bombay only when the clinical signs of an unexplained transfusion reaction prompt the extra test.

---

## Other epistasis patterns — yellow Labradors and the 9:3:4 ratio

The Bombay phenotype is recessive epistasis. There are several other classic epistasis patterns that show up regularly in undergraduate genetics, distinguished by *which* genotype combinations produce *which* phenotypes. The clearest non-clinical example is coat color in Labrador retrievers, and it is worth working through because (a) it generalizes the epistasis arithmetic and (b) every dog-owning student in your class has the genetics in their living room.

Two loci control Labrador coat color (this is a simplification — there are several more modifier loci in real-world canine genetics, but two suffices for the lesson):

- **B locus** (*TYRP1*, tyrosinase-related protein 1, chromosome 11): determines whether the eumelanin pigment is black or brown. B = black (dominant); b = brown (recessive). BB and Bb produce black pigment; bb produces brown pigment.
- **E locus** (*MC1R*, melanocortin-1 receptor, chromosome 5): determines whether eumelanin is deposited in the coat at all, or whether phaeomelanin (yellow pigment) is deposited instead. E = pigment deposited (dominant); e = no pigment deposited, yellow coat results (recessive).

The combined phenotypes:

| Genotype | Phenotype |
|----------|-----------|
| B_E_ (BBEE, BBEe, BbEE, BbEe) | Black |
| bbE_ (bbEE, bbEe) | Chocolate (brown) |
| B_ee (BBee, Bbee) | Yellow |
| bbee | Yellow |

Notice the key fact: when the dog is homozygous *ee* at the E locus (MC1R is non-functional, no eumelanin deposited), the coat is yellow *regardless of the B-locus genotype*. The E locus is **epistatic** to the B locus in this case. A genotypically chocolate dog (bb) that is also homozygous ee will look yellow, not chocolate. The chocolate genotype is hidden — it is in the dog's DNA, but the dog will look like a yellow Labrador, and only by breeding tests (or DNA testing) can you tell the difference.

The F₂ ratio. Cross two doubly heterozygous parents (BbEe × BbEe) — equivalent to a Mendelian dihybrid cross at the gametogenesis level:

- 9/16 B_E_ → black
- 3/16 bbE_ → chocolate
- 3/16 B_ee → yellow
- 1/16 bbee → yellow

Group by phenotype: 9 black : 3 chocolate : (3 + 1) yellow = **9 : 3 : 4**.

This is **recessive epistasis at one locus** (the homozygous ee genotype at E masks the B locus), producing the classic 9 : 3 : 4 ratio that is the diagnostic signature of recessive epistasis in dihybrid F₂ crosses. The 9:3:3:1 you would get under no epistasis collapses by combining the 3 (genotype B_ee) and the 1 (bbee) into a single yellow class.

Other epistasis patterns produce other modified ratios from 9:3:3:1:

| Pattern | Mechanism | Modified F₂ ratio |
|---------|-----------|-------------------|
| No epistasis | Standard Mendelian | 9 : 3 : 3 : 1 |
| Recessive epistasis | Homozygous recessive at one locus masks both phenotypes at the other (yellow Lab; Bombay) | 9 : 3 : 4 |
| Dominant epistasis | A dominant allele at one locus produces one phenotype regardless of the other locus's genotype (squash color: yellow W_ is dominant epistatic to green/yellow at the G locus) | 12 : 3 : 1 |
| Duplicate recessive epistasis | Homozygous recessive at either locus produces the same recessive phenotype (the two loci act redundantly) | 9 : 7 |
| Duplicate dominant epistasis | A dominant allele at either locus is sufficient for the dominant phenotype | 15 : 1 |
| Dominant suppression | A dominant allele at one locus suppresses the dominant phenotype at the other | 13 : 3 |

All of these are derived by taking the standard 9:3:3:1 dihybrid F₂ ratios and applying a *phenotype-assignment rule* that combines or reassigns specific genotype classes. The Punnett square is unchanged. The arithmetic is unchanged. The genotype-to-phenotype function is what changes. This is the operational pattern of every extension in this chapter.

---

## Polygenic inheritance — when many genes contribute to one trait

The previous sections kept the number of genes per trait small (one or two). Most quantitative traits in real populations are not like that. **Polygenic inheritance** is the pattern in which *many* genes (often hundreds or thousands) each contribute a small additive effect to one continuously varying trait. Human height. Skin color. Blood pressure. Body mass index. Most psychiatric disease risk. These traits do not show 1:2:1 or 9:3:3:1 ratios because they are not produced by one or two loci; they are produced by a sum of small contributions across many loci, plus environmental modification.

The arithmetic of how a continuous distribution emerges from many small Mendelian contributions was first worked out by **Herman Nilsson-Ehle** at Lund, Sweden, in 1908, in his experiments on wheat kernel color ([Nilsson-Ehle H. *Kreuzungsuntersuchungen an Hafer und Weizen*. Lunds Universitets Årsskrift 5; 1909](https://archive.org/details/kreuzungsuntersuc00nils) [verify]). Nilsson-Ehle crossed dark-red wheat with white wheat. The F₁ was uniformly medium-red. The F₂ showed a *range* of colors — not just three classes, but five or seven, depending on the parental lines, with the extreme colors (dark red and white) rare and the intermediate colors common. The pattern fit a model in which two or three genes contributed additively to kernel color, with each "red" allele adding a fixed amount of pigment.

Here is the model worked out for two genes contributing additively, each with two alleles where one adds one "unit" of pigment and the other adds zero. Each parent is doubly heterozygous (AaBb), and we treat the alleles as additive contributors with no dominance:

- AABB (4 red alleles): darkest red — frequency 1/16
- AABb or AaBB (3 red alleles): dark-medium red — frequency 4/16 = 1/4
- AAbb or AaBb or aaBB (2 red alleles): medium red — frequency 6/16 = 3/8
- Aabb or aaBb (1 red allele): light red — frequency 4/16 = 1/4
- aabb (0 red alleles): white — frequency 1/16

The F₂ distribution is 1 : 4 : 6 : 4 : 1 — five phenotype classes in *binomial distribution* proportions. This is the binomial coefficient expansion of (1+1)⁴ = 16, distributed as C(4,0), C(4,1), C(4,2), C(4,3), C(4,4). The pattern generalizes: for *n* additive loci with two alleles each, the F₂ phenotype distribution is the binomial expansion of (1+1)^{2n} = 4^n, with 2n+1 phenotype classes following binomial coefficients C(2n, 0), C(2n, 1), ..., C(2n, 2n).

The key consequence: **as the number of contributing loci grows, the F₂ phenotype distribution converges to a normal (Gaussian) bell curve.** The number of phenotype classes grows (2n + 1), the distance between adjacent classes shrinks (since the total trait range stays bounded but is divided into more steps), and the binomial coefficients converge to the Gaussian shape predicted by the **central limit theorem**: the sum of many independent random variables, each with bounded variance, approaches a normal distribution as the number of variables grows. This is why height, blood pressure, and other quantitative traits show smooth bell curves in human populations rather than discrete Mendelian classes — they are sums of many small genetic contributions, each itself a Mendelian outcome.

Genome-wide association studies (GWAS) have systematically mapped the loci contributing to polygenic human traits over the past two decades. Height — perhaps the most-studied human polygenic trait — has been associated with more than 12,000 distinct genetic variants in studies of more than 5 million individuals, with the variants together explaining roughly 40–50% of the variance in height in European-ancestry populations ([Yengo et al. 2022 *Nature* 610:704–712](https://www.nature.com/articles/s41586-022-05275-y) [verify]). Each variant has a tiny individual effect — the largest typically less than a centimeter, most less than a millimeter — but their cumulative effect across thousands of variants produces the substantial heritability we observe. The variants that have been identified do not yet explain all of the heritability — the rest is sometimes called *missing heritability*, attributed to rare variants, gene-gene interactions, and gene-environment interactions. This is an active area of research, and the explanatory fraction continues to grow with larger samples and better methods.

The clinical translation. Polygenic risk scores (PRS) are computed by summing the effects of many trait-associated variants, weighted by the effect size each variant has been shown to confer in GWAS. For coronary artery disease, type 2 diabetes, breast cancer, and other complex diseases, polygenic risk scores are increasingly used in research and beginning to enter clinical practice — predicting an individual's risk based on the cumulative effect of many small-effect alleles. The arithmetic is the same Mendelian arithmetic, applied to many loci simultaneously, with each locus contributing a small additive effect. The Mendelian framework does not break; it gets used at scale.

---

## Pleiotropy — when one gene affects many traits

**Pleiotropy** is the mirror image of polygenic inheritance: *one gene affecting many traits*. The textbook example is **sickle cell disease**, caused by a single nucleotide substitution in the *HBB* gene encoding the β-globin subunit of hemoglobin. The mutation (Glu6Val in the β-globin amino acid sequence) was identified by [Linus Pauling and colleagues in 1949](https://www.science.org/doi/10.1126/science.110.2865.543) as the first "molecular disease" — a disease caused by a specific change in protein structure. The β-globin substitution alters hemoglobin S (HbS) so that in low-oxygen conditions, hemoglobin S polymerizes into long fibers that distort red cells into the characteristic sickle shape. The single base change produces:

- **Red-cell sickling** in low-oxygen tissues
- **Hemolytic anemia** (sickled cells are fragile and short-lived; baseline hemoglobin ~7–8 g/dL vs. normal ~14)
- **Painful vaso-occlusive crises** (sickled cells block small vessels, causing tissue ischemia)
- **Organ damage** (chronic vaso-occlusion damages spleen, kidneys, lungs, brain over decades)
- **Increased infection risk** (functional asplenia from repeated infarction)
- **Resistance to *Plasmodium falciparum* malaria** in heterozygotes — the reason the allele is common in populations historically exposed to malaria; the selective advantage of HbAS heterozygotes was demonstrated by [Anthony Allison in 1954 *BMJ* 1:290–294](https://www.bmj.com/content/1/4857/290) [verify]

One mutation. Many traits. The traits are not independent extensions of the genetic apparatus — they all flow from one upstream molecular change, with downstream consequences spreading across many tissues and physiological systems. This is **pleiotropy**: the genotype-phenotype map is one-to-many, with one allele variant producing many phenotypic effects.

Another canonical example is **Marfan syndrome**, an autosomal-dominant connective-tissue disorder caused by mutations in the *FBN1* gene encoding fibrillin-1, a structural protein in elastic tissues. *FBN1* was identified by [Dietz et al. 1991 *Nature* 352:337–339](https://www.nature.com/articles/352337a0) as the causative gene. One mutation in *FBN1* causes:

- **Tall stature** with disproportionately long limbs
- **Arachnodactyly** (long, slender fingers)
- **Pectus deformity** (chest-wall abnormalities)
- **Scoliosis**
- **Lens dislocation** (ectopia lentis)
- **Aortic root dilation and dissection** — the major cause of premature death in Marfan patients
- **Mitral valve prolapse**
- **Pneumothorax risk**

The mechanism: fibrillin-1 is a structural protein found in elastic tissues throughout the body — in the aortic wall, in the suspensory ligament of the lens, in the periosteum of long bones, in the heart valves, in the lung. A mutation in *FBN1* affects every tissue that uses fibrillin-1. Many phenotypes from one gene because *fibrillin-1 is everywhere*.

The distinction from polygenic inheritance is sharp. Polygenic: many genes → one trait. Pleiotropic: one gene → many traits. Both are common in real biology; they are orthogonal phenomena (a trait can be both polygenic *and* affected by pleiotropic genes; a gene can be both pleiotropic and one of many contributors to a polygenic trait). The Mendelian framework handles pleiotropy without modification: a pleiotropic allele segregates exactly like any other allele, and the offspring's genotype determines the offspring's *suite* of phenotypes rather than a single phenotype. The Punnett square is unchanged.

---

## Penetrance and expressivity — why "having the allele" and "having the disease" are different sentences

We are now back where the chapter opened — the two sisters, same *BRCA1* mutation, different lives. The technical machinery is two distinct but related concepts.

**Penetrance** is the fraction of individuals carrying a particular genotype who actually display the corresponding phenotype. Complete penetrance is 100% (every carrier shows the phenotype). Reduced penetrance is anything less than 100%. *BRCA1* breast-cancer penetrance is roughly 60–72% by age 80 in current best estimates [verify], meaning that ~28–40% of *BRCA1* mutation carriers will not develop breast cancer in their lifetime. Penetrance is a *population-level* property: it describes the probability, averaged across many carriers, that the phenotype appears.

**Expressivity** is the *severity* or *form* of the phenotype among those who do display it. Variable expressivity means that two individuals with the same genotype can have very different clinical presentations — one with mild disease, one with severe disease — even if both are "affected." Marfan syndrome is the classic example of variable expressivity: some affected individuals have mild lens dislocation and modest aortic root dilation; others have catastrophic aortic dissection in their twenties. The mutation is the same. The trait's *expression* varies.

The relationship: penetrance is *whether* the phenotype appears; expressivity is *how severely* it appears when it does. A disorder can have high penetrance with variable expressivity (Marfan: almost every *FBN1* mutation carrier has some clinical features, but the severity spans a wide range). It can have reduced penetrance with relatively stereotyped expressivity (some autosomal-dominant epilepsies: many carriers never have seizures, but those who do tend to have similar seizure types). It can have both (the *BRCA1* situation: not every carrier develops cancer, and among those who do, the age at onset, tumor subtype, and prognosis vary).

The clinical pedigree consequence is important. An autosomal-dominant disorder with *reduced penetrance* will often *appear to skip generations*. The grandfather has the disease, the father is a carrier but unaffected (the penetrance gap), the son has the disease. The pedigree shows the trait in generations I and III but not in generation II — which naively looks like autosomal recessive inheritance (homozygous recessive in I and III, heterozygous carrier in II). The diagnostic feature that distinguishes reduced-penetrance autosomal dominant from autosomal recessive is the *number* of affected individuals in each generation and the inheritance from affected to offspring. In autosomal recessive, two carrier parents have a 1/4 risk per pregnancy of an affected child. In autosomal dominant with reduced penetrance, an affected parent has a (penetrance × 1/2) probability per pregnancy of having a clinically affected child, plus a (1 - penetrance) × 1/2 probability of an "unaffected" carrier child. The numbers depend on the specific penetrance. For a 70%-penetrant autosomal-dominant condition, an affected parent has a 35% chance per pregnancy of a clinically affected child and a 15% chance of an unaffected carrier child.

The arithmetic in the genetic-counseling office: the counselor estimates the penetrance from the literature, applies the autosomal-dominant 1/2 transmission rate, multiplies, and gives the patient the resulting per-pregnancy risk along with the unaffected-carrier risk. This is the same Mendelian apparatus we built in Chapter 02, with one extra parameter (the penetrance) inserted into the genotype-to-phenotype rule. The Punnett square is unchanged.

A common misconception worth naming explicitly. "I have the BRCA1 mutation, so I'm going to get cancer." No. The penetrance is 60–72% by age 80. About one in three or four mutation carriers will not develop breast cancer. The mutation is a *risk factor*, not a deterministic cause. The arithmetic of genetic counseling distinguishes between these by reporting probabilities, not certainties. (The opposite misconception is also dangerous: "the penetrance is only 70%, so I don't really need to worry." A 70% lifetime risk of an aggressive cancer is *enormous*. Population baseline lifetime risk of breast cancer for women in the U.S. is about 13%. A *BRCA1* mutation roughly five times the risk. That is more than enough to justify intensive screening and to consider risk-reducing surgery.)

---

## Environmental modification — PKU, G6PD, and the genotype-times-environment phenotype

The fifth Mendelian assumption — no environmental modification — fails in a particularly clinically important way for some disorders. The genotype alone does not determine the phenotype; the phenotype is the product of genotype *and* environmental exposure.

**Phenylketonuria (PKU)** is the textbook case. PKU is an autosomal-recessive disorder of the *PAH* gene, which encodes phenylalanine hydroxylase, the liver enzyme that converts the amino acid phenylalanine into tyrosine. Without functional PAH, phenylalanine accumulates in the blood; the elevated phenylalanine is toxic to the developing brain; on a normal-protein diet, untreated PKU produces severe intellectual disability, microcephaly, seizures, and behavioral abnormalities. PKU was first described by [Asbjørn Følling in Norway in 1934](https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1748-1716.1934.tb00787.x) [verify]; the molecular basis was worked out over the following decades.

But — and this is the central point — *PKU is preventable*. An infant identified by newborn screening (the first universal newborn screening program in the U.S., introduced in the 1960s) can be placed on a phenylalanine-restricted diet from infancy. With dietary management, blood phenylalanine stays in a controlled range, the brain develops normally, and the affected individual has near-normal intellectual function. The same genotype (homozygous-recessive *PAH* mutations), with different environmental exposure (normal-protein diet vs. restricted diet), produces radically different phenotypes (severe intellectual disability vs. normal cognition). The mathematics of inheritance — autosomal recessive, 1/4 affected offspring of two carrier parents — is intact. The clinical phenotype depends on what the parents do with the diagnosis.

**G6PD deficiency** (glucose-6-phosphate dehydrogenase deficiency) is another example. G6PD is an X-linked enzyme involved in red-cell antioxidant defense. Mutation carriers — about 400 million people worldwide, concentrated in populations historically exposed to malaria — have reduced G6PD activity in their red cells. *In the absence of oxidative challenge, they are usually asymptomatic.* On exposure to certain triggers — fava beans (the historical name "favism" comes from this), sulfa antibiotics, the antimalarial primaquine, certain other drugs — affected individuals develop acute hemolytic anemia: red cells lyse, hemoglobin spills into the urine, the patient becomes jaundiced and anemic, occasionally severely enough to require transfusion. The phenotype is *contingent on environment*: same genotype, different exposures, dramatically different outcomes. Public-health guidance for G6PD-deficient patients is precisely a list of triggers to avoid; with avoidance, most patients live unremarkable lives.

The conceptual lesson is that **phenotype = genotype × environment**, in a multiplication sign rather than an addition sign — meaning that the *interaction* between the two is sometimes essential. Some genotypes have one phenotype across all environments; some environments produce one phenotype across all genotypes; but in many cases, the phenotype is jointly determined, and only the combination matters. This is the **norm of reaction**: a curve plotting an individual's phenotype across a range of environmental conditions. Different genotypes have different norms of reaction; some are flat (genotype dominates), some are steep (environment dominates), some cross (the genotype with higher phenotype in one environment has lower phenotype in another). The strict Mendelian framework, with its deterministic genotype-to-phenotype map, cannot capture this. The extended framework treats genotype as one input and environment as another, with a function that combines them — and the field of *gene-environment interaction* (G × E) statistics is the modern descendant.

---

## Sex-influenced and sex-limited inheritance — autosomal genes whose expression depends on sex

Chapter 01 introduced X-linked inheritance, in which the gene itself is on the X chromosome and the dosage difference between XX females and XY males produces the characteristic patterns (affected males more common in X-linked recessive; "skip-a-generation through daughters" pedigrees). This chapter adds two related but distinct patterns: **sex-influenced inheritance** (autosomal gene, but expression varies by sex) and **sex-limited inheritance** (autosomal gene, but expressed in only one sex).

**Male-pattern baldness** (androgenetic alopecia) is the classic example of sex-influenced inheritance, though the genetics is actually more complex than "one autosomal gene" — multiple loci contribute, with the *AR* (androgen receptor) gene on the X chromosome being one of the most important contributors, alongside several autosomal modifiers ([Hagenaars et al. 2017 *PLoS Genetics* 13:e1006594](https://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1006594) [verify]). For the simplified Mendelian-pedagogy version: the trait depends on testosterone exposure. Heterozygous men, with high circulating testosterone, develop the bald phenotype. Heterozygous women, with much lower testosterone, do not — they may have mild hair thinning but rarely the frank balding seen in heterozygous men. The same genotype, the same allele, but the phenotype depends on sex-hormone exposure. *Sex-influenced*: the allele acts as dominant in one sex and recessive in the other.

**Sex-limited inheritance** is the stronger version: the trait is expressed in *only one sex*. Milk production in dairy cattle is determined by autosomal genes that are expressed only in females (males don't lactate even when they carry the lactation-promoting alleles). Feather patterns in some bird species are expressed only in males. The autosomal genes can be inherited equally by both sexes, and the alleles transmitted through the silent sex are perfectly intact — they just are not phenotypically visible in carriers of the wrong sex. A bull carrying high-milk-production alleles passes them to his daughters, who then express them; the bull himself shows nothing.

Both patterns preserve Mendelian transmission. The arithmetic of segregation, gamete formation, and offspring genotype is unchanged. What changes — once again — is the genotype-to-phenotype rule, which here includes sex as an input variable.

---

## Mitochondrial inheritance — the only thing that really does not fit

Of all the extensions in this chapter, **mitochondrial inheritance** is the one that genuinely does not fit the Mendelian framework — not because the framework needs amending, but because the underlying biology is fundamentally different.

Mitochondria are cytoplasmic organelles, descended from a free-living bacterium that became symbiotic with the ancestor of all eukaryotic cells more than a billion years ago. They retain a small circular chromosome of their own — the human mitochondrial genome is 16,569 base pairs long and encodes 37 genes (13 protein-coding genes for components of the electron-transport chain, 22 tRNAs, and 2 rRNAs), referenced from [Anderson et al. 1981 *Nature* 290:457–465](https://www.nature.com/articles/290457a0). When a sperm fertilizes an egg, only the *nuclear* DNA of the sperm enters the zygote; the sperm's mitochondria, located in the midpiece, are usually destroyed or excluded. The mitochondria of the zygote are essentially all maternal in origin, derived from the egg's cytoplasm.

This produces **maternal inheritance**, the diagnostic pattern of mitochondrial-DNA disorders:

- *All* children of an affected mother inherit the mitochondrial mutation.
- *None* of the children of an affected father inherit it.
- The trait passes through the maternal line, generation after generation, with affected mothers always producing affected children of both sexes, and affected fathers always producing unaffected children of both sexes.

The classic examples are **Leber's hereditary optic neuropathy (LHON)**, a mitochondrial disorder causing painless, often bilateral, central-vision loss in young adults, due to mutations in mitochondrial respiratory-chain genes (most commonly *MT-ND4*) ([Wallace et al. 1988 *Science* 242:1427–1430](https://www.science.org/doi/10.1126/science.3201231) [verify]); and **MELAS** (mitochondrial encephalomyopathy with lactic acidosis and stroke-like episodes), a multisystem disorder due to mutations typically in *MT-TL1* (a mitochondrial tRNA gene); and **MERRF** (myoclonic epilepsy with ragged-red fibers).

Two complications make mitochondrial inheritance even less Mendelian-looking. First, every cell contains many mitochondria (hundreds to thousands), and each mitochondrion contains multiple copies of the mitochondrial genome. A mutation may be present in some of the mitochondria and not others — a state called **heteroplasmy**. The phenotype severity depends on the fraction of mutant mitochondria, which varies between cells in the same individual, between tissues, and between siblings, because mitochondrial inheritance is *stochastic* at the cellular level — when a cell divides, the mitochondria are distributed randomly between the daughter cells. Two siblings inheriting the same mutation from the same mother can have very different proportions of mutant mitochondria, and consequently very different phenotypes. Second, the random distribution during oogenesis means even the *initial* heteroplasmy passed from mother to child is unpredictable.

The pedigree pattern is unmistakable: maternal transmission only, affected sons and daughters in roughly equal proportions, no father-to-child transmission ever. If a pedigree shows the trait being transmitted from an affected father to even one child, mitochondrial inheritance is essentially ruled out. The Mendelian framework — built around nuclear-chromosome inheritance, equal parental contribution, and segregation — does not describe this pattern at all. Mitochondrial inheritance is its own framework, layered onto the nuclear-Mendelian one.

---

## Genomic imprinting — when parent-of-origin matters

The final and conceptually strangest extension is **genomic imprinting**: a pattern in which the *parent of origin* of an allele matters. The same DNA sequence produces a different phenotype depending on whether it was inherited from the mother or the father.

Most genes are expressed from both maternal and paternal copies; a heterozygote with one functional and one non-functional allele typically expresses the functional one regardless of which parent contributed it. But a small number of genes (roughly 100–200 in humans) are subject to **imprinting** — one of the two alleles is *silenced* by parent-of-origin-specific epigenetic marks (DNA methylation, histone modifications), so the gene is effectively monoallelically expressed from either the maternal or the paternal copy, depending on the specific imprinted gene. (Epigenetics gets a full treatment in Chapter 06; here we just need the basic idea — that gametes from male and female parents carry distinct chemical marks on their DNA that control which alleles are expressed in the offspring.)

The textbook example is the **Prader-Willi / Angelman pair** of syndromes, both caused by genetic abnormalities in the same chromosomal region (15q11-q13). The region contains several imprinted genes: some are normally expressed only from the paternal copy (with the maternal copy silenced by imprinting), and at least one (*UBE3A*) is normally expressed only from the maternal copy (with the paternal copy silenced).

- **Deletion of paternal 15q11-q13** (or maternal uniparental disomy — when both copies of chromosome 15 come from the mother): the *paternally expressed* genes are absent, producing **Prader-Willi syndrome**. Hypotonia at birth, feeding difficulties in infancy, hyperphagia and severe obesity in childhood, intellectual disability, hypogonadism.
- **Deletion of maternal 15q11-q13** (or paternal uniparental disomy — both copies from the father): the *maternally expressed* genes (particularly *UBE3A*) are absent, producing **Angelman syndrome**. Severe intellectual disability, seizures, ataxia, characteristic gait, frequent inappropriate laughter, minimal speech.

Same chromosomal region. Same kind of mutation (a deletion). Two different syndromes, distinguished entirely by which parent the abnormal chromosome came from. The mechanism was worked out by [Nicholls et al. 1989 *Nature* 342:281–285](https://www.nature.com/articles/342281a0) [verify], showing that the inheritance pattern of these disorders required parent-of-origin tracking.

The Mendelian framework, on its own, cannot represent this. Mendel's first law (dominance) does not depend on which parent provided the dominant allele. The extension required is to add, alongside the allele identity (A vs. a), a tag identifying which parent the allele came from — and to make the phenotype depend on the combination of identity and parental origin. The gametogenesis is still Mendelian. The genotype-to-phenotype rule, again, is what differs.

The same machinery (parent-of-origin-specific imprinting) underlies several other disorders, including Beckwith-Wiedemann syndrome (overgrowth syndrome with embryonal tumor predisposition) and some forms of transient neonatal diabetes. It is part of the larger field of **epigenetics**, which we will return to in Chapter 06 (gene regulation) and Chapter 13 (molecular evolution — including the question of whether some epigenetic states can be transgenerationally inherited, as suggested by the [Dutch Hunger Winter](https://www.pnas.org/doi/10.1073/pnas.0806560105) [verify] and [Överkalix](https://www.nature.com/articles/5201538) [verify] cohort studies, which document apparent grandparental-nutritional effects on grandchild metabolic phenotypes).

---

## Common misconceptions, named and corrected

Before the exercises, three misconceptions worth flagging explicitly. Each one comes up in classroom discussion, on exams, and (most importantly) in clinical conversations where stakes are real.

**Misconception 1: "Incomplete dominance means the alleles are weaker."** No. Incomplete dominance is about *protein dosage*. Both alleles are fully functional in their own right; the heterozygote produces an intermediate phenotype because the *amount* of functional product is intermediate. This is the haploinsufficiency model: one functional copy is not enough to produce the full phenotype, but it is fully functional as far as it goes. The molecular biology is dosage, not weakness. Familial hypercholesterolemia heterozygotes have *exactly half* the LDL-receptor activity of homozygous-normal individuals — not "weak" receptors, but *fewer* receptors.

**Misconception 2: "Dominant means common in the population."** This was already flagged in Chapter 02 but it bears repeating with the extensions in mind. Dominance is a property of the *heterozygote phenotype*: in a heterozygote with one dominant and one recessive allele, the phenotype matches the dominant. It says nothing about how frequent the allele is in the population. Huntington's disease is autosomal dominant and the dominant disease allele has a population frequency of about 1 in 20,000; the wild-type "recessive" allele is overwhelmingly more common. Many polymorphisms in the human genome have rare dominant variants and common recessive variants. The two concepts — dominance and frequency — are independent.

**Misconception 3: "If you have the BRCA1 mutation, you'll get cancer."** No. The penetrance is roughly 60–72% lifetime risk of breast cancer by age 80 in *BRCA1* carriers [verify]. About a third of carriers do not develop the disease in their lifetime. The mutation is a strong risk factor — far stronger than any common variant — but it is not a deterministic cause. The clinical implication is that genetic counseling must report probabilities, not certainties; that screening and risk-reducing options should be offered but not mandated; and that two sisters with the same mutation can legitimately have different lives.

A bonus misconception that comes up in genetics classes:

**Misconception 4: "Polygenic traits don't follow Mendel."** They follow Mendel exactly. Polygenic traits *are* Mendelian — at each individual locus, the alleles segregate normally, the gametes carry one allele each, the product rule gives the joint frequencies. What changes is that the *trait* is the sum of contributions across many loci, so the F₂ phenotype distribution is the binomial-coefficient pattern (or, in the limit of many loci, a normal distribution) rather than a discrete few-class ratio. Mendel's apparatus produces the bell curve; the central limit theorem is what links them. Polygenic inheritance is Mendelian inheritance summed up.

---

## Exercises

**Warm-up**

1. **Incomplete dominance, monohybrid F₂.** A pure-breeding red snapdragon (R^R R^R) is crossed with a pure-breeding white snapdragon (R^W R^W). The F₁ are uniformly pink. F₁ × F₁ self-pollination produces 320 F₂ plants. (a) Predict the F₂ genotype ratio. (b) Predict the F₂ phenotype ratio. (c) How many F₂ plants do you expect of each color? (d) Could you establish a pure-breeding pink line by selection? Why or why not? *Tests: incomplete dominance arithmetic; the difference between genotype ratio and phenotype ratio under incomplete dominance; why heterozygotes cannot breed true.*

2. **ABO blood typing.** A type AB mother (genotype I^A I^B) and a type O father (genotype i i) have children. (a) What is the genotype distribution among the children? (b) What is the phenotype (blood type) distribution? (c) Can any child of this couple have type AB blood? Type O? Explain. *Tests: codominance with the i recessive allele; gamete enumeration from a heterozygous parent.*

3. **Sickle cell as pleiotropy.** Name three distinct phenotypic effects of the homozygous HbSS sickle-cell genotype and one phenotypic effect that is specific to the HbAS heterozygote. Why is the heterozygote effect (sickle-cell trait) different from the homozygote effect, and what does this tell you about the dominance relationship between HbA and HbS? *Tests: identifying multiple phenotypes from one gene; distinguishing dominance/recessivity in a pleiotropic system.*

**Application**

4. **Yellow Labrador epistasis — F₂ ratios.** A black Labrador heterozygous at both loci (BbEe) is crossed with another black Labrador also heterozygous at both loci (BbEe). They produce 480 puppies (across many litters). Assuming Mendelian inheritance with recessive epistasis at the E locus: (a) Predict the F₂ phenotype distribution by genotype class (B_E_, bbE_, B_ee, bbee). (b) Combine the phenotype classes that produce the same coat color. (c) Express the result as a simplified ratio (e.g., 9:3:4). (d) How many puppies of each color (black, chocolate, yellow) would you expect from 480 total? (e) A yellow puppy from this litter is bred to a chocolate dog of genotype bbEe. Predict the phenotype distribution of their offspring. *Tests: identifying recessive epistasis from a dihybrid F₂ cross; computing modified ratios; reasoning about offspring of a cross involving the epistatic genotype.*

5. **ABO offspring-type probabilities.** A type AB mother and a type B father (genotype unknown, could be I^B I^B or I^B i) have four children. The children's blood types are: A, B, AB, and O. (a) From the appearance of the type-O child, what does this tell you about the father's genotype? (b) Given the inferred father genotype, what is the probability distribution of blood types for any subsequent child? (c) The couple is planning a fifth child. The mother has a transfusion history that suggests she may have anti-A antibodies in her serum — which would imply she is actually type B, not type AB. How would you resolve the apparent inconsistency between her serological typing and the appearance of a type-A child among her existing children? *Tests: inferring genotype from offspring phenotypes; offspring-type probabilities with multiple alleles; clinical reasoning about ABO discrepancies.*

6. **BRCA1 pedigree with reduced penetrance.** A four-generation pedigree shows the following pattern. Generation I: an unaffected great-grandmother and an affected great-grandfather (breast cancer at age 55). Generation II: their three children — an unaffected daughter, an affected daughter (ovarian cancer at age 49), and an unaffected son. Generation III: the affected Generation II daughter has two children, both unaffected so far. The unaffected Generation II son has three children, of whom one daughter has been diagnosed with breast cancer at age 42. (a) What inheritance pattern is most consistent with this pedigree? Justify your answer using the diagnostic features visible in the pedigree. (b) The unaffected Generation II daughter is now 65 and has never had cancer. What is the probability she is a *BRCA1* mutation carrier, given the family history, assuming 70% penetrance by age 65? (c) The Generation II son has now had his daughter test positive for the family's *BRCA1* mutation. What does this tell us about him? (d) What is the per-pregnancy probability that the affected Generation III daughter (age 42, has the mutation) will pass the mutation to a child? Will every child who inherits the mutation develop cancer? *Tests: distinguishing reduced-penetrance autosomal dominant from autosomal recessive; computing carrier probabilities with reduced penetrance; the difference between mutation transmission and disease development.*

**Synthesis**

7. **From Mendel's framework to Bombay.** Walk through the Bombay-phenotype cross from the chapter (Hh I^A i × Hh I^B i) and produce the modified F₂ ratio (3 : 3 : 3 : 7 in the order AB : A : B : "type O"). Now suppose you observe an apparent type-O child in a family where both parents have been blood-typed as A and B. Most genetics textbooks would say this is impossible (since type-A × type-B parents who are I^A I^A and I^B I^B should produce only type-AB children, and if they are I^A i and I^B i should produce A, B, AB, and O in 1:1:1:1 — making O perfectly possible). Suppose the genetic counselor finds out that the apparent-O child is actually anti-H positive and is Bombay. What does this tell you about the parents? Could both parents be Bombay? Could only one be? Trace the reasoning. *Tests: reasoning from phenotypes back to genotypes when epistasis is present; recognizing the diagnostic signature of Bombay (anti-H positivity) in apparent O blood.*

8. **Polygenic-to-Mendelian translation.** A trait is controlled by *three* additive loci, each with two alleles where the "tall" allele adds one unit of height and the "short" allele adds zero. A cross between two triply heterozygous parents (AaBbCc × AaBbCc) produces F₂ offspring. (a) What is the maximum possible height (in trait units) for an F₂ individual? The minimum? (b) What is the F₂ phenotype distribution (frequencies of each possible height value)? (c) Express this as a binomial-coefficient ratio. (d) How would the distribution look qualitatively if the cross involved 10 additive loci rather than 3? Why does the discrete Mendelian-class structure get hard to see as the number of loci grows? (e) Now suppose the environment adds Gaussian noise to each individual's phenotype with variance equal to half the genetic variance. Sketch (qualitatively) what the resulting phenotype distribution would look like. *Tests: polygenic-inheritance arithmetic; the binomial-to-Gaussian convergence; the additive genotype-environment phenotype model.*

**Challenge**

9. **A mitochondrial disorder pedigree problem.** A four-generation pedigree shows the following. Generation I: an affected great-grandfather (with mitochondrial-encephalomyopathy symptoms) married to an unaffected great-grandmother. Generation II: three children — none affected, despite the father being affected. Generation III: each of those three Generation II individuals has children of their own; one Generation II daughter has three affected children, the others have unaffected children. (a) Is this pattern consistent with mitochondrial inheritance? Why or why not? (b) Could it be autosomal dominant with reduced penetrance? Compare the diagnostic features. (c) What single observation in the pedigree most cleanly distinguishes mitochondrial inheritance from autosomal dominant reduced-penetrance inheritance? (d) Now suppose instead that Generation I shows an *affected great-grandmother* (not great-grandfather), and her three children are all affected, and each of her three children has affected children. Now is mitochondrial inheritance consistent? Justify. *Tests: distinguishing mitochondrial from autosomal inheritance patterns from pedigree features; reasoning about absence-of-male-transmission as the diagnostic.*

10. **Build the simulator.** Using the Brutalist file conventions from Chapter 00, write the four-move prompt (Show / Say / Constrain / Verify) for `03-extended-inheritance.html`. The simulation should extend Chapter 02's Mendelian-crosses simulator with new capabilities: (a) **Inheritance-mode selector**: complete dominance (Mendelian baseline), incomplete dominance, codominance, multiple alleles (with editable dominance series), recessive epistasis, dominant epistasis, polygenic (with adjustable number of contributing loci 2–10 and adjustable effect-size-per-allele slider). (b) **Polygenic histogram panel**: as the number of loci increases, the F₂ phenotype histogram should transition smoothly from discrete classes (2 loci → 5 classes) to a continuous bell curve (10 loci → effectively Gaussian); include a "central limit theorem in action" overlay showing the Gaussian fit. (c) **Epistasis panel**: for any selected epistasis mode, display the modified Punnett square with cells colored by phenotype class, and show the resulting modified F₂ ratio (e.g., 9 : 3 : 4 for recessive epistasis) compared to the standard 9 : 3 : 3 : 1. (d) **Penetrance toggle**: a slider (0–100%) that adjusts the probability that a "genotype-affected" individual displays the affected phenotype; the simulator should update pedigree-style outputs to show how reduced penetrance makes the inheritance pattern appear to skip generations. (e) **ABO/Bombay calculator**: parental ABO genotypes plus optional Bombay (Hh) status for each parent, with computed offspring blood-type-phenotype distribution including the apparent-O class that hides Bombay individuals. *Deliverable*: the four-move prompt, the file (built and run), and a screenshot of the polygenic panel at 2 loci vs. 10 loci showing the Gaussian convergence. *Tests: the full computational framework of the chapter applied through the same simulation-building method introduced in Chapter 00; visualization of central-limit-theorem convergence; the modified-ratio arithmetic for each extension mode.*

---

## Bridge to Chapter 04

This chapter has been an exercise in patching the Mendelian genotype-to-phenotype rule, one extension at a time, while preserving the underlying gametogenesis arithmetic. Incomplete dominance changes the rule for one-locus heterozygotes. Codominance changes the rule differently. Multiple alleles enlarge the genotype space without changing the gamete-combination arithmetic. Epistasis links two loci' rules so that one constrains the other. Pleiotropy is the dual of polygenic inheritance (one gene → many traits versus many genes → one trait). Penetrance adds a probabilistic layer to the genotype-to-phenotype function. Environment adds an entire new input variable. Sex influence adds another. Mitochondrial inheritance escapes the framework entirely because the gene is not on a nuclear chromosome. Imprinting adds a parent-of-origin tag to the allele.

Through all of it, one assumption has gone unexamined: that the allele is a discrete unit of inheritance, faithfully transmitted, doing some specific molecular thing. What is the allele, physically? What is the gene, physically? What is being passed from parent to offspring at the molecular level?

Chapter 04 takes up that question. We are going to leave the Mendelian framework behind for one chapter and dive into the molecule itself — DNA. The structure: the double helix, the antiparallel strands, the complementary base pairing that Watson and Crick proposed in 1953 from Rosalind Franklin's X-ray data. The mechanism of replication: how each strand serves as a template for the synthesis of its complement, so that two daughter molecules emerge from one parent molecule — the semiconservative replication that Meselson and Stahl demonstrated in 1958, sometimes called "the most beautiful experiment in biology." The enzymatic machinery: helicase, primase, DNA polymerase, ligase, the leading-and-lagging-strand asymmetry. And the repair systems that fix the inevitable damage: mismatch repair, base-excision repair, nucleotide-excision repair, double-strand-break repair — the machinery that, when it fails, opens the door to mutation and cancer.

The shift in chapter is also a shift in scale. Chapters 01–03 worked at the cellular and organismal level — meiosis, gametes, offspring counts, family pedigrees. Chapter 04 zooms in to the angstrom scale, the level of the bonds between atoms and the geometry of the nucleotide stacking. We will be looking at the molecule that holds the information all of Mendel's arithmetic was about.

---

**What would change my mind:** If a clearly characterized inheritance pattern, in a model organism with full molecular and genomic characterization, refused to fit *any* combination of the extensions catalogued in this chapter — that is, if there were a real, reproducible inheritance pattern that required postulating a new class of inheritance mechanism orthogonal to those already named (alleles segregating at meiosis, gametes combining at fertilization, with phenotype determined by the combination of genotype, environment, sex, parental origin, and penetrance) — I would have to extend the framework further. To date no such pattern has been clearly documented. Every observed inheritance pattern in the genetic literature can be modeled as some combination of these mechanisms. The framework, with its dozen extensions, is the modern descendant of Mendel's three laws, and it is the one clinical genetics and population genetics actually use.

**Still puzzling:** I do not yet fully understand how to estimate clinical penetrance from family-based pedigree data when ascertainment bias is severe. *BRCA1* penetrance estimates have ranged in the published literature from below 50% to above 80%, depending on the population studied, the ascertainment criteria (do you require a specific number of affected relatives to enter the study?), and the statistical model used. Estimates from population-based studies tend to be lower than estimates from clinic-ascertained families (because the latter are enriched for high-risk families). The "true" penetrance — meaning, the lifetime risk of disease for an average mutation carrier in the general population — is harder to pin down than the literature sometimes suggests, and clinical genetic counseling has to navigate this uncertainty honestly. The arithmetic in this chapter assumes a fixed penetrance; in practice, the penetrance estimate itself has uncertainty bands, and the recurrence-risk number reported to a patient is a point estimate of a distribution rather than a precise value.

---

**Tags:** incomplete-dominance, codominance, multiple-alleles, ABO-blood-groups, epistasis, Bombay-phenotype, polygenic-inheritance, pleiotropy, penetrance, expressivity, mitochondrial-inheritance, genomic-imprinting, BRCA1, Marfan-syndrome, sickle-cell, PKU, central-limit-theorem
