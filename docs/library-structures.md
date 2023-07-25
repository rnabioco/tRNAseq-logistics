---
layout: page
title: Library preparation & structures
permalink: /library-structures/
nav_order: 3
---

# Library preparation & structures

Published methods for generating direct tRNA sequencing libraries

## Direct mRNA sequencing workflow
### Oxford nanopore SQK-RNA002 nanopore sequencing kit
The methods below assume you have some knowledge of how these libraries are generated. Here's the diagram from the protocol:

## The original, minimalist approach (UCSC Nanopore Group):
### Source: [Thomas _et al._ 2021, ACS Nano](https://pubmed.ncbi.nlm.nih.gov/34618430/)

#### Workflow overview
1. Gel purify tRNA
2. Ligate ~1 µg tRNA to pre-annealed double stranded adapters
3. Gel purify ligation products
4. Attach helicase-loaded RMX adapter
5. SPRI bead clean up
6. Load libraries onto flow cell

#### Custom adapter sequences (RNA:DNA hybrids)
5´ splint adapter: `/5/CCTAAGrArGrCrArArGrArArGrArArGrCrCrUrGrGrN`

3´ splint adapter: `/5Phos/rGrGrCrUrUrCTTCTTGCTCTTAGGTAGTAGGTTC`


#### Technical considerations
- Gel purification may cause fragmentation of tRNAs
- The DNA bases in both splint adapters will be interpreted by the RNA basecalling model and will not align well

## nano-tRNAseq (Novoa lab, CRG)
### Source: [Lucas _et al._ 2023, Nature Biotechnology](https://pubmed.ncbi.nlm.nih.gov/37024678/)

#### Workflow overview
1. Column purify ~1 µg of small RNA (17-200 nt) using [Zymo Clean & Concentrator-5](https://www.zymoresearch.com/collections/rna-clean-concentrator-kits-rcc/products/rna-clean-concentrator-5) kit (max input 10 µg)
2. Ligate ~1 µg input to pre-annealed double stranded adapters
3. SPRI bead clean up
4. Attach nanopore RTA adapter
5. SPRI bead clean up
6. Reverse transcribe with Maxima RT
7. SPRI bead clean up 
8. Attach helicase-loaded RMX adapter
9. SPRI bead clean up
10. Load libraries onto flow cell

#### Custom adapter sequences
5′ RNA splint adapter: `/5/rCrCrUrArArGrArGrCrArArGrArArGrArArGrCrCrUrGrGrN`

3′ splint RNA:DNA adapter: `/5Phos/rGrGrCrUrUrCrUrUrCrUrUrGrCrUrCrUrUrArGrGrArArArArArArArArArAAAA`

#### Technical considerations
- In our hands, SPRI bead cleanup of ligated tRNAs is highly inefficient
- Maxima RT is a highly processive enzyme, and should make it through much of the structure and modifications on tRNAs. However, if it truncates early it's no big deal because the cDNA strand is not sequenced.