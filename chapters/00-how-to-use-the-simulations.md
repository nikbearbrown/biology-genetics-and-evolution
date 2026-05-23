# Chapter 00 — How to Use the Simulations

**Suggested titles:**
- *Before You Read Any Genetics, Build a Punnett Square That Won't Quit*
- *Three Files, Two Letters, and a Grid That Doubles Until Your Laptop Notices*
- *How to Make Mendel's Arithmetic Run on Your Browser*

---

**TL;DR.** Before you read any new genetics in this book, you will build a working Punnett-square generator on your laptop — three governing files (CLAUDE.md, DESIGN.md, PROJECT.md), one HTML file, one equation that doubles as it goes. The point is not the simulation; the point is the habit of prompting an LLM precisely enough that the simulation runs the first time, scales from a 2×2 grid to a 128×128 grid without rewriting, and tells you on load whether the combinatorics are right.

---

## Learning objectives

By the end of this chapter, you will be able to:

1. **Construct** the three Brutalist governing files — CLAUDE.md, DESIGN.md, PROJECT.md — for a genetics simulation project, and **explain** what each one constrains.
2. **Compose** a four-move prompt (Show / Say / Constrain / Verify) that produces a runnable D3 v7 Punnett-square generator in a single pass.
3. **Derive** the 2^N gamete count for N independently assorting heterozygous loci and **show** that the Punnett-square grid is 2^N × 2^N = 4^N cells.
4. **Verify** a genetics simulation against biology by reading three falsifiable claims off the console — the 1:2:1 monohybrid genotype ratio, the 9:3:3:1 dihybrid phenotype ratio, the 27:9:9:9:3:3:3:1 trihybrid phenotype ratio.
5. **Critique** four common failure modes ("dominant means common," "1:2:1 means exactly one out of four," "if the LLM wrote it, it's right," "Punnett squares predict every cross") and **apply** the critique to your own build.

**Prerequisites.** A laptop with a text editor and a browser. An account on claude.ai (or any LLM — the prompts work in ChatGPT and Gemini with small edits). The ability to double-click an HTML file. No coding background assumed. No prior genetics beyond "kids look like their parents, sort of."

---

## A scene from a monastery garden

Brno, Moravia, summer of 1856. A 34-year-old Augustinian friar named Gregor Mendel kneels at the edge of a rectangular plot of pea plants and, with a small pair of forceps, removes the immature anthers from a flower before its own pollen can ripen. He is not the abbot. He is not famous. He has failed his teaching certification exam twice — once in 1850 in natural science, again in 1856 in the same subject — and he is back from a stint at the University of Vienna where he picked up physics from Christian Doppler and probability from Andreas von Ettingshausen. He has chosen pea plants because they let him control which flower pollinates which, because they self-fertilize when left alone, and because they come in pairs of contrasting traits a person can sort at a glance — round seeds versus wrinkled, yellow seeds versus green, tall plants versus short. Over the next eight years he will grow, by the standard count he reported, on the order of 28,000 plants across multiple generations and write down what he sees in columns of integers. *5474 round seeds. 1850 wrinkled.* That is a 2.96 : 1 ratio. He rounds it to 3:1.

In 1865 he reads his results aloud to forty members of the Brno Natural History Society — botanists, physicians, a meteorologist — across two evening lectures, on 8 February and 8 March. They are polite. They do not understand what they have heard. The paper is published the next year in the society's *Verhandlungen* and accumulates dust for thirty-four years until three botanists, in 1900, independently rediscover the same ratios and Mendel becomes Mendel. (Mendel G. *Versuche über Pflanzen-Hybriden*. *Verhandlungen des naturforschenden Vereines in Brünn*. 1866;4:3–47. The published date is 1866; the lectures are 1865.)

Now imagine you are a genetic counselor in a hospital in 2024. A couple sits across from you. Both carry one copy of a recessive allele at the *CFTR* gene — the gene whose protein product is a chloride channel; the failure of that channel is cystic fibrosis. Both are healthy heterozygotes, Aa. They want to know the chance that any child they have will be affected, aa. You take out a small piece of paper. You draw a 2×2 grid. You label the rows with the mother's two gamete types — A and a — and the columns with the father's — A and a. You fill in the four cells: AA, Aa, Aa, aa. You circle the aa cell. *One in four*, you say. *Each pregnancy, independent of the last.*

The grid you just drew is a Punnett square. Reginald Punnett at Cambridge formalized it around 1905 and published it in his short textbook *Mendelism*. The square is bookkeeping — gametes across the top, gametes down the side, offspring genotypes in the cells. The arithmetic underneath is Mendel's, from sixty years earlier and four hundred miles away. The clinical decision in front of you depends on getting it right.

A monohybrid cross — one locus, both parents heterozygous — is a 2×2 grid you can sketch on a napkin. A dihybrid is a 4×4. A trihybrid is an 8×8. Add a fourth locus and the grid is 16×16 — two hundred fifty-six cells. Add three more — Mendel's full seven traits — and the grid is 128 × 128, sixteen thousand three hundred eighty-four cells. The arithmetic is the same arithmetic. What fails is the napkin.

This chapter is about replacing the napkin.

---

## What we are actually doing

Three things, in order.

**One.** We are setting up a project structure that will outlast this chapter. The structure is called Brutalist because there is nothing decorative in it — three plain-text files governing the entire workshop, no frameworks, no build tools, no `npm install`. The files are CLAUDE.md, DESIGN.md, and PROJECT.md. CLAUDE.md tells the LLM how to write code for this book. DESIGN.md tells it how the result should look. PROJECT.md tells it what already exists and what comes next. Every simulation in every chapter will refer back to these three files. Get them right once and you will not write them again.

**Two.** We are learning a four-move prompt structure. Most students paste vague requests into Claude — *"make me a Punnett-square thing"* — and then spend an hour cleaning up output that looks plausible and sums to 13. We are going to skip that hour. The structure is **Show / Say / Constrain / Verify**. Show the LLM the files it should follow. Say what you want in one paragraph. Constrain how it has to be built (D3 v7, single HTML file, no external dependencies). Verify by giving it a falsifiable biology question it must satisfy — *the trihybrid phenotype counts must sum to 64*. Four moves. Used together they are far more reliable than any one move alone.

**Three.** We are building one specific simulation — a generalized Punnett-square generator that handles a cross at one locus, two loci, three loci, up to seven — because every chapter that follows is, in one way or another, an extension of this combinatorics. Meiosis (Chapter 1) is the *mechanism* that produces the 2^N gametes the square assumes. Linkage (Chapter 3) is the *failure mode* of the square's independence assumption. Hardy-Weinberg (Chapter 10) is the *population-scale* extension of the same arithmetic. The combinatorics underneath every one of these is the combinatorics you are about to put on the screen.

