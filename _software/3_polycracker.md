---
layout: page
title: PolyCRACKER
description: unsupervised partitioning of polyploid subgenomes by signatures of repetitive DNA evolution  
img: assets/img/polycracker.webp
importance: 3
category: complete
---

## Quick summary

polyCRACKER is an unsupervised machine learning approach to the classification and extraction
of sub-genomes from a set of genomic sequences provided in FASTA format. It currently
tailored to the analysis of moderate to recently derived allopolyploid species. It does not
require training data or even the number of subgenomes to be known (although this helps). It does require
some empirical testing, however, in order to determine the most likely number of subgenomes.

#### polyCRACKER can be used to:

1. **Identify subgenomes**  

2. **Extract subgenomes**

3. **Validate subgenomes**

4. **Explorative analysis of subgenomes relative to genomic features**

polyCRACKER works by using repeat kmers (corresponding to viruses, transposons, and other
selfish repetitive elements) as molecular barcodes for identifying species of origin. Since
such repetitive sequences evolve quickly and copy themselves throughout a genome of a species,
but not other closely related species), they can be used to group subsequences based on species
of origin.

Given a pool of DNA sequences derived from multiple species,
polyCRACKER can be used to identify and separate sequences belonging to one species versus another.
In some cases, polyCRACKER performs as well at separating subgenomes of an allopolyploid as the manual
extraction of subgenomes by sequence alignment, when the progenitor genome sequences are known and available.

#### For more information, see the polyCRACKER manuscript. Please cite the following article if you use polyCRACKER in your work.

**[PolyCRACKER, a robust method for the unsupervised partitioning of polyploid subgenomes by signatures of repetitive DNA evolution.
\*Sean P Gordon, \*Joshua J Levy, John P Vogel](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-019-5828-5)**

(First and second authors are co-first authors.)
