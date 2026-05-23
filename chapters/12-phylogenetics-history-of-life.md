# Chapter 12 — Phylogenetics and the History of Life: Reading the Tree from the Speciation Events That Built It

*The tree sees what the microscope cannot.*

---

In 1977, Carl Woese published a five-page paper reporting that the methanogens — the anaerobic microbes that respire by converting hydrogen and carbon dioxide into methane, found in cow rumens, swamp sediments, and termite guts — were not bacteria.

The methanogens *looked* like bacteria. Under a microscope they were small, simple, prokaryote-shaped cells without nuclei or organelles. Every textbook of microbiology placed them inside the prokaryotic kingdom alongside *Escherichia coli*. They had been classified as bacteria since the 1880s.

Woese's evidence was a single molecule. He had developed a laborious technique called oligonucleotide cataloguing — digesting 16S ribosomal RNA with a restriction enzyme, separating the fragments by two-dimensional electrophoresis, sequencing them by hand, and comparing the catalog across species. The 16S rRNA is the structural RNA at the heart of the small ribosomal subunit, about 1,540 nucleotides long, performing the same job in every prokaryotic ribosome on Earth. By 1976 he had cataloged about 60 species. The methanogens shared fewer 16S fragments with *E. coli* than *E. coli* shared with human mitochondrial rRNA. *The methanogens were as distantly related to typical bacteria as bacteria were to anything in the eukaryotic world.*

Life was not divided into prokaryotes and eukaryotes. Life was divided into three lineages of approximately equal evolutionary depth: the typical bacteria (Bacteria), the methanogens-and-relatives (Archaea), and the nucleated cells (Eukarya). The two-kingdom split that had structured biology for a century was wrong at the deepest level the tree had.

Woese met enormous resistance. Salvador Luria — a Nobel laureate, the dean of American molecular biology — reportedly called Woese personally to demand he stop talking about a third kingdom. Ernst Mayr dismissed the rRNA evidence as a single-molecule artifact. The textbooks did not rewrite their introductions until the 1990s.

But here is the thing to hold. *Woese never looked at a methanogen under a microscope and decided it was not a bacterium.* He could not have made the discovery that way. The methanogens are not visibly different from typical bacteria; their cells are the same size, the same shape, the same range of metabolic strategies as far as the microscope can see. The discovery was made by inference from a tree. Woese built a phylogenetic tree from 16S rRNA sequence data, applied the tree to the question "where do the methanogens sit?", and got back an answer that contradicted every textbook.

This is what phylogenetics does. It takes evidence that is local and present-tense — sequences in a database, characters scored on living specimens, fossils dated in stratigraphic columns — and infers history. Every branch on a phylogenetic tree is a hypothesis about who descended from whom. When you do the inference well, the tree tells you things no one knew. The same methodology that revealed a third domain of life has told us that whales are nested inside the artiodactyls (closer to hippos than to any fish), that birds are dinosaurs, that fungi are closer to animals than to plants, that the human genome contains about 2% Neanderthal DNA from a hybridization event roughly 60,000 years ago. None of these are visible to inspection. All of them are visible to the inference.

---

## How to read a tree without misreading it

A phylogenetic tree is a branching diagram representing inferred evolutionary relationships. Six features carry information; misread any one and you have made a wrong claim about the history.

**Tips** are the endpoints — extant species, extinct species with fossils, or sequences in a database. They are the data the tree is built from.

**Internal nodes** are the branch points. Each represents a hypothetical common ancestor — a population that existed at some past time and gave rise to the descendants at the two branches emerging from it. The human-chimp node represents the African great-ape population from which both *Pan troglodytes* and *Homo sapiens* descend, about 6 million years ago.

**Branches** connect nodes to nodes or to tips. Branch length can mean elapsed time (a chronogram), amount of evolutionary change (a phylogram), or nothing (a cladogram, where only topology matters). Always check the figure caption.

**The root** anchors the tree's direction, usually by including an outgroup — a taxon known to lie outside the group of interest, which polarizes the tree and tells you which nodes are older.

**Sister groups** are two taxa or clades sharing a more recent common ancestor with each other than with anything else in the tree. Chimpanzees and bonobos are sisters; humans are the sister of the (chimpanzees + bonobos) clade, not the sister of chimpanzees alone.

**Clades** — each an ancestor plus all of its descendants — are the natural units the tree picks out. Mammals are a clade. Vertebrates are a clade. A clade is distinguished by **synapomorphies** — shared derived characters that originated in the most recent common ancestor and were inherited by every descendant.

Only **monophyletic groups** (clades — ancestor plus all descendants) are the natural units of evolutionary biology. **Paraphyletic groups** drop some descendants: traditional "reptiles" (lizards, snakes, turtles, crocodiles, excluding birds) is paraphyletic because crocodiles are more closely related to birds than to lizards; the natural group is Reptilia including birds. "Fish" is paraphyletic because the common ancestor of all fish is also the ancestor of all tetrapods, and lobe-finned fish are more closely related to you than to a ray-finned fish. **Polyphyletic groups** gather organisms from different ancestors by convergent similarity: "warm-blooded animals" groups mammals and birds together, but endothermy evolved independently in both lineages.

