# Chapter 05 — From Gene to Protein: Transcription and Translation

**Suggested titles:**
- *One Base, One Amino Acid, One Disease — Tracing Sickle Cell Through the Central Dogma*
- *Why a Bacterium Can Make Human Insulin, and Why an mRNA Vaccine Works at All*
- *The Code That Has Not Changed in Four Billion Years — and the Three Machines That Read It*

---

**TL;DR.** DNA stores information; RNA carries it; proteins do the work. The two steps between them — transcription (DNA → RNA) and translation (RNA → protein) — are run by two distinct molecular machines reading the same code in opposite directions. RNA polymerase walks a DNA template at roughly 50 nucleotides per second, building a single-stranded copy whose chemistry is just unstable enough to be disposable. In eukaryotes, that copy gets capped, tailed, and spliced — introns cut out, exons stitched together — before it leaves the nucleus, and the splice choices alone let about 20,000 human genes produce roughly 100,000 distinct proteins. The ribosome, ~50% RNA by mass, then reads the mature messenger three nucleotides at a time, using a code of 64 codons specifying 20 amino acids plus stop, degenerate in its third position by design. The active site that forms every peptide bond in every protein you have ever made is not a protein. It is a piece of ribosomal RNA — a ribozyme — and that single fact is why a 2009 Nobel went to Steitz, Yonath, and Ramakrishnan and why most antibiotics work the way they do. The chapter traces one sickle-cell mutation — a single A→T in the β-globin gene — end to end through the central dogma until it becomes a deformed red cell in a vaso-occlusive crisis. The same machinery is why *E. coli* can make human insulin (Eli Lilly, 1982) and why synthetic spike-protein mRNA in a 2020 vaccine vial gets translated by your ribosomes without modification. The genetic code is universal. That universality is not philosophy. It is the engineering specification on which modern medicine runs.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **State** the central dogma in Crick's original 1958 formulation — information flows DNA → RNA → protein — and **name** the one legitimate exception (reverse transcription in retroviruses) and why it does not violate the principle.
2. **Walk** through a single round of transcription in order, naming the role of each player — RNA polymerase, promoter, template strand, coding strand, sigma factor (bacteria) or general transcription factors (eukaryotes), terminator — and **explain** why RNA polymerase needs no primer when DNA polymerase does.
3. **Diagram** the three eukaryotic post-transcriptional processing steps — 5' 7-methylguanosine cap, 3' polyadenylation, intron splicing by the spliceosome — and **explain** how alternative splicing lets one gene encode multiple proteins, with the *Drosophila* Dscam (~38,000 isoforms) extreme as the anchor.
4. **Read** any codon from the standard genetic-code chart, **identify** the start codon (AUG) and the three stop codons (UAA, UAG, UGA), and **explain** the wobble hypothesis as the geometric reason ~32 tRNAs are sufficient to read all 61 sense codons.
5. **Trace**, step by step, one round of ribosome elongation — A-site entry, peptidyl-transferase peptide-bond formation, translocation, E-site exit — and **state** which component of the ribosome catalyzes the peptide bond (23S rRNA, a ribozyme).
6. **Distinguish** the four mutation types — silent, missense, nonsense, frameshift — by predicting from a given DNA change which codon outcome results and what consequence for the protein follows.
7. **Trace** the sickle-cell mutation from a single A→T change in DNA through transcription, processing, translation, and folding to the clinical phenotype, and **explain** which step in the chain is responsible for each clinical feature (anemia, vaso-occlusion, pain crisis).
8. **Explain** why aminoglycoside, tetracycline, chloramphenicol, and macrolide antibiotics kill bacteria without killing the patient — selective binding to the 70S prokaryotic ribosome versus the 80S eukaryotic ribosome — and **name** the structural difference each drug class exploits.
9. **Explain** how recombinant insulin (Humulin, 1982) and mRNA vaccines (BNT162b2, mRNA-1273; 2020) both depend on the universality of the genetic code, and **identify** one engineering modification each platform makes to the natural sequence (codon optimization for *E. coli*; pseudouridine substitution for mRNA stability).
10. **Diagnose** at least three common misconceptions about the central dogma (e.g., "RNA is just unstable DNA," "ribosomes are protein machines," "the code is not really universal") and **explain** from mechanism why each is wrong.
11. **Build** a translation-and-transcription simulator (`05-transcription-translation.html`) with three linked panels — transcription, mRNA processing, translation — including an antibiotic toggle that shows where each drug class blocks the ribosome.