Let me define the vocabulary now, plainly, before we touch any code.

### Allele, genotype, phenotype — in one paragraph

A **gene** is a stretch of DNA at a specific location on a chromosome that codes for something — often a protein, sometimes a regulatory RNA, sometimes a control element. The specific location on the chromosome is called a **locus**. An **allele** is a particular version of the gene that lives at that locus — one variant out of however many variants exist in the population. *CFTR* is a gene; the wild-type sequence is one allele, the ΔF508 deletion is another, the G551D substitution is another, and so on across more than two thousand catalogued variants. A diploid organism — a pea plant, a human, a fruit fly — carries two copies of each chromosome and therefore two alleles at each locus, one inherited from each parent.

The pair of alleles a person carries at a given locus is their **genotype** at that locus. By convention we write it as two letters — *AA*, *Aa*, *aa* — where uppercase is the dominant allele and lowercase is the recessive. The observable trait that genotype produces is the **phenotype**. *Homozygous* means both alleles are the same (AA or aa). *Heterozygous* means the two alleles differ (Aa). *Dominant* means the allele's effect is what you see in the heterozygote — Aa looks like AA. *Recessive* means the allele's effect is hidden in the heterozygote and visible only in the homozygote — aa is the only genotype that produces the recessive phenotype.

A few of these words mislead. *Dominant* sounds like *strong* or *common*. It is neither. The allele for Huntington's disease is dominant and rare — about one carrier in ten thousand in most populations. The allele for blood group O is recessive and common — frequency above 0.6 in most of the world. Dominance is a statement about phenotype in the heterozygote. Frequency is a statement about how many copies of the allele exist in the population. They are independent facts.

### Segregation and independent assortment, plainly

In 1865 Mendel could not see chromosomes. He could not see DNA. He could not see meiosis. He could see seeds — round and wrinkled, yellow and green — and he could count them. From the counts he inferred two principles which we now know to be statements about how chromosomes behave during cell division (the subject of Chapter 1).

**The principle of segregation** says: when a parent makes gametes — sperm, egg, pollen — the two alleles at each locus separate, and each gamete carries exactly one allele from each parent. A heterozygote Aa produces gametes that are 50% A and 50% a. Not a mixture. Not a blend. One allele per gamete, drawn cleanly from the pair.

**The principle of independent assortment** says: when a parent makes gametes for two or more loci that live on different chromosomes, the alleles at one locus assort independently of the alleles at the other. A heterozygote AaBb produces four kinds of gametes — AB, Ab, aB, ab — each in equal proportion, 1:1:1:1. The choice of A versus a does not constrain the choice of B versus b.

For N independently assorting heterozygous loci, the gamete count is *2^N*. Each locus contributes a factor of 2 (uppercase or lowercase), and the loci are independent, so the choices multiply. One locus, two gametes. Two loci, four gametes. Three loci, eight. Seven loci — Mendel's count — 128.

This is the engine of the Punnett square. Lay the 2^N gametes from one parent across the top of the grid; lay the 2^N gametes from the other parent down the side; the grid has 2^N × 2^N = 4^N cells; each cell is one possible offspring genotype, weighted equally because every gamete combination is equally likely under independent assortment. Count the cells by genotype class. Count them by phenotype class. The ratios fall out.

### The math worked once on the page

I am going to do the monohybrid and the trihybrid in full, because the trihybrid is where the human runs out of patience and the simulation starts to earn its place. Watch the size of the grid double, then double again, then double again — and then watch what the simulation will do at N = 7.

**Monohybrid: Aa × Aa.**

Each parent makes two kinds of gamete, A and a, each with probability 1/2. The grid:

|       | A (1/2)   | a (1/2)   |
|-------|-----------|-----------|
| **A (1/2)** | AA (1/4)  | Aa (1/4)  |
| **a (1/2)** | Aa (1/4)  | aa (1/4)  |

Genotype probabilities: P(AA) = 1/4, P(Aa) = 2/4, P(aa) = 1/4. The genotype ratio is **1 : 2 : 1**.

Under complete dominance, AA and Aa share a phenotype. The phenotype probabilities are P(dominant) = 3/4 and P(recessive) = 1/4. The phenotype ratio is **3 : 1**.

This is the cystic-fibrosis number from the counseling scene. Two heterozygous parents. Each pregnancy, the probability of an affected (aa) child is 1/4. Independent across pregnancies — the second child's odds do not change because the first child was unaffected.

**Dihybrid: AaBb × AaBb.**

Each parent makes 2² = 4 kinds of gamete — AB, Ab, aB, ab — each with probability 1/4. The grid is 4×4 = 16 cells, each at probability 1/16.

Under complete dominance at both loci, the phenotype classes factor cleanly:

- A_B_ (dominant at both): (3/4) × (3/4) = 9/16
- A_bb (dominant at A, recessive at B): (3/4) × (1/4) = 3/16
- aaB_ (recessive at A, dominant at B): (1/4) × (3/4) = 3/16
- aabb (recessive at both): (1/4) × (1/4) = 1/16

The phenotype ratio is **9 : 3 : 3 : 1**. The underscore notation A_ means "AA or Aa, indistinguishable by phenotype." The factorization (3/4 + 1/4) × (3/4 + 1/4) = 1 is independent assortment, expressed in probability — the dihybrid ratio is just the *product* of two monohybrid ratios. This is the only sentence in the section that matters. *Independent assortment means probabilities multiply.*

**Trihybrid: AaBbCc × AaBbCc.**

Each parent makes 2³ = 8 kinds of gamete — ABC, ABc, AbC, Abc, aBC, aBc, abC, abc — each with probability 1/8. The grid is 8×8 = 64 cells, each at probability 1/64.

The phenotype classes factor again, this time as (3/4 + 1/4)³:

- A_B_C_: (3/4)³ = 27/64
- A_B_cc: (3/4)² × (1/4) = 9/64
- A_bbC_: 9/64
- aaB_C_: 9/64
- A_bbcc: (3/4) × (1/4)² = 3/64
- aaB_cc: 3/64
- aabbC_: 3/64
- aabbcc: (1/4)³ = 1/64

The phenotype ratio is **27 : 9 : 9 : 9 : 3 : 3 : 3 : 1**. The eight numbers sum to 64. Each is 3^(N − k) where k is the number of recessive-homozygous loci in that class, multiplied by the number of ways to choose *which* k loci are recessive. The whole ratio is the binomial expansion (3 + 1)^N for N = 3, sliced apart by which loci take the 1 and which take the 3.