Three misreadings recur constantly enough to name explicitly. *Leftmost means most primitive* — wrong; trees can be drawn with tips in any order; rotating branches around a node changes nothing. *Humans evolved from chimpanzees* — wrong; humans and chimps share a common ancestor from which both lineages have been diverging for 6 million years; modern chimps are not our ancestors. *Older lineage means more primitive organism* — wrong; sponges and humans have been evolving for the same total elapsed time since the protistan ancestor of all animals; sponges changed less morphologically, but their genomes have accumulated mutations at comparable rates.

<!-- → [INFOGRAPHIC: annotated phylogenetic tree diagram showing all six vocabulary items — tips (labeled), internal nodes (labeled as "hypothetical common ancestor"), branches (one labeled as chronogram with scale bar, one labeled as phylogram with substitution scale), root (labeled with outgroup arrow), sister group pair circled and labeled, and one clade shaded and labeled with a synapomorphy listed. A second smaller panel shows three misreadings: (1) two identical trees with tips in different left-right order demonstrating that rotation does not change relationships; (2) human and chimp on a tree with the node labeled "shared common ancestor ~6 Ma" and an arrow explicitly labeled "not 'humans descended from chimps'"; (3) sponge and human branch lengths equal on a time-scaled tree. Student should be able to apply each label and identify each misreading.] -->

---

## Three ways to build a tree

**Parsimony** asks: which tree requires the fewest evolutionary changes? For each possible tree topology, score it by counting the minimum number of character-state changes across all branches needed to explain the observed distribution. The tree with the lowest score is preferred. The logic is Occam's razor applied to evolutionary inference — one common origin of a shared character is simpler than two independent origins.

Where parsimony fails: when two lineages independently experience high rates of evolution on long branches, parsimony can mistakenly group them together based on shared convergent changes — a failure mode called **long-branch attraction**. Parsimony cannot tell the difference between "similar because of common ancestry" (homology) and "similar because of independent evolution" (homoplasy), and it makes that distinction badly when branches are long.

**Maximum likelihood** carries an explicit model of how sequences evolve — substitution rates between specific nucleotides, rate variation across sites — and asks which tree topology and branch lengths make the observed data most probable. The simplest model (Jukes-Cantor) treats all twelve possible nucleotide substitutions as equally likely. More elaborate models allow transitions to differ from transversions, allow rate variation across sites by a gamma distribution, allow different base frequencies. Maximum likelihood handles long-branch attraction better than parsimony because the model explicitly accounts for the elevated probability of convergence on long branches.

**Bayesian inference** treats the tree, the branch lengths, and the substitution model parameters as random variables, places prior probability distributions on each, and computes the posterior distribution over trees. Because the posterior is not computable in closed form for any large dataset, it uses Markov chain Monte Carlo sampling — running for millions of steps, drawing trees from the posterior, summarizing the posterior by reporting the consensus topology and the posterior probability on each node (the fraction of sampled trees containing that clade). A node with posterior probability 0.95 is found in 95% of the posterior sample; this is explicit probabilistic uncertainty quantification in a way the ML bootstrap is not.

**Bootstrap** assesses how robustly the data support each node. Resample the alignment sites with replacement to create a new alignment of the same length; build a tree from the resampled alignment; record which clades appear; repeat 1,000 times; the bootstrap support for a node is the fraction of resampled trees containing that clade. Above 70% is moderate support; above 95% is very strong. Bootstrap support is not the same as the probability the clade is correct — under model misspecification, you can get high bootstrap support for a wrong clade — but it is the standard report of data robustness.

---

## A worked example — building a primate tree and calibrating the clock

Take four primate species — human, chimpanzee, gorilla, orangutan — and a 250-base-pair piece of the mitochondrial *COX1* gene. Mitochondrial sequences evolve roughly 10× faster than nuclear sequences and accumulate enough variation in a few million years to resolve great-ape relationships. *COX1* is also the standard barcode locus used for animal species identification, so it is well-curated in GenBank.

Here are illustrative pairwise differences in the range typical for great-ape *COX1*:

| Pair | Observed differences in 250 bp | Raw p-distance |
|---|---:|---:|
| Human – Chimp | 7 | 0.028 |
| Human – Gorilla | 11 | 0.044 |
| Human – Orangutan | 22 | 0.088 |
| Chimp – Gorilla | 11 | 0.044 |
| Chimp – Orangutan | 22 | 0.088 |
| Gorilla – Orangutan | 22 | 0.088 |

