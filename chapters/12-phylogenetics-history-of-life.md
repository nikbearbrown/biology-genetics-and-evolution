# Chapter 12 — Phylogenetics and the History of Life: Reading the Tree from the Speciation Events That Built It

**Suggested titles:**
- *Carl Woese in a Basement at Urbana, 1977 — How One Molecule Cut Life Into Three Domains and Burned the Old Textbook*
- *Why a Dolphin Is Not a Fish, a Whale Is a Hippo, and a Bird Is a Dinosaur — Phylogenetic Inference from Evidence*
- *Three and a Half Billion Years in One Tree — The Methods That Read the Past from Sequences in the Present*

---

**TL;DR.** Chapter 11 ended with one lineage splitting into two. Run that process over four billion years across every lineage and you get the tree of life — a branching record of speciation events. This chapter walks the methods by which the tree is reconstructed from data we can actually measure (morphological characters, DNA sequences, fossil dates), the major shape of the tree as it is now understood (three domains, the last universal common ancestor, endosymbiosis as the origin of eukaryotes, the Cambrian explosion, the Big Five mass extinctions and the human-driven sixth), and the conditions under which the tree metaphor breaks down (horizontal gene transfer in prokaryotes, hybridization in plants, ancient admixture in vertebrates). The worked example takes four real primate sequences — human, chimpanzee, gorilla, orangutan — at a 250-base-pair piece of the mitochondrial *COX1* gene, walks the pairwise distance calculation with the Jukes-Cantor correction, builds a neighbor-joining tree, scores parsimony at the inferred internal nodes, bootstraps the support, calibrates the molecular clock against the orangutan split at ~14 million years ago, and uses the calibrated rate to predict the human-macaque divergence — recovering 25–30 million years for the Old World monkey/ape split that the fossil record independently puts at ~25 million years. By the end you should be able to read a published phylogeny without misreading it, score a small parsimony problem by hand, compute a Jukes-Cantor distance and a molecular clock rate from sequence data, name what each of the Big Five mass extinctions did to the standing diversity, and explain at the level of the mechanism why the prokaryotic "tree of life" is closer to a "web of life" at deep time.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **Read** a phylogenetic tree correctly — identify nodes, branches, tips, root, sister groups, and clades — and **name** at least three common misreadings (most basal = primitive, left-to-right ordering encodes time, similar tips are most closely related).
2. **Classify** any named group as monophyletic, paraphyletic, or polyphyletic, and **explain** why only monophyletic groups (clades) are the natural unit of evolutionary biology.
3. **Distinguish** homology (shared by ancestry) from homoplasy (convergent evolution producing similar form independently), and **identify** which kind of similarity supports a clade and which kind misleads.
4. **Score** a small parsimony problem by hand — given a character matrix for 4–6 taxa with binary characters, **find** the tree requiring the fewest evolutionary changes.
5. **Compute** the Jukes-Cantor corrected distance from raw sequence divergence between two species, and **explain** why uncorrected p-distance underestimates the true number of substitutions at high divergence.
6. **Define** the maximum-likelihood and Bayesian approaches to tree inference in plain language and **name** what each adds over parsimony.
7. **Compute** a molecular clock rate from two species' sequence divergence and a fossil calibration time, and **predict** the divergence time of a third species pair from the calibrated rate.
8. **Name** the three domains of life (Bacteria, Archaea, Eukarya), **state** what evidence put Archaea on its own branch, and **explain** why Archaea sit closer to Eukarya than to Bacteria.
9. **State** the endosymbiotic theory in mechanism (which organelles, from which bacteria, when) and **list** at least four lines of evidence (double membranes, circular DNA, 70S ribosomes, binary fission, rRNA sequence affinity).
10. **Construct** a timeline of major events in the history of life from origin (~4 Ga) through LUCA, oxygenic photosynthesis, the Great Oxidation Event, eukaryotes, multicellularity, the Cambrian explosion, and the Big Five mass extinctions.
11. **Explain** at the level of the mechanism why horizontal gene transfer breaks the tree assumption for prokaryotes, and **predict** which genes (core, ribosomal, conserved) are still treelike and which (accessory, antibiotic resistance, metabolic) are not.
12. **Build** a `12-phylogenetics.html` tree-inference panel that takes a small sequence alignment, computes pairwise distances, builds a neighbor-joining tree, scores parsimony, runs a bootstrap, and compares the result to a calibrated tree-of-life navigator.
13. **Name** at least three common misconceptions about phylogenies (humans evolved from chimps, evolution has a goal, older lineages are more primitive) and **explain** what is mechanistically wrong with each.

**Prerequisites.** Chapter 11 produced the speciation event — one lineage becoming two. This chapter strings those events into a tree. You need to be comfortable with the five forces of Chapter 10 (mutation, selection, drift, gene flow, non-random mating) and the divergence-rate logic from Chapters 9 and 10, because phylogenetic inference is the inverse problem of those forward dynamics. You will need to be comfortable enough with logarithms to evaluate the Jukes-Cantor correction `d = -(3/4) ln(1 - (4/3)p)` and with simple probability to evaluate `(1/2)^n` for the unbalanced-gamete calculation that already showed up in Chapter 11. The mass-extinction and Great Oxidation Event timelines lean on geological dating you don't need to derive yourself — fossil and isotopic calibrations are inputs to the chapter, not outputs.

---

## A methanogen in a hot spring and the textbook that had to be rewritten