For general N — N loci, both parents heterozygous at all of them, complete dominance, independent assortment — there are 2^N gametes per parent, the grid is 4^N cells, and the phenotype ratio is the binomial expansion of (3 + 1)^N = 4^N split into 2^N terms. At N = 7 — Mendel's count — the grid is 16,384 cells, and the all-dominant phenotype class has count 3^7 = 2187 out of 4^7 = 16,384. If you grew 100,000 offspring from a 7-locus heterozygous self-cross, the expected number with the all-seven-recessive phenotype is 100,000 × (1/16,384) ≈ 6.1 plants. Six plants out of a hundred thousand. This is the kind of number Mendel needed his ~28,000 plants to estimate well — and the kind of number a human cannot extract from a hand-drawn grid the size of a small room.

The simulation does it in milliseconds. That is the move.

---

## The three governing files

Before you write any HTML, you write three text files. They go in the same folder as the simulation. The LLM reads them every time you ask for new code. This is the cheap, durable substitute for everything that more elaborate development environments do — there is no `package.json`, no `vite.config.js`, no framework. Three text files.

### CLAUDE.md — the coding constitution

This file tells the LLM what kind of code to produce. It is short. It does not change between chapters.

```markdown
# CLAUDE.md — Genetics Simulation Coding Constitution

## Stack
- Single .html file per simulation. No external build step.
- D3 v7 loaded from CDN: <script src="https://d3js.org/d3.v7.min.js"></script>
- Plain HTML, CSS, and JavaScript. No frameworks. No npm.

## Visualization
- All drawing happens inside one <svg> element.
- Grid-based diagrams (Punnett squares, genotype matrices) use a
  2D array of <rect> elements with <text> labels at the center of
  each cell showing the genotype.
- Stochastic population panels (drift, selection) use <circle>
  elements bound to a data array of individuals, with fill set by
  genotype.
- Allele-frequency line charts use d3.scaleLinear for time, d3.line
  for the trajectory, d3.axisBottom/Left for ticks. Replicate runs
  shown as thin colored lines; mean as thick dark line; theoretical
  expectation (Hardy-Weinberg) as a dashed line.
- Phylogenetic trees (later chapters) use d3.tree() or d3.cluster()
  with branches as <path> elements colored gray #95a5a6.
- Animated transitions on parameter change: duration 250 ms.

## Layout
- Default SVG canvas: 720 x 480.
- Punnett-square cells sized dynamically: cell size =
  min(40, 600 / 2^N) px, so the trihybrid (64 cells) still fits
  comfortably and the 7-locus (128 x 128) grid still renders.

## Interaction
- Parameter controls are <input type="range"> sliders and
  <input type="text"> fields for genotype strings.
- A <div id="readout"> displays current parameter values and the
  computed genotype and phenotype ratios.
- Inputs update the simulation in real time via an input listener.

## Biology
- Every simulation models a named genetics or evolution phenomenon.
- Variables in the code use genetics names (alleles, genotype,
  phenotype, p, q, Ne, s, mu, r) — not generic ones like x and y.
- A short comment at the top of every <script> block states the
  biological claim the simulation is making and its limits.

## Verification
- Every simulation includes a console.log block that prints the
  result of one or more biology checks the moment the file loads.
- For Punnett squares: the monohybrid Aa x Aa cross must report a
  1:2:1 genotype ratio and a 3:1 phenotype ratio under complete
  dominance. The dihybrid AaBb x AaBb cross must report 9:3:3:1.
  The trihybrid must report 27:9:9:9:3:3:3:1 summing to 64.
```

Forty-odd lines. The LLM follows it because you point at it in every prompt: *"Conform to CLAUDE.md."*

### DESIGN.md — the visual constitution

```markdown
# DESIGN.md — Visual Constitution

## Color palette (genetics-coded)
- Dominant homozygous (AA):     #1a5276   (dark blue)
- Heterozygous (Aa):            #2980b9   (medium blue)
- Recessive homozygous (aa):    #85c1e9   (light blue)
- Wild-type phenotype:          #27ae60   (green)
- Mutant / disease phenotype:   #c0392b   (red)
- Phylogenetic branches:        #95a5a6   (gray)
- Bootstrap values on trees:    #e67e22   (orange)
- Allele frequency p (line):    #2c3e50   (near-black)
- Allele frequency q (line):    #7f8c8d   (gray)
- Generic small molecule:       #34495e   (slate)

## Chart styling
- Time series: dark line on white background.
- Dark-mode background: #1a1a1a. Line color in dark mode: #f8f9fa.
- Hardy-Weinberg reference line: #adb5bd dashed at 1 px.
- Drift replicates: ten thin colored lines from d3.schemeCategory10,
  alpha 0.4; mean overlay at full opacity.
- Axis labels: 12 px sans-serif. Title: 16 px.
- Grid lines: #e9ecef at 1 px.

## Sliders and inputs
- 320 px wide. Labels above. Current value to the right.
- Genotype text fields: monospace, 14 px.

## Layout
- SVG canvas: 720 x 480 px by default.
- Margins: top 30, right 30, bottom 50, left 60.

## Type
- system-ui, -apple-system, sans-serif.
- Genotype labels inside Punnett cells: monospace, sized to cell.
```

DESIGN.md says nothing about biology. It says how things look. Keeping the two files separate matters: when you change a color scheme, you do not touch the biology. When you fix a biology bug, you do not touch the colors. The dominant–heterozygous–recessive blue triad is the visual contract of the whole book — every cross in every chapter shades the same way.

### PROJECT.md — the state file

```markdown
# PROJECT.md — Genetics Simulation Workshop

## Built so far
- (chapter, file, what it models)

## In progress
- 00-punnett-square.html — generalized Punnett square generator.
  Inputs: parent genotype strings (e.g., "AaBbCc"); locus-count
  slider (1 to 7). Outputs: 2^N x 2^N colored grid; genotype and
  phenotype ratios; on-load verification of the 1:2:1, 9:3:3:1,
  and 27:9:9:9:3:3:3:1 ratios.

## Next
- 01-meiosis.html — animated meiotic chromosome behavior producing
  2^N gametes from a diploid heterozygote.

## Conventions
- File naming: NN-slug.html, where NN is chapter number.
- Each file is self-contained (no shared JS).
- Every file has a one-line // CLAIM: comment at the top.
```

PROJECT.md is the only file you actually edit chapter to chapter. The other two stay fixed.

---

## The four-move prompt

Now you have three governing files. To get a working simulation, you paste one prompt at Claude. The structure is **Show / Say / Constrain / Verify**.

**Show** — point at the files Claude must conform to. *"Read CLAUDE.md and DESIGN.md."* If you are working in Claude.ai, you attach the files. If you are working in Claude Code or Cowork, the files are already on disk and the LLM reads them automatically.