<!-- → [TABLE: extended primate distance table — two additional columns added to the existing table: "Jukes-Cantor corrected distance d_JC" and "% inflation over raw p". Values computed from the formula: Human-Chimp d_JC ≈ 0.0285 (+1.8%); Human-Gorilla ≈ 0.0454 (+3.2%); Human-Orangutan ≈ 0.094 (+6.8%). Student should see that the correction is negligible at low divergence and grows substantially at higher divergence — motivating why raw p-distances fail at deeper evolutionary comparisons.] -->

### Step 1 — correct for multiple hits

The raw p-distance underestimates true divergence because, over evolutionary time, some sites have been hit more than once. A site that mutated A→C→A looks identical between species today but represents two substitutions. A site that mutated A→C→G looks like one change but is two. The longer the divergence time, the worse the underestimate.

The Jukes-Cantor correction:

$$d_{JC} = -\frac{3}{4} \ln\!\left(1 - \frac{4}{3}p\right)$$

For Human–Chimp: `p = 0.028`. Compute `1 − (4/3)(0.028) = 0.963`. Take `ln(0.963) = −0.038`. Multiply by `−3/4`: `d_JC = 0.0285`. Very close to raw p at this low divergence.

For Human–Orangutan: `p = 0.088`. Compute `1 − (4/3)(0.088) = 0.883`. Take `ln(0.883) = −0.125`. Multiply by `−3/4`: `d_JC = 0.094`. About 6% higher than the raw p-distance; the multiple-hit correction has started to matter.

At much deeper distances — say, p ≈ 0.45 comparing humans to fish at the same gene — the Jukes-Cantor correction inflates the estimate from 0.45 to roughly 0.85, nearly double. This is the central reason raw p-distances are not used in modern phylogenetics at evolutionary depths beyond a few tens of millions of years.

### Step 2 — build the neighbor-joining tree

Neighbor-joining takes a distance matrix and iteratively joins the closest pair, computing an averaged distance from that new internal node to remaining taxa, and repeating. Applied to the corrected matrix, it picks Human and Chimp (closest at 0.029) first, then joins Gorilla to the Human-Chimp node, then roots with Orangutan. The result:

```
(((Human, Chimp), Gorilla), Orangutan)
```

Human and Chimp sister to each other, Gorilla sister to the (Human, Chimp) clade, Orangutan as the outgroup. This is the textbook great-ape topology, recovered from a single 250-bp gene. Published trees using thousands of base pairs from dozens of genes converge on the same topology with bootstrap support of ~100% at every node.

<!-- → [IMAGE: neighbor-joining tree of (((Human, Chimp), Gorilla), Orangutan) — drawn as a phylogram with branch lengths proportional to JC-corrected distances; Human-Chimp branch short (~0.014 each), Gorilla branch slightly longer, Orangutan branch longest; bootstrap support values shown at each internal node (~98% for Human-Chimp clade, ~100% for Human-Chimp-Gorilla clade, ~100% for Orangutan as outgroup); scale bar in substitutions per site. Student should see how branch lengths encode the relative distances and how support values map to node confidence.] -->

### Step 3 — calibrate the molecular clock

The orangutan–African ape split is calibrated to approximately 14 million years ago from Miocene fossil great apes — particularly *Sivapithecus* from the Siwalik formation of Pakistan, which shows the characteristic orangutan facial morphology and dates to about 12–13 Ma.

The corrected distance from the (Human, Chimp, Gorilla) clade to orangutan is `d_JC ≈ 0.094`. This distance accumulated along both lineages from the common ancestor; the per-lineage distance is half the total.

$$r = \frac{d}{2t} = \frac{0.094}{2 \times 14 \times 10^6\,\text{yr}} \approx 3.4 \times 10^{-9}\,\text{substitutions per site per year}$$

Now use the calibrated rate to date the Human–Chimp split. `d_JC ≈ 0.029`:

$$t = \frac{d}{2r} = \frac{0.029}{2 \times 3.4 \times 10^{-9}} \approx 4.3 \times 10^6\,\text{years}$$

This ~4–5 Ma estimate is somewhat shorter than the modern best estimate of 6–7 Ma for the human-chimp split. The undershoot illustrates a real limitation: a single 250-bp gene gives a noisy estimate, and the molecular clock is an approximation — substitution rates vary across genes, lineages, and time. Published estimates use hundreds of genes with relaxed-clock models that allow rate variation across branches, and multiple fossil calibrations; they produce the 6–7 Ma estimate that single-gene arithmetic only approximately recovers.

Now extend the calibrated rate to predict a deeper divergence. Macaques (Old World monkeys) diverged from apes roughly 25–30 Ma based on fossils. Predicted divergence per site:

$$d = 2 \times 3.4 \times 10^{-9} \times 27.5 \times 10^6 \approx 0.19\,\text{substitutions per site}$$

Observed human-macaque *COX1* divergences are in the range 14–18% uncorrected (corresponding to roughly 0.17–0.22 corrected). The calibrated clock recovers the macaque divergence approximately, with spread from clock noise and genuine rate variation on the deeper catarrhine branches.