**Prerequisites.** Chapter 04 (DNA structure, antiparallelism, 5'→3' synthesis, the polymerase chain reaction's machinery in caricature). The chemistry of the helix is assumed. The language of "template strand," "5' end," and "3'-OH" is assumed. Mendel's particulate factors (Chapter 02) become, here, specific sequences specifying specific proteins.

---

## A vial that the cell does not know is a drug

December 18, 2020. A nurse at a Pfizer-BioNTech vaccination clinic loads 0.3 mL of clear liquid from a thawed vial into a syringe. The liquid contains, in a lipid-nanoparticle coat the size of a small virus, roughly 30 micrograms of synthetic single-stranded RNA. The mRNA is about 4,300 nucleotides long ([Pfizer-BioNTech BNT162b2 EUA dossier, FDA briefing document December 2020](https://www.fda.gov/media/144245/download) [verify]). It codes for a stabilized version of the SARS-CoV-2 spike protein. Every U in the synthetic transcript has been replaced by N1-methylpseudouridine — a chemical trick that lets the RNA evade the innate immune sensors that would otherwise destroy it before it could be translated ([Karikó et al. 2008 *Mol Ther* 16:1833–1840](https://www.cell.com/molecular-therapy-family/molecular-therapy/abstract/S1525-0016\(16\)33060-9) [verify]; the 2023 Nobel Prize in Physiology or Medicine to Karikó and Weissman recognized exactly this).

The syringe goes into a deltoid muscle. Lipid nanoparticles fuse with muscle and dendritic cell membranes. The mRNA spills into the cytoplasm. And then — this is the part to sit with — the recipient's own ribosomes pick up the synthetic transcript, find the AUG start codon, and begin translating spike protein. Codon by codon. Three nucleotides at a time. About two amino acids per second per ribosome. A single mRNA molecule recruits a polysome of perhaps a dozen ribosomes, each producing a spike-protein copy on staggered offsets. Within hours, the muscle and dendritic cells of the recipient are studded with surface spike, and the immune system is being trained against a pathogen the body has never seen.

Here is the part to stop on. The vaccine works because the ribosome does not care where its mRNA came from. A ribosome that has spent the morning translating actin, then a cytochrome subunit, then a metabolic enzyme — when a foreign mRNA appears that carries the right initiation signals, the ribosome reads it the same way. The genetic code in the synthetic spike-protein mRNA is exactly the same code the ribosome was already using. AUG still means start. GCC still means alanine. UAA still means stop. Nothing has to be retrained.

This is the chapter's claim in one paragraph. The central dogma is not a metaphor. It is the architecture of an information system that runs in every living cell on this planet, and the system is *interoperable* in the way the internet's TCP/IP is interoperable. A protein-coding sequence from a virus, a bacterium, a human, or a chemist's synthesizer is read by the same machinery, in the same direction, using the same dictionary. The universality of the genetic code is what makes recombinant insulin in *E. coli* possible. It is what makes mRNA vaccines architecturally possible. It is also what makes a single A→T mutation in one β-globin gene become a clinical syndrome severe enough to fill its own ward — because the same machinery that reads a healthy gene reads the mutated one, with no idea anything has changed. We will spend the chapter building both halves: the machinery, and the consequences of a single base in the wrong place.

---

## What Crick actually said in 1958, and what people often think he said

The phrase "central dogma" is **Francis Crick's**, coined in a 1958 lecture at the Society for Experimental Biology and published in 1970 in a clarifying *Nature* paper after a decade of misunderstanding ([Crick 1958 *Symp Soc Exp Biol* 12:138–163](https://profiles.nlm.nih.gov/spotlight/sc/catalog/nlm:nlmuid-101584582X73-doc) [verify]; [Crick 1970 *Nature* 227:561–563](https://www.nature.com/articles/227561a0)). Crick chose "dogma" mischievously — he later said in interviews he had not really known what the word meant when he picked it, and that he had used it for the same reason a physicist might say "principle." The choice of word has confused students ever since. A dogma in religious usage is unfalsifiable doctrine. Crick's "dogma" is the exact opposite: a concrete, mechanistic claim about information flow that experiments could and did test.

Here is the claim, stated as Crick stated it. Once "sequential information" has passed *into protein*, it cannot get out again. Information flows from nucleic acid sequence to nucleic acid sequence (DNA-to-DNA in replication, DNA-to-RNA in transcription, RNA-to-DNA in reverse transcription), and from nucleic acid sequence to protein sequence (RNA-to-protein in translation). It does *not* flow from protein sequence back to nucleic acid sequence. There is no mechanism by which the amino acid sequence of a folded protein can be transcribed back into DNA or RNA.

Note carefully what this does *not* claim. It does not claim that information only flows DNA → RNA → protein in that order. Reverse transcription — RNA → DNA — is allowed. That is how retroviruses (HIV, the leukemia viruses, hepatitis B) and our own retrotransposons work. Crick anticipated reverse transcription as a theoretical possibility in 1970, before it had been observed; **Howard Temin** and **David Baltimore** independently demonstrated the existence of reverse transcriptase in 1970 and shared the 1975 Nobel for the discovery ([Temin and Mizutani 1970 *Nature* 226:1211–1213](https://www.nature.com/articles/2261211a0); [Baltimore 1970 *Nature* 226:1209–1211](https://www.nature.com/articles/2261209a0)). RNA → DNA does not violate the central dogma. Protein → RNA would. No one has ever observed protein → RNA. Prions — misfolded proteins that propagate their misfolding to other proteins of the same type — sometimes get cited as an apparent exception, but prion propagation is conformational, not sequence-encoding; the amino acid sequence does not change, only the fold ([Prusiner 1998 *PNAS* 95:13363–13383](https://www.pnas.org/doi/10.1073/pnas.95.23.13363)). Crick's claim survives.

The diagram people draw in textbooks — a one-way arrow from DNA to RNA to protein — is therefore a simplification of the simplification. The honest diagram has three arrows on the nucleic-acid side (DNA↔DNA, DNA↔RNA, RNA↔RNA in some viruses) and one arrow into protein (RNA→protein), and no arrow out of protein. The central dogma is, in its original form, a statement about *what cannot happen*, not just a statement about what does. The negative claim is the falsifiable one. Every observation since 1958 has been consistent with it.

Why does this matter for the chapter? Because the next sixty pages of mechanism — RNA polymerase, ribosomes, tRNAs, peptide-bond formation — only earn their place if the information flow they implement is in fact what living systems do. We are about to walk through the machinery. The machinery is interesting on its own. The machinery is interesting *because* it is the substrate on which Crick's claim turns out to be true.

---

## Transcription — making the disposable copy

**Transcription** is the process by which an enzyme called **RNA polymerase** uses one strand of DNA as a template to synthesize a complementary single-stranded RNA copy. The output is a transcript — an mRNA, if the gene encodes a protein; a tRNA, rRNA, or other non-coding RNA, if not. The transcript is chemically similar to DNA but with three differences. First, the sugar is ribose instead of 2-deoxyribose — ribose has a 2'-OH that 2-deoxyribose lacks, which makes RNA more chemically reactive and less stable (we will see why that matters). Second, RNA uses uracil (U) instead of thymine (T); U pairs with A across two hydrogen bonds, exactly like T does. Third, the molecule is single-stranded — though it can and does fold back on itself to form local double-helical regions, hairpins, and other structures.

Why bother making this disposable copy at all? Three reasons, each mechanically sound.

First, **protection**. DNA is the archive. It has to survive intact for a cell's whole lifetime — and through every cell division, in every daughter, for every generation. Threading the DNA through a ribosome thousands of times a day would tear it up. Instead, the cell makes a temporary mRNA transcript, lets the ribosomes manhandle the transcript, and degrades the transcript when it has served its purpose. The original stays coiled in the nucleus (or, in bacteria, in a tight loop in the cytoplasm), touched only by RNA polymerase.

Second, **multiplication**. One gene can be transcribed into many mRNA copies simultaneously. Each mRNA copy can be translated by many ribosomes simultaneously — the structure of multiple ribosomes on one mRNA is called a **polysome**, and electron micrographs of polysomes (a row of ribosomes on a single mRNA strand, like beads on a string) are some of the cleanest images in molecular biology. One gene, dozens of mRNAs, hundreds of ribosomes — and the cell can produce a thousand copies of a protein in seconds. If ribosomes had to read DNA directly, only one ribosome at a time could occupy each gene. The intermediate uncouples production from the single-copy archive.

Third, **regulation**. Every step in the path — making the transcript, processing it, exporting it, translating it, degrading it — is a control point. A cell that needs more of a protein can transcribe the gene faster, process the transcript faster, translate it faster, or degrade it slower. A cell that needs less can dial down any of those steps. A one-step DNA → protein system would have one control point. A two-step system has at least five, and eukaryotes exploit every one. Chapter 06 is largely about how.

### RNA polymerase — the machine

In bacteria, there is one **RNA polymerase** that transcribes everything. The core enzyme has five subunits (α₂ββ'ω); together with a sixth subunit called **sigma factor (σ)**, it forms the **holoenzyme** — the version of the polymerase that can find a gene to transcribe. Without sigma, the polymerase binds DNA non-specifically and does nothing useful. With sigma, it finds the promoter.

In eukaryotes, there are three RNA polymerases, each transcribing a different class of genes. **RNA polymerase I** transcribes the large ribosomal RNA genes (the precursor to 18S, 5.8S, and 28S rRNAs) in the nucleolus. **RNA polymerase II** transcribes all protein-coding genes plus some non-coding RNAs (miRNA precursors, lncRNAs). **RNA polymerase III** transcribes tRNAs, 5S rRNA, and a handful of other small RNAs. For the rest of this chapter, when I say "RNA polymerase" in a eukaryotic context, I mean Pol II unless I say otherwise.

The polymerase reads the template strand 3'→5' and synthesizes the RNA 5'→3', adding ribonucleoside triphosphates (NTPs — ATP, GTP, CTP, UTP) to the growing 3' end. The chemistry is the same chemistry DNA polymerase uses: the 3'-OH of the growing chain attacks the α-phosphate of the incoming NTP; pyrophosphate is released; a phosphodiester bond is formed. The energetics are the same too — the high-energy phosphate bond of the incoming triphosphate provides the energy that drives chain extension. This is why a 3'→5' polymerase is geometrically impossible in either DNA or RNA synthesis: the energy lives on the incoming nucleotide, not on the chain.

There is one critical difference between DNA polymerase and RNA polymerase. **DNA polymerase cannot initiate** — it can only extend an existing primer with a free 3'-OH. **RNA polymerase can initiate** — it can start a chain from scratch on a single-stranded DNA template, using just two NTPs to make the first phosphodiester bond. This is why the cell uses *RNA* primers during DNA replication: primase, an RNA polymerase, can start chains; DNA polymerase then extends them. The ability to initiate is what makes RNA polymerase the right tool for transcription, where there is no pre-existing chain to extend.

RNA polymerase is also **less accurate than DNA polymerase**. Its intrinsic error rate is on the order of one mistake per 10⁴ to 10⁵ nucleotides, roughly a hundred-fold worse than the post-proofreading DNA polymerase rate of ~10⁻⁷ ([Sydow and Cramer 2009 *Curr Opin Struct Biol* 19:732–739](https://www.sciencedirect.com/science/article/abs/pii/S0959440X09001407) [verify]). This is acceptable because transcripts are disposable. If one mRNA copy out of a thousand has an error, the other 999 produce correct protein, and the error-bearing protein is rapidly degraded by quality-control machinery. The fidelity that DNA replication has to achieve — to preserve the archive across a lifetime — is not the fidelity transcription has to achieve. The intermediate is allowed to be sloppy because it does not have to survive.

### The three stages — initiation, elongation, termination

I want to walk transcription in order, the way I walked the replication fork in Chapter 04. Bacterial transcription first, because it is cleaner. Then the eukaryotic complications.

**Initiation in bacteria.** RNA polymerase holoenzyme (core enzyme + sigma factor) scans the DNA, looking for a **promoter** — a specific DNA sequence upstream of a gene that says "transcribe here." Bacterial promoters have two conserved sequence blocks: the **-10 box** with consensus sequence **TATAAT**, located about 10 base pairs upstream of the transcription start site, and the **-35 box** with consensus sequence **TTGACA**, located about 35 base pairs upstream. (The numbers count from the start site, with the start site at +1; negative numbers are upstream.) Sigma factor recognizes these two sequences. When holoenzyme finds a -35 / -10 pair separated by the right distance (~17 bp), it clamps down and forms a **closed complex** (DNA still double-stranded). The polymerase then melts about 12–14 base pairs of DNA around the start site, forming an **open complex** with a small "transcription bubble" of single-stranded DNA. The polymerase begins synthesizing short RNA fragments (a few nucleotides), often falling off and starting over — a stuttering phase called **abortive initiation**. Once a transcript reaches ~10 nucleotides, the polymerase commits: sigma factor dissociates, the core enzyme grips the DNA, and the polymerase begins productive elongation.

Different sigma factors recognize different promoter consensus sequences, and that is how bacteria express different gene sets under different conditions. *E. coli* has seven sigma factors. **σ⁷⁰** is the housekeeping sigma that handles normal growth genes; **σ³²** kicks in under heat shock and directs transcription of chaperones and proteases; **σ⁵⁴** handles nitrogen starvation. Swapping sigma factor swaps which genes get transcribed — an elegant control mechanism we will revisit in Chapter 06.

**Initiation in eukaryotes** is dramatically more elaborate. RNA polymerase II does not bind promoters on its own. Instead, a sequence of **general transcription factors** (GTFs) assemble first, and Pol II joins last. The promoter of a typical Pol II gene contains a **TATA box** — consensus TATAAA — located ~25–35 bp upstream of the start site. (Note: the bacterial -10 box is also TATAAT-like; both bacteria and eukaryotes evolved to use AT-rich sequences upstream because AT pairs have only two hydrogen bonds and melt open more easily than GC pairs.)

The assembly order is reasonably canonical and worth knowing. **TFIID** binds first, with its TATA-binding-protein (TBP) subunit locking onto the TATA box and bending the DNA by ~90°. Then **TFIIA** and **TFIIB** dock to stabilize TFIID. Then **TFIIF** brings in **RNA polymerase II**. Then **TFIIE** and **TFIIH** join. TFIIH is the workhorse — it contains a helicase activity that melts the DNA at the start site (forming the eukaryotic open complex) and a kinase activity that phosphorylates Pol II's carboxy-terminal domain (CTD) to release the polymerase from the GTF assembly. The whole structure is called the **pre-initiation complex (PIC)**, and it is enormous — well over a megadalton. Pol II then escapes into elongation, leaving most of the GTFs behind ([Sainsbury et al. 2015 *Nat Rev Mol Cell Biol* 16:129–143](https://www.nature.com/articles/nrm3952) [verify]).

Why the elaborate assembly? Because eukaryotic transcription is regulated. Each GTF is a potential control point. Each step is a potential gate. Chapter 06 will show how enhancers and transcription factors thousands of base pairs away from the gene loop in and modulate PIC assembly. For now, hold this: bacteria need one polymerase + one sigma to find a gene; eukaryotes need ~50 proteins. The complexity is the price of fine-grained regulation.

**Elongation.** Once initiated, RNA polymerase advances along the DNA at a remarkably constant rate. Bacterial RNA polymerase elongates at roughly 50 nucleotides per second ([Vogel and Jensen 1994 *J Bacteriol* 176:2807–2813](https://journals.asm.org/doi/10.1128/jb.176.10.2807-2813.1994) [verify]); eukaryotic Pol II is similar, around 25–50 nt/s in vivo when actively elongating, though it spends a lot of time paused ([Singh and Padgett 2009 *Nat Struct Mol Biol* 16:1128–1133](https://www.nature.com/articles/nsmb.1666) [verify]). The polymerase maintains a transcription bubble — about 12–14 base pairs of melted DNA — moving with it down the gene. Behind the polymerase, the DNA re-anneals into double-helix; the nascent RNA is peeled off and emerges from the back of the polymerase.

Two side problems get solved during elongation. First, **supercoiling**. When the polymerase unwinds the DNA ahead of itself, it generates positive supercoiling (the DNA twists tighter); behind itself, it generates negative supercoiling. In a long chromosome, this accumulated torsion would eventually stall the polymerase. **Topoisomerases** — the same enzyme family that solved the replication-fork twist problem in Chapter 04 — relieve the supercoiling by transiently cutting and resealing the DNA. Second, **histone displacement** in eukaryotes. Pol II has to push past nucleosomes (DNA wrapped around histone octamers). A protein complex called **FACT** helps disassemble nucleosomes ahead of the polymerase and reassemble them behind. Transcribed regions of chromatin are not nucleosome-free during transcription; they are nucleosome-*remodeled*.

**Termination in bacteria** uses one of two mechanisms. **Intrinsic** (rho-independent) termination relies on a sequence in the RNA that folds back on itself to form a GC-rich hairpin followed by a run of U's. The hairpin stalls the polymerase; the weak rU:dA base pairs (only two H-bonds) between the RNA and template let the transcript dissociate; transcription stops. **Rho-dependent** termination uses a protein called **Rho**, a hexameric ATPase that loads onto the nascent RNA at a specific sequence (a rut site), chases the polymerase along the RNA, catches up when the polymerase stalls, and physically pulls the RNA-DNA hybrid apart.

**Termination in eukaryotes** for Pol II uses a different logic. The polymerase keeps transcribing past the end of the gene for hundreds to thousands of nucleotides. A specific sequence in the transcript — **AAUAAA**, the polyadenylation signal — is recognized by a cleavage complex, which cuts the transcript at a position ~10–30 nucleotides downstream of the AAUAAA. The cut releases the mRNA. The polymerase continues for a while longer, transcribing irrelevant sequence, until it is dislodged by a "torpedo" — a 5'→3' exonuclease (Xrn2 in mammals) that chases the polymerase down the DNA, chewing the leftover RNA as it goes, and eventually catches the polymerase and triggers its release. The mechanism is called the **torpedo model** ([Proudfoot 2016 *Science* 352:aad9926](https://www.science.org/doi/10.1126/science.aad9926) [verify]).

### Template strand vs. coding strand — a small but lethal distinction

One vocabulary item that students get wrong forever if it is not pinned down on first encounter. A gene's DNA is double-stranded. One strand is the **template strand** (also called the *antisense* strand) — the strand that RNA polymerase actually reads, 3'→5'. The other strand is the **coding strand** (also called the *sense* strand) — the strand whose sequence *matches* the mRNA, except with T instead of U.

Why does this matter? Because when geneticists write a gene's sequence, they conventionally write the coding strand, 5'→3'. If the textbook says "the β-globin gene has the sequence ...CTGACTCCTGAGGAG... at codon 6," that is the coding strand. The mRNA will read ...CUGACUCCUGAGGAG..., same letters with U for T. The template strand — the one the polymerase actually reads — is the complement of that: ...CTCCTCAGGAGTCAG... read 3'→5'. When we trace the sickle-cell mutation later, the A→T change is reported on the coding strand. On the template strand it is a T→A change. The mRNA change is A→U. Same mutation, three different ways of writing it. Pin this down now; it will return.

---

## mRNA processing in eukaryotes — three modifications, none of them optional

A bacterial mRNA emerges from RNA polymerase ready to translate. Ribosomes attach to it while it is still being transcribed — sometimes the 5' end of the mRNA is already studded with ribosomes before the 3' end has been synthesized. The mRNA is naked, single-stranded, and short-lived (half-life of a few minutes in *E. coli*).

A eukaryotic mRNA cannot work that way. It is born in the nucleus; it has to make it to the cytoplasm; it has to find a ribosome that is not co-transcribing with its polymerase; it has to survive long enough (eukaryotic mRNAs typically have half-lives of hours to days) to be translated many times. Three processing steps prepare it.

### The 5' cap — added before the transcript is finished

About 20–30 nucleotides into transcription, before Pol II has even cleared the promoter region, the **5' cap** is added. A **7-methylguanosine** (a guanosine with a methyl group on its N7 nitrogen, written **m⁷G**) is attached to the 5' end of the transcript through an unusual **5'-5' triphosphate linkage** — the G is connected backwards, head to head, with the first transcribed nucleotide. This is a chemically distinct linkage from the normal 5'-3' phosphodiester bonds along the rest of the transcript, and it serves as a chemical signal that says *this end is the start*.

Three enzymes carry out capping, all of them docked onto the phosphorylated CTD of Pol II so they can find the nascent transcript as soon as it emerges. **RNA triphosphatase** removes the γ-phosphate from the first nucleotide. **Guanylyltransferase** attaches a GMP from GTP onto the resulting diphosphate, releasing pyrophosphate. **N7-methyltransferase** adds a methyl group to N7 of the new guanine. The cap is now complete.

What does the cap do? Three things. It protects the mRNA from 5'→3' exonucleases, which would otherwise rapidly degrade the transcript by chewing it from the 5' end. (Without the cap, eukaryotic mRNA half-life would be seconds, not hours.) It marks the transcript for nuclear export. And it serves as the **ribosome landing pad** in the cytoplasm — the small ribosomal subunit's initiation factors recognize the cap structure and load onto the mRNA at the cap, then scan downstream for the start codon. Cap-dependent translation initiation is the dominant mechanism for eukaryotic protein synthesis. (A handful of viral and stress-induced mRNAs use cap-independent **internal ribosome entry sites (IRES)** to recruit ribosomes directly to internal positions on the transcript — a trick the cell sometimes appropriates during stress, when cap-dependent initiation is shut down.)

### The 3' polyadenylation — cleave, then add a tail

While the 5' end is being capped, the 3' end is still being transcribed. Eventually Pol II passes the **polyadenylation signal**, **AAUAAA**, in the transcript. About 10–30 nucleotides further downstream is the cleavage site (often after a CA dinucleotide). The **cleavage and polyadenylation specificity factor (CPSF)** complex recognizes AAUAAA. The **cleavage stimulation factor (CstF)** complex binds a downstream GU-rich element. Together they cut the transcript at the cleavage site. Pol II keeps going for a while longer (the torpedo will catch it). The newly cut 3' end of the transcript has a free 3'-OH.

Now **poly(A) polymerase** binds the cut end and adds adenines, one at a time, without a template. About 200 A's get added. This is the **poly(A) tail**. Unlike everything else we have looked at, poly(A) addition is *not* template-directed — poly(A) polymerase is a non-templated nucleotidyltransferase, putting on bases by sheer enzymatic preference.

The tail does for the 3' end what the cap does for the 5' end. It protects against 3'→5' exonucleases. It promotes nuclear export. It enhances translation — initiation factors recognize the tail-binding protein **PABP** and bridge it to the cap-binding complex, **circularizing** the mRNA into a closed loop that enhances re-initiation by ribosomes that have just finished translating. mRNA half-life in the cytoplasm is in part controlled by tail length: as the tail gets shorter over time (chewed back by deadenylases), the mRNA becomes vulnerable to decapping and to 3'→5' degradation.

### Splicing — cutting out the introns

This is the strangest part of eukaryotic mRNA biology, and the part that startled the field most when it was discovered in 1977 by **Phillip Sharp** and **Richard Roberts** (independently; they shared the 1993 Nobel Prize in Physiology or Medicine for the discovery; [Berget et al. 1977 *PNAS* 74:3171–3175](https://www.pnas.org/doi/10.1073/pnas.74.8.3171); [Chow et al. 1977 *Cell* 12:1–8](https://www.cell.com/cell/abstract/0092-8674\(77\)90180-5)). Most eukaryotic genes are *interrupted*. The protein-coding sequence is broken into segments — **exons** — separated by stretches of non-coding sequence — **introns** — that have to be physically removed from the mRNA before it can be translated.

Example. The human β-globin gene has **3 exons and 2 introns**. The exons total ~440 nucleotides of coding sequence; the introns total ~1,000 nucleotides of intervening sequence; the pre-mRNA is ~1,600 nucleotides long. The mature, spliced mRNA is ~620 nucleotides long (including UTRs and the cap/tail). Most of the original transcript is thrown away. This is normal. Many human genes are dramatically more intron-heavy: dystrophin, the gene mutated in Duchenne muscular dystrophy, is **~2.4 million base pairs of DNA, 79 exons, 78 introns**, with mature mRNA only ~14,000 nucleotides. The introns account for over 99% of the gene's length ([Tennyson et al. 1995 *Nat Genet* 9:184–190](https://www.nature.com/articles/ng0295-184) [verify]).

The machine that does splicing is the **spliceosome** — a huge ribonucleoprotein complex assembled fresh on each intron from five small nuclear ribonucleoprotein particles called **snRNPs** (pronounced "snurps"): **U1, U2, U4, U5, U6**. Each snRNP contains one small nuclear RNA (snRNA) and a set of proteins. Like the ribosome, the spliceosome's catalytic activities are RNA-driven — the snRNAs recognize splice sites by base-pairing with conserved sequences in the pre-mRNA, and they catalyze the bond-breaking and bond-forming chemistry. The spliceosome is, at heart, another ribozyme ([Fica et al. 2013 *Nature* 503:229–234](https://www.nature.com/articles/nature12734) [verify]).

The chemistry of splicing is worth tracing because it is one of biology's strangest and cleverest reactions. Every intron has three landmarks:

- A **5' splice site** at the intron's beginning, with the nearly-invariant sequence **GU**.
- A **3' splice site** at the intron's end, with the nearly-invariant sequence **AG**.
- A **branch point** — a specific adenosine (A) located about 20–50 nucleotides upstream of the 3' splice site.

Splicing proceeds in two steps, each a **transesterification** — meaning a phosphodiester bond is broken and a new phosphodiester bond is formed in the same chemical step, with no net hydrolysis (no water needed).

**Step 1.** The **2'-OH of the branch-point adenosine** attacks the phosphodiester bond at the 5' splice site. This breaks the bond between the upstream exon and the intron, and *simultaneously* forms a new 2'-5' phosphodiester bond between the branch-point A and the first G of the intron. The intron now hangs off the branch point as a lariat (a loop with a tail), and the upstream exon is free with a 3'-OH.

**Step 2.** The free **3'-OH of the upstream exon** attacks the phosphodiester bond at the 3' splice site. This breaks the bond between the intron and the downstream exon, and *simultaneously* forms a new phosphodiester bond between the two exons. The exons are joined. The intron lariat is released and degraded.

Two transesterifications. No ATP used. The whole splicing reaction is run on the energy of bond rearrangement, with the spliceosome providing the precise geometry that aligns the reactants. The 2'-OH of ribose, which I mentioned earlier as the reason RNA is less stable than DNA, is the nucleophile that makes splicing chemistry possible. That same 2'-OH is what makes RNA capable of catalysis — what makes ribozymes a thing — and what makes the spliceosome and the ribosome work.

### Alternative splicing — one gene, many proteins

Here is the kicker. The cell does not always splice the same way. Many genes have **alternative splice sites** — multiple choices of which exons to include and which to exclude. Different choices produce different mRNAs from the same pre-mRNA, encoding different proteins.

Recent surveys estimate that **~95% of multi-exon human genes** undergo alternative splicing in at least some context ([Pan et al. 2008 *Nat Genet* 40:1413–1415](https://www.nature.com/articles/ng.259) [verify]). The average human protein-coding gene produces about **7 distinct protein isoforms** through alternative splicing ([Ezkurdia et al. 2014 *Mol Biol Evol* 31:2879–2887](https://academic.oup.com/mbe/article/31/11/2879/1014868) [verify]). The current GENCODE annotation lists roughly **20,000 human protein-coding genes** but well over **100,000 distinct transcript isoforms** ([Frankish et al. 2021 *Nucleic Acids Res* 49:D916–D923](https://academic.oup.com/nar/article/49/D1/D916/5965149) [verify]).

The extreme champion is the *Drosophila* **Dscam** gene — Down syndrome cell adhesion molecule, a neural cell-surface receptor. *Dscam* has 95 alternative exons grouped into four cassettes, and combinatorial splicing across the cassettes can produce in principle **38,016 distinct protein isoforms** from one gene ([Schmucker et al. 2000 *Cell* 101:671–684](https://www.cell.com/cell/fulltext/S0092-8674\(00\)80878-8) [verify]). Each fly neuron expresses a roughly unique subset of these isoforms, giving each neuron a unique cell-surface identity that lets it tell self from non-self during axon wiring. One gene encodes more distinct proteins than the entire genome of some bacteria. The economy of information packing is breathtaking.

Alternative splicing is one reason the "20,000 genes" headline finding from the Human Genome Project was less of a disappointment than it sounded. We do not have fewer "genes" than expected; we have far more *proteins* than the gene count suggests, because each gene is, in effect, a parameterized recipe with multiple realizations.

---

## The genetic code — 64 codons, 20 amino acids, and four billion years without a major edit

The ribosome reads mRNA three nucleotides at a time. Each three-nucleotide unit is a **codon**. With four possible bases at each of three positions, there are 4³ = **64 possible codons**. With only **20 standard amino acids** to specify (plus the need for at least one stop signal), 64 codons is plenty. The mapping from codon to amino acid is the **genetic code**.

### Reading the code

The standard genetic code table is a 4×4 grid of 4×4 sub-grids. The first base of the codon is the row of the outer grid; the second base is the column; the third base is the row of the inner sub-grid. Let me read a few entries.

- **AUG** → **Methionine (Met, M).** Also the **start codon**.
- **UUU, UUC** → **Phenylalanine (Phe, F).**
- **GAA, GAG** → **Glutamate (Glu, E).** Negatively charged. (Remember this one — sickle cell is coming.)
- **GUA, GUC, GUG, GUU** → **Valine (Val, V).** Hydrophobic. (Remember this one too.)
- **UAA, UAG, UGA** → **Stop.** No amino acid; ribosome terminates here.
- **UGG** → **Tryptophan (Trp, W).** Note: UGG is the *only* tryptophan codon; UGA, which differs by one base, is a stop codon. A single mutation that converts UGG to UGA produces a nonsense mutation right in the middle of a protein. Tryptophan is structurally one of the most fragile residues in the genome because of this proximity to a stop codon.

### Properties of the code

The code has five properties worth pinning down explicitly.

**(1) Triplet.** Each codon is exactly three nucleotides. This was nailed down by **Crick, Brenner, Barnett, and Watts-Tobin** in a beautiful 1961 paper using frameshift mutations in T4 phage — adding one base produced a defective protein, adding two bases produced a different defective protein, adding three bases produced a roughly functional protein, demonstrating that the reading frame is restored when three are added ([Crick et al. 1961 *Nature* 192:1227–1232](https://www.nature.com/articles/1921227a0)). The triplet result was inferred before any codon's meaning was known.

**(2) Non-overlapping and comma-free.** Once the ribosome starts at AUG, it reads codons sequentially, three bases at a time, without skipping bases and without overlap. The codon UAC at positions 4-5-6 is not also the codon ACX at positions 5-6-7. Each base is part of exactly one codon. This is why **frameshift mutations are catastrophic** — inserting or deleting a single base shifts the reading frame, so every codon downstream of the indel is a different codon.

**(3) Degenerate (redundant).** Most amino acids are specified by more than one codon. Methionine and tryptophan are the only amino acids with single codons; serine, leucine, and arginine each have six. The redundancy is not random. **Synonymous codons** typically differ at the **third position** — UCU, UCC, UCA, UCG all code for serine; CUU, CUC, CUA, CUG all code for leucine. This means a mutation at the third base of a codon is often **silent** (no amino acid change). The code is shaped to absorb third-position mutations.

**(4) Universal — with footnotes.** The same codon means the same amino acid in *E. coli*, in a tulip, in a shark, in you. With known exceptions of a few codon reassignments in **mitochondria** (UGA codes for tryptophan in vertebrate mitochondria, not stop; AUA codes for methionine, not isoleucine; AGA and AGG are stop in vertebrate mitochondria) and in a few unusual single-celled organisms (some ciliates, mycoplasmas), the standard code is the same code across all known life ([Knight et al. 2001 *Nat Rev Genet* 2:49–58](https://www.nature.com/articles/35047500) [verify]). The exceptions are interesting precisely because they are rare. The rule is the universality. We will come back to *why* in a moment.

**(5) Has explicit start and stop.** AUG starts translation. UAA, UAG, UGA stop it. The code is bounded — translation has defined endpoints, not just a tape running forever.

### The wobble hypothesis — why the cell only needs ~32 tRNAs

The cell has 61 sense codons (64 minus 3 stops). You might expect 61 different **tRNAs** — each one a small RNA molecule (~76 nucleotides) folded into a cloverleaf shape, charged at one end with a specific amino acid and presenting a **three-nucleotide anticodon** at the other end that base-pairs with the mRNA codon. The codon-anticodon pairing is what links the genetic sequence to the amino acid sequence — tRNAs are the *adapters*, in Crick's original language from his 1958 "adapter hypothesis."

But cells do not have 61 tRNAs. They have closer to 32 in most organisms ([Lowe and Eddy 1997 *Nucleic Acids Res* 25:955–964](https://academic.oup.com/nar/article/25/5/955/1207247) [verify]). The same tRNA reads multiple synonymous codons. How?

This is the **wobble hypothesis**, proposed by Crick in 1966 ([Crick 1966 *J Mol Biol* 19:548–555](https://www.sciencedirect.com/science/article/abs/pii/S0022283666800221) [verify]). The first two bases of the codon (positions 1 and 2) pair with the corresponding bases of the anticodon by strict Watson-Crick rules — A pairs with U, G pairs with C, no exceptions. The **third base of the codon** pairs with the **first base of the anticodon** — but at this single position, the geometry of the bond is slightly relaxed, allowing some non-standard pairings. Specifically:

- A U at the anticodon's 5' end (wobble position) can pair with A *or* G at the codon's 3' end.
- A G at the anticodon's wobble position can pair with U *or* C.
- An **inosine (I)** at the anticodon's wobble position — produced by enzymatic deamination of A in the tRNA — can pair with U, C, *or* A.

So one tRNA with anticodon ICG (where I is inosine) can read codons CGU, CGC, and CGA — three of the four arginine codons. The fourth (CGG) is read by a different tRNA. With this kind of flexibility, ~32 tRNAs cover all 61 sense codons. The wobble position is the structural reason the code's third-position redundancy works in practice — the cell does not need 61 distinct tRNA species, only enough to span the redundancy classes.

### Why the code looks designed for error tolerance

Look at the code table carefully and a pattern emerges. **Chemically similar amino acids tend to have similar codons.** Codons starting with C tend to specify hydrophobic amino acids (Leu, Ile, Pro). Codons starting with U tend to specify aromatic or hydrophobic amino acids. Codons with a middle A tend to specify polar or charged amino acids. The pattern is not perfect, but it is striking enough that quantitative analyses have repeatedly shown the standard genetic code is far more robust against single-nucleotide mutations than a randomly assigned code would be — robust by a factor of hundreds to thousands ([Freeland and Hurst 1998 *J Mol Evol* 47:238–248](https://link.springer.com/article/10.1007/PL00006381) [verify]).

This is interpreted as evidence the code was **selected** during early evolution to minimize the phenotypic impact of mutations. A mutation at the third position of a codon is usually silent. A mutation at the first or second position often changes the amino acid to a *chemically similar* one — leucine to isoleucine, glutamate to aspartate, lysine to arginine. The protein survives. This is not engineering; it is the residue of four billion years of selection in a system where mutations happen and proteins still need to fold.

### Why the code is frozen

Why has the code not changed in four billion years? **Crick's "frozen accident" hypothesis** from 1968 ([Crick 1968 *J Mol Biol* 38:367–379](https://www.sciencedirect.com/science/article/abs/pii/0022283668903922) [verify]) is still the best answer: once the code was established, *any* change would simultaneously break every protein in the cell. To swap one codon's meaning, you would need to change every gene that uses that codon, every tRNA that reads it, every aminoacyl-tRNA synthetase that charges those tRNAs — all at once, in a way that did not kill the organism. There is no path through fitness space from one code to a slightly different one. The system is locked in by its own consistency.

The fact that the code has nevertheless been (slightly) re-assigned in mitochondria and a few oddball lineages is interesting — those are organisms with very small genomes and very limited gene sets, where the consistency cost of a codon reassignment is small enough to be paid. The general universality of the code in the rest of life is the rule. The mitochondrial exceptions are the proof that the rule is upheld by cost, not by chemistry. If chemistry forced AUG to mean methionine, mitochondria could not have rewired it. They did rewire it. So chemistry does not force it. Only history does.

---

## Translation — the ribosome at work

Now we get to the machine itself. The **ribosome** is the largest, most conserved, and most studied molecular machine in biology. It is roughly half RNA, half protein, by mass — and the RNA half is doing the chemistry. The protein half is mostly structural scaffolding.

### Anatomy

The bacterial ribosome (the **70S** ribosome — the "S" is **Svedberg units**, a measure of sedimentation rate under centrifugation; the numbers add weirdly because they reflect both size and shape, not just mass) has two subunits:

- **Small subunit (30S)**: contains the **16S rRNA** (~1,540 nucleotides) plus ~21 proteins. Reads the mRNA codons.
- **Large subunit (50S)**: contains the **23S rRNA** (~2,900 nucleotides) and the small **5S rRNA** (~120 nucleotides) plus ~33 proteins. Catalyzes peptide bond formation.

The eukaryotic ribosome (the **80S** ribosome) has:

- **Small subunit (40S)**: contains **18S rRNA** plus ~33 proteins.
- **Large subunit (60S)**: contains **28S, 5.8S, and 5S rRNAs** plus ~49 proteins.

Eukaryotic ribosomes are roughly 50% larger than bacterial ribosomes, with extra rRNA segments (called **expansion segments**) and extra proteins of unclear function. Both architectures, however, share a deeply conserved core — the catalytic regions of the 23S and 28S rRNAs are nearly identical between *E. coli* and *Homo sapiens*. That conservation will matter when we get to antibiotics.

The ribosome has **three tRNA-binding sites**, spanning the boundary between the two subunits:

- **A site (aminoacyl)** — where the *next* tRNA arrives, carrying the next amino acid to be added.
- **P site (peptidyl)** — where the tRNA carrying the *growing peptide chain* sits.
- **E site (exit)** — where a now-empty tRNA briefly resides before falling off.

The mRNA is threaded through a channel in the small subunit; the codons currently in the A and P sites are exposed, ready for tRNA pairing.

### Peptidyl transferase is rRNA

The most important single fact about the ribosome is this. **The active site that catalyzes peptide bond formation is RNA, not protein.** When you eat a meal and your liver synthesizes albumin, every peptide bond linking every two adjacent amino acids in every albumin molecule is forged by a piece of ribosomal RNA, the 23S rRNA in the large subunit, at a position deep in the subunit called the **peptidyl transferase center (PTC)**.

This was suspected since the 1980s on the basis of biochemistry (the catalytic activity survived treatments that removed proteins; antibiotics that target the PTC bind to rRNA), but the structural proof came in 2000 with the **atomic-resolution crystal structures of the bacterial ribosome** solved by **Thomas Steitz** (50S subunit), **Ada Yonath** (independent work on 50S and other subunits going back to the 1980s), and **Venki Ramakrishnan** (30S subunit). The crystal structures showed unambiguously that the closest amino acid residue to the active site is ~18 Å away — too far to participate in catalysis. The catalytic residues are nucleotides of the 23S rRNA, specifically A2451 and nearby bases ([Nissen et al. 2000 *Science* 289:920–930](https://www.science.org/doi/10.1126/science.289.5481.920); [Ban et al. 2000 *Science* 289:905–920](https://www.science.org/doi/10.1126/science.289.5481.905)). The three shared the **2009 Nobel Prize in Chemistry** for the ribosome structure work ([Nobel Prize in Chemistry 2009](https://www.nobelprize.org/prizes/chemistry/2009/summary/)).

This is not a curiosity. It is the strongest single piece of evidence for the **RNA world hypothesis** — the idea that early life was based on RNA molecules that could both store information *and* catalyze reactions, before protein enzymes evolved. If proteins were required to catalyze the synthesis of proteins, the origin of life faces a chicken-and-egg problem. If RNA can do both — and the ribosome's RNA core proves it can — then RNA could have been the original self-replicating, self-translating substrate from which protein enzymes later emerged. The ribosome is, in effect, a four-billion-year-old fossil of the RNA world, frozen in the act of making the proteins that replaced its world.

A word we should pin down. A **ribozyme** is an RNA molecule that catalyzes a chemical reaction — the RNA equivalent of an enzyme. The first ribozyme was found in 1982 by **Thomas Cech** in *Tetrahymena* (a self-splicing intron) and confirmed in 1983 by **Sidney Altman** for RNase P (the tRNA-processing enzyme); the two shared the 1989 Nobel in Chemistry ([Cech et al. 1981 *Cell* 27:487–496](https://www.cell.com/cell/abstract/0092-8674\(81\)90390-1); [Guerrier-Takada et al. 1983 *Cell* 35:849–857](https://www.cell.com/cell/abstract/0092-8674\(83\)90117-4) [verify]). The ribosome is by far the largest and most important known ribozyme. Every peptide bond in your body was formed by a ribozyme.

### Initiation

Translation begins at the start codon, **AUG**, which codes for methionine. The initiator tRNA is special — in bacteria it is charged with N-**formylmethionine** (the methionine has a formyl group on its amino terminus, blocking it; this is a marker for the start of a protein); in eukaryotes it is regular methionine on a special initiator tRNA, **Met-tRNAi**. In both cases, the initiator tRNA enters the **P site** directly, not the A site (the only tRNA that does this in normal translation).

**Bacterial initiation.** The small ribosomal subunit (30S) finds the start codon using a sequence called the **Shine-Dalgarno sequence** — a short purine-rich segment (consensus **AGGAGG**) located 6–10 nucleotides upstream of the AUG ([Shine and Dalgarno 1974 *PNAS* 71:1342–1346](https://www.pnas.org/doi/10.1073/pnas.71.4.1342)). The 16S rRNA in the 30S subunit has a complementary anti-Shine-Dalgarno sequence near its 3' end. Base-pairing between the Shine-Dalgarno on the mRNA and the anti-Shine-Dalgarno on the 16S rRNA correctly positions the AUG in the P site. Initiation factors **IF1, IF2, IF3** facilitate this; IF2 brings the charged fMet-tRNA to the P site. The 50S subunit then joins, the initiation factors are released, and the 70S initiation complex is ready for elongation.

**Eukaryotic initiation** is more elaborate (sensing a pattern?). The 40S small subunit, together with **Met-tRNAi** and a suite of **eukaryotic initiation factors (eIFs)**, forms a **43S preinitiation complex**. The complex is recruited to the 5' cap of the mRNA by **eIF4F**, a cap-binding complex (eIF4F contains eIF4E, the cap-binding protein; eIF4G, a scaffold; and eIF4A, an RNA helicase that unwinds secondary structure). The 43S complex then **scans** the mRNA in the 5'→3' direction until it finds the first AUG codon in a suitable context. The "suitable context" is the **Kozak sequence** — consensus **(gcc)gccRccAUGG**, where R is a purine (A or G); the most important positions are the purine at -3 and the G at +4 ([Kozak 1986 *Cell* 44:283–292](https://www.cell.com/cell/fulltext/0092-8674\(86\)90762-2) [verify]). If the first AUG is in a poor Kozak context, the ribosome may skip it and continue scanning to a downstream AUG — a phenomenon called **leaky scanning**. Once the start codon is found, the 60S large subunit joins; the eIFs are released; the 80S initiation complex is ready.

The key difference: bacteria find the start codon by direct base-pairing (Shine-Dalgarno → 16S rRNA). Eukaryotes find it by scanning from the 5' cap. The same problem, two different solutions. The reason this matters for medicine: when you want to express a human protein in bacteria (recombinant insulin, growth hormone, monoclonal antibody scaffolds), you have to *add* a Shine-Dalgarno sequence to the engineered gene. Bacterial ribosomes do not know how to scan from a cap. Get the upstream signals wrong and your protein will not be made.

### Elongation — one cycle, three steps

The ribosome elongates by repeating a three-step cycle. I will walk one cycle carefully, because it is the chapter's mechanistic centerpiece (alongside the sickle-cell trace).

**Starting state.** The P site holds a tRNA carrying the growing peptide chain (1, 2, 3, ... n amino acids long). The A site is empty, exposing the next mRNA codon. The E site is empty.

**Step 1 — A-site entry and codon-anticodon proofreading.** A charged aminoacyl-tRNA, complexed with the elongation factor **EF-Tu** (or **eEF1A** in eukaryotes) and GTP, diffuses into the A site. The anticodon of the tRNA is tested against the codon of the mRNA. *If the anticodon-codon match is correct* (perfect Watson-Crick at positions 1 and 2; wobble allowed at position 3), the tRNA fits cleanly into the A site; EF-Tu hydrolyzes its GTP and dissociates; the aminoacyl end of the tRNA swings into position next to the P-site tRNA's peptidyl end. *If the match is incorrect*, the tRNA fits poorly; it tends to fall back out before EF-Tu hydrolyzes GTP; the wrong tRNA is rejected.

This is **kinetic proofreading** — a two-stage discrimination scheme proposed by **John Hopfield** in 1974 and **Jacques Ninio** independently in 1975. Initial selection (does the tRNA fit?) is followed by a delay (GTP hydrolysis) before commitment (peptide bond formation). The delay lets a poorly-fitting tRNA escape. The two-stage selection lets the ribosome achieve an error rate of about one mistake per ~10⁴ amino acids — far better than thermodynamics alone would predict, because thermodynamics says the energy difference between correct and incorrect codon-anticodon pairing is only ~3 kcal/mol, which would give an error rate of ~10⁻² ([Hopfield 1974 *PNAS* 71:4135–4139](https://www.pnas.org/doi/10.1073/pnas.71.10.4135); [Ninio 1975 *Biochimie* 57:587–595](https://www.sciencedirect.com/science/article/abs/pii/S0300908475800396) [verify]).

**Step 2 — Peptide bond formation.** This is the chemistry. The A-site tRNA carries an amino acid attached to its 3' end via an ester bond (the amino acid's carboxyl group esterified to the tRNA's 3'-OH). The P-site tRNA carries the growing peptide chain attached to its 3' end the same way. The **peptidyl transferase center** of the 23S rRNA holds the two tRNAs in a precise geometry such that the **α-amino group** (the free NH₂) of the A-site amino acid is positioned to attack the **carbonyl carbon** of the ester bond between the peptide chain and the P-site tRNA. The attack forms a new bond — the peptide bond — between the growing chain and the new amino acid, while simultaneously breaking the ester bond holding the chain to the P-site tRNA. The chain has *transferred* from the P-site tRNA to the A-site tRNA.

Notice: the ribosome did not provide an energy source for this reaction. It did not use ATP or GTP at this step. It simply positioned the two reactants. The reaction itself runs on the energy already present in the ester bond holding the amino acid to the tRNA. This is why the aminoacyl-tRNAs are charged using ATP back at the aminoacyl-tRNA synthetase step — the energy is loaded into the ester bond there, and discharged into the peptide bond here. The ribosome is, in this respect, a precise catalyst rather than an energetic motor.

After the peptide bond forms: the A-site tRNA carries the elongated chain (now n+1 amino acids); the P-site tRNA is empty.

**Step 3 — Translocation.** The elongation factor **EF-G** (eEF2 in eukaryotes), bound to GTP, enters the ribosome. EF-G hydrolyzes its GTP and uses the energy to drive a conformational change in the ribosome that shifts everything by one codon: the empty P-site tRNA moves to the E site (and dissociates a moment later); the A-site tRNA (carrying the chain) moves to the P site; the next mRNA codon is now in the A site, ready for the next aminoacyl-tRNA. The mRNA has slid through the ribosome by exactly three nucleotides.

Cycle complete. The ribosome is back in the starting state, with one more amino acid added.

How fast does this run? In bacteria, **~20 amino acids per second per ribosome** under ideal conditions ([Bremer and Dennis 1996 *E. coli and Salmonella: Cellular and Molecular Biology* ASM Press](https://www.asmscience.org/content/book/10.1128/9781555818401) [verify]). In eukaryotes, slower — **~2-6 amino acids per second** ([Boehlke and Friesen 1975 *J Bacteriol* 121:429–433](https://journals.asm.org/doi/10.1128/jb.121.2.429-433.1975) [verify]). A 300-amino-acid protein is finished in ~15 seconds in *E. coli*, ~1-2 minutes in a human cell.

### Termination

The ribosome elongates until it encounters one of the three stop codons — **UAA, UAG, UGA** — in the A site. No tRNA has an anticodon that pairs with a stop codon (with rare exceptions in selenoprotein and pyrrolysine systems, where engineered tRNAs read UGA or UAG as the unusual amino acids selenocysteine and pyrrolysine; see below).

Instead, a **release factor** protein binds the A site directly. In bacteria, **RF1** recognizes UAA and UAG; **RF2** recognizes UAA and UGA. (The split assignment is one of the few cases in biology where a chemical signal has two distinct protein readers.) In eukaryotes, a single release factor **eRF1** recognizes all three stops. The release factor occupies the A site as if it were a tRNA, but instead of carrying an amino acid, it triggers **hydrolysis** of the ester bond between the peptide chain and the P-site tRNA. Water attacks the carbonyl carbon (instead of an amino group from a next amino acid, as in elongation). The peptide chain is released. The ribosome dissociates into its two subunits, with help from recycling factors. The ribosomes recycle. The mRNA is either translated again by a new initiation complex or degraded.

A nice oddity to know about. **Selenocysteine** (Sec, the "21st amino acid") is incorporated at certain UGA codons in specific mRNAs that contain a downstream stem-loop called a **SECIS element**. The cell has a dedicated tRNA-Sec, a dedicated synthetase pathway, and a dedicated elongation factor SelB that delivers Sec-tRNA to UGA codons only when the SECIS element signals "this UGA is not a stop." Selenocysteine is found in ~25 human proteins, including glutathione peroxidases and the iodothyronine deiodinases that activate thyroid hormone ([Lobanov et al. 2009 *Biochim Biophys Acta* 1790:1424–1428](https://www.sciencedirect.com/science/article/abs/pii/S0304416509001354) [verify]). **Pyrrolysine** (Pyl, the "22nd amino acid") is incorporated at certain UAG codons in some methanogenic archaea, by a similar context-dependent mechanism. These are the exceptions that prove the rule: stop codons mean stop *unless* the local sequence context says otherwise, in which case the ribosome reads them as a (rare) amino acid. The genetic code is not entirely fixed at every codon. It is fixed in steady-state, with allowed reassignments under controlled signals.

### Protein folding — the work continues after translation

A nascent polypeptide does not work as a flat chain of amino acids. It has to **fold** into a specific three-dimensional structure determined by its sequence — a result first established by **Christian Anfinsen's** experiments on ribonuclease in the 1950s and 60s (Nobel 1972; [Anfinsen 1973 *Science* 181:223–230](https://www.science.org/doi/10.1126/science.181.4096.223)). Anfinsen denatured ribonuclease in 8M urea (unfolded it completely), then removed the urea and found that the protein refolded *spontaneously* into its native, active conformation. The conclusion: **all the information needed to specify a protein's three-dimensional structure is contained in its amino acid sequence.** This is **Anfinsen's dogma** — and it is, like Crick's, a falsifiable claim about information flow, this time at the protein level.

In the cell, folding starts during translation — the N-terminus of the protein emerges from the ribosome's exit tunnel and begins folding while the C-terminus is still being synthesized. Many proteins fold without help. Others need assistance from a class of proteins called **chaperones** ("chaperone" — a word borrowed from social context, meaning a protein that protects an unfolded chain from misfolding without becoming part of the final product).

The major chaperone families:

- **Hsp70** (in bacteria, DnaK) — binds short stretches of exposed hydrophobic residues on nascent chains, preventing them from aggregating with other unfolded proteins before they have a chance to fold properly. Uses ATP hydrolysis to cycle between binding and release.
- **Hsp60 / GroEL** — a chaperonin barrel. Unfolded proteins enter the central cavity of GroEL; a cap (GroES) closes; the protein is held in the cavity for ~10 seconds while it has a chance to fold in isolation, free of aggregating neighbors; the cap opens and the (hopefully folded) protein is released. ATP-driven.
- **Hsp90** — specializes in stabilizing client proteins that are nearly folded but conformationally labile (steroid hormone receptors, signaling kinases). Drug target — Hsp90 inhibitors are being developed for cancer.

Most proteins fold correctly without intervention. A small fraction misfold. The cell has quality-control systems to detect misfolded proteins and either re-fold them (chaperones get another shot) or destroy them. The destruction system is the **ubiquitin-proteasome pathway**: misfolded proteins are tagged with chains of a small protein called **ubiquitin**, which targets them to the **proteasome** — a large barrel-shaped protease that chews up the protein into short peptides. The 2004 Nobel in Chemistry went to **Aaron Ciechanover**, **Avram Hershko**, and **Irwin Rose** for the ubiquitin-proteasome discovery ([Nobel Prize in Chemistry 2004](https://www.nobelprize.org/prizes/chemistry/2004/summary/)).

When the quality-control systems are overwhelmed — or when a misfolded protein is itself capable of templating misfolding in other copies of the same protein — disease results. **Alzheimer's disease** is associated with extracellular β-amyloid plaques and intracellular tau tangles, both of which are misfolded proteins. **Parkinson's disease** involves misfolded α-synuclein. **Huntington's disease** involves a polyglutamine-expanded huntingtin that misfolds and aggregates. **Prion diseases** (Creutzfeldt-Jakob disease, kuru, fatal familial insomnia in humans; scrapie in sheep; bovine spongiform encephalopathy in cattle) are caused by a single misfolded form of the prion protein PrP^Sc that catalyzes the misfolding of normally-folded PrP^C — propagating the misfolded conformation through the brain like an infection without nucleic acid ([Prusiner 1998](https://www.pnas.org/doi/10.1073/pnas.95.23.13363)). Prions are the strangest infectious agents in biology: they have no genome, only a fold.

The path from the right amino acid sequence to the right protein structure passes through folding. Translation gets you the sequence. Folding decides whether you get a protein or a problem.

---

## Worked example — one base, one disease, traced from DNA to vaso-occlusion

This is the chapter's mechanistic spine. I am going to walk **sickle cell anemia** from a single A→T mutation in DNA all the way through to a child in pain crisis at a hematology clinic. The chain is rare in its cleanness — single point mutation → single amino acid change → single protein defect → single clinical syndrome — and that cleanness is exactly what makes it the textbook example. Most disease genetics is messier. This one is pure.

### Step 1 — The DNA

Hemoglobin in adult red cells is a tetramer of **two α-globin chains and two β-globin chains** (designated **α₂β₂** or **HbA**), each chain wrapped around a heme group that binds oxygen. The β-globin protein is 146 amino acids long. Its gene, *HBB*, is on **chromosome 11** at locus 11p15.4. The gene has **3 exons and 2 introns**, with the coding sequence beginning at the start codon AUG (Met) and ending at the stop codon TAA, both within exon 3 in the case of β-globin's reading frame.

Codon 6 of the β-globin coding sequence in the wild-type gene reads, written on the coding strand 5'→3':

$$5'\text{-...GAG...-}3'$$

GAG codes for **glutamate (Glu, E)** — a negatively charged amino acid. The β-globin protein therefore has glutamate at position 6.

Now the mutation. **HbS** — sickle hemoglobin — carries a single base change at codon 6:

$$5'\text{-...GTG...-}3' \quad \text{(coding strand)}$$

The A at position 2 of the codon has become a T. On the template strand, the corresponding change is T→A. On the mRNA, the change will be A→U.

This is the **β^S allele** — the sickle allele. It was first identified as a hemoglobin variant by **Linus Pauling** in 1949 (using electrophoresis; [Pauling et al. 1949 *Science* 110:543–548](https://www.science.org/doi/10.1126/science.110.2865.543)) and as a single amino acid change by **Vernon Ingram** in 1956 (using protein fingerprinting; [Ingram 1957 *Nature* 180:326–328](https://www.nature.com/articles/180326a0)). Ingram's paper was the first demonstration that a Mendelian disease could be traced to a single amino acid substitution in a single protein — and it was a foundational moment for molecular medicine. We have known about this mutation for sixty-eight years. The mechanism we are about to trace is the consensus answer to a question Pauling was right to ask in 1949.

### Step 2 — Transcription

RNA polymerase II, with its full GTF assembly, binds the *HBB* promoter on chromosome 11, melts the DNA, and begins synthesizing pre-mRNA. The polymerase reads the **template strand** 3'→5', producing mRNA 5'→3'. At codon 6, where the coding strand reads **GTG** (sickle) or **GAG** (wild-type), the template strand reads:

- Wild-type template strand at codon 6: 3'-CTC-5'
- Sickle template strand at codon 6: 3'-CAC-5'

The mRNA synthesized antiparallel and complementary to the template will read:

- Wild-type mRNA at codon 6: 5'-GAG-3'
- Sickle mRNA at codon 6: 5'-GUG-3'

(Recall: U replaces T in RNA. The U pairs with the template's A.) Note that **the mRNA sequence is identical to the coding strand sequence, with U replacing T**. This is why we conventionally write genes as coding strands — they read the same as the mRNA.

### Step 3 — Processing

The β-globin pre-mRNA gets a 5' cap (added almost immediately after transcription starts), gets cleaved and polyadenylated at the 3' end (after the AAUAAA signal in the 3' UTR), and gets its two introns spliced out by the spliceosome. The mature mRNA is ~620 nucleotides long, of which 441 are the coding sequence for 146 amino acids plus the stop codon.

The mutation at codon 6 is *within exon 1* of β-globin and is *not* near any splice junction. Splicing is unaffected. The mature mRNA contains the GUG codon at the corresponding position. Mutations in *other* β-globin codons can disrupt splice sites and cause β-thalassemia rather than sickle cell — a reminder that not every disease-causing mutation acts at the protein-coding level. This one does.

The mature mRNA is exported through the nuclear pore complex to the cytoplasm.

### Step 4 — Translation

A ribosome finds the mature mRNA, recognizes the 5' cap, scans to the AUG start codon, and begins translating. The first amino acid is methionine (later cleaved off the mature protein). The codons proceed:

| Codon # | Wild-type codon | Wild-type amino acid | Sickle codon | Sickle amino acid |
|---|---|---|---|---|
| 1 | AUG | Met | AUG | Met |
| 2 | GUG | Val | GUG | Val |
| 3 | CAC | His | CAC | His |
| 4 | CUG | Leu | CUG | Leu |
| 5 | ACU | Thr | ACU | Thr |
| **6** | **GAG** | **Glu** | **GUG** | **Val** |
| 7 | GAG | Glu | GAG | Glu |
| ... | ... | ... | ... | ... |

(The codons through position 5 are the standard β-globin amino-terminal sequence after the initial Met is cleaved; published as Met-Val-His-Leu-Thr-Pro-Glu-Glu-... in the mature protein. I have simplified the codons here; the exact codon usage varies by individual but the consensus has GAG at position 6.)

At codon 6, the ribosome's A site reads GUG (sickle) instead of GAG (wild-type). The codon-anticodon scan brings in **tRNA-Val** (with anticodon 3'-CAC-5', or its wobble equivalent) instead of **tRNA-Glu** (with anticodon 3'-CUC-5'). The peptidyl transferase center of the 23S rRNA — the ribozyme — forms a peptide bond between valine and the growing chain (Met-Val-His-Leu-Thr-) instead of between glutamate and the growing chain. Translocation occurs. The next codon is read. The ribosome continues through all 146 codons without further differences from wild-type.

Result: a 146-amino-acid β-globin protein that is identical to wild-type at 145 of its 146 positions, and *valine instead of glutamate* at position 6.

### Step 5 — The chemistry of one amino acid

Glutamate and valine are not chemically similar.

- **Glutamate** has a side chain — CH₂-CH₂-COO⁻ — that ends in a **carboxylate group**. At physiological pH it is **negatively charged**. It is **hydrophilic** (water-loving) and likes to face the protein's surface, where it can interact with water and with positively charged residues on neighboring molecules.
- **Valine** has a side chain — CH(CH₃)₂ — that is a **branched alkyl group**. It is **uncharged**. It is **hydrophobic** (water-fearing) and prefers to face the protein's interior, away from water.

Substituting valine for glutamate at position 6 of β-globin puts a **hydrophobic patch on the surface** of the β-globin protein — exactly where there used to be a negative charge. The hemoglobin tetramer that contains two of these mutant β-chains now has *two hydrophobic patches* on its surface, in symmetric positions on the two β-chains.

### Step 6 — Polymerization under low oxygen

Hemoglobin in red cells exists in two conformational states: **R state** (relaxed, oxygen-bound) and **T state** (tense, oxygen-released). Under normal arterial oxygen pressure, most hemoglobin is in the R state; in capillaries where oxygen is being delivered to tissues, more shifts to T. The two states have slightly different shapes and surface properties.

The hydrophobic patch on HbS β-chains turns out to fit into a complementary pocket on a *different* HbS tetramer — specifically, into a hydrophobic pocket created by valine 88 and other residues on the β-chain of an adjacent molecule, but only when that adjacent molecule is in the T (deoxygenated) state. In the R (oxygenated) state, the pocket is not exposed; HbS stays in solution like normal hemoglobin.

In deoxygenated conditions — venous blood, capillaries in active tissues, anywhere oxygen tension is low — the T-state pocket opens up, and the Val-6 hydrophobic patch of one HbS tetramer binds the pocket on an adjacent T-state HbS tetramer. *And then* the bound HbS exposes its own pocket, and the next HbS binds to it. The result is a long **polymer** — a rod of HbS molecules stacked into a fiber. Many fibers can form in parallel, generating **deoxyhemoglobin S fibers** that are stiff, several micrometers long, and capable of physically distorting the red cell from its normal flexible biconcave-disk shape into a **sickle shape** ([Eaton and Hofrichter 1990 *Adv Protein Chem* 40:63–279](https://www.sciencedirect.com/science/article/abs/pii/S0065323308608370) [verify]).

When the red cell returns to high-oxygen conditions in the lungs, the fibers depolymerize; HbS returns to soluble R-state monomers; the red cell relaxes (usually) back to its normal shape. But every cycle of sickling-and-unsickling damages the red cell membrane, and after many cycles the cell loses its ability to recover and becomes **irreversibly sickled**.

### Step 7 — The clinical phenotype

Three downstream consequences follow.

First, **hemolytic anemia.** Irreversibly sickled cells have damaged membranes and shortened lifespans. Where normal red cells survive ~120 days, sickle cells survive only ~10–20 days ([Steinberg 1999 *N Engl J Med* 340:1021–1030](https://www.nejm.org/doi/10.1056/NEJM199904013401307) [verify]). The bone marrow tries to compensate by producing more red cells, but cannot fully keep up. The patient runs chronically anemic, with hemoglobin levels typically 6–8 g/dL (normal ~13–16 g/dL).

Second, **vaso-occlusion.** Sickle-shaped red cells are stiff and angular. They get stuck in capillaries and small post-capillary venules — particularly in tissues with low oxygen tension (skeletal muscle during exertion, the spleen, kidney medulla, bone marrow). The trapped cells block blood flow downstream. Tissue distal to the occlusion becomes ischemic. The patient experiences **pain crises** — severe, sometimes excruciating pain in bones, joints, abdomen, chest. Repeated crises lead to chronic organ damage: avascular necrosis of femoral heads, splenic infarction (the spleen "auto-infarcts" by adolescence in many sickle cell patients, leaving them functionally asplenic and at high risk for encapsulated bacterial infections), pulmonary infarction ("acute chest syndrome" — a leading cause of death), stroke, renal insufficiency.

Third, **organ damage over time.** Patients in their 30s and 40s accumulate cumulative end-organ damage. Life expectancy in sickle cell disease has improved dramatically with modern care (newborn screening, prophylactic penicillin in infancy, transfusion programs, hydroxyurea, and in 2023, FDA-approved gene therapies including Casgevy/exa-cel and Lyfgenia; [FDA approval announcement December 2023](https://www.fda.gov/news-events/press-announcements/fda-approves-first-gene-therapies-treat-patients-sickle-cell-disease) [verify]) but remains lower than the general population.

### Step 8 — The lesson, and its limits

That is one A→T change in DNA, traced through transcription, processing, translation, folding, polymerization, vaso-occlusion, and clinical phenotype. **The chain is mechanistic and traceable.** Every step has been observed; every step has a named mechanism; every step is, in principle, a place where a therapy could intervene. Hydroxyurea works at the level of γ-globin reactivation, raising fetal hemoglobin (HbF) levels and diluting the HbS pool. Voxelotor stabilizes the R state of HbS, reducing T-state polymerization. Gene therapies edit the DNA — either to restore the wild-type β-globin sequence or to disrupt BCL11A and reactivate fetal hemoglobin. Each therapy targets a specific link in the chain. The chain is what makes targeted therapy thinkable.

**Two important limits.** First, **most disease-causing mutations are messier.** Cystic fibrosis (CFTR) has hundreds of disease-causing mutations across the gene; most are not single base changes; many disrupt protein folding rather than amino acid identity. Hereditary cancer syndromes (BRCA1/2, Lynch) involve loss of one allele plus somatic loss of the other, with the disease phenotype emerging only in tissues where the somatic loss happens. Complex disease (diabetes, schizophrenia, heart disease) involves polygenic combinations of dozens to thousands of small-effect variants. Sickle cell is unusual in being a *clean* Mendelian disease with a *clean* molecular mechanism. That cleanness is why it teaches well.

Second, even within sickle cell, the **carrier state** (heterozygote: one β^A and one β^S allele) is informative. Carriers have ~40% HbS and ~60% HbA in their red cells; the HbA dilutes the HbS enough that polymerization rarely happens under normal oxygen conditions; carriers are largely asymptomatic. The β^S allele has reached high frequency in populations from sub-Saharan Africa, parts of the Mediterranean, the Arabian peninsula, and India — because heterozygotes are partially protected against severe malaria caused by *Plasmodium falciparum*. The parasite has more difficulty completing its intracellular life cycle in HbS-containing red cells, and infected HbS heterozygote red cells are cleared more rapidly by the spleen. **Heterozygote advantage** — also called balancing selection — keeps the allele at frequencies of 5–15% in malarial regions ([Allison 1954 *BMJ* 1:290–294](https://www.bmj.com/content/1/4857/290) [verify]; [Aidoo et al. 2002 *Lancet* 359:1311–1312](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736\(02\)08273-9/fulltext) [verify]). Chapter 09 will pick this up as a worked example of natural selection acting on a single locus. For now, hold this: the same mutation that is devastating in homozygotes is *adaptive* in heterozygotes in the right environment, and that fact is why the allele has not been selected out of the human gene pool over the millennia it has been present.

A single A→T change. Followed through the central dogma. Producing a clinical syndrome that has shaped human population genetics. *This* is what it means to say molecular biology and medicine are the same story.

---

## Antibiotics — exploiting the difference between 70S and 80S

Bacterial ribosomes are 70S. Human ribosomes are 80S. The core of the catalytic machinery is conserved (peptidyl transferase center is nearly identical across all life), but the surrounding architecture — the proteins, the rRNA expansion segments, the precise geometry of the A and P sites — is different enough that small molecules can bind one and not the other. Most clinically important antibiotics that target translation exploit exactly this difference. They are some of the most useful drugs in medicine. They are also, increasingly, losing their effectiveness to bacterial resistance — a story we will pick up in Chapter 09 when we talk about evolution under selection.

A short tour, organized by where on the ribosome the drug binds. (Note: many of these drugs have eukaryotic mitochondrial ribosomes — which are 55S, prokaryote-like — as a low-level off-target. This is why some of them have characteristic mitochondrial toxicities. Mitochondria are evolutionary descendants of α-proteobacteria; their ribosomes are still recognizable as bacterial.)

**Aminoglycosides** — streptomycin, gentamicin, tobramycin, neomycin. Bind the **30S subunit** at the decoding center of the 16S rRNA. They distort the A-site geometry so that incorrect tRNAs are accepted as correct — the ribosome reads the codon wrong. The resulting proteins are full of errors; the bacterium dies from accumulated misfolded membrane proteins and metabolic enzymes. Mechanism: **codon misreading**. Side effects: nephrotoxicity and ototoxicity (irreversible hearing loss), because aminoglycosides also bind mitochondrial 12S rRNA in hair cells of the inner ear.

**Tetracyclines** — tetracycline, doxycycline, minocycline, tigecycline. Bind the **30S subunit** at the A site. Mechanism: **block A-site tRNA entry**. Without the next tRNA arriving, elongation halts. Bacteriostatic (stops bacteria from growing) rather than bactericidal (killing them outright), but combined with the immune system that is usually enough.

**Chloramphenicol.** Binds the **50S subunit** at the **peptidyl transferase center**. Mechanism: **inhibits peptide bond formation directly** — it occupies the A-site amino acid binding pocket, preventing the α-amino group of the incoming amino acid from attacking the carbonyl of the P-site peptide. Bacteriostatic. Side effects: aplastic anemia (rare but severe), gray baby syndrome — used now in very limited circumstances because of toxicity.

**Macrolides** — erythromycin, clarithromycin, azithromycin. Bind the **50S subunit** in the **peptide exit tunnel** — the channel through which the nascent peptide chain leaves the ribosome. Mechanism: **physically obstruct the exit tunnel**. The growing peptide gets stuck after ~6-8 amino acids; the ribosome stalls; translation aborts. Bacteriostatic.

**Oxazolidinones** — linezolid. Binds the **50S subunit** at the A site of the peptidyl transferase center. Mechanism: **prevents formation of the initiation complex** — interferes with the joining of the large subunit. Used against resistant Gram-positive infections (MRSA, VRE).

In each case, the drug exploits a structural feature of the bacterial ribosome that is sufficiently different from the eukaryotic version that the drug binds bacterial but not eukaryotic. The therapeutic index — the gap between the dose that kills bacteria and the dose that harms the patient — depends on how well-conserved the binding site is between the two ribosome types. Aminoglycosides, with their hair-cell mitochondrial off-target, have a narrower therapeutic index than tetracyclines, which have fewer off-target effects.

A standard exam question that I want you to be able to reason through: **Why does an aminoglycoside affect bacterial cells but not human cells?** The first-order answer is: the drug binds the 30S subunit of the 70S bacterial ribosome at a position that is structurally different in the 40S subunit of the 80S eukaryotic ribosome. The drug fits one but not the other. The second-order answer (the one that earns full credit): the drug *does* bind to a low-level extent at the 12S rRNA of the mitochondrial ribosome inside hair cells of the cochlea, which is why aminoglycoside ototoxicity is a real clinical issue — particularly in patients with the mitochondrial mutation A1555G in 12S rRNA, who are hypersusceptible to aminoglycoside-induced hearing loss after a single dose. The selectivity is not perfect. It is enough to be useful.

---

## Recombinant proteins and mRNA vaccines — the genetic code as engineering substrate

Two clinical platforms — separated by forty years of biotechnology — both turn on the same fact: **the genetic code is universal**. If you can give a cell a piece of DNA or RNA that codes for a protein, the cell's transcription and translation machinery will make that protein, regardless of where the sequence came from.

### Recombinant insulin (Humulin, 1982)

Before 1982, insulin for diabetic patients was extracted from pig and cow pancreases obtained from slaughterhouses. Animal insulin differs from human insulin by one to three amino acids; some patients developed immune reactions to the non-self residues. The supply was also limited by the slaughterhouse pipeline.

In 1978, a team at **Genentech** led by **Herbert Boyer** synthesized the human insulin gene chemically — they did not isolate it from a human cell; they wrote it from scratch using a DNA synthesizer, using the genetic code to back-translate from the known amino acid sequence of human insulin to a DNA sequence ([Goeddel et al. 1979 *PNAS* 76:106–110](https://www.pnas.org/doi/10.1073/pnas.76.1.106)). They inserted the synthetic gene into a plasmid, transformed the plasmid into *E. coli*, and the bacteria began producing human insulin protein. **Eli Lilly** licensed the technology and brought Humulin to market in 1982 — the first FDA-approved recombinant DNA product ([Johnson 1983 *Science* 219:632–637](https://www.science.org/doi/10.1126/science.6337396) [verify]).

The architecture works because the *E. coli* ribosome reads AUG as Met, GCC as Ala, GAG as Glu — exactly as the human ribosome does. The synthetic gene was actually a slightly modified DNA sequence — it used codons that *E. coli* prefers (codon usage frequencies are different across species; rare codons in *E. coli* are translated more slowly and can stall ribosomes), with a bacterial Shine-Dalgarno sequence added upstream, and the two insulin chains (A and B) initially produced separately and then disulfide-bonded after purification. But the *amino acid sequence* the bacterium produced was identical to the natural human insulin sequence. The same protein.

Today, virtually all insulin used clinically is recombinant — from bacteria or yeast. The same approach has produced recombinant human growth hormone, recombinant erythropoietin, recombinant clotting factors VIII and IX, recombinant monoclonal antibodies, and dozens of other therapeutic proteins. The biotechnology industry is built on the genetic code being interpretable across species.

### mRNA vaccines (BNT162b2 / Comirnaty, mRNA-1273 / Spikevax, 2020)

The mRNA-vaccine architecture takes the same principle one step further. Instead of putting a gene into a cell and waiting for the cell to transcribe and translate it, you put an *mRNA* into the cell — skipping the transcription step entirely. The cell's ribosomes do the rest.

The Pfizer-BioNTech and Moderna COVID-19 vaccines from 2020 follow this design. The mRNA encodes the SARS-CoV-2 spike protein in a slightly modified form: the spike is "**proline-stabilized**" with two proline substitutions (K986P, V987P) that lock the protein in the pre-fusion conformation, which presents the most immunogenic epitopes to the immune system ([Pallesen et al. 2017 *PNAS* 114:E7348–E7357](https://www.pnas.org/doi/10.1073/pnas.1707304114) [verify]). The mRNA sequence is **codon-optimized for human translation** — choosing among synonymous codons to favor those the human ribosome translates fastest. Every uridine in the mRNA is replaced with **N1-methylpseudouridine** (m1Ψ), a modified base that pairs with adenosine the same way uridine does, but evades the innate immune system's RNA sensors (TLR3, TLR7, RIG-I, MDA5) that would otherwise detect the synthetic RNA as viral and destroy it. The 5' cap is a synthetic cap analog. The 3' poly(A) tail is built into the in vitro transcription template. The mRNA is encapsulated in a **lipid nanoparticle** designed to fuse with cell membranes and deliver the mRNA to the cytoplasm ([Hou et al. 2021 *Nat Rev Mater* 6:1078–1094](https://www.nature.com/articles/s41578-021-00358-0) [verify]).

The vaccine is injected. Lipid nanoparticles fuse with cells (mostly muscle cells and dendritic cells at the injection site). The mRNA enters the cytoplasm. Ribosomes pick it up, find the AUG, translate spike protein. The spike protein gets processed through the secretory pathway, presented on the cell surface (and on MHC molecules to T cells), and the immune system is trained against it. The mRNA is degraded within hours to days by normal cellular ribonucleases. The synthetic protein is degraded along with normal cellular proteins on its usual timescale. Nothing persists.

Phase 3 results from BNT162b2 showed ~95% efficacy against symptomatic COVID-19 in the first months after the second dose ([Polack et al. 2020 *N Engl J Med* 383:2603–2615](https://www.nejm.org/doi/10.1056/NEJMoa2034577); published online December 10, 2020). mRNA-1273 was similar ([Baden et al. 2021 *N Engl J Med* 384:403–416](https://www.nejm.org/doi/10.1056/NEJMoa2035389)). The platform now has applications under clinical development for influenza, RSV, melanoma, pancreatic cancer, and more. The 2023 Nobel in Physiology or Medicine to **Katalin Karikó** and **Drew Weissman** recognized the pseudouridine modification breakthrough that made mRNA vaccines clinically feasible ([Nobel Prize 2023](https://www.nobelprize.org/prizes/medicine/2023/summary/)).

The mRNA vaccine works because the genetic code is universal. The ribosome reads AUG as Met regardless of whether the mRNA was transcribed from your DNA or assembled on a benchtop. The architectural principle is the central dogma, exploited as a design constraint. The engineering is in the modifications — pseudouridine, codon optimization, lipid nanoparticles — that make a synthetic mRNA stable enough to reach the ribosome and stealthy enough to escape immune detection until the ribosome has done its job.

---

## Common misconceptions — at least three to defuse

**Misconception 1.** *"RNA is just a less stable version of DNA."* No. RNA serves at least three categorically distinct roles, only one of which is informational. **Messenger RNA (mRNA)** carries protein-coding information — this is the role that looks like "DNA with extra steps." **Transfer RNA (tRNA)** and **ribosomal RNA (rRNA)** are structural and catalytic — tRNAs adapt codons to amino acids; rRNAs are the catalytic core of the ribosome, doing peptide-bond chemistry. **Regulatory RNAs** (miRNAs, lncRNAs, siRNAs, snRNAs of the spliceosome) regulate gene expression and process other RNAs. The 2'-OH that makes RNA chemically less stable than DNA is the same 2'-OH that makes RNA capable of catalysis. The instability is a feature, not a bug. It is what allows mRNA half-lives to be tuned for regulation, what allows ribozymes to exist, and what suggests early life was RNA-based before protein enzymes evolved.

**Misconception 2.** *"The genetic code isn't really universal — every species has its own code."* It is universal, with a handful of well-characterized exceptions all in unusual contexts. The standard code is the same in *E. coli*, archaea, plants, animals, and fungi. The major exceptions are: **mitochondrial codes**, where a few codon reassignments differ between vertebrate, yeast, and plant mitochondria; **some ciliates and yeasts**, where stop codons UAA/UAG occasionally code for glutamine; **mycoplasmas**, where UGA codes for tryptophan; and the **selenocysteine and pyrrolysine** context-dependent reassignments mentioned earlier. The exceptions are confined to specific contexts and almost always involve reassigning stop codons rather than reassigning amino-acid codons. The general rule — AUG starts, UAA/UAG/UGA stop, the 61 sense codons map to 20 amino acids — holds across nearly all life. Recombinant insulin in *E. coli*, recombinant erythropoietin in CHO cells, mRNA vaccines in human cells — these all *only work* because the code is the same.

**Misconception 3.** *"The ribosome is a protein machine."* The ribosome is roughly 60% RNA by mass (~50% in bacteria), and the active site that catalyzes every peptide bond formed in every protein in every organism is RNA, not protein. The 2009 Nobel was given for this very fact — the crystal structures definitively showed there is no protein within 18 Å of the peptidyl transferase active site. The proteins of the ribosome are scaffolding, contributing to stability and to the kinetics of subunit assembly, but they are not the catalyst. The ribosome is the largest known **ribozyme**, and the fact that protein synthesis itself is catalyzed by RNA is one of the strongest pieces of evidence we have that early life ran on RNA before proteins existed.

**Misconception 4.** *"Frameshift mutations are similar in severity to point mutations."* They are not. A single-base point mutation typically affects one codon (silent, missense, or nonsense). A single-base insertion or deletion shifts the reading frame for *every codon downstream of the indel* — every amino acid from the indel to the end of the protein is wrong, and new stop codons (statistically present every ~21 codons in a random sequence) usually truncate the protein early. Frameshift mutations are almost always loss-of-function. Indel mutations at the start of a gene are catastrophic; indels near the end may leave most of the protein intact and produce a partial loss-of-function. **Insertion of three bases or deletion of three bases** — multiples of three — preserves the reading frame and produces in-frame insertions or deletions of a single amino acid, which are usually much milder than frameshifts. Δ508 in CFTR (cystic fibrosis) is an in-frame deletion of three nucleotides removing a single phenylalanine — far less severe at the sequence level than a frameshift, but the missing residue disrupts protein folding, causing the disease.

**Misconception 5.** *"Splicing always produces the same mRNA from the same gene."* No — most multi-exon human genes undergo alternative splicing, producing multiple distinct protein isoforms from a single gene. The choice of which exons to include is tissue-specific, developmental-stage-specific, and condition-specific. *Drosophila* Dscam produces in principle ~38,000 isoforms from one gene; average human genes produce ~7 distinct protein isoforms. The "one gene, one protein" framing of mid-20th-century biology turned out to be wrong; the correct framing is "one gene, many proteins, depending on regulation."

---

## Exercises

### Warm-up — mechanism check

**Exercise 1.** A DNA template strand reads, written 3'→5': $3'\text{-TACCGTAATGCG-}5'$. Use this to:

(a) Write the **mRNA** that RNA polymerase would synthesize from this template, in 5'→3' direction.

(b) Write the **coding strand** of the DNA (the strand whose sequence matches the mRNA except T for U), in 5'→3' direction.

(c) Identify which strand RNA polymerase reads and in which direction it moves along that strand.

(d) Translate the mRNA into a polypeptide. Use the standard genetic code table. Identify the start codon and the stop codon.

*Tests: transcription directionality; template vs. coding strand distinction; translation in the correct frame.*

**Exercise 2.** Explain why **RNA polymerase needs no primer** but **DNA polymerase does**. Your answer should reference the chemistry of chain initiation (what kind of bond gets formed when the very first phosphodiester bond is made), and should explain why this difference makes evolutionary and engineering sense (why the cell does not use a DNA polymerase that can self-initiate).

*Tests: understanding of chain-initiation chemistry, polymerase fidelity tradeoffs, the role of primase in replication.*

**Exercise 3.** The genetic code is **degenerate** (most amino acids are specified by multiple codons), but not **ambiguous** (no codon specifies more than one amino acid). State what each property means in one sentence, and explain why a code that was *ambiguous* (with single codons coding for multiple amino acids depending on context) would be unworkable for an organism that needs to produce a specific protein reproducibly.

*Tests: precise vocabulary; understanding of why degeneracy is tolerable and ambiguity is not.*

### Application — mutation classification and prediction

**Exercise 4.** A short coding sequence reads, on the mRNA:

$$5'\text{-AUG CCG UAC GAA UAA-}3'$$

Translate this sequence into an amino acid chain, then predict the effect of each of the following independent mutations:

(a) The second codon CCG is changed to CCU.
(b) The third codon UAC is changed to UAA.
(c) The third codon UAC is changed to UGC.
(d) A single U is deleted from position 5 of the mRNA (immediately after the AUG).
(e) The second codon CCG is changed to CGG.

For each, classify the mutation as **silent**, **missense**, **nonsense**, or **frameshift**, and describe the consequence for the protein. For missense mutations, comment on whether the substituted amino acid is chemically similar or different from the original (and therefore whether the mutation is likely to be tolerated or disruptive).

*Tests: comprehensive mutation classification and reasoning about functional consequences.*

**Exercise 5.** A patient with **sickle cell trait** (heterozygous β^A/β^S) is largely asymptomatic but partially protected against severe *Plasmodium falciparum* malaria. Explain, using the mechanism developed in this chapter, why:

(a) Heterozygotes are not symptomatic — given that ~40% of their hemoglobin is HbS.

(b) Heterozygotes are partially protected against malaria — what feature of the HbS red cell makes it a less good host for *Plasmodium*?

(c) Homozygotes (β^S/β^S) are severely symptomatic — what is qualitatively different in a homozygote red cell compared to a heterozygote red cell?

*Tests: integration of molecular mechanism (HbS polymerization is concentration-dependent) with population genetics (heterozygote advantage). Connects to upcoming Chapter 09 on natural selection.*

**Exercise 6.** A bacterium is being treated with **chloramphenicol**, an antibiotic that binds the 50S subunit of the 70S ribosome at the peptidyl transferase center. Predict:

(a) What specific step of translation will be blocked? Walk through which step of the elongation cycle (A-site entry, peptide bond formation, translocation) is the direct target.

(b) Why does the drug affect bacteria but spare the patient's own protein synthesis?

(c) The drug has, as a rare but serious side effect, **aplastic anemia** — failure of bone marrow stem cells. Given that bone marrow cells are eukaryotic and have 80S ribosomes (which are not the target), propose at least one mechanism by which chloramphenicol might still affect bone marrow cells. (Hint: where else in a eukaryotic cell would you find ribosomes that look more like bacterial ribosomes than like 80S eukaryotic ribosomes?)

*Tests: mechanism of drug action; reasoning about off-target effects via mitochondrial ribosomes.*

### Synthesis — beyond a single mutation

**Exercise 7.** Two genes have **identical coding sequences** in their mRNAs but produce **different proteins**. Both are transcribed from the same primary RNA transcript. Explain how this is possible — what cellular process accounts for this — and give one specific named example. Then explain how the cell "knows" which version to produce in which tissue (one or two named mechanisms).

*Tests: understanding of alternative splicing and tissue-specific regulation.*

**Exercise 8.** The bacterial ribosome and the eukaryotic ribosome share a deeply conserved catalytic core (peptidyl transferase center, decoding center) but differ enough in surrounding structure that many antibiotics can selectively bind one but not the other. From this fact, reason backward to a claim about **evolutionary history**:

(a) What does the conservation of the catalytic core tell you about when the ribosome evolved relative to the split between bacteria and eukaryotes?

(b) What does the divergence of the surrounding structure tell you about the timescale over which ribosome structure has continued to evolve?

(c) The mitochondrial ribosome (55S) is more similar to the bacterial 70S than to the cytoplasmic 80S. What does this fact suggest about the origin of mitochondria? (This is one of the founding pieces of evidence for the **endosymbiotic theory**.)

*Tests: integration of molecular biology with evolutionary reasoning. Connects to later chapters on molecular evolution and the origin of complex cells.*

### Challenge — engineering and clinical reasoning

**Exercise 9.** You are designing a synthetic gene to express a human protein in *E. coli* for therapeutic manufacture (a recombinant cytokine). You know the amino acid sequence of the protein.

(a) **Codon optimization.** Using the degeneracy of the genetic code, explain why you have many possible DNA sequences that could encode this protein. Then explain why you would not just pick the first one you can write down — specifically, why **codon usage** differs between *E. coli* and humans and why "rare codons" in *E. coli* would slow or stall translation.

(b) **Initiation signal.** What feature must you include **upstream** of your coding sequence to allow the bacterial ribosome to find and initiate translation? Name the sequence. Why is this feature *not* present in human mRNAs?

(c) **Post-translational issues.** Many human proteins require post-translational modifications (glycosylation, disulfide bond formation, phosphorylation) that *E. coli* does not perform. For one named modification, explain how you would handle this if your therapeutic protein needs it — what alternative host cell would you use, and why?

(d) **Quality control.** You will need to verify that the protein you produce has the correct amino acid sequence. Name one analytical method that could do this and explain in one sentence what it measures.

*Tests: practical application of the central dogma to recombinant protein engineering; integration of codon usage, translation initiation, post-translational processing, and analytical verification.*

**Exercise 10.** The Pfizer-BioNTech BNT162b2 mRNA vaccine has the following design features:

- mRNA encoding a stabilized SARS-CoV-2 spike protein (two proline substitutions in the S2 stalk).
- All uridines replaced with **N1-methylpseudouridine**.
- A 5' cap (synthetic cap analog).
- A 3' poly(A) tail.
- Codon-optimized for human translation.
- Encapsulated in a lipid nanoparticle.

For each of the six design features, explain in one or two sentences **why** it is included — what would go wrong if you left it out, and what specific step of the central dogma or cellular biology it supports. Order your answers from "without this, the mRNA never reaches the ribosome" to "without this, the protein still gets made but the immune response is less effective."

*Tests: integration of every step of the central dogma at the level of a real engineered system. Forces students to reason about both the necessity and the priority of each modification.*

---

## What would change my mind

If a confirmed example of **information flow from protein sequence back to nucleic acid sequence** — protein → mRNA, or protein → DNA — were demonstrated under controlled conditions, the central dogma in Crick's original 1958 formulation would have to be revised. Prion propagation is conformational, not sequence-encoding, and does not count. The empirical absence of protein → nucleic acid information transfer is what makes Crick's claim falsifiable and currently correct. A real exception would be the most important molecular-biology result in seventy years.

A weaker but still significant finding: if **codon reassignments** turned out to be common in mainstream lineages of life — if a substantial fraction of bacterial or animal genomes used codes meaningfully different from the standard — the "frozen accident" explanation for the universality of the code would have to be replaced with something else (perhaps recurring convergence). The current data, in which the standard code holds across nearly all life with only narrow mitochondrial and ciliate exceptions, supports the frozen-accident model. A broader survey overturning this would force a reinterpretation.

---

## Still puzzling

The **peptidyl transferase reaction** — the actual bond-forming step at the catalytic core of the ribosome — is now understood at atomic resolution, but the question of *how* the 23S rRNA achieves the rate enhancement it does (the reaction goes about ~10⁷-fold faster on the ribosome than in solution) is still debated. The leading model is "substrate positioning" — the ribosome organizes the geometry of the two tRNAs and the water network around the active site, and the catalysis is essentially entropic rather than electrostatic ([Sievers et al. 2004 *PNAS* 101:7897–7901](https://www.pnas.org/doi/10.1073/pnas.0402488101) [verify]). But the proposed contributions from specific 23S nucleotides — A2451 in particular — have been argued back and forth for two decades. The cleanest single-residue knockout experiments do not eliminate catalysis. I find this satisfying. The ribosome has been with us for four billion years; we have only had the structure for twenty-five. We are still figuring out exactly how it does the chemistry it does.

---

**Tags:** central-dogma, transcription, translation, genetic-code, ribosome-as-ribozyme, sickle-cell, mRNA-vaccines, antibiotics, recombinant-insulin, wobble-hypothesis