**Say** — one paragraph describing the artifact in biological terms. *"Build a Punnett-square generator. Two parent genotypes are entered as strings of letters (Aa, AaBb, AaBbCc, …, up to seven loci). The simulation enumerates the 2^N gametes for each parent, builds the 2^N × 2^N grid, fills each cell with the offspring genotype produced by combining the row gamete with the column gamete, and shades the cell by genotype class. A readout panel reports the genotype ratio, the phenotype ratio under complete dominance, and a comparison to the theoretical expectation."*

**Constrain** — the rules the file must obey, beyond what CLAUDE.md already says. The slider ranges, the input formats, the cell-size formula, the color mapping for homozygous-dominant versus heterozygous versus homozygous-recessive cells.

**Verify** — one or several falsifiable biology checks the simulation must pass. *"On load, run three checks. (1) For Aa × Aa, the genotype counts must be 1 AA, 2 Aa, 1 aa, summing to 4. (2) For AaBb × AaBb, the phenotype counts must be 9 A_B_, 3 A_bb, 3 aaB_, 1 aabb, summing to 16. (3) For AaBbCc × AaBbCc, the phenotype counts must be 27, 9, 9, 9, 3, 3, 3, 1 in the standard order, summing to 64. Print each check as a pass/fail line."*

That is the entire prompt. Four moves. Three short paragraphs. The LLM writes one HTML file. You double-click it. It runs.

Let me show you what that looks like in practice.

---

## A worked example — building 00-punnett-square.html

Here is the actual prompt I would paste at Claude:

> **Show:** Read CLAUDE.md and DESIGN.md from this project. Conform to them.
>
> **Say:** Build `00-punnett-square.html` — a generalized Punnett-square generator. The user enters two parent genotypes as strings of letters: an uppercase letter for the dominant allele at each locus, a lowercase letter for the recessive. *"Aa"* is a monohybrid heterozygote at locus A. *"AaBb"* is a dihybrid heterozygote at loci A and B. *"AaBbCc"* is a trihybrid. The simulation accepts up to seven loci using letters A through G. For each parent, enumerate the 2^N gamete strings produced under independent assortment (each gamete contains exactly one allele from each locus, all combinations equally likely). Build the 2^N × 2^N grid. Each cell is filled by taking the row gamete from parent 1, the column gamete from parent 2, and combining them locus by locus to produce a diploid offspring genotype (e.g., row "AB" × column "ab" → "AaBb"). Color the cell by *genotype class*: homozygous dominant at every locus → dark blue *#1a5276*; homozygous recessive at every locus → light blue *#85c1e9*; everything else (heterozygous at one or more loci) → medium blue *#2980b9*. Label each cell with the offspring genotype in monospace text sized to fit. A readout panel below the grid lists: (a) the genotype ratio summary, grouping by exact genotype string; (b) the phenotype ratio under complete dominance, using the underscore convention (A_ for "AA or Aa"); (c) the theoretical expectation for that cross — (1:2:1) and (3:1) at N = 1; (9:3:3:1) at N = 2; (27:9:9:9:3:3:3:1) at N = 3; the general (3+1)^N binomial expansion at higher N — and a green "match" badge or red "mismatch" badge.
>
> **Constrain:** A slider sets the number of loci *N* (range 1 to 7, default 3). Two text inputs accept the parent-genotype strings, validated to length 2N and to the format *Aa*, *Bb*, *Cc*, … (uppercase letter followed by lowercase letter of the same letter, in alphabetical order). Cell size = min(40, 600 / 2^N) px. Grid centered horizontally in the SVG canvas. Use `d3.scaleLinear` only for color interpolation if needed; the layout is a uniform grid, so do not bring in a layout primitive that adds complexity. Single self-contained HTML file, no dependencies beyond D3 v7 from CDN. Add a comment at the top of the script:
> `// CLAIM: For N independently assorting loci, both parents heterozygous, the Punnett-square grid has 2^N × 2^N cells and the phenotype ratio under complete dominance is the binomial expansion (3+1)^N.`
>
> **Verify:** Biology check — print to the console on every parameter change, as pass/fail lines with measured values:
>   (1) For Aa × Aa, count the cells by genotype class. Must be 1 AA, 2 Aa, 1 aa, summing to 4.
>   (2) For AaBb × AaBb, count cells by phenotype class (using underscore convention). Must be 9 A_B_, 3 A_bb, 3 aaB_, 1 aabb, summing to 16.
>   (3) For AaBbCc × AaBbCc, count cells by phenotype class. Must be 27, 9, 9, 9, 3, 3, 3, 1 in the order (all-dominant, two-dom-one-rec in three ways, one-dom-two-rec in three ways, all-recessive), summing to 64.
>   (4) For arbitrary N, the cell count must equal 4^N and the all-dominant phenotype class must equal 3^N.
> Each line as PASS or FAIL with the measured value, the expected value, and the cross.

Paste that into Claude. Wait twenty seconds. Save the file. Double-click it in your browser.

You should see, in the upper panel, an 8×8 grid of dark-blue, medium-blue, and light-blue squares, each labeled with a six-letter genotype like *AaBbCc* or *AABBCC*. In the readout below, you should see two ratios: a genotype ratio (with twenty-seven entries — the trihybrid has twenty-seven distinct genotype strings, from *AABBCC* through *aabbcc*) and a phenotype ratio with eight entries summing to 64: **27 : 9 : 9 : 9 : 3 : 3 : 3 : 1**. Next to the phenotype ratio you should see a green "match" badge.

Now open the developer console (Cmd-Option-J on Mac, Ctrl-Shift-J on Windows). The console should print four lines:

```
[Verify] Aa x Aa genotype counts = {AA: 1, Aa: 2, aa: 1}, sum = 4 → PASS
[Verify] AaBb x AaBb phenotype counts = {A_B_: 9, A_bb: 3, aaB_: 3, aabb: 1}, sum = 16 → PASS
[Verify] AaBbCc x AaBbCc phenotype counts = {A_B_C_: 27, A_B_cc: 9, A_bbC_: 9, aaB_C_: 9, A_bbcc: 3, aaB_cc: 3, aabbC_: 3, aabbcc: 1}, sum = 64 → PASS
[Verify] At N = 3, total cells = 64 = 4^3, all-dominant class = 27 = 3^3 → PASS
```