The lesson: phylogenetic inference is statistical inference about history. You start with sequence differences in the present, apply explicit models of how those differences accumulated, and recover both the branching pattern and the timing of the past — with quantifiable uncertainty. The Jukes-Cantor calculation, the neighbor-joining topology, and the clock calibration all have error bars; the correct answer from modern multi-gene analyses falls within those bars.

---

## The three domains and why Archaea matter

Woese's tree forced the three-domain classification into existence. The framework formalized in 1990 by Woese, Kandler, and Wheelis has held under every subsequent reanalysis, with one major refinement: the Archaea are not equidistant from the other two domains. *Archaea are sisters to Eukarya.* The deepest split is between Bacteria on one side and (Archaea + Eukarya) on the other.

Evidence that Archaea and Eukarya are sisters comes from translation machinery — RNA polymerase subunits, initiation factors, ribosomal proteins — that is more similar between Archaea and Eukarya than between either and Bacteria. Archaeal RNA polymerase has 11–13 subunits; eukaryotic RNA polymerase has 12–17; bacterial RNA polymerase has 5. When 30 genes present in essentially every cellular organism are analyzed jointly, the consensus tree robustly places Archaea and Eukarya as sisters.

Then came the Asgard archaea. Starting around 2015, metagenomic work on deep marine sediments recovered sequences from a superphylum of uncultured archaea — *Lokiarchaeota*, *Thorarchaeota*, *Odinarchaeota*, *Heimdallarchaeota*, named for Norse mythology because the first samples came from a hydrothermal vent near Loki's Castle on the Mid-Atlantic Ridge. These organisms encode a remarkable number of eukaryotic signature proteins: actin-related cytoskeletal proteins, small GTPases, ubiquitin-like proteins, ESCRT-III homologs. When universal-gene trees are built with Asgard sequences, the Eukarya emerge from *inside* the Asgard radiation — not as the sister of all Archaea, but as a nested branch within Archaea. The first cultured Asgard archaeon, *Prometheoarchaeum syntrophicum*, isolated in 2019–2020 from deep-sea sediment, showed long branching cellular protrusions consistent with the cellular architecture proposed for the eukaryote-originating event.

The current best reading: eukaryotes are derived from Archaea — specifically the Asgard lineage — through an early endosymbiotic event in which an archaeal cell engulfed a bacterium (the proto-mitochondrion) and the two cells fused into the eukaryotic ancestor about 2 billion years ago.

---

## Endosymbiosis — how the eukaryotic cell acquired its organelles

Inside the eukaryotic cell, the deepest history is recorded not by the nuclear genome alone but by the organelles. Lynn Margulis's 1967 paper — rejected by about fifteen journals before publication — proposed that mitochondria are descended from a free-living α-proteobacterium engulfed by a proto-eukaryotic host cell roughly 1.5–2 billion years ago.

The evidence is unusually direct.

**Double membranes.** Mitochondria have two membranes. The outer membrane is derived from the original phagocytic vesicle that engulfed the bacterium; the inner membrane is the original bacterial plasma membrane, including its characteristic cardiolipin — a lipid otherwise found mainly in bacterial membranes. The two-membrane architecture is the engulfment event preserved in the cell.

**Circular DNA.** Human mitochondrial DNA is a single circular molecule of about 16,569 base pairs, encoding 13 proteins, 22 tRNAs, and 2 rRNAs. The circular organization is bacterial; the small size reflects gene loss to the nucleus over two billion years of integration.

**70S ribosomes.** Mitochondrial ribosomes are 70S, like bacterial ribosomes — not 80S like the cytoplasmic eukaryotic ribosomes. This is why aminoglycosides, tetracyclines, chloramphenicol, and macrolides (which target the 70S ribosome) can have mitochondrial off-target effects in eukaryotic patients. The fact that mitochondrial ribosomes are bacterial-style ribosomes is direct structural evidence of the bacterial ancestry of the organelle.

**Binary fission.** Mitochondria divide by splitting in two, exactly as bacteria do, and are partitioned between daughter cells during host-cell division. Cells that lose all mitochondria cannot make new ones — mitochondria are heritable in the sense that bacteria are heritable.

**rRNA phylogenetic placement.** When mitochondrial rRNA is included in a tree built from 16S/18S rRNA sequences across all three domains, it branches *inside* the Bacteria, specifically in the α-proteobacteria, alongside *Rickettsia*. The mitochondrion is not a generic bacterium; it is a specific kind of α-proteobacterium that has been a host-cell resident for two billion years.

The same logic applies in parallel to chloroplasts and cyanobacteria. Chloroplast rRNA places them inside the Cyanobacteria; chloroplasts have double membranes, circular DNA, 70S ribosomes, and divide by binary fission. They are descended from a cyanobacterial engulfment event in the lineage leading to plants, about 1–1.5 billion years ago.