In 1977, Carl Woese and his colleague George Fox at the University of Illinois at Urbana-Champaign published a five-page paper in *Proceedings of the National Academy of Sciences* with a deceptively quiet title: "Phylogenetic structure of the prokaryotic domain: The primary kingdoms" ([Woese & Fox 1977, *PNAS* 74:5088–5090](https://www.pnas.org/doi/10.1073/pnas.74.11.5088); the founding three-domain paper). The paper reported that a class of microbes called the *methanogens* — anaerobic single-celled organisms that respire by converting hydrogen and carbon dioxide into methane, found in cow rumens, swamp sediments, and the gut of every termite on Earth — were not bacteria.

The methanogens looked like bacteria. They had no nucleus, no mitochondria, no organelles. Under a microscope they were small, simple, prokaryote-shaped cells. Every textbook of microbiology placed them inside the prokaryotic kingdom alongside *Escherichia coli* and *Bacillus subtilis*. They had been classified as bacteria since the 1880s.

Woese's evidence was a single molecule. The 16S ribosomal RNA — the structural RNA at the heart of the small subunit of the bacterial ribosome, about 1,540 nucleotides long, performing the same job in every prokaryotic ribosome on Earth — turned out to look fundamentally different in methanogens than in *E. coli*. Woese had developed a laborious technique called **oligonucleotide cataloguing**: he digested 16S rRNA with the enzyme T1 ribonuclease, separated the resulting short fragments by two-dimensional electrophoresis, sequenced them by hand, and compared the catalog of fragments between species. By 1976 he had cataloged about 60 species' worth of rRNA fragments. Methanogens shared fewer fragments with *E. coli* than *E. coli* shared with human mitochondrial rRNA. *The methanogens were as distantly related to typical bacteria as bacteria were to anything in the eukaryotic world.*

The conclusion was not subtle. Life was not divided into prokaryotes-and-eukaryotes. Life was divided into three lineages of approximately equal evolutionary depth: the typical bacteria (which Woese first called *eubacteria* and which we now call **Bacteria**), the methanogens-and-relatives (which Woese called *archaebacteria* and which we now call **Archaea**), and the nucleated cells (which Woese called *eukaryotes* and which we now call **Eukarya**). The Archaea were as different from the Bacteria as either was from us. The two-kingdom split that had structured biology for a century was wrong at the deepest level the tree had.

Woese met enormous resistance. Salvador Luria — a Nobel laureate, the dean of American molecular biology — reportedly called Woese personally to demand he stop talking about a third kingdom. Ernst Mayr, the architect of the biological species concept, dismissed the rRNA evidence as a single-molecule artifact. The microbiology establishment did not adopt the three-domain framework for nearly twenty years. The textbooks did not rewrite their introductions until the 1990s. Woese was elected to the National Academy of Sciences in 1988, finally honored for the rRNA work with a National Medal of Science in 2000 and a Crafoord Prize in 2003, and died in 2012 — still slightly ambivalent about whether the field had fully absorbed what he had done ([Pace et al. 2012, *RNA Biol* 9:1–4, obituary](https://www.tandfonline.com/doi/full/10.4161/rna.22918) [verify the obituary citation]; or see the *Nature* obituary, [Goldenfeld & Woese 2007, *Nature* 445:369](https://www.nature.com/articles/445369a)).

Here is the puzzle I want you to hold for the whole chapter. *Woese never looked at a methanogen under a microscope and decided it was not a bacterium.* He could not have made the discovery that way. The methanogens are not visibly different from typical bacteria; their cells are the same size, the same shape, the same range of metabolic strategies as far as the microscope can see. The discovery was made *by inference from a tree*. Woese built a phylogenetic tree from 16S rRNA sequence data, applied the tree to the question "where do the methanogens sit?", and got back an answer that contradicted every textbook. The tree saw what the microscope could not.

This is what phylogenetics does. It is the procedure by which you take evidence that is local and present-tense — sequences in a database, characters scored on living specimens, fossils dated in stratigraphic columns — and infer history. Every branch on a phylogenetic tree is a hypothesis about who descended from whom. The hypothesis is not free; it is constrained by what the data make most probable under explicit models of evolution. When you do the inference well, the tree tells you things no one knew. Woese's tree told the world that a third domain of life existed. The same methodology has told us that whales are nested inside the artiodactyls (closer to hippos than to any fish), that birds are dinosaurs (their closest non-avian relatives are *Tyrannosaurus* and *Velociraptor*), that fungi are closer to animals than to plants, that the human genome contains about 2% Neanderthal DNA (in non-African modern humans) inherited from a hybridization event in the Middle East roughly 60,000 years ago. None of these conclusions are visible to inspection. All of them are visible to phylogenetic inference.

The chapter walks the inference. Then it walks the tree — what the methodology has shown us about the four-billion-year history. Then it walks the limits — where the tree fails as a metaphor and what we use instead. The cichlid radiation, the *Geospiza* speciation, the *Rhagoletis* host shift from Chapter 11 are the inputs. The tree of life is the output.

---

## How to read a tree without misreading it

Before we can build trees, we need to read them. This sounds trivial; it is not. A 2003 study of biology majors at a large U.S. research university found that about half of upper-level biology students could not correctly answer basic tree-reading questions on a published phylogeny ([Gregory 2008, *Evolution: Education and Outreach* 1:121–137](https://link.springer.com/article/10.1007/s12052-008-0035-x); the tree-thinking review). Mistakes are easy to make precisely because trees look like simple drawings. The drawing carries a lot of information; misreading any piece of it produces a wrong claim about the history.

A **phylogenetic tree** is a branching diagram representing inferred evolutionary relationships among a set of taxa. Six features carry information; learn each one explicitly.

**Tips (also called leaves or terminal taxa).** The endpoints of the branches. Each tip represents either an extant species we sampled, an extinct species we have fossils of, or a sequence in a database. Tips are the data the tree is built from.

**Internal nodes.** Points inside the tree where branches split. Each internal node represents a *hypothetical common ancestor* — not necessarily a fossil organism we have in hand, but a population that existed at some past time and gave rise to the descendants at the two branches emerging from the node. The chimp-human node represents the population from which both *Pan troglodytes* and *Homo sapiens* descend, roughly 6 million years ago, fossils of which we have partial evidence for in *Sahelanthropus* and *Orrorin*.

**Branches (also called edges or lineages).** The lines connecting nodes to other nodes or to tips. A branch represents an unbroken line of descent — a chain of generations from one population to the next. Branch *length* can mean three different things depending on the tree:
- *Time-scaled tree* (chronogram): branch length is proportional to elapsed time. A 6-million-year branch is twice as long as a 3-million-year branch.
- *Distance-scaled tree* (phylogram): branch length is proportional to amount of evolutionary change (substitutions per site, or some other character distance). A branch with many substitutions is long; a branch with few is short.
- *Cladogram*: branch length is arbitrary, carrying no information; only the topology (the branching pattern) is meaningful.

Always check the figure caption. A tree with no caption is ambiguous on what its branch lengths mean.

**The root.** The single point at the base of the tree representing the most recent common ancestor of every taxon in the tree. A tree without a root (an *unrooted tree*) shows the topology of relationships but does not specify which way evolution ran — you cannot tell which node is older. A **rooted tree** has been polarized, usually by including an *outgroup* — a taxon known a priori to lie outside the group of interest — that anchors the root.

**Sister groups.** Two taxa or two clades are *sisters* if they share a more recent common ancestor with each other than either does with anything else in the tree. Sister relationship is the basic claim about kinship the tree makes. Chimpanzees and bonobos are sisters; humans are the sister of (chimpanzees + bonobos), not the sister of chimpanzees alone. Naming a single sister requires care about what is in the tree.

**Clades.** A **clade** is an ancestor and *all* of its descendants — a complete branch of the tree. Mammals are a clade. Vertebrates are a clade. Animals are a clade. The mammalian clade includes hair, mammary glands, and the three-bone middle ear as **synapomorphies** — shared derived characters that originated in the most recent common ancestor of all mammals and were inherited by every descendant.

The clade is the natural unit of evolutionary biology. It is the thing the tree picks out as a real grouping. There is no biological grouping more fundamental than "a population's complete descendant set." Everything else — taxonomic ranks, common names, ecological categories — is human bookkeeping layered on top.

### Three kinds of group, only one of which is real

Phylogenetic logic gives a precise vocabulary for the kinds of groups people draw out of the tree.

**Monophyletic group (= clade).** An ancestor plus all of its descendants. Mammals, birds, primates, eukaryotes. Always a real grouping.

**Paraphyletic group.** An ancestor plus *some but not all* of its descendants. The classic example: "reptiles," in the traditional sense (lizards + snakes + turtles + crocodiles, *excluding birds*) is paraphyletic. Crocodiles are more closely related to birds than to lizards — the closest living relatives of crocodilians are the birds — so the traditional "reptile" category drops out one whole descendant branch (birds) of the reptilian common ancestor. The natural group is *Reptilia + Aves* (sometimes called *Sauropsida* or *Reptilia sensu lato*), which includes birds. "Fish" is also paraphyletic — the common ancestor of all fish is also the ancestor of all tetrapods (you, the dog, the frog, the bird), and "fish" in the traditional sense excludes those descendants. Strictly, every tetrapod is a lobe-finned fish; the everyday word "fish" describes a paraphyletic remnant.

**Polyphyletic group.** A group containing members descended from *different* ancestors, gathered together by some convergent feature rather than by ancestry. "Warm-blooded animals" (endotherms) groups mammals and birds together, but the common ancestor of mammals and birds was not warm-blooded — endothermy evolved independently in the mammal lineage and the bird lineage. Birds and mammals are not sister groups; they are scattered on the amniote tree, with reptiles in between. "Marine mammals" (whales + seals + sea otters + manatees) is polyphyletic — these groups each independently re-entered the ocean from different terrestrial mammal ancestors.

Phylogenetic systematics — the modern formal study of evolutionary classification — accepts only monophyletic groups as valid biological units ([Hennig 1966, *Phylogenetic Systematics*, University of Illinois Press](https://www.press.uillinois.edu/books/?id=p085994); the foundational book, originally published in German 1950, English 1966). Paraphyletic and polyphyletic groupings are useful sometimes for everyday communication ("fish" picks out a familiar set of organisms) but they are not what the tree picks out as a unit. Whenever the tree-reading and the common-language grouping disagree, the tree is the more precise statement.

### Common tree-reading mistakes

Three misreadings are common enough that I want to head them off explicitly.

**Mistake one: the leftmost or topmost taxon is "most primitive."** No. Trees can be drawn with tips in any order. You can rotate the branches around any internal node without changing what the tree says about relationships. The order of tips along the page is a visual convention, not biology.

**Mistake two: "older lineage" means "more primitive organism."** A sponge is not a primitive human. The lineage leading to sponges has been evolving for the same total elapsed time as the lineage leading to humans; both have had roughly 600 million years since the protistan ancestor of all animals. Sponges have changed less morphologically than humans have over that time, but their genomes have accumulated mutations at comparable rates and their cellular machinery has been remodeled in ways their bodies do not advertise. The tree shows order of divergence, not order of complexity.

**Mistake three: humans evolved from chimpanzees.** Humans did not evolve from chimpanzees. Humans and chimpanzees share a common ancestor approximately 6 million years ago, and the lineage leading to modern chimps and the lineage leading to modern humans have been evolving in parallel ever since. The common ancestor was neither a modern chimp nor a modern human; it was a population of African great apes that we do not have a complete fossil record of. The tree shows the sister relationship — chimps and humans are sisters — not a descent of humans from chimps.

These three misreadings recur in popular accounts of evolution. They are easy to fall into if you have not internalized the distinction between "the tree" (a hypothesis about relationships among current taxa) and "evolution as a directional process" (which the tree does not depict, because evolution is not directional).

---

## Three ways to build a tree

Given sequences or characters from a set of taxa, three main computational approaches infer the most likely tree. Each approach makes different assumptions and has different strengths. Modern phylogenetics typically runs more than one approach on the same data and asks whether they agree.

### Parsimony — fewest evolutionary changes wins

The oldest of the modern methods, formalized by Hennig in the 1950s and computerized in the 1970s. The **maximum parsimony** principle: given several possible trees that could explain a character distribution, prefer the tree that requires the *fewest evolutionary changes* across all branches. Each tree is scored by counting how many character-state changes you have to invoke to explain the data; the tree with the lowest score wins.

The logic is the philosophical principle of parsimony — Occam's razor — applied to evolutionary inference. If two unrelated lineages share a complex character, the simplest explanation is that they inherited it from a common ancestor (one origin event), not that the same character independently evolved twice (two origin events). One event is more parsimonious than two; parsimony prefers the tree that minimizes events.

Here is the worked example. Three species A, B, C, with one binary character (0 = absent, 1 = present). Suppose the character state pattern is: A = 1, B = 1, C = 0. There are three possible unrooted topologies for three taxa, but two of them are biologically identical up to rotation; effectively there are three rooted trees to consider.

*Tree 1: ((A, B), C).* A and B are sisters; together they are the sister of C. Character: if the common ancestor of A and B had state 1, and C and the deeper ancestor had state 0, then *one* character change (0 → 1) on the branch leading to (A, B) explains the data. **Score = 1.**

*Tree 2: ((A, C), B).* A and C are sisters; together they are the sister of B. Character: if both A and B have state 1 and C has state 0, then either the ancestor of (A, C) had state 1 and then C reverted to 0 (one change), and B independently evolved 1 (one change) — for a total of 2; or some other reconstruction. Minimum score = **2 changes.**

*Tree 3: ((B, C), A).* B and C are sisters; together they are the sister of A. By the same logic as Tree 2, minimum score = **2 changes.**

Tree 1 is most parsimonious. The data say that A and B are more likely to be sisters than either is to C, because the simplest reading of the shared character is that A and B inherited it from a common ancestor that already had it.

For real datasets — say, twenty species and a thousand characters — the parsimony score of each candidate tree is computed by the **Fitch algorithm** (Fitch 1971, *Syst Zool* 20:406–416 [verify]), which traverses the tree from tips to root, assigning to each internal node the smallest set of states consistent with its descendants and accumulating change-counts along the way. The space of possible trees grows superexponentially with the number of taxa; for *n* taxa there are `(2n − 5)!!` distinct unrooted topologies, which is 945 for *n* = 7, about 213 million for *n* = 10, and about 8 × 10²¹ for *n* = 20. Exhaustive search is impractical above ~10 taxa; heuristic searches (branch swapping, nearest-neighbor interchange, subtree pruning and regrafting) explore the space and return locally optimal trees.

**Where parsimony works well.** When evolutionary change is rare per character, when rates of evolution are similar across lineages, and when there is no large amount of convergence (homoplasy) producing similar character states by independent evolution.

**Where parsimony fails.** When two lineages experience high rates of evolution on long branches, parsimony can mistakenly group them together based on shared independent changes that happen to look the same — a failure mode called **long-branch attraction** ([Felsenstein 1978, *Syst Zool* 27:401–410](https://academic.oup.com/sysbio/article/27/4/401/1648395); the paper that named the problem). Long-branch attraction is most severe at deep evolutionary distances and was a primary motivation for developing model-based methods that explicitly account for substitution rate variation among branches.

### Maximum likelihood — best tree under a model

The model-based response. **Maximum likelihood (ML)** inference asks: given an explicit probabilistic model of how sequence evolution works (substitution rates between specific nucleotides, possibly varying among sites, possibly varying among branches), which tree topology *and* set of branch lengths makes the observed data most probable?

The basic likelihood for one site (one column of the alignment) under one tree is `P(data at this site | tree, branch lengths, substitution model)`. The likelihood of the whole data is the product of per-site likelihoods (assuming sites evolve independently). The ML tree is the tree that maximizes this likelihood — equivalently, that maximizes the log-likelihood `Σ log P(site | tree, ...)`.

The model is the explicit thing parsimony lacks. The simplest substitution model — the **Jukes-Cantor model** ([Jukes & Cantor 1969](https://www.semanticscholar.org/paper/Evolution-of-protein-molecules-Jukes-Cantor/2876f56e83fb8aa6abe98a92a4c0b1abdbe06a98) [verify]) — treats all twelve possible nucleotide substitutions (A↔C, A↔G, A↔T, etc.) as equally likely. More elaborate models (Kimura 2-parameter, HKY85, GTR, GTR+Γ+I) allow transitions (purine↔purine, pyrimidine↔pyrimidine) to differ from transversions (purine↔pyrimidine), allow different base frequencies, allow rate variation across sites by a gamma distribution, allow a fraction of sites to be invariant. Model selection — choosing which substitution model to use for a given dataset — is itself a computational step, typically done by **AIC** or **BIC** scoring before tree inference begins.

ML tree inference is computationally intensive. The standard packages — **RAxML** ([Stamatakis 2014, *Bioinformatics* 30:1312–1313](https://academic.oup.com/bioinformatics/article/30/9/1312/238053)), **IQ-TREE** ([Nguyen et al. 2015, *Mol Biol Evol* 32:268–274](https://academic.oup.com/mbe/article/32/1/268/2925592)), **PhyML** ([Guindon et al. 2010, *Syst Biol* 59:307–321](https://academic.oup.com/sysbio/article/59/3/307/1702850)) — implement aggressive heuristics for the search and return ML trees with branch lengths in units of expected substitutions per site.

**Where ML works well.** When the substitution model is reasonable for the data, when the alignment is high quality, and when there is enough data per branch (a hundred sites per branch is a rough heuristic minimum) to estimate likelihoods well. ML handles long-branch attraction better than parsimony because the model explicitly accounts for the higher probability of homoplasy on long branches.

**Where ML fails.** When the substitution model is misspecified (the true substitution process differs systematically from the assumed model), ML can be confidently wrong — it returns a tree with high likelihood that is wrong for the systematic reason it cannot see. Model misspecification is a leading driver of the few cases where ML and other approaches disagree on the same data.

### Bayesian inference — posterior probability over trees

The fully probabilistic approach. **Bayesian inference** treats the tree itself, the branch lengths, and the substitution model parameters as random variables, places prior probability distributions on each, and computes the posterior distribution `P(tree | data)` using Bayes' theorem:

```
P(tree | data) ∝ P(data | tree) × P(tree)
```

The likelihood `P(data | tree)` is computed under a substitution model in the same way ML uses it. The prior `P(tree)` encodes whatever belief about plausible trees you brought to the analysis (often a uniform prior over topologies, sometimes a fossil-calibrated prior on divergence times).

The posterior is not computable in closed form for any but the smallest datasets. Bayesian phylogenetic inference uses **Markov chain Monte Carlo (MCMC)** sampling to draw a representative sample of trees from the posterior. The standard packages — **MrBayes** ([Ronquist et al. 2012, *Syst Biol* 61:539–542](https://academic.oup.com/sysbio/article/61/3/539/1674894)), **BEAST** ([Bouckaert et al. 2019, *PLoS Comput Biol* 15:e1006650](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006650)) — run MCMC for millions of steps, output a posterior sample of trees, and summarize the posterior by reporting (a) the consensus tree (the topology most frequently sampled) and (b) the **posterior probability** on each node (the fraction of sampled trees that contain that clade). A node with posterior probability 0.95 is found in 95% of the posterior sample.

**What Bayesian inference adds.** Explicit uncertainty quantification. A 0.95 posterior on a clade means something probabilistically — it is the probability that the clade is real given the data and the model. ML support is measured by bootstrap (next section); Bayesian support is measured by posterior probability; the two scales are not identical but both measure something like "how confident should I be in this clade?"

Bayesian inference also handles complex models — clock-relaxation, fossil calibration with prior distributions, coestimation of tree and substitution model — more naturally than ML, because everything is a random variable with a prior. The trade-off is computational cost; Bayesian analyses on large datasets routinely take days or weeks of compute time.

### Bootstrap — assessing how much the data support each node

A separate but essential question: *how much do the data actually support the tree we inferred?* The answer comes from the **bootstrap** ([Felsenstein 1985, *Evolution* 39:783–791](https://onlinelibrary.wiley.com/doi/10.1111/j.1558-5646.1985.tb00420.x); the paper that introduced bootstrap to phylogenetics).

Bootstrap procedure:

1. Take the original alignment (say, 500 sites × 20 species).
2. Resample sites *with replacement* to create a new alignment of the same size (500 sites again, but each site is drawn at random from the original 500, so some sites appear two or three times, others not at all).
3. Build a tree from the resampled alignment using whatever method you prefer (parsimony, ML, distance).
4. Repeat steps 2–3 a thousand times (or more).
5. For each node in the original tree, compute the fraction of the 1,000 bootstrap trees that contain the same clade. This is the **bootstrap support** for the node.

The interpretation. A node with bootstrap support 95% means that 95% of resamplings of the data recover the same clade. It is a statement of how robustly the data support that clade against perturbations of the dataset. A node with 50% bootstrap support means the data are roughly evenly split between including and excluding that clade; the node is not well supported.

Rough informal cutoffs in the literature: bootstrap above 70% is "moderate" support, above 90% is "strong" support, above 95% is "very strong." These are conventions, not theorems. Bootstrap support is not the same as the probability the clade is correct — under model misspecification, you can get high bootstrap support for a wrong clade ([Hillis & Bull 1993, *Syst Biol* 42:182–192](https://academic.oup.com/sysbio/article/42/2/182/1768824); the foundational paper on bootstrap interpretation).

The combination of (parsimony or ML or Bayesian tree topology) + (bootstrap or posterior probability support values) is the standard reporting format. A modern phylogeny paper presents the tree with support values at every internal node and a note about which method produced the tree.

---

## Worked example — building a primate phylogeny from a short sequence

Let me do all of this on one small example so the procedure is concrete. Take four primate species — human, chimpanzee, gorilla, orangutan — and a 250-base-pair piece of the mitochondrial *COX1* gene (cytochrome *c* oxidase subunit 1). Mitochondrial sequences evolve roughly 10× faster than nuclear sequences and so accumulate enough variation in a few million years to be informative for primate phylogeny. *COX1* is the standard barcode locus used in the Barcode of Life Data System for animal species identification ([Hebert et al. 2003, *Proc R Soc B* 270:313–321](https://royalsocietypublishing.org/doi/10.1098/rspb.2002.2218)) and so is well-curated in GenBank.

I will not work an actual sequence here — I would have to write the alignment out and ask you to count differences — but I will write the calculation as if we had the alignment in hand with the following pairwise differences (these are illustrative numbers in the range typical for great-ape *COX1* sequences; treat them as a worked-example scaffold rather than an actual published distance matrix):

| Pair | Observed differences in 250 bp | Raw p-distance |
|---|---:|---:|
| Human – Chimp | 7 | 0.028 |
| Human – Gorilla | 11 | 0.044 |
| Human – Orangutan | 22 | 0.088 |
| Chimp – Gorilla | 11 | 0.044 |
| Chimp – Orangutan | 22 | 0.088 |
| Gorilla – Orangutan | 22 | 0.088 |

The **p-distance** is the simplest possible measure of sequence divergence: count the number of sites that differ between the two sequences, divide by the total number of sites compared. p-distance is what the raw observation gives you.

### Step 1 — correct the raw distance for multiple substitutions

The p-distance underestimates the true number of substitutions per site because, over evolutionary time, some sites have been hit more than once. A site that started as A, mutated to C, then mutated back to A, looks identical between species today even though *two* substitutions occurred at that site. A site that mutated A → C → G looks like one substitution today but is actually two. The longer the time since divergence, the worse the underestimate gets, because the probability of multiple hits at the same site grows.

The simplest correction is the **Jukes-Cantor distance**:

```
d_JC = -(3/4) × ln(1 - (4/3)p)
```

Here `p` is the observed p-distance, `d_JC` is the corrected estimate of expected substitutions per site, and the factor of 3/4 comes from the fact that under a model with four equally likely nucleotides, a site has 3/4 probability of changing to any other nucleotide per substitution event.

Let me compute the corrections for the table above.

Human – Chimp: `p = 0.028`. Compute `1 − (4/3)(0.028) = 1 − 0.0373 = 0.9627`. Take `ln(0.9627) = −0.0380`. Multiply by `−3/4`: `d_JC = 0.0285`. Very close to the raw p-distance, as expected for low divergence (the correction is small when sites haven't had time to be multiply hit).

Human – Gorilla: `p = 0.044`. `1 − (4/3)(0.044) = 1 − 0.0587 = 0.9413`. `ln(0.9413) = −0.0605`. `d_JC = 0.0454`. Slightly larger than p.

Human – Orangutan: `p = 0.088`. `1 − (4/3)(0.088) = 1 − 0.1173 = 0.8827`. `ln(0.8827) = −0.1248`. `d_JC = 0.0936`. About 6% higher than p; the multiple-hit correction has started to matter.

If we were comparing humans to a much more distant taxon — say, a fish, with p ≈ 0.45 in the same gene — the Jukes-Cantor correction would inflate the estimate from p ≈ 0.45 to d_JC ≈ 0.85, nearly double, because so many sites have been hit multiple times that the raw p-distance is no longer close to the true number of substitutions. *This is the multiple-hit problem, and it is the central reason raw p-distances are not used in modern phylogenetic inference at deep evolutionary distances.*

### Step 2 — build the neighbor-joining tree

The **neighbor-joining (NJ) method** ([Saitou & Nei 1987, *Mol Biol Evol* 4:406–425](https://academic.oup.com/mbe/article/4/4/406/1029664)) takes a distance matrix as input and returns a tree as output by a clever iterative procedure: at each step, identify the pair of taxa that minimizes a corrected distance criterion, join them into a new internal node, and repeat with the reduced matrix.

For the corrected distance matrix above (Human-Chimp = 0.029, Human-Gorilla = 0.045, etc.), neighbor-joining picks the closest pair first. Human and Chimp are closest at 0.029. They are joined into a new internal node, call it HC. The distances from HC to the remaining taxa are computed by an averaging formula. Then the closest remaining pair is identified: Gorilla and HC are closer than Orangutan and HC. So Gorilla joins HC at a deeper node, call it HCG. Finally Orangutan joins HCG at the root. The resulting topology is:

```
(((Human, Chimp), Gorilla), Orangutan)
```

— Human and Chimp sister to each other, Gorilla sister to the (Human, Chimp) clade, Orangutan as the outgroup at the root.

This is the textbook great-ape topology, recovered from a 250-bp piece of one mitochondrial gene. Real published trees use thousands of base pairs from dozens of genes and converge on the same topology with bootstrap support of 100% at every internal node ([Goodman et al. 1998, *Mol Phylogenet Evol* 9:585–598](https://www.sciencedirect.com/science/article/pii/S105579039890495X); [Glazko & Nei 2003, *Mol Biol Evol* 20:424–434](https://academic.oup.com/mbe/article/20/3/424/995978)).

### Step 3 — parsimony score on this topology

What is the parsimony score of this tree, given the data?

For each variable site in the alignment, count the minimum number of substitutions required on this tree to produce the observed states at the tips. Sum over all variable sites. For the 250-bp piece used here, the parsimony score is approximately equal to the total number of changes — somewhere between 22 and 30, depending on how many sites are "informative" (showing the same state in at least two non-sister taxa).

A site at which only one species differs from the other three (an *autapomorphy*) does not affect tree choice — it adds one change on any tree. A site at which two species share a derived state different from the other two (a *synapomorphy* candidate) is the discriminating signal. On a 250-bp alignment of these four species, perhaps 5–10 sites are phylogenetically informative; the rest are constant or autapomorphic.

The parsimony score on the (((H, C), G), O) topology is the minimum; alternative topologies (((H, G), C), O) and (((C, G), H), O) require more changes because they fail to explain the human-chimp shared derived sites with a single common origin.

### Step 4 — bootstrap support

Resample the 250 sites with replacement to create a new alignment of 250 sites. Recompute the distance matrix on the new alignment, build a new neighbor-joining tree, record whether the new tree contains the (Human, Chimp) clade, the (Human, Chimp, Gorilla) clade, and the (Orangutan as outgroup) split. Repeat 1,000 times.

For real great-ape data with this sequence length, bootstrap support for the (Human, Chimp) sister relationship is typically about 95–98% ([Ruvolo 1997, *Mol Biol Evol* 14:248–265](https://academic.oup.com/mbe/article/14/3/248/1018091); [Satta et al. 2000, *Mol Phylogenet Evol* 14:259–275](https://www.sciencedirect.com/science/article/abs/pii/S1055790399906838)). The (Human, Chimp, Gorilla) clade — separating great apes from orangutan — gets essentially 100% support because the orangutan branch is long. The interpretation: the data robustly distinguish humans and chimps as sisters, and robustly place orangutan as the outgroup, even when sites are randomly resampled.

### Step 5 — calibrate the molecular clock

Now use the tree to date the splits.

We need a calibration — a node whose age we know independently from the fossil record. The **orangutan–African ape split** is conventionally calibrated to about 14 million years ago based on Miocene fossil great apes — particularly the *Sivapithecus* fossils from the Siwalik formation of Pakistan, dated to about 12–13 Ma, which show the characteristic orangutan facial morphology and so are taken to lie on the orangutan stem ([Pilbeam 1982, *Nature* 295:232–234](https://www.nature.com/articles/295232a0)). The calibration is contested by 1–3 million years depending on which fossils you accept ([Begun 2010, *Annu Rev Anthropol* 39:67–84](https://www.annualreviews.org/doi/10.1146/annurev.anthro.012809.105047)); we will use 14 Ma as the working number.

The distance from the (Human, Chimp, Gorilla) clade to orangutan is `d_JC ≈ 0.094`. This is the distance accumulated along *both* lineages from their common ancestor; the per-lineage time is half the total. So:

```
substitution rate r = 0.094 / (2 × 14 million years)
                    = 0.094 / 28 million years
                    ≈ 3.4 × 10⁻⁹ substitutions per site per year
```

This is the calibrated rate for *COX1* in great apes. Hold onto it.

### Step 6 — predict a deeper divergence

Now use the calibrated rate to date the chimp–human split.

Human–Chimp distance is `d_JC ≈ 0.029`. The time since divergence is:

```
t = d / (2r) = 0.029 / (2 × 3.4 × 10⁻⁹) ≈ 4.3 million years
```

This estimate — about 4–5 million years — is somewhat shorter than the modern best estimate of the chimp–human split at 6–7 million years ago ([Patterson et al. 2006, *Nature* 441:1103–1108](https://www.nature.com/articles/nature04789); [Langergraber et al. 2012, *PNAS* 109:15716–15721](https://www.pnas.org/doi/10.1073/pnas.1211740109)). The undershoot illustrates a real limitation: a single 250-bp piece of one gene gives a noisy estimate of divergence time, and the molecular clock assumption (constant rate across lineages) breaks down to some extent over millions of years. Published estimates use hundreds of genes, relaxed-clock models that explicitly allow rate variation across branches, multiple fossil calibrations, and produce the 6–7 Ma estimate that the worked-example arithmetic only approximately recovers.

Now use the same rate to predict a deeper divergence. Macaques (genus *Macaca*) are Old World monkeys; the split between Old World monkeys and apes (the catarrhine common ancestor) is conventionally dated by fossils to about 25–30 million years ago ([Stevens et al. 2013, *Nature* 497:611–614](https://www.nature.com/articles/nature12161); the Rukwa Rift fossil)). What sequence divergence would our calibrated rate predict at that depth?

```
d = 2 × r × t = 2 × 3.4 × 10⁻⁹ × 27.5 × 10⁶ ≈ 0.19 substitutions per site
```

Predicted p-distance (uncorrected) at this depth, inverting the Jukes-Cantor formula: 

```
p = (3/4) × (1 − e^(-4d/3)) = 0.75 × (1 − e^(-0.25)) = 0.75 × 0.221 ≈ 0.166
```

So about 17% of sites should differ between humans and macaques at *COX1*. Observed values are in the range 14–18% ([Wertheim et al. 2010, *Mol Biol Evol* 27:1581–1597](https://academic.oup.com/mbe/article/27/7/1581/1097681); great-ape vs. macaque mitochondrial divergences). The calibrated clock recovers the macaque divergence approximately, with the spread reflecting both the clock noise and the genuine rate variation across the deeper portion of the catarrhine tree.

### What this exercise teaches

The deep lesson. Phylogenetic inference is statistical inference about history. You start with sequence differences in the present, apply explicit models of how those differences accumulated, and recover both the branching pattern and the timing of the past — with quantifiable uncertainty. The (Human, Chimp) sister relationship is supported with bootstrap > 95%, the (Human, Chimp, Gorilla) clade with bootstrap ≈ 100%. The molecular clock rate is calibrated from a fossil-anchored node and used to date other splits, with predictions that match independent fossil and molecular evidence to first order.

The limits. The molecular clock is an approximation — substitution rates vary across genes (mitochondrial vs. nuclear), across lineages (rodents have higher rates per year than apes), across time (some periods of rapid evolutionary change), across sites within a gene. Single-gene estimates are noisy; large multi-gene datasets with relaxed-clock models are the modern standard. At deep evolutionary distances — say, the bacteria-eukaryote split — the molecular clock is so uncertain that estimates have spread over orders of magnitude.

The honest description: phylogenetics gives you the past with quantified uncertainty. The point estimate of the chimp-human split at 6 Ma comes with a 95% confidence interval of perhaps 5–7 Ma; the point estimate of the bacteria-eukaryote split at 2–3 Ga comes with a 95% confidence interval that may span 1.5–4 Ga. Both estimates are the best the data support; both come with explicit uncertainty.

---

## The three domains and the last universal common ancestor

With the methods in place, walk now to the deepest part of the tree.

Woese's 1977 paper proposed three primary kingdoms; the framework as it stands today calls them three **domains**: **Bacteria**, **Archaea**, and **Eukarya**. The classification was formalized by Woese, Otto Kandler, and Mark Wheelis in 1990 ([Woese, Kandler & Wheelis 1990, *PNAS* 87:4576–4579](https://www.pnas.org/doi/10.1073/pnas.87.12.4576)), proposing "domain" as a taxonomic rank above kingdom. The three-domain framework has held up under every subsequent reanalysis with new molecular data, with one major refinement: the Archaea are not equidistant from the other two domains. *Archaea are sisters to Eukarya.* The deepest split is between Bacteria on one side and (Archaea + Eukarya) on the other.

Evidence that Archaea and Eukarya are sisters comes from multiple molecular sources:

1. **Translation machinery.** The components of the ribosome and the translation apparatus — RNA polymerase subunits, initiation factors, elongation factors, ribosomal proteins — are more similar between Archaea and Eukarya than between either and Bacteria. Archaeal RNA polymerase has 11–13 subunits; eukaryotic RNA polymerase has 12–17 depending on which polymerase you look at; bacterial RNA polymerase has 5 ([Werner & Grohmann 2011, *Nat Rev Microbiol* 9:85–98](https://www.nature.com/articles/nrmicro2507)).

2. **Membrane lipids.** Archaea use ether-linked isoprenoid lipids; Bacteria and Eukarya use ester-linked fatty-acid lipids. This is a major chemical difference — but the ether/ester distinction does not pattern across the tree the way the translation-machinery similarity does, and it appears Archaea uniquely innovated the ether lipids early.

3. **Universal genes.** When 30 genes that are present in essentially every cellular organism are aligned and analyzed jointly, the consensus topology robustly places Archaea and Eukarya as sisters ([Hug et al. 2016, *Nat Microbiol* 1:16048](https://www.nature.com/articles/nmicrobiol201648); the modern tree of life with ~92 genes from ~3,083 organisms).

4. **The Asgard archaea.** Discovered in deep marine sediments around 2015 — first described in samples from a hydrothermal vent at the Mid-Atlantic Loki's Castle, hence the names *Lokiarchaeota*, *Thorarchaeota*, *Odinarchaeota*, *Heimdallarchaeota* ([Spang et al. 2015, *Nature* 521:173–179](https://www.nature.com/articles/nature14447); [Zaremba-Niedzwiedzka et al. 2017, *Nature* 541:353–358](https://www.nature.com/articles/nature21031)) — this superphylum of uncultured archaea encodes a remarkable number of "eukaryotic signature proteins" (actin-related cytoskeletal proteins, small GTPases, ubiquitin-like proteins, ESCRT-III homologs). When the universal-gene tree is built with Asgard sequences, the Eukarya emerge from *inside* the Asgard radiation — not as the sister of all Archaea but as a nested branch within Archaea. The first cultured Asgard archaeon, *Prometheoarchaeum syntrophicum*, was isolated in 2019–2020 from deep-sea sediment and showed long branching protrusions reminiscent of the cellular architecture proposed for the eukaryote-Archaea hybrid event ([Imachi et al. 2020, *Nature* 577:519–525](https://www.nature.com/articles/s41586-019-1916-6); the cultivation paper).

The current best phylogenetic reading: eukaryotes are *derived from Archaea* (specifically the Asgard lineage) through an early endosymbiotic event in which an archaeal cell engulfed a bacterium — the proto-mitochondrion — and the two cells fused into the eukaryotic ancestor about 2 billion years ago ([Eme et al. 2017, *Curr Opin Microbiol* 38:165–174](https://www.sciencedirect.com/science/article/pii/S1369527417300280); review of the Asgard-eukaryote model).

### LUCA — the last universal common ancestor

Trace the three domains back to their root and you reach a population of cells whose descendants are everything alive today. This population is the **last universal common ancestor (LUCA)** — not a single individual but a community of related cells from which the bacterial, archaeal, and eukaryotic lineages all derive. LUCA is conventionally dated to about 3.5–4 billion years ago ([Weiss et al. 2016, *Nat Microbiol* 1:16116](https://www.nature.com/articles/nmicrobiol2016116); the LUCA reconstruction paper).

What do we know about LUCA? More than you might think. Any gene present in all three domains with similar function and structure must have been present in their common ancestor; the alternative — three independent inventions of the same complex molecular machine — is implausible. Reconstructing the universally-shared genes gives a partial portrait.

- **A DNA genome.** All three domains have DNA-based heredity with double-stranded helical structure and the same four nucleotides.
- **A ribosome.** The translation apparatus is universal in detail. LUCA had a small subunit (16S in prokaryotes, 18S in eukaryotes), a large subunit (23S/28S), and tRNA-mediated codon-amino-acid mapping with essentially the universal genetic code from Chapter 5.
- **Core metabolism.** Glycolysis and the citric acid cycle are universal, with some lineage-specific modifications. LUCA could oxidize organic compounds for energy and synthesize amino acids and nucleotides.
- **Membrane.** LUCA had a lipid bilayer membrane, but the lipid chemistry is contested (the ether-linked archaeal lipids versus the ester-linked bacterial/eukaryotic lipids must have diverged either at LUCA itself or shortly after).
- **Probably hydrothermal vent affiliation.** The 2016 reconstruction by Weiss and colleagues, based on 355 protein families found in both Bacteria and Archaea and inferred to be present in LUCA, suggests an anaerobic chemolithoautotroph using H₂ and CO₂ as energy and carbon sources — consistent with a hydrothermal vent environment.

LUCA is the bottom of the tree we can build by molecular comparison. Below LUCA — the origin of life itself, the RNA world, the transition from chemistry to heredity — is largely outside what current phylogenetic methods can read. The signal degrades into the noise.

---

## Endosymbiosis — how eukaryotes got their organelles

Inside the eukaryotic cell, the deepest history is recorded not by the nuclear genome alone but by the organelles. Mitochondria and chloroplasts each carry their own DNA — small circular genomes of bacterial-style organization, encoding rRNAs, tRNAs, and a handful of proteins — and the DNA tells a specific story.

The **endosymbiotic theory**, in the form it now holds, was developed by Lynn Margulis (then Lynn Sagan) in a famously-rejected 1967 paper ([Sagan 1967, *J Theor Biol* 14:225–274](https://www.sciencedirect.com/science/article/pii/0022519367900793); the manuscript was rejected by about fifteen journals before being published). The theory: **mitochondria are descended from a free-living α-proteobacterium that was engulfed by an archaeal-or-proto-eukaryotic host cell roughly 1.5–2 billion years ago and gradually integrated into the host as an obligate intracellular organelle.** A similar engulfment event involving a cyanobacterium gave rise to **chloroplasts** in the lineage leading to plants, about 1 billion years ago.

The evidence is unusually direct.

**Mitochondria have double membranes.** The outer membrane is the host-derived membrane (from the original phagocytic vesicle that engulfed the bacterium); the inner membrane is the original bacterial plasma membrane, including its characteristic phospholipid composition with cardiolipin (a lipid otherwise found mainly in bacterial membranes). The two-membrane architecture is the engulfment event preserved in the cell.

**Mitochondria have their own circular DNA genome.** Vertebrate mitochondrial DNA (mtDNA) is a single circular molecule of about 16,569 base pairs in humans, encoding 13 proteins, 22 tRNAs, and 2 rRNAs ([Anderson et al. 1981, *Nature* 290:457–465](https://www.nature.com/articles/290457a0); the original human mitochondrial genome paper). The circular organization is bacterial; the small size reflects extensive gene loss to the nucleus during the integration (most of the ancestral α-proteobacterial genes have been transferred to the host nuclear genome over the past two billion years, but a small number remain in the mitochondrion).

**Mitochondrial ribosomes are 70S, like bacterial ribosomes** — not 80S like the cytoplasmic eukaryotic ribosomes. The 70S/80S distinction matters mechanistically because antibiotics like aminoglycosides, tetracyclines, chloramphenicol, and macrolides target the 70S ribosome and so can have mitochondrial off-target effects in eukaryotic patients (Chapter 5 walked through this in detail). The fact that mitochondrial ribosomes are bacterial-style ribosomes is direct evidence of the bacterial ancestry of the organelle.

**Mitochondria divide by binary fission.** They do not arise *de novo* by the cell's regular machinery; they replicate themselves by splitting in two, just as bacteria do, and are then partitioned between daughter cells during host-cell division. Cells that lose all mitochondria cannot make new ones; mitochondria are heritable in the sense that bacteria are heritable.

**Mitochondrial rRNA sequences place them inside the α-proteobacteria phylogenetically.** When you build a tree from 16S/18S rRNA sequences across all three domains and include mitochondrial rRNA as a sequence, the mitochondrial rRNA branches *inside the Bacteria*, specifically in the α-proteobacteria, alongside *Rickettsia* and *Rhodospirillum* ([Andersson et al. 1998, *Nature* 396:133–140](https://www.nature.com/articles/24094); the *Rickettsia* genome paper that placed mitochondria phylogenetically). The closest free-living relatives of modern mitochondria are intracellular bacterial parasites of the *Rickettsia*-group. The mitochondrion is not a generic bacterium; it is a specific kind of α-proteobacterium that has been a host-cell resident for two billion years.

The same logic, in parallel, applies to chloroplasts and cyanobacteria. Chloroplast rRNA places them inside the Cyanobacteria; chloroplasts have double membranes, circular DNA, 70S ribosomes, and divide by binary fission. They are descended from a cyanobacterial engulfment event in the lineage leading to plants ([Gould et al. 2008, *Annu Rev Plant Biol* 59:491–517](https://www.annualreviews.org/doi/10.1146/annurev.arplant.59.032607.092915)). Secondary and tertiary endosymbiosis — where one eukaryote that already has a chloroplast is engulfed by a second eukaryote — has produced the complex plastid organization of organisms like diatoms, kelp, and apicomplexan parasites (which contain a non-photosynthetic relict plastid, the apicoplast, used for fatty acid and isoprenoid synthesis; the *Plasmodium falciparum* malaria parasite has an apicoplast that is a target for antimalarial drugs).

The eukaryotic cell is, mechanically, a chimera. It carries genes of three ancestries: a host genome derived from the Asgard archaea, a mitochondrial component derived from an α-proteobacterium, and (in plants and algae) a chloroplast component derived from a cyanobacterium. The tree-of-life metaphor breaks down at the eukaryotic root for this reason — eukaryotes are not on a single branch but on a fusion of multiple branches.

---

## The history of life — a four-billion-year timeline

With the methods and the major lineages in hand, walk the major events on the timeline. The dates are rough — most of them carry uncertainty of tens to hundreds of millions of years for events more than a billion years ago — but the rough sequence is robustly supported by multiple independent lines of evidence (radiometric dating of associated rocks, isotopic signatures, molecular-clock estimates, biomarker fossils).

**~4.5 Ga (billion years ago)** — Earth forms. The planet is initially a magma ocean; surface conditions are uninhabitable for at least 100 million years. By about 4.4 Ga, the surface had cooled enough to allow liquid water (zircon crystal isotope evidence; [Wilde et al. 2001, *Nature* 409:175–178](https://www.nature.com/articles/35051550)).

**~4 Ga** — The earliest possible origin of life. The oldest accepted biological evidence is from **3.7-billion-year-old graphite inclusions in metamorphosed Greenland sedimentary rocks** with isotopic carbon signatures consistent with biology ([Rosing 1999, *Science* 283:674–676](https://www.science.org/doi/10.1126/science.283.5402.674)). Even earlier candidate biosignatures from Quebec rocks dated 3.77–4.28 Ga are contested ([Dodd et al. 2017, *Nature* 543:60–64](https://www.nature.com/articles/nature21377)). The honest reading: life arose somewhere between 4.2 and 3.5 Ga; we cannot pin the date more precisely. The *RNA world hypothesis* — that the earliest replicating systems used RNA both as informational molecule and as catalyst before DNA and proteins were invented — is the dominant working model ([Gilbert 1986, *Nature* 319:618](https://www.nature.com/articles/319618a0)) but remains hypothetical for the pre-LUCA period.

**~3.5 Ga** — LUCA. The last universal common ancestor of all current life. Stromatolites from the Pilbara region of Western Australia and the Barberton greenstone belt of South Africa show layered microbial mats from this era ([Allwood et al. 2006, *Nature* 441:714–718](https://www.nature.com/articles/nature04764)); the cells producing the mats were unicellular prokaryotes with the basic machinery LUCA had.

**~2.7 Ga** — Oxygenic photosynthesis evolves in cyanobacteria. Before cyanobacteria, photosynthesis was anoxygenic (used electron donors other than water, did not produce O₂). Cyanobacteria evolved water-splitting Photosystem II ([Hohmann-Marriott & Blankenship 2011, *Annu Rev Plant Biol* 62:515–548](https://www.annualreviews.org/doi/10.1146/annurev-arplant-042110-103811)), enabling the use of an effectively inexhaustible electron donor and the release of O₂ as a waste product. Oxygen begins accumulating in the oceans.

**~2.4 Ga** — The **Great Oxidation Event** ([Lyons et al. 2014, *Nature* 506:307–315](https://www.nature.com/articles/nature13068)). Atmospheric oxygen rises from approximately zero to roughly 1–2% of modern levels over a few hundred million years. The shift was driven by cyanobacterial oxygen production overwhelming abiotic oxygen sinks (reduced iron and sulfur in the oceans). The consequences were catastrophic for anaerobic life and revolutionary for what followed: aerobic respiration (which extracts roughly 18× more energy from glucose than fermentation) became possible, and the ozone layer began to form, blocking UV and making the surface habitable for the first time. (The cell-book chapter on bioenergetics covers the molecular consequences of the GOE in detail; this chapter touches it as a historical pivot.)

**~2 Ga** — Eukaryotes appear, by the Asgard-archaeon + α-proteobacterium fusion event described above. The oldest accepted eukaryotic fossils — the *Grypania spiralis* coil-shaped fossils from Michigan — date to about 1.85 Ga ([Han & Runnegar 1992, *Science* 257:232–235](https://www.science.org/doi/10.1126/science.1631544); see also revised dating). Molecular clock estimates for the eukaryotic crown group cluster around 1.5–2 Ga.

**~1.5–1 Ga** — Chloroplasts evolve, by cyanobacterial endosymbiosis in the lineage leading to plants. Major eukaryotic lineages — opisthokonts (animals + fungi), amoebozoa, archaeplastida (plants + green algae + red algae + glaucophytes), excavates, SAR (stramenopiles + alveolates + rhizaria) — diversify.

**~800 Ma to ~600 Ma** — Multicellularity evolves, *independently*, in many eukaryotic lineages. Modern phylogenetic and developmental work supports at least 25–30 independent origins of multicellularity across eukaryotes ([Knoll 2011, *Annu Rev Earth Planet Sci* 39:217–239](https://www.annualreviews.org/doi/10.1146/annurev.earth.031208.100209)) — separately in plants, animals, fungi, brown algae, red algae, multiple lineages of green algae, slime molds, and several others. The conditions enabling the transition — division of labor across cells, cell-cell adhesion molecules, cell-cell signaling — appear to have been available in multiple lineages and produced multicellular grades multiple times.

**~635 Ma** — The Ediacaran biota. The oldest large multicellular animal-like fossils (or perhaps lichens, or perhaps an extinct experimental grade — interpretation contested) appear in the Ediacara Hills of Australia and worldwide ([Erwin et al. 2011, *Science* 334:1091–1097](https://www.science.org/doi/10.1126/science.1206375)). The Ediacaran fauna includes flat, frondose, quilted organisms of uncertain phylogenetic placement; most do not survive into the Cambrian.

**~540–520 Ma** — The **Cambrian explosion**. Most major animal phyla appear in the fossil record over a window of about 10–30 million years ([Marshall 2006, *Annu Rev Earth Planet Sci* 34:355–384](https://www.annualreviews.org/doi/10.1146/annurev.earth.33.031504.103001)). The Burgess Shale (British Columbia, ~508 Ma) and the Chengjiang biota (Yunnan, China, ~520 Ma) preserve soft-bodied animals representing arthropods, mollusks, brachiopods, echinoderms, chordates, and a remarkable diversity of stem-group lineages that do not survive. The Cambrian explosion is one of the great puzzles of paleontology: was it a true biological radiation following the evolution of body plans (Hox genes, see Chapter 13), an environmental trigger (oxygen levels rising again to enable larger animals), or a taphonomic effect (the first time mineralized skeletons made fossils possible at scale)? Best current reading: a combination of all three, with the genuine biological radiation being the dominant factor.

**~440 Ma — End-Ordovician mass extinction.** ~85% of marine species lost [verify the percentage; modern estimates vary 70–86%]. Cause: combination of glaciation and sea-level fall, possibly triggered by drift of Gondwana over the South Pole ([Sheehan 2001, *Annu Rev Earth Planet Sci* 29:331–364](https://www.annualreviews.org/doi/10.1146/annurev.earth.29.1.331)).

**~370 Ma — End-Devonian mass extinction.** ~75% of species lost [verify]. Cause: contested; possible combination of marine anoxia, climate cooling, and plant evolution (the first forests draw down atmospheric CO₂).

**~252 Ma — End-Permian mass extinction.** *The largest mass extinction in Earth history.* ~96% of marine species lost; ~70% of terrestrial vertebrate species lost ([Erwin 2006, *Extinction: How Life on Earth Nearly Ended 250 Million Years Ago*, Princeton University Press](https://press.princeton.edu/books/paperback/9780691165653/extinction)). Cause: massive volcanism of the Siberian Traps, ejecting ~3 million cubic kilometers of basalt and releasing CO₂, sulfur dioxide, and methane on a scale that drove rapid global warming, ocean acidification, and ocean anoxia. Recovery took roughly 5–10 million years. The end-Permian shifted the dominant marine fauna from the trilobite-and-brachiopod-dominated Paleozoic to the mollusk-and-fish-dominated Mesozoic.

**~200 Ma — End-Triassic mass extinction.** ~50% of species lost [verify]. Cause: volcanism associated with the breakup of Pangaea — the Central Atlantic Magmatic Province eruptions — and the consequences for global climate and ocean chemistry.

**~66 Ma — End-Cretaceous (K-Pg) mass extinction.** ~75% of species lost, including all non-avian dinosaurs, all ammonites, all marine reptiles (mosasaurs, plesiosaurs). Cause: the Chicxulub asteroid impact, a roughly 10-km-diameter asteroid striking the Yucatán Peninsula and ejecting a global dust-and-sulfate aerosol cloud that blocked sunlight for months to years, killed photosynthesis worldwide, and triggered a global firestorm visible as the iridium layer in the K-Pg boundary clay ([Alvarez et al. 1980, *Science* 208:1095–1108](https://www.science.org/doi/10.1126/science.208.4448.1095); the iridium-anomaly paper; [Schulte et al. 2010, *Science* 327:1214–1218](https://www.science.org/doi/10.1126/science.1177265); the unified Chicxulub-impact interpretation). The K-Pg ended the Mesozoic and opened the Cenozoic; *mammals*, which had been present since the late Triassic as small nocturnal generalists for ~150 million years under dinosaur dominance, radiated into the empty niches over the next 10 million years. Modern primate lineages, including the ancestors of humans, are descended from one of those small mammalian survivors.

**Present** — The **Sixth Extinction**. Human-driven habitat destruction, climate change, overharvesting, and species introductions have produced background extinction rates 100–1,000× the pre-human rates inferred from the fossil record ([Ceballos et al. 2015, *Sci Adv* 1:e1400253](https://www.science.org/doi/10.1126/sciadv.1400253)). Whether the current biodiversity loss reaches Big-Five magnitude depends on next-century trajectories, but the empirical case for an unprecedented anthropogenic extinction event is now well documented. The honest reading: we are inside the early portion of a mass extinction; whether it stabilizes at moderate magnitude or continues to deepen depends on choices being made now.

---

## When the tree breaks — horizontal gene transfer and the web of life

The tree metaphor works well for sexually reproducing eukaryotes, where each generation inherits genes vertically from two parents and lineages diverge by speciation. The metaphor breaks for prokaryotes.

In Bacteria and Archaea, genes move between organisms by mechanisms that have nothing to do with reproduction. Three pathways dominate ([Ochman et al. 2000, *Nature* 405:299–304](https://www.nature.com/articles/35012500); the foundational review of HGT in bacterial evolution):

**Transformation.** A bacterium takes up free DNA from its environment — DNA released by dead, lysed cells — and incorporates it into its genome by homologous recombination if a matching sequence exists, or by integration into a recombination hotspot. *Streptococcus pneumoniae*, *Bacillus subtilis*, *Neisseria gonorrhoeae*, and *Haemophilus influenzae* are naturally competent for transformation under specific conditions.

**Transduction.** A bacteriophage (a virus that infects bacteria) accidentally packages some of the host bacterium's DNA into its capsid instead of (or in addition to) viral DNA. When that phage infects a new cell, it injects the captured DNA, which can integrate into the new host's genome. Lambda phage of *E. coli* and P22 of *Salmonella* are the classical model systems for transduction.

**Conjugation.** Two bacteria physically connect via a protein bridge called a pilus, and one transfers a plasmid (a small circular DNA molecule, often carrying genes for antibiotic resistance, heavy metal resistance, virulence factors, or specialized metabolism) to the other. The F plasmid of *E. coli* and the Ti plasmid of *Agrobacterium tumefaciens* are well-studied. Conjugation can transfer plasmids across substantial phylogenetic distances — *Agrobacterium* uses its Ti plasmid to transfer DNA into plant cells, which is the molecular basis of agricultural plant transformation technology.

These mechanisms move genes between cells that are not in a parent-offspring relationship, and they do so frequently. Estimates of the **horizontally transferred fraction** of bacterial genomes vary by organism but average in the 5–20% range for many species, with some organisms (including pathogens that have acquired antibiotic resistance) showing much higher fractions in specific gene categories ([Soucy et al. 2015, *Nat Rev Genet* 16:472–482](https://www.nature.com/articles/nrg3962)).

The consequence for phylogenetic reconstruction: **different genes in the same bacterial genome can have different evolutionary histories.** Gene A places species X and Y as sisters; gene B places species X and Z as sisters; gene C places species Y and Z as sisters. The conflict is not a methodological problem to be resolved; it is the real biology. Each gene has its own history, the history is partly vertical descent and partly horizontal transfer, and the "species tree" is at best an average of many gene trees.

The phenomenon is called **xenology** when a gene tree differs from the species tree because of HGT. Xenologous genes are common enough that some authors have argued the "tree of life" is at best a misleading metaphor for prokaryotes, and at worst a misrepresentation. The alternative metaphor — the **web of life** ([Doolittle 1999, *Science* 284:2124–2129](https://www.science.org/doi/10.1126/science.284.5423.2124); [Doolittle 2009, *Phil Trans R Soc B* 364:2221–2228](https://royalsocietypublishing.org/doi/10.1098/rstb.2009.0032)) — captures the network structure better than a strictly bifurcating tree does.

The pragmatic compromise modern phylogenetics adopts: build the species tree from a *core* of genes that are essential, conserved, and rarely transferred (the ribosomal RNAs are the classic example; some authors argue that even rRNA can be transferred but at very low rates and so remains usable as a phylogenetic backbone), and treat *accessory* genes (those involved in metabolism, antibiotic resistance, virulence) as a separate analysis with explicit network methods. The 2016 tree-of-life paper by [Hug et al. (*Nat Microbiol* 1:16048)](https://www.nature.com/articles/nmicrobiol201648) used 16 ribosomal protein genes — chosen specifically because they are universally conserved, syntenic, and rarely subject to HGT — and built a tree across 3,083 genomes that resolves much of the bacterial diversity (including the newly recognized **Candidate Phyla Radiation** — a major branch of Bacteria with reduced genomes and apparently obligate dependence on other microbes, comprising a substantial fraction of bacterial diversity that was missing from earlier trees).

The HGT problem is severe at deep evolutionary time and at the prokaryote–eukaryote interface (because endosymbiosis is itself a form of massive horizontal transfer — the proto-mitochondrion brought ~2,000 genes into the eukaryotic ancestor, most of which subsequently transferred from the mitochondrion to the nucleus). It is milder, but not absent, in modern animals — endogenous retroviruses are a clear example of recent (within the last few hundred million years) horizontal gene transfer in vertebrates, and **introgression** between hybridizing animal species can shuffle genes across lineages in ways that produce phylogenetic conflict at specific loci (the Neanderthal-modern-human admixture from Chapter 11 is exactly this kind of localized HGT).

The honest reading: **the tree model is a good approximation for eukaryotic relationships at most depths, and an increasingly approximate model as you move into Bacteria and Archaea or into deep time.** The model is not wrong; it is a simplification whose validity depends on the question. For the major branches — the three domains, the major eukaryotic supergroups, the major animal phyla — the tree captures the dominant evolutionary signal. For the fine structure within bacteria, or for the deep tree below LUCA, the tree is a coarse approximation of a more complicated network.

---

## Common misconceptions

Three misreadings of phylogeny recur in classrooms and in popular science writing. Each is mechanistically wrong, and each is worth dismantling explicitly.

**Misconception one: humans evolved from chimpanzees.** Humans did not evolve from chimpanzees. The lineage leading to modern *Homo sapiens* and the lineage leading to modern *Pan troglodytes* diverged from a common ancestor approximately 6–7 million years ago. Both lineages have been evolving independently ever since. The common ancestor was not a chimp; it was an African great ape, fossils of which are partial and contested (*Sahelanthropus tchadensis* ~7 Ma, *Orrorin tugenensis* ~6 Ma, *Ardipithecus kadabba* ~5.6 Ma being candidate stem-hominins). Modern chimps and modern humans are sister taxa. The branch leading to chimps and the branch leading to humans are of equal length on the tree.

The misconception comes from a misreading of the tree as a ladder, with humans at the top and other primates as stepping stones underneath. The tree is not a ladder. Every tip is a contemporary endpoint; every tip has been evolving for the same total elapsed time since the last common ancestor.

**Misconception two: evolution has a direction or goal.** Evolution is not directed toward complexity, toward humans, or toward anything else. The processes that drive evolutionary change — mutation, selection, drift, gene flow, non-random mating — operate locally on populations in specific environments. Selection optimizes locally for whatever traits enhance fitness in the current environment, without reference to any long-term goal. A lineage may become simpler over time (parasitic organisms often lose genes and structures their free-living ancestors had — tapeworms have lost their digestive systems, *Mycoplasma* bacteria have lost much of their core metabolism), become more complex (eukaryotes added organelles and cytoskeletal architecture relative to their prokaryotic ancestors), or remain in roughly the same form for hundreds of millions of years (horseshoe crabs have changed relatively little since the Ordovician ~450 Ma; their morphology is conserved because their ecology has been conserved).

The misconception comes from the false analogy between evolution and engineering. Engineering has a designer with a goal; evolution does not. The tree records the history of what happened, not the history of what was supposed to happen.

**Misconception three: extant "primitive" organisms are ancestors of "advanced" organisms.** Sharks are not primitive humans. Lungfish are not primitive lobe-finned fish on the way to tetrapods. The bacterium in your gut is not a precursor of your nucleated cells; it is a modern bacterium with its own four billion years of evolution since the last common ancestor with you. Every organism alive today is at the tip of a branch, and every branch is as long as every other.

The misconception comes from confusing "early-diverging lineage" with "primitive form." Early-diverging means that lineage split off near the base of the tree of the group you are looking at. It does not mean that lineage has not evolved since the split. Sponges are early-diverging animals — they split off from the rest of the animal tree before the cnidarian/bilaterian split — but modern sponges have been evolving for the same ~600 million years as you have. They have lost and gained traits; their genomes have accumulated substitutions at characteristic animal rates; they are modern animals, not living fossils of the Precambrian.

This third misconception underlies a great deal of bad popular writing about evolution. *"The crocodile, an evolutionary throwback to the Mesozoic..."* — no, the modern crocodile is not a Mesozoic animal preserved unchanged; modern crocodilians are descendants of a Mesozoic lineage that have continued to evolve. The branching pattern of the tree tells you order of divergence; it does not tell you that the early-diverging lineages are static.

---

## Synthesis — what phylogenetics buys us

Step back. The chapter did six things.

**First.** It walked the procedure for reading a phylogenetic tree correctly — identifying nodes, branches, tips, root, sister groups, and clades; distinguishing monophyletic groups (the natural unit) from paraphyletic (ancestor + some descendants, like "reptiles") and polyphyletic (multiple ancestries, like "warm-blooded"); and naming the common misreadings.

**Second.** It walked three approaches to building trees — parsimony (minimize evolutionary changes), maximum likelihood (best tree under a model of substitution), Bayesian inference (posterior over trees) — and the bootstrap procedure that assesses node support. Each approach makes different assumptions; modern phylogenetics typically runs more than one and asks whether they agree.

**Third.** It worked the full primate phylogeny end to end on a 250-bp piece of *COX1*: pairwise distance counts, Jukes-Cantor multiple-hit correction (`d = -(3/4) ln(1 - (4/3)p)`), neighbor-joining tree construction, parsimony scoring, bootstrap support, fossil-calibrated molecular clock (`r ≈ 3.4 × 10⁻⁹ substitutions per site per year` from the 14-Ma orangutan calibration), and predicted divergence times for human-chimp and human-macaque that match published estimates to first order.

**Fourth.** It walked the deepest part of the tree — Carl Woese's 1977 discovery of the Archaea from 16S rRNA sequence comparison; the three-domain framework as it now stands (Bacteria, Archaea, Eukarya); the modern best reading that Archaea and Eukarya are sisters, with eukaryotes likely derived from within the Asgard archaea; LUCA at ~3.5 Ga as the reconstructable common ancestor; and the endosymbiotic origin of mitochondria (from α-proteobacteria ~2 Ga) and chloroplasts (from cyanobacteria ~1 Ga), with five named lines of evidence each (double membranes, circular DNA, 70S ribosomes, binary fission, rRNA sequence affinity).

**Fifth.** It walked the four-billion-year history — origin of life ~4 Ga; LUCA ~3.5 Ga; oxygenic photosynthesis ~2.7 Ga; the Great Oxidation Event ~2.4 Ga; eukaryotes ~2 Ga; chloroplasts ~1.5–1 Ga; multicellularity independently 25–30 times beginning ~800 Ma; the Ediacaran ~635 Ma; the Cambrian explosion ~540–520 Ma; and the Big Five mass extinctions (End-Ordovician ~440 Ma, End-Devonian ~370 Ma, End-Permian ~252 Ma at ~96% marine species loss, End-Triassic ~200 Ma, End-Cretaceous ~66 Ma) — each with its proximate cause (glaciation, anoxia, volcanism, asteroid impact) and its evolutionary consequence (turnover of dominant lineages). The current sixth extinction, human-driven, with background rates 100–1,000× pre-human, is the live example of the same machinery in real time.

**Sixth.** It named where the tree metaphor breaks. Horizontal gene transfer in prokaryotes — transformation, transduction, conjugation — moves genes between unrelated cells frequently enough that different genes in the same bacterial genome have different evolutionary histories. The tree becomes a web at deep time and in microbial space. The pragmatic compromise: build species trees from a core of essential, rarely-transferred genes (ribosomal RNAs and ribosomal proteins) and treat accessory genes (metabolism, resistance, virulence) with network methods.

The big claim. *Phylogenetics is statistical inference about history.* It takes evidence from the present — sequences, characters, fossils — and recovers the past with quantifiable uncertainty. Carl Woese's tree from 16S rRNA was inference, not observation; it concluded that the methanogens were a separate domain because the tree said so, and the conclusion turned out to be right. The methodology that produced that conclusion produces every other major reading of evolutionary history we now hold: whales nested in artiodactyls, birds as dinosaurs, fungi as the sister of animals, eukaryotes derived from Asgard archaea. None of these are visible to inspection. All of them are visible to the inference.

The bridge to Chapter 13. Phylogenetics gave us the tree — the branching record of who descended from whom. Chapter 13 asks the next question: *what kinds of changes accumulated along the branches?* It walks the molecular evolution machinery — synonymous vs. nonsynonymous substitutions, the dN/dS ratio as a diagnostic for selection, Kimura's neutral theory and the molecular clock at the mechanistic level, transposable elements as a source of novelty, and (the punchline) the Hox-gene and evo-devo machinery that explains why small changes in gene regulation produce large changes in morphology. The tree tells you that the human and chimp lineages have been diverging for 6 million years; the molecular evolution chapter tells you what kinds of changes happened, and where, and which ones mattered.

The methods inferred the past. The molecules tell you why the past looked the way it did.

---

## Exercises

**Warm-up**

1. Identify each of the following groups as monophyletic, paraphyletic, or polyphyletic. Explain in one sentence each why. (a) Mammals. (b) Reptiles (lizards, snakes, turtles, crocodiles — *excluding* birds). (c) Marine mammals (whales + seals + manatees + sea otters). (d) Tetrapods (amphibians + reptiles + birds + mammals). (e) Endotherms (mammals + birds). (f) Animals. *Tests: basic classification of groups by phylogenetic logic.*

2. Define each of the following in one sentence, in plain language: (a) clade, (b) synapomorphy, (c) homoplasy, (d) outgroup, (e) bootstrap, (f) molecular clock, (g) parsimony, (h) maximum likelihood, (i) horizontal gene transfer, (j) endosymbiosis. *Tests: vocabulary recall with mechanism attached.*

3. The chapter says that Carl Woese discovered Archaea from 16S rRNA sequence comparison, not from microscopy. Why was the molecular evidence necessary? What would a microscopist, examining a methanogen and an *E. coli* side by side under a light microscope, see — and why would the microscopist conclude they are the same kind of organism? *Tests: understanding the limits of morphological inference at the microbial scale.*

**Application**

4. **Parsimony scoring by hand.** You have four taxa (A, B, C, D) and three binary characters scored as follows:

   | Taxon | Char 1 | Char 2 | Char 3 |
   |---|:---:|:---:|:---:|
   | A | 1 | 1 | 0 |
   | B | 1 | 1 | 0 |
   | C | 0 | 1 | 1 |
   | D | 0 | 0 | 1 |

   (a) Identify which characters are phylogenetically informative (showing a shared derived state in at least two taxa). (b) For the tree topology ((A, B), (C, D)), compute the parsimony score (minimum number of character changes on the tree). (c) For the alternative topology ((A, C), (B, D)), compute the parsimony score. (d) Which topology is more parsimonious, and what is the parsimony argument for preferring it? (e) Now suppose Char 2 is actually a convergent feature that evolved independently in three lineages. Does this change your answer? Explain. *Tests: hand-scoring parsimony; understanding how shared derived characters resolve trees and how homoplasy degrades the signal.*

5. **Jukes-Cantor correction.** Two species have an observed p-distance of 0.30 over a 1,000-bp alignment (300 sites differ). (a) Compute the Jukes-Cantor corrected distance `d = -(3/4) ln(1 - (4/3)p)`. (b) Compare to the uncorrected p-distance: how much does the correction inflate the estimate? (c) Now consider a more diverged pair with p = 0.50. Compute `d_JC`. (d) At what value of p does the Jukes-Cantor formula become undefined (give a negative argument to the logarithm)? What does this say about the limit of the multiple-hit correction? (e) Why is p-distance fine at 1% divergence but bad at 50%? *Tests: mechanical use of the correction formula and understanding why uncorrected distances are biased at high divergence.*

6. **Molecular clock calibration.** Two great-ape species have a sequence divergence of `d = 0.012` at the mitochondrial *COX1* gene. A fossil-calibrated split between humans and orangutans (`d = 0.094`) is taken to occur at 14 million years ago. (a) Compute the substitution rate `r` from the orangutan calibration. (b) Use the rate to estimate the divergence time of the two great-ape species. (c) Now suppose mitochondrial substitution rates are not constant: rodents evolve about 5× faster per year than apes. What happens to your estimate if you tried to apply the great-ape rate to a divergence between two rodent species? Would you overestimate or underestimate the time? (d) Name one technique modern phylogenetics uses to account for rate variation across lineages. *Tests: calibration arithmetic and the assumption of clock constancy.*

**Synthesis**

7. **Reading a published phylogeny.** Suppose you are reading a paper that presents a maximum-likelihood phylogeny of fifteen mammal species with bootstrap support values at every internal node. The paper claims that whales (Cetacea) are nested *inside* the artiodactyls (the even-toed ungulates — pigs, cows, deer, hippos), making artiodactyls without whales a paraphyletic group. The clade (whales + hippos) is called Whippomorpha. (a) What kind of evidence would the paper need to present to support this claim — what data would have produced the tree? (b) What bootstrap support would constitute "strong" evidence for the Cetacea-Hippopotamidae clade? (c) Why is this claim surprising compared to traditional morphological classification of whales as a separate order? (d) What does the claim imply about the appropriate use of the term "Artiodactyla" — should it now include whales, or should "whale" continue to be used as a separate category? Defend your answer. *Tests: integration of phylogenetic methodology, paraphyly recognition, and the practical question of naming.*

8. **The Asgard-archaeon hypothesis for eukaryote origin.** Recent molecular work has placed eukaryotes as a nested branch *within* the Asgard archaea — making Archaea a paraphyletic group as currently defined and eukaryotes phylogenetically a kind of archaeon. (a) What molecular evidence (which kinds of genes, which kinds of analyses) would be required to support this claim? (b) The proto-mitochondrion is hypothesized to have been an α-proteobacterium engulfed by the Asgard host. Explain what this means for the eukaryotic genome — what fraction of eukaryotic genes should phylogenetically place inside Archaea, and what fraction should phylogenetically place inside Bacteria, and why? (c) Does this hypothesis imply that the three-domain framework is wrong, or that it is approximately right with refinement? Explain. (d) The first cultured Asgard archaeon, *Prometheoarchaeum syntrophicum* (Imachi et al. 2020), showed long branching cellular protrusions. Why is this morphological feature relevant to the engulfment hypothesis? *Tests: integration of recent molecular evidence, paraphyly logic, endosymbiosis, and the structure of high-level classification.*

9. **Bootstrap support vs. posterior probability.** Two papers analyze the same dataset and reach different support values for the same internal node. Paper A uses maximum likelihood with 1,000 bootstrap replicates and reports bootstrap support of 78%. Paper B uses Bayesian inference with MCMC and reports posterior probability of 0.99 for the same clade. (a) Are bootstrap support and posterior probability the same kind of statistic? Explain the difference in what they measure. (b) Which value is the more conservative estimate of confidence in the clade? Justify. (c) Hillis and Bull (1993) showed that bootstrap support can be a poor predictor of accuracy when the substitution model is misspecified. What does this say about reading high bootstrap support as "the clade is definitely real"? (d) What would you want to see in a published phylogeny before treating a single high support value as decisive? *Tests: understanding two different kinds of support, the difference between confidence and correctness, and best-practice phylogenetics.*

**Challenge**

10. **The web-of-life argument.** Doolittle (1999) and others have argued that the "tree of life" is at best a misleading metaphor for prokaryotic evolution because horizontal gene transfer is so common. (a) Explain at the level of the mechanism why HGT breaks the tree assumption — what does it do that vertical descent does not? (b) Three pathways of HGT operate in bacteria: transformation, transduction, conjugation. Pick one and describe how it transfers genes between cells, including what specific gene categories are most often moved. (c) The Hug et al. (2016) tree of life used 16 ribosomal protein genes specifically to build a backbone tree. Why these genes and not others? What property of these genes makes them less subject to HGT? (d) Now consider a published claim: "*Streptococcus pneumoniae* and *Acinetobacter baumannii* both carry a tet(M) tetracycline-resistance gene that is 98% identical." Is the most parsimonious interpretation common ancestry of the gene, or HGT? Why? (e) Propose a quantitative test that would distinguish "deep tree of all bacteria" from "shallow tree of bacteria with extensive HGT-induced network structure." What signature in the data would each model produce? *Tests: integration of HGT mechanism, the meaning of homology in a network setting, and methodology for diagnosing HGT vs. vertical descent.*

11. **The K-Pg extinction in numbers.** The Chicxulub asteroid struck the Yucatán Peninsula 66 million years ago. The impact is estimated to have released energy equivalent to about 10²³ joules — comparable to about 10 billion Hiroshima bombs. The crater is approximately 180 km in diameter. The global aftermath included a sulfate aerosol haze, a brief global firestorm, ocean acidification from impact-released CO₂ and SO₂, and roughly 6 months to several years of darkened skies. (a) Approximately 75% of species went extinct. *All* non-avian dinosaurs went extinct, but birds and mammals survived. Propose a mechanism-level explanation for why these two groups survived when their dinosaur relatives did not. Consider body size, metabolic rate, diet flexibility, and habitat use. (b) Following the K-Pg, mammals radiated into the niches emptied by the extinction; primate lineages diverged within the first 10–20 million years of the Cenozoic. What does this tell you about the conditions enabling adaptive radiation (which Chapter 11 covered as a phenomenon — ecological opportunity, evolvable lineage, geographic structure)? (c) The current sixth extinction is roughly 100–1,000× the pre-human background rate but has not yet reached Big-Five magnitude. What kinds of measurements would tell you whether the extinction is accelerating, plateauing, or reversing? Propose at least three. (d) Mass extinctions are *contingent* — the radiation of mammals is contingent on the K-Pg, and the path that led to humans is contingent on that radiation. If the Chicxulub asteroid had missed, would humans exist? Defend your answer with reference to what you know about adaptive radiation and contingency in evolution. *Tests: integration of mass-extinction mechanisms, adaptive radiation, contingency in evolutionary history, and the structure of counterfactual reasoning in evolution.*

12. **The reflexive move — what kind of statistical inference is phylogenetic inference?** The chapter has claimed throughout that phylogenetics is "statistical inference about history." (a) Is the inference about a *single* tree (the one tree that was actually realized), or about a *distribution* of trees (a posterior given the data)? What is the practical difference? (b) Compare to the kind of inference a court does in a criminal trial: it tries to determine which of multiple possible histories actually occurred, with the standard "beyond reasonable doubt." Are phylogenetic methods using a comparable evidentiary standard, or a different one? (c) Bayesian posterior probability on a clade is, strictly, the probability of the clade *given the data and the model*. What happens to this probability if the model is wrong in a specific way (e.g., the substitution rates assumed in the model don't match the true rates)? (d) Some authors (e.g., Felsenstein 2004) argue that all phylogenetic methods are essentially likelihood methods under different assumptions about evolution. Is parsimony a likelihood method under an implicit model, and if so, what model? (e) The chapter says that "no fabricated citations" is a hard rule. Phylogenetic methods, applied to organisms that left no DNA evidence, must infer relationships from morphology alone — and morphology can be misleading. Should phylogenetic papers about extinct lineages carry larger explicit uncertainty than papers about extant lineages with DNA evidence? Why or why not? *Tests: reflexive examination of phylogenetics as an epistemological practice; the relationship between method, model, and what the inference can and cannot establish.*

---

## What the student builds

`12-phylogenetics.html` — a two-panel phylogenetic tree explorer.

**Panel 1 — Tree inference from sequence alignment.** Controls: select 5–10 species from a list (preset options: great apes, mammals, vertebrates, the three domains); display a short DNA sequence alignment (~200–500 bp from a conserved gene like *COX1* or 16S rRNA); choose inference method (parsimony, neighbor-joining, maximum likelihood); choose substitution model (Jukes-Cantor, K2P, HKY+Γ); set bootstrap replicates (100, 500, 1,000). Display: the pairwise distance matrix shown in the corner; the inferred tree shown with branch lengths in substitutions per site; bootstrap support shown at each internal node; topology comparison: switch between methods and see how the topology rearranges or stays the same; molecular-clock panel optional, where the student calibrates one node from a fossil age and uses the calibrated rate to date other nodes.

Students should be able to recover the great-ape topology ((Human, Chimp), Gorilla), Orangutan) with high bootstrap support and a chimp-human split of ~5–7 Ma under any reasonable substitution model. Students should also be able to see (a) why neighbor-joining is fast but cruder than ML, (b) why parsimony and ML occasionally disagree on the same data (long-branch attraction shows up when one terminal taxon has a much longer branch than the others), and (c) why the molecular clock is approximate (the student can deliberately accept or reject the constant-rate assumption and see how dating shifts).

**Panel 2 — Tree of life navigator.** A zoomable, clickable tree showing the major branches of life on a 4-Ga timescale. Controls: zoom level (continental view down to species-level branches), highlight options (mass extinctions marked as red bands on the timeline, GOE as a green band ~2.4 Ga, Cambrian explosion as a fanned-out radiation ~540 Ma, endosymbiosis events as merged branches at ~2 Ga and ~1.5 Ga). Display: the three-domain backbone (Bacteria, Archaea, Eukarya) with the (Archaea + Eukarya) sister relationship visible; major eukaryotic supergroups (Opisthokonta, Amoebozoa, Archaeplastida, SAR, Excavata) labeled; click on any internal node to see the inferred age, the synapomorphies that define the clade, and a brief description of the lineage's significance.

Stretch goal: an "Asgard archaea" visualization mode where the student can see how the eukaryotic branch is nested inside the Asgard radiation under the current best phylogenetic interpretation. A second stretch goal: an "HGT view" toggle in Panel 1 that overlays horizontal arrows showing inferred HGT events on the prokaryotic part of the tree, illustrating where the tree assumption breaks.

The clearest pedagogical demonstration is having the student start in Panel 1 with the great-ape alignment, recover the textbook ((H, C), G, O) topology with bootstrap > 95%, calibrate the molecular clock against the orangutan fossil split, and then jump to Panel 2 to see the great apes as a tiny branch on the eukaryotic side of the tree — 6–7 million years of human-chimp divergence sitting inside 4 billion years of total tree depth. The scale shift is the lesson: phylogenetic inference applies the same machinery from one-million-year-scale primate divergences up to four-billion-year-scale domain divergences, with the methodology consistent and only the uncertainty growing as you go deeper.

---

**What would change my mind.** A demonstration that one of the major phylogenetic conclusions invoked here — the three-domain framework, the Asgard origin of eukaryotes, the α-proteobacterial origin of mitochondria, the cyanobacterial origin of chloroplasts, the nesting of whales inside artiodactyls, the dinosaurian origin of birds — turned out to be systematically wrong under a more careful or larger analysis. The structural claim of the chapter is that phylogenetic inference reliably recovers evolutionary history with quantifiable uncertainty when the methods are applied carefully. If a major published phylogeny were systematically inverted by a methodology improvement — say, if the Asgard-archaeon-as-eukaryote-host hypothesis were undermined by an explicit demonstration that the eukaryotic signature proteins in Asgard genomes are in fact horizontally transferred from eukaryotes rather than ancestrally archaeal — the chapter's confidence in the phylogenetic method as historically accurate would need to be tempered. Recent work has consistently tightened the Asgard model rather than weakened it ([Imachi et al. 2020](https://www.nature.com/articles/s41586-019-1916-6); [Liu et al. 2021, *Nature* 593:553–557](https://www.nature.com/articles/s41586-021-03494-3), additional Asgard genomes with more eukaryotic-signature proteins), but the model remains an active research area and the details may yet shift.

**Still puzzling.** The rooting of the tree of life — *which* of the three domains diverged first, or whether the deepest split is truly between (Bacteria) and (Archaea + Eukarya) versus some other arrangement — is genuinely unresolved at the deepest level. Different gene sets, different substitution models, and different choices about how to handle the LUCA problem can produce different roots for the universal tree. The 2016 Weiss et al. LUCA reconstruction inferred LUCA features from genes shared between Bacteria and Archaea, but the root itself was assumed rather than derived. Some recent work has argued that LUCA may have been a more complex organism than previously thought ([Moody et al. 2024, *Nat Ecol Evol* 8:1654–1666](https://www.nature.com/articles/s41559-024-02461-1) [verify the citation]), others have argued the opposite. The honest answer is that the precise root of the universal tree, and the corresponding nature of LUCA, are at the limit of what current phylogenetic methods can resolve. The chapter's reading is the best current consensus; a different consensus might emerge in the next decade.

---

**Tags:** phylogenetics, tree-of-life, three-domains, Carl-Woese, Archaea, LUCA, endosymbiosis, mitochondria, chloroplasts, Lynn-Margulis, parsimony, maximum-likelihood, Bayesian-inference, neighbor-joining, bootstrap, Jukes-Cantor, molecular-clock, monophyletic, paraphyletic, polyphyletic, clade, synapomorphy, homoplasy, long-branch-attraction, Cambrian-explosion, mass-extinction, K-Pg, Chicxulub, end-Permian, Great-Oxidation-Event, horizontal-gene-transfer, web-of-life, Asgard-archaea, primate-phylogeny, COX1