Now do the verification yourself with your eyes. Drag the locus slider to *N = 1*. The grid shrinks to 2×2 — four cells, one dark blue (AA), two medium blue (Aa, Aa), one light blue (aa). The readout reports 1:2:1 genotype and 3:1 phenotype with a green badge. This is the cystic-fibrosis case. Now drag the slider to *N = 2*. The grid expands to 4×4 — sixteen cells. The readout reports 1 AABB : 2 AABb : 1 AAbb : 2 AaBB : 4 AaBb : 2 Aabb : 1 aaBB : 2 aaBb : 1 aabb on the genotype side (sums to 16) and 9 A_B_ : 3 A_bb : 3 aaB_ : 1 aabb on the phenotype side. Now drag to *N = 7*. The grid is 128 × 128, which is 16,384 cells. The cells are tiny — each one a few pixels — but the colors form a fractal-like pattern (dark-blue cells are rare, light-blue cells are rare, medium-blue cells dominate the field, exactly as you would expect when seven independent loci each contribute a one-quarter chance of all-dominant or all-recessive). The phenotype readout now has 2^7 = 128 entries summing to 4^7 = 16,384. The all-dominant class is 2187 = 3^7. The all-recessive class is 1. The ratio of all-dominant to all-recessive is 2187 : 1. *Six plants out of a hundred thousand would carry every recessive trait.* The simulation does in twenty milliseconds the calculation it would take a human three weekends to make and then mistrust.

If any of the verification lines fail — if the trihybrid sums to 65 instead of 64, or the dihybrid reports 9:3:3:2, or the genotype assignment confuses Aa and aA — the simulation is wrong, and you push back at the LLM with the exact failure: *"For AaBb × AaBb, the console reports phenotype counts {A_B_: 9, A_bb: 3, aaB_: 4, aabb: 1} summing to 17. The aaB_ count is wrong by one. Trace the genotype-to-phenotype mapping for the four gamete combinations that should land in aaB_ and tell me which one is being misclassified."*

**A note on the verification logic.** The check is not "does the output look like a Punnett square" — Punnett squares are a very recognizable image, and an LLM will reliably produce something that looks like one even when the underlying counts are off by a cell or two. The check is *do the integers add up to the integers the biology requires*. Sixty-four cells in the trihybrid. Sixteen-thousand-three-hundred-eighty-four in the seven-locus cross. Twenty-seven in the all-dominant phenotype class of the trihybrid. *Numbers that have to be exact.* That is what makes the verification falsifiable, and that is why it works as a firewall against fluent-but-wrong output.

**The lesson.** When the verification passes — and with this prompt it usually does on the first try, because the integer checks are specific enough that the LLM cannot fake them — you have a working tool you can probe for the rest of the course. Every later chapter that involves a cross will reuse this template. Set N to 1 and one parent to *Aa*, the other to *aa*, and you have a testcross (1 Aa : 1 aa, used to distinguish homozygous from heterozygous dominant individuals). Set N to 2 with one locus showing incomplete dominance and you have the snapdragon flower-color case (1 : 2 : 1 : 2 : 4 : 2 : 1 : 2 : 1, nine phenotype classes). Set N to 7 with the seven Mendelian pea traits and you have Mendel's actual experimental design. The simulation does not know any of this. You will know it, because you will have built the comparison.

**The limit.** The simulation is wrong about several things, and the way it is wrong is itself worth naming. (1) It assumes *independent assortment*. When two loci are linked — physically close on the same chromosome — they do not assort independently, and the dihybrid ratio is not 9:3:3:1. Linkage is Chapter 3. (2) It assumes *complete dominance*. When dominance is incomplete (Rr is pink in snapdragons) or codominant (the AB blood type), the genotype-to-phenotype map is different and the phenotype ratios change. Extensions are Chapter 3 as well. (3) It assumes *no epistasis* — one locus's phenotype does not depend on another locus's genotype in a non-multiplicative way. Epistasis (the Bombay phenotype, coat color in mice, comb shape in chickens) breaks the 9:3:3:1 into 9:3:4, 12:3:1, 9:7, 13:3, and other modified ratios. Also Chapter 3. (4) It treats the offspring counts as *exact expectations*. Real offspring are a finite sample, and small samples deviate from expectation by random fluctuation — the same statistical sampling that gives genetic drift its teeth in Chapter 10. The simulation as built reports the deterministic ratio; an extension prompt would add a stochastic mode that generates N actual offspring and watches the empirical ratio converge to the theoretical one as N grows.

---

## Common misconceptions

**"1:2:1 means literally one, two, and one of every four offspring."** No. The 1:2:1 genotype ratio and 3:1 phenotype ratio are *expected proportions in the limit of large offspring numbers*. Each individual offspring is the result of an independent random sampling — one allele drawn from each parent — with the underlying probabilities 1/4, 1/2, 1/4. With four offspring you might get exactly 1 AA, 2 Aa, 1 aa. You might also get 0 AA, 4 Aa, 0 aa, or 3 AA, 1 Aa, 0 aa, or any other combination consistent with the binomial distribution. The 1:2:1 is the *mean*, not a guarantee. This is Mendel's reason for ~28,000 plants — small samples produce coincidences, large samples produce laws. The formal statistical statement is that the count of aa offspring in n trials is binomially distributed *Bin(n, 1/4)*, with mean *n/4* and standard deviation *√(n · 1/4 · 3/4)*. For n = 4, the standard deviation of the aa count is about 0.87 — almost as big as the expected value (1). For n = 1000, the standard deviation is about 13 while the expected count is 250 — fluctuations are small relative to the mean. *Sample size is everything.* The 3:1 ratio is not a fact about any particular family; it is a statement about what averages to be true across many families.

**"Dominant alleles are stronger or more common in the population."** No. The word *dominant* describes phenotypic dominance only — which allele's effect is visible in the heterozygote. It does not describe allele frequency in any population. A dominant allele can be rare. A recessive allele can be common. **Huntington's disease** is caused by a dominant allele at the *HTT* gene (a CAG-trinucleotide expansion). The disease allele has frequency roughly 1 in 10,000 in most populations of European descent — extremely rare despite being dominant. (Walker FO. "Huntington's disease." *Lancet*. 2007;369(9557):218–228. doi:10.1016/S0140-6736(07)60111-1 [verify].) **Blood group O** in the *ABO* system is caused by a recessive allele at the *ABO* gene. The *i* allele has frequency near 0.6 worldwide and above 0.8 in some Indigenous American populations — extremely common despite being recessive. (Cavalli-Sforza LL, Menozzi P, Piazza A. *The History and Geography of Human Genes*. Princeton: Princeton University Press; 1994. [verify exact frequencies].) The relationship between allele frequency and phenotype frequency in a population is the **Hardy-Weinberg equation** *p² + 2pq + q² = 1*, which Chapter 10 develops in full. Dominance and frequency are two independent facts about an allele — one is about phenotype expression, the other is about how many copies exist in the population.