The eukaryotic cell is, mechanically, a chimera. It carries genes of three ancestries: a host genome from the Asgard archaea, a mitochondrial component from an α-proteobacterium, and (in plants and algae) a chloroplast component from a cyanobacterium. The tree-of-life metaphor breaks down at the eukaryotic root for this reason.

<!-- → [INFOGRAPHIC: endosymbiotic origin of mitochondria — left panel shows a free-living α-proteobacterium approaching a proto-eukaryotic (Asgard-derived) host cell; center panel shows the engulfment event with the original bacterium inside a double membrane (outer = phagocytic vesicle, inner = original bacterial plasma membrane, inner membrane highlighted with cardiolipin); right panel shows the modern mitochondrion with all five lines of evidence labeled: (1) double membranes, (2) circular DNA genome, (3) 70S ribosome subunits, (4) binary fission arrow, (5) phylogenetic placement inside α-proteobacteria on a small rRNA tree inset. Student should see each evidence type connected to its mechanistic basis.] -->

---

## A four-billion-year timeline

The dates carry uncertainty — tens to hundreds of millions of years for events more than a billion years ago — but the sequence is robustly supported by radiometric dating, isotopic signatures, molecular-clock estimates, and biomarker fossils.

**~4 Ga** — Earth forms. By about 4.4 Ga the surface had cooled enough to allow liquid water. The earliest accepted biological evidence is graphite inclusions in 3.7-billion-year-old Greenland sedimentary rocks with isotopic carbon signatures consistent with biology. The honest reading: life arose somewhere between 4.2 and 3.5 Ga; we cannot pin the date more precisely.

**~3.5 Ga** — LUCA, the last universal common ancestor. Not a single individual, but a community of related cells from which the bacterial, archaeal, and eukaryotic lineages all derive. Stromatolites from the Pilbara region of Western Australia record layered microbial mats from this era. Reconstructing the universally shared genes gives a partial portrait: LUCA had a DNA genome, a ribosome with essentially the universal genetic code, core metabolic pathways, and a lipid bilayer membrane. Weiss and colleagues' 2016 reconstruction from 355 protein families suggests an anaerobic chemolithoautotroph using H₂ and CO₂ as energy and carbon sources — consistent with a hydrothermal vent environment.

**~2.7 Ga** — Oxygenic photosynthesis evolves in cyanobacteria. Before cyanobacteria, photosynthesis was anoxygenic, using electron donors other than water. Cyanobacteria evolved water-splitting Photosystem II, enabling an effectively inexhaustible electron donor and the release of O₂ as a waste product.

**~2.4 Ga** — The Great Oxidation Event. Atmospheric oxygen rises from approximately zero to roughly 1–2% of modern levels over a few hundred million years, as cyanobacterial production overwhelms abiotic sinks. The consequences: aerobic respiration (extracting roughly 18× more energy from glucose than fermentation) becomes available; the ozone layer begins to form; the surface becomes habitable to a new tier of organisms. Anaerobic life retreats to subsurface and anoxic niches where much of it still lives.

**~2 Ga** — Eukaryotes appear, from the Asgard-archaeon + α-proteobacterium fusion.

**~1.5–1 Ga** — Chloroplasts evolve; major eukaryotic lineages diversify.

**~800–600 Ma** — Multicellularity evolves independently in many eukaryotic lineages. Modern phylogenetic work supports at least 25–30 independent origins — in plants, animals, fungi, brown algae, red algae, multiple green algal lineages, slime molds. The conditions enabling the transition (division of labor across cells, cell-cell adhesion, cell-cell signaling) appear to have been available in multiple lineages.

**~540–520 Ma** — The Cambrian explosion. Most major animal phyla appear in the fossil record over a window of about 10–30 million years. The Burgess Shale (~508 Ma) and the Chengjiang biota (~520 Ma) preserve arthropods, mollusks, brachiopods, echinoderms, chordates, and a remarkable diversity of stem-group lineages that do not survive. Cause: probably a combination of Hox-gene duplication enabling new body-plan diversity, atmospheric oxygen rising to enable larger active animals, and evolution of mineralized skeletons making the fossil record possible for the first time.

**Five mass extinctions.** End-Ordovician (~440 Ma), ~85% of marine species lost, cause: glaciation and sea-level fall. End-Devonian (~370 Ma), ~75% of species lost, cause: contested combination of marine anoxia and climate cooling. End-Permian (~252 Ma), *~96% of marine species lost* — the largest mass extinction in Earth history — cause: massive Siberian Traps volcanism, rapid global warming, ocean acidification, ocean anoxia; recovery took roughly 5–10 million years. End-Triassic (~200 Ma), ~50% of species lost, cause: volcanism associated with Pangaea's breakup. End-Cretaceous (~66 Ma), ~75% of species lost, including all non-avian dinosaurs and all ammonites, cause: the Chicxulub asteroid impact, a roughly 10-km-diameter asteroid striking the Yucatán Peninsula, ejecting a global dust-and-sulfate aerosol cloud that blocked sunlight for months to years and killed photosynthesis worldwide. Mammals — small nocturnal generalists for 150 million years under dinosaur dominance — radiated into the empty niches over the next 10 million years. The ancestral primate lineages that eventually produced *Homo sapiens* are descended from survivors of that extinction.

**Present** — The Sixth Extinction, human-driven. Habitat destruction, climate change, overharvesting, and species introductions have produced background extinction rates 100–1,000× the pre-human rates inferred from the fossil record. Whether the current biodiversity loss reaches Big-Five magnitude depends on next-century trajectories.

<!-- → [CHART: four-billion-year timeline of life — horizontal axis from 4 Ga to present (right = present); key events marked as vertical lines or bands with labels: ~4 Ga Earth forms; ~3.5 Ga LUCA/stromatolites; ~2.7 Ga oxygenic photosynthesis; ~2.4 Ga Great Oxidation Event (shaded green band); ~2.0 Ga eukaryotes; ~1.5–1 Ga chloroplasts; ~0.8–0.6 Ga multicellularity; ~0.54 Ga Cambrian explosion (shaded orange fan); five mass extinctions marked as red vertical bars with approximate % species loss labeled (85%, 75%, 96%, 50%, 75%); present marked with a thin red line for Sixth Extinction. Above the timeline, three domain labels (Bacteria, Archaea, Eukarya) span from their earliest evidence to the present. Student should use this chart as a reference map for dating major events.] -->

---

## When the tree breaks — horizontal gene transfer

The tree metaphor works well for sexually reproducing eukaryotes, where genes are inherited vertically from two parents and lineages diverge by speciation. The metaphor breaks for prokaryotes.

In Bacteria and Archaea, genes move between organisms through three mechanisms that have nothing to do with reproduction. **Transformation** — a cell takes up free DNA from its environment and integrates it by homologous recombination. **Transduction** — a bacteriophage accidentally packages some host DNA and injects it into a new cell. **Conjugation** — two bacteria physically connect via a pilus, and one transfers a plasmid carrying genes for antibiotic resistance, virulence, or specialized metabolism to the other.

These mechanisms move genes between cells that are not in a parent-offspring relationship, and they do so frequently. The fraction of bacterial genomes acquired by horizontal gene transfer averages 5–20% in many species, with pathogens that have accumulated antibiotic resistance genes much higher. The consequence for phylogenetic reconstruction: different genes in the same bacterial genome can have different evolutionary histories. Gene A places species X and Y as sisters; gene B places species X and Z as sisters; gene C places species Y and Z as sisters. The conflict is not a methodological problem to be resolved — it is the real biology. The "tree of life" for prokaryotes is better described as a **web of life**, with reticulate connections between lineages layered over a vertical descent scaffold.

The pragmatic compromise modern phylogenetics adopts: build the species tree from a *core* of genes that are essential, conserved, and rarely transferred — ribosomal RNAs are the classic example, and the 2016 Hug et al. tree of life used 16 ribosomal protein genes across 3,083 genomes for exactly this reason — and treat accessory genes (metabolism, resistance, virulence) as a separate network analysis. The tree model is a good approximation for the major branches: the three domains, the major eukaryotic supergroups, the major animal phyla. For the fine structure within bacteria, or for the deep evolutionary history below LUCA, the tree is a coarse approximation of a more complicated network.

The HGT problem reaches into eukaryotes too. Endosymbiosis is itself a form of massive horizontal transfer — the proto-mitochondrion brought roughly 2,000 genes into the eukaryotic ancestor, most of which subsequently transferred from the mitochondrion to the nucleus. Endogenous retroviruses are recent horizontal transfers in vertebrate genomes. The Neanderthal-modern-human admixture documented at roughly 2% of the non-African human genome (Chapter 11) is exactly this kind of localized horizontal transfer between recently-diverged lineages, producing phylogenetic conflict at specific loci.

<!-- → [INFOGRAPHIC: tree vs. web contrast — left panel: clean bifurcating tree for three bacterial lineages A, B, C with vertical descent only; right panel: same three lineages but with horizontal arrows added between A and B (transformation event, resistance gene), between B and C (conjugation event, plasmid), creating a network with reticulations. A gene-tree panel below shows how gene X has a different tree topology from the species backbone because it was horizontally transferred. Annotation: which genes stay treelike (ribosomal RNAs, essential metabolic core) versus which are frequently transferred (antibiotic resistance, virulence factors, specialized metabolism). Student should see why the tree metaphor works for the core and breaks for the accessory genome.] -->

---

## Exercises

**Warm-up**