**"At equilibrium, the cross produces the expected ratio in every batch."** No. Every batch is a finite sample. The 3:1 ratio is an expectation about an infinite-sample limit. Real families of four can deviate by a lot. Real cohorts of 100 deviate by a little. Real Mendelian datasets of 28,000 deviate by very little — and Mendel's deviations are, in fact, *too small* to be fully consistent with binomial sampling, which is the basis of Ronald Fisher's famous 1936 critique that Mendel's data are "too good to be true." (Fisher RA. "Has Mendel's work been rediscovered?" *Annals of Science*. 1936;1(2):115–137. [verify DOI].) The modern reading is that Mendel may have unconsciously corrected ambiguous cases toward expectation; the bigger lesson, for us, is that real biological data have noise, and a simulation that always returns 3:1 to two decimal places is making a deterministic prediction about an underlying probabilistic process. Chapter 10's drift simulator restores the noise.

**"Punnett squares predict every cross."** No. The Punnett square is exact when its assumptions hold and approximately correct when they fail mildly. The assumptions are: (1) loci assort independently — no linkage; (2) dominance is complete — no incomplete dominance, codominance, or multiple alleles with intermediate phenotypes; (3) there is no epistasis — one locus's expression does not modify another locus's phenotype; (4) penetrance is 100% — every genotype produces the expected phenotype; (5) the population samples randomly — no segregation distortion or meiotic drive. When these fail, the Punnett square gives incorrect predictions in well-characterized ways. Linkage produces excess parental genotypes and deficient recombinant genotypes (Chapter 3 with map distances). Incomplete dominance (snapdragons; some forms of human hair) produces 1:2:1 phenotype ratios that match the genotype ratios. Epistasis produces modified dihybrid ratios like 9:3:4, 12:3:1, or 13:3 (Chapter 3 again). Variable expressivity and incomplete penetrance, common in human medical genetics, require probabilistic rather than deterministic predictions and are the reason genetic counseling is harder than a single Punnett square. The chapter's simulation as built assumes all five conditions hold; an extension prompt could relax them, one assumption at a time, and watch the ratios change.

**"If the LLM produced a Punnett square, it must be right."** This is the genetics-specific version of the misconception that appears in every Chapter 00 in this series. The LLM has read patterns in text about Punnett squares — millions of examples of 9:3:3:1, hundreds of examples of 27:9:9:9:3:3:3:1, a handful of examples of N-locus scaling. Sometimes those patterns line up with the underlying combinatorics; sometimes they look right but encode a subtle error — a phenotype class miscounted, a genotype like *AaBB* miscolored as homozygous-dominant when it should be heterozygous, a 27:9:9:9:3:3:3:1 ratio that sums to 63 because one cell got dropped. The verification clause is the firewall. *If the trihybrid phenotype counts do not sum to 64, the simulation is wrong, no matter how good the grid looks.* You are not delegating biological judgment to the LLM. You are delegating typing. The biological judgment is yours, expressed in the four integer-checks the console must print on load.

A subtler one I will add because students hit it: *"The simulation is the biology."* It is not. The Punnett-square grid is a bookkeeping device — a finite, exact, deterministic representation of the probabilities that result from one specific kind of cross under five specific assumptions. The actual biological process is happening at the level of chromosomes in meiosis, sperm-egg fusion, gene expression during development, and so on across an enormous causal cascade. The Punnett square skips all of it and just reports the expected gamete combinations. When the assumptions hold, this is a brilliant economy. When the assumptions fail, the gap between the grid and the biology is where the interesting science lives. Linkage, epistasis, incomplete penetrance, polygenic traits — every one of these is a place where the square's bookkeeping diverges from what real organisms actually do, and the divergence is the subject of most of the rest of this book.

---

## Exercises

**Exercise 1 — Build (warm-up).** Create the three governing files (CLAUDE.md, DESIGN.md, PROJECT.md) using the templates above. Use the four-move prompt to build `00-punnett-square.html`. Open it in your browser and confirm: (a) at *N = 1* with both parents *Aa*, the grid is 2×2 and the readout reports 1:2:1 genotype, 3:1 phenotype with a match badge; (b) at *N = 2* with both parents *AaBb*, the grid is 4×4 and the readout reports 9:3:3:1 phenotype with a match badge; (c) at *N = 3* with both parents *AaBbCc*, the grid is 8×8 and the readout reports 27:9:9:9:3:3:3:1 summing to 64; (d) the console prints four verification lines on each parameter change. *Deliverable:* a working HTML file plus a one-sentence description of what the readout looks like at *N = 7*.

**Exercise 2 — Apply (Mendel's seven).** Mendel chose seven trait pairs in pea plants: seed shape (round/wrinkled), seed color (yellow/green), pod color (green/yellow), pod shape (inflated/constricted), flower color (purple/white), flower position (axial/terminal), stem length (tall/short). Each was controlled, as far as he could tell, by a single locus with complete dominance, and — by extraordinary luck — each happened to be on a different pea chromosome (peas have seven chromosome pairs). Set your simulation to *N = 7* with both parents heterozygous at all seven loci. *(a)* Read off the phenotype ratio. The all-dominant class should be 2187, the all-recessive class 1, and the total should be 16,384. *(b)* Compute by hand the expected number of plants showing all seven recessive phenotypes if you grew exactly 100,000 offspring from this cross. *(c)* Compute the expected number of plants showing exactly one recessive phenotype (out of seven loci) and any combination of dominants at the other six. The combinatorial formula is *7 · 3⁶ · 100,000 / 4⁷*. Show the calculation. *Deliverable:* the two numbers and the calculation.

**Exercise 3 — Explain (the dominant-but-rare puzzle).** Huntington's disease is caused by a dominant allele at the *HTT* gene. The disease allele has frequency roughly 1 in 10,000 in most populations of European descent. (Walker FO. *Lancet*. 2007;369:218–228 [verify].) *(a)* Compute, under the Hardy-Weinberg assumption of random mating, the expected frequency of heterozygous Aa carriers in a population where the dominant disease allele has frequency *q = 1/10,000*. (Hint: *2pq* with *p ≈ 1*.) *(b)* Compute the expected frequency of homozygous AA individuals, who in this case would be a person with two copies of the disease allele. *(c)* In three sentences, explain why a dominant allele can be vanishingly rare in a population while a recessive allele can be extremely common — distinguishing *dominance* (an allele's phenotypic relationship to its partner in the heterozygote) from *frequency* (the proportion of allele copies in the population). *Deliverable:* the three numbers and the three sentences. This is the setup for the Hardy-Weinberg chapter (Chapter 10).