1. **Tree vocabulary.** Examine the tree `(((Human, Chimp), Gorilla), Orangutan)` written in Newick notation. (a) Which pair of taxa is a sister group? (b) Which node represents the most recent common ancestor of all great apes in the tree? (c) Is "great apes excluding humans" (i.e., chimps + gorillas + orangutans) a monophyletic, paraphyletic, or polyphyletic group? Explain why. (d) If you redraw this tree with Orangutan on the left and Human on the right, does the topology change? (e) What kind of evidence would place the root between Orangutan and the rest, making Orangutan the outgroup? *Tests: tree-reading vocabulary across all six structural features; monophyletic/paraphyletic classification; understanding that branch rotation does not change topology.*

2. **Classify the groups.** For each of the following, state whether it is monophyletic, paraphyletic, or polyphyletic, and explain in one sentence: (a) Mammals; (b) Reptiles (lizards, snakes, turtles, crocodiles, excluding birds); (c) "Fish" (all aquatic, gill-breathing vertebrates, excluding tetrapods); (d) Endotherms (mammals + birds); (e) Animals; (f) Vertebrates. *Tests: systematic application of the three-group classification to familiar taxa.*

3. **The three methods.** For each of the following descriptions, identify whether it applies to parsimony, maximum likelihood, or Bayesian inference: (a) "We prefer the tree requiring the fewest evolutionary changes across all characters." (b) "The support value at each node is the fraction of resampled datasets that recovered that clade." (c) "The support value at each node is the probability of the clade given the data and the model." (d) "Long-branch attraction is a known failure mode because the method has no explicit model of substitution rate variation." (e) "The GTR+Γ model is one example of the type of assumption this approach makes explicit." *Tests: distinguishing the three main inference methods and the bootstrap.*

**Application**

4. **Jukes-Cantor correction.** Two species show a p-distance of 0.15 over a 500-bp alignment. (a) Compute the Jukes-Cantor corrected distance `d_JC = −(3/4) ln(1 − (4/3)p)`. (b) By what percentage does the correction inflate the estimate relative to the raw p-distance? (c) Now compute d_JC for p = 0.40. (d) At what value of p does the Jukes-Cantor formula become undefined (the argument of the logarithm reaches zero or goes negative)? What does this say about the limits of the multiple-hit correction at very high divergence? (e) Why is raw p-distance adequate at 1% divergence but misleading at 45%? *Tests: mechanical use of the JC formula; understanding why multiple hits bias uncorrected distances.*

5. **Molecular clock calibration.** Two bird species have a Jukes-Cantor distance of `d = 0.055` at *COX1*. A fossil-calibrated divergence between the bird and a lizard outgroup (`d = 0.21`) occurred about 240 million years ago. (a) Compute the substitution rate *r* from the lizard calibration. (b) Use the calibrated rate to estimate the divergence time of the two bird species. (c) A rodent lineage evolves at approximately 3× the bird rate per year at the same gene. If you applied the bird-calibrated rate to two rodent species with `d = 0.08`, would you overestimate or underestimate their divergence time? By approximately how much? (d) Name one technique modern phylogenetics uses to accommodate this kind of rate variation across lineages. *Tests: clock calibration arithmetic; the rate-constancy assumption and its violations.*

6. **Parsimony scoring.** You have three taxa (A, B, C) and one binary character: A = 1, B = 1, C = 0. Three possible rooted topologies are ((A,B),C), ((A,C),B), and ((B,C),A). (a) Score each topology (minimum changes required to explain the data). (b) Which topology is most parsimonious, and why does the shared character between A and B favor it? (c) Suppose the character state pattern instead is A = 1, B = 0, C = 1. Re-score all three topologies. Which is now most parsimonious? (d) In a dataset of 500 characters, 30 are "phylogenetically informative" (showing shared derived states in at least two non-sister taxa). The rest are autapomorphies or constant characters. Explain why only the 30 informative characters determine tree topology under parsimony, while autapomorphies add only noise. *Tests: hand-scoring parsimony; understanding which characters contain topological signal.*

**Synthesis**

7. **Endosymbiosis, five lines of evidence.** Describe each of the five named lines of evidence for the endosymbiotic origin of mitochondria. For each, state (a) what is observed, (b) what the observation implies about the ancestry of the organelle, and (c) what alternative hypothesis (if any) the evidence rules out. Then answer: why is the combination of all five lines of evidence stronger than any one alone? *Tests: integration of the five-evidence argument; understanding why convergent evidence from independent sources makes a hypothesis robust.*

8. **Reading Woese's tree.** The Asgard archaea discovery changed the three-domain tree from "Eukarya sister to Archaea" to "Eukarya nested within Archaea." (a) What does this change imply about whether the three-domain framework is monophyletic, paraphyletic, or polyphyletic for Archaea? (b) If Eukarya are nested within Asgard archaea, what fraction of the eukaryotic genome would you predict to have phylogenetic affinity with Archaea versus with Bacteria, and why? (c) The first cultured Asgard archaeon, *Prometheoarchaeum syntrophicum*, showed long branching cellular protrusions. Why is this morphological feature relevant to the hypothesis that a proto-eukaryote originated from an Asgard host engulfing a bacterial endosymbiont? (d) Name one additional prediction you would make about Asgard archaea if the eukaryote-inside-Asgard hypothesis is correct, that has not yet been confirmed. *Tests: integrating the three-domain update with paraphyly logic, genomic predictions, and hypothesis-testing reasoning.*