**Exercise 4 — Stretch (when the Punnett square fails).** Extend the simulation prompt so that one locus exhibits *incomplete dominance* — *Rr* produces a pink phenotype distinct from *RR* red and *rr* white. The dihybrid ratio is no longer 9:3:3:1; phenotypes now distinguish all three genotypes at the incompletely dominant locus. *(a)* By hand, predict the new dihybrid phenotype ratio for the cross *RrAa × RrAa*, where the *R* locus is incompletely dominant (three phenotypes: red RR, pink Rr, white rr) and the *A* locus is fully dominant (two phenotypes: A_ and aa). The answer is the outer product of a 1:2:1 with a 3:1, giving six phenotype classes — write them out and confirm the counts sum to 16. *(b)* Modify the four-move prompt so that the verification clause checks the new ratio. *(c)* Run the simulation and confirm. *Deliverable:* the predicted ratio, the modified prompt, and a screenshot or copy-paste of the readout. This is a preview of how Chapter 3 generalizes the Punnett square.

---

## What would change my mind

The Punnett-square approach as I have presented it — a deterministic combinatorial calculation under the five assumptions of independence, complete dominance, no epistasis, full penetrance, and unbiased segregation — would fail as a *first approximation* to real Mendelian inheritance if, across a substantial and well-characterized body of crossing data (for example, the historic pea, fruit fly, and yeast datasets reviewed in Griffiths AJF, Wessler SR, Carroll SB, Doebley J. *Introduction to Genetic Analysis*. 12th ed. New York: W. H. Freeman; 2020, Chapters 2–3), the simple predicted ratios (1:2:1, 3:1, 9:3:3:1, 27:9:9:9:3:3:3:1) did not show up in monohybrid, dihybrid, and trihybrid crosses *when the experimenters had taken care to select unlinked loci with complete dominance*. The evidence to date is that the simple ratios do show up cleanly under those conditions, which is why the square has remained a teaching tool for a century — and the well-known *exceptions* (linkage, epistasis, multiple alleles, incomplete penetrance, sex linkage, gene-environment interaction, polygenic traits) are explained by named violations of the Punnett-square assumptions rather than by a failure of the underlying combinatorics. If a modern reanalysis showed that *unlinked, complete-dominance, single-locus traits* systematically failed to give the expected ratios across multiple species, I would downgrade the Punnett-square from "exact under stated assumptions" to "historical convention" and rewrite this chapter with a probabilistic model from the start.

## Still puzzling

I do not yet fully understand how much of Mendel's reported data is exactly as observed and how much reflects unconscious correction toward the expected ratios — Fisher's 1936 critique that Mendel's numbers are *too close* to the predicted binomial expectations to be plausible random samples has been revisited many times across the twentieth and early twenty-first centuries and has never quite been resolved. (Fisher RA. *Annals of Science*. 1936;1:115–137; reviewed in Franklin A, Edwards AWF, Fairbanks DJ, Hartl DL, Seidenfeld T. *Ending the Mendel-Fisher Controversy*. Pittsburgh: University of Pittsburgh Press; 2008 [verify].) If Fisher was right, the bookkeeping move I have just walked you through obscures a subtle methodological problem in the founding data; if Fisher was overreaching, the suspicious-cleanness is a coincidence within the binomial fluctuation range across the specific subset of trait pairs Mendel chose to report. I genuinely cannot tell which from the current literature, and the question of whether Mendel was a perfect record-keeper, a slightly idealizing one, or something stranger remains a live debate among historians of genetics. The simulation in this chapter is exact about the mathematics. The garden in 1856 was probably less so.

---

## LLM Exercise — Build your Punnett-square generator

This block is the one you actually do. The prompt below is ready to paste at Claude (or ChatGPT, or Gemini) once you have CLAUDE.md and DESIGN.md saved in the same folder.

### The simulation prompt

```
Show: Read CLAUDE.md and DESIGN.md from this project. Conform to them.

Say: Build 00-punnett-square.html — a generalized Punnett-square
generator. The user enters two parent genotypes as strings of letters:
uppercase = dominant allele, lowercase = recessive. "Aa" is a
monohybrid heterozygote. "AaBb" is a dihybrid. "AaBbCc" is a
trihybrid. Accept up to seven loci using letters A through G in
alphabetical order. For each parent, enumerate the 2^N gamete
strings under independent assortment (each gamete carries one allele
from each locus; all 2^N combinations equally likely). Build the
2^N x 2^N grid. Each cell combines the row gamete from parent 1 with
the column gamete from parent 2 to produce a diploid offspring
genotype. Color each cell by genotype class: homozygous-dominant at
every locus = #1a5276 (dark blue); homozygous-recessive at every
locus = #85c1e9 (light blue); anything else (heterozygous at one or
more loci) = #2980b9 (medium blue). Label each cell with the
offspring genotype string in monospace text sized to fit. A readout
panel below the grid lists: (a) the exact-genotype count summary
grouped by genotype string; (b) the phenotype count summary under
complete dominance using the A_ underscore convention; (c) the
theoretical expectation — 1:2:1 and 3:1 at N=1, 9:3:3:1 at N=2,
27:9:9:9:3:3:3:1 at N=3, the binomial expansion (3+1)^N for general
N — with a green "match" or red "mismatch" badge.

Constrain: Slider — N (1 to 7, default 3). Two text inputs accept
parent-genotype strings, validated to length 2N and format
[A-G][a-g] pairs in alphabetical order. Cell size =
min(40, 600 / 2^N) px. Grid centered horizontally. Single
self-contained HTML file. D3 v7 from CDN. Add at the top of script:
// CLAIM: For N independently assorting loci, both parents
// heterozygous, the Punnett-square grid has 2^N x 2^N cells and the
// phenotype ratio under complete dominance is the binomial expansion
// (3+1)^N.

Verify: Biology check — print to the console on every parameter
change, as PASS/FAIL lines with measured values, expected values,
and the cross:
  (1) For Aa x Aa: genotype counts must be {AA:1, Aa:2, aa:1},
      sum = 4.
  (2) For AaBb x AaBb: phenotype counts must be
      {A_B_:9, A_bb:3, aaB_:3, aabb:1}, sum = 16.
  (3) For AaBbCc x AaBbCc: phenotype counts must be
      {A_B_C_:27, A_B_cc:9, A_bbC_:9, aaB_C_:9, A_bbcc:3,
       aaB_cc:3, aabbC_:3, aabbcc:1}, sum = 64.
  (4) For arbitrary N: total cell count = 4^N; all-dominant
      phenotype class count = 3^N.
```

### Exploration tasks

Once the file runs, work through these. Each one is a small experiment.

1. **The integer-check test.** Set N = 3 with both parents *AaBbCc*. Open the console. The third verification line should read *PASS* with the eight-number ratio summing to 64. Now manually edit the LLM-generated code to introduce a deliberate bug — for instance, replace a `>=` with `>` in the genotype-to-phenotype mapping. Reload. The console should now report *FAIL* with a measured ratio that does not sum to 64. The point is to confirm that the verification is real — that it catches errors when they exist and passes only when the counts are exactly right. Reverse the edit when you are done.

2. **The locus-doubling test.** Hold both parents at full heterozygosity (*AaBbCc...Gg*) and step *N* from 1 to 7 in unit increments. At each value, write down the total cell count, the all-dominant phenotype count, the all-recessive phenotype count, and the ratio of all-dominant to all-recessive. The cell counts should be 4, 16, 64, 256, 1024, 4096, 16,384 — powers of four. The all-dominant counts should be 3, 9, 27, 81, 243, 729, 2187 — powers of three. The all-recessive should always be 1. The all-dominant-to-all-recessive ratio is 3^N : 1. *(Aside: this is why the rarest recessive trait in any high-locus cross is exponentially rare. It is the bookkeeping reason a child of two healthy carriers of a rare recessive condition has only a one-in-four chance of being affected — and a child carrying every recessive trait across many independent loci is effectively never observed.)*

3. **The dominance-versus-frequency test.** Set N = 1 with one parent *Aa* and the other *aa*. This is a testcross. The grid is 1×2 (or 2×2 with two cells duplicated). The phenotype ratio is 1:1 — half dominant, half recessive — even though *A* is the dominant allele. Now reverse: one parent *Aa*, the other *AA*. The phenotype ratio is now 1:0 — all dominant — because no aa genotypes are produced. Same dominant allele in both crosses. Different phenotype ratios. *Dominance is not a statement about ratio. It is a statement about how an allele expresses in the heterozygote.* The testcross is the standard tool for determining whether an individual with a dominant phenotype is homozygous (AA, all offspring dominant) or heterozygous (Aa, offspring split 1:1).

4. **The sample-size test.** This is conceptually the most important exercise in the chapter — and the move that previews Chapter 10's drift simulation. The Punnett square as built reports the *expected* ratios deterministically. Real offspring are a finite sample. Modify the prompt with this extension:

> *"Add a stochastic mode. When stochastic mode is enabled, instead of displaying the full Punnett-square grid, generate n actual offspring by sampling, for each offspring, one gamete from parent 1 (uniformly at random over the 2^N gamete types) and one gamete from parent 2 (the same), then combining to produce a diploid genotype. Tally the observed genotype and phenotype counts and display them next to the theoretical expectations. A slider sets n (range 4 to 10,000, default 100)."*

Run this with N = 1, both parents *Aa*, and n = 4. Look at the observed counts. Repeat the sample (a button labeled "resample") ten times. You will see ratios like 1:3:0, 0:2:2, 2:1:1, 1:2:1, 1:1:2 — all of them consistent with the underlying probabilities 1/4, 1/2, 1/4, none of them exactly 1:2:1. Now set n = 1000. The observed counts will be tight around 250 AA, 500 Aa, 250 aa. Now n = 10,000. They will be tighter. *Sample size is everything.* This is what Mendel was doing across ~28,000 plants. This is also the seed of Chapter 10 (drift), where the *finite* nature of real populations causes allele frequencies to wander stochastically across generations.

### Extension prompt

Once the basic Punnett-square simulator works, the obvious extension is to handle one of the exceptions to Mendelian inheritance. Paste this:

```
Extension: Modify 00-punnett-square.html to support incomplete
dominance at a designated locus. Add a dropdown next to the
parent-genotype input that lets the user mark each locus as either
"complete dominance" (default; heterozygote phenotype = dominant
homozygote phenotype) or "incomplete dominance" (heterozygote
phenotype = a third intermediate category, distinct from both
homozygotes). When a locus is marked incompletely dominant, the
phenotype ratio for crosses involving that locus changes: a
monohybrid Aa x Aa cross now gives 1:2:1 phenotype (not 3:1); a
dihybrid AaBb x AaBb cross with the A locus incompletely dominant
and the B locus fully dominant gives a 6-class ratio of
3:6:3:1:2:1 across (red A_B_, pink A_bb red-not-found wait — let me
restate cleanly: the new phenotype ratio is the outer product of
the per-locus phenotype ratios). Verification: for a monohybrid
incompletely-dominant cross Aa x Aa, the phenotype counts must be
1 red : 2 pink : 1 white, summing to 4. For a dihybrid cross with
the A locus incompletely dominant and the B locus fully dominant
(AaBb x AaBb), the phenotype counts must be the outer product
(1:2:1) × (3:1) = 3:6:3:1:2:1, summing to 16.
```

This is the simulation you will reach for when Chapter 3 introduces extensions to Mendelian inheritance — incomplete dominance, codominance, multiple alleles, lethal alleles, sex linkage, epistasis. The point is not yet that real biology breaks the simple Punnett-square ratios in interesting ways, but that the *same scaffolding* — gametes, grid, count, ratio — handles every extension once the genotype-to-phenotype map is generalized.

A connection forward, then. The Punnett-square simulation you just built tells you *the outcomes* of a cross — which genotypes appear, in what proportions, producing which phenotypes. It does not tell you *why* those outcomes occur. The why is meiosis — the cellular process during which a diploid cell with two copies of every chromosome divides twice in a row, with homologous chromosomes pairing and separating in the first division and sister chromatids separating in the second, producing four haploid gametes each carrying exactly one allele from each parental locus. Chapter 1 takes the 2^N gamete count the Punnett square assumed and *derives* it from the behavior of chromosomes at metaphase I, where N independently orienting homolog pairs produce 2^N combinations. You will carry the simulator with you. The first time Chapter 1 talks about a chromosome, a bivalent, or an anaphase — the first time it says the words *independent assortment* with a mechanism behind them — you will be able to pull up `00-punnett-square.html`, set *N = 7*, and watch the 16,384 cells of a fully-loaded pea-plant cross, knowing now where every one of those cells came from.

---

**What would change my mind:** If the same four-move prompt structure, applied to a non-D3 stack or to a domain outside biology, produced reliable runnable simulations in a single pass without any of Show / Say / Constrain / Verify, then the four-move discipline would not be a real teaching object — it would be ceremonial scaffolding around a process that works anyway.

**Still puzzling:** I do not yet know whether students with no coding background can read the LLM-generated JavaScript well enough to spot a phenotype-class miscounted by one, and that gap — between running the file and reading the file — is the real test of whether this method teaches.

---

**Tags:** Punnett-square, Mendel, independent-assortment, D3-v7, Brutalist-files