9. **The mass extinction record.** A paleontologist reports a new fossil bed with evidence of a major marine extinction: approximately 60% of species disappear at a single stratigraphic horizon, the event correlates with a large igneous province (a flood basalt eruption), and the overlying sediments show evidence of ocean acidification. (a) Which of the Big Five mass extinctions does this most closely resemble in cause and magnitude? (b) The recovery fauna (the taxa that reradiate after the extinction) is dominated by opportunistic generalists with broad ecological tolerance. Predict how long recovery to pre-extinction diversity levels takes, citing the pattern from the analogous historical event. (c) If instead the extinction horizon showed an iridium anomaly and shocked-quartz grains, what would change about your causal interpretation? (d) The Sixth Extinction lacks a single stratigraphic horizon because it is ongoing. What geological proxy would a future paleontologist 50 million years from now use to identify the onset of the Sixth Extinction in the fossil record? *Tests: applying knowledge of extinction causes and patterns to a novel scenario; reasoning about both historical and ongoing extinction events.*

**Challenge**

10. **The web of life, quantitatively.** A researcher sequences 200 bacterial genomes and builds gene trees for 500 individual genes. She finds that 80% of gene trees are roughly concordant with the species backbone tree built from 16 ribosomal protein genes, but 20% of gene trees place species in dramatically different positions — sometimes grouping species from very different phyla as sisters. (a) Explain at the mechanism level why 20% of genes show trees that conflict with the backbone tree. Name the three HGT mechanisms and predict which one is most likely responsible for resistance-gene trees conflicting, versus metabolic-gene trees conflicting. (b) The researcher wants to use her data to estimate the rate of HGT in this bacterial community. Propose a quantitative definition of "gene successfully transferred" and explain what data would establish that a gene conflict is due to HGT rather than incomplete lineage sorting or convergent evolution. (c) She finds that ribosomal protein genes are 99% concordant with the backbone while metabolic genes are only 60% concordant. What property of ribosomal protein genes makes them resistant to HGT? (d) Now she discovers that two distantly related bacteria (different phyla) share a 99%-identical antibiotic resistance gene. Evaluate: is this more likely to be common ancestry or recent HGT? Compute the expected Jukes-Cantor distance between two genes that genuinely diverged 500 million years ago at a bacterial substitution rate of ~10⁻⁹ per site per year, and compare to the observed 1% divergence. *Tests: integrating HGT mechanisms, quantitative divergence expectations, and the tree-vs-web distinction in a research-design context.*

---

Phylogenetics is statistical inference about history. You start with sequences in the present, apply explicit models of accumulation, and recover the past with quantifiable uncertainty. Carl Woese's 1977 tree concluded from 16S rRNA sequences that a third domain of life existed — a conclusion that contradicted every textbook but turned out to be correct. The methodology that produced that conclusion also tells us that whales are nested inside the artiodactyls, that birds are dinosaurs, that eukaryotes are derived from an archaeal lineage related to the Asgard archaea. None of these are visible to morphological inspection. All of them are visible to the inference.

The limits are real. The molecular clock is an approximation that breaks across genes, lineages, and timescales. Single-gene estimates are noisy; large multi-gene datasets with relaxed-clock models are the modern standard. At the deepest evolutionary distances — the bacteria-eukaryote split, the root of the universal tree — the molecular clock is so uncertain that estimates span hundreds of millions of years. Horizontal gene transfer makes the tree a web at the prokaryotic scale.

Neither limitation undermines the methodology. The uncertainty is quantifiable, and the quantified uncertainty is itself information. A 95% bootstrap on the (Human, Chimp) sister relationship means the data robustly distinguish that relationship from any alternative under perturbation of the dataset. A 6 ± 1 Ma estimate for the human-chimp divergence means something — the 95% confidence interval does not include 2 Ma or 15 Ma. The methods infer the past; the uncertainty tells you how much to trust the inference at each depth.

The tree of life — from LUCA at 3.5 Ga, through the three domains, through the Cambrian explosion and five mass extinctions, through the great ape radiation and the 7-generation Big Bird lineage on Daphne Major — is a single history, read from the same molecular evidence at every scale. Chapter 11 produced the speciation events. This chapter strings them into the tree. The next question is what kinds of changes accumulated along the branches: which mutations were selected, which were neutral, which drove morphological change, and how small changes in gene regulation produced the extraordinary morphological diversity of life. That is Chapter 13.

---

*The tree tells you who descended from whom. The molecular evolution chapter will tell you what changed, where, and why those changes mattered.*
