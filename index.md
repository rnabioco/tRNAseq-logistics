---
title: Home
layout: home
nav_order: 1
description: An overview of direct tRNA sequencing on Oxford Nanopore platforms.
---

# Nanopore tRNA sequencing!
{: .fs-9 }
Library workflows, logistics, and analysis considerations
{: .fs-6 .fw-300 }

Direct RNA sequencing is uniquely suited to the study of tRNA biology because it enables the simultaneous capture of signals derived from a tRNA's sequence and modification status. This site is a collection of practical information about sequencing tRNAs via nanopore, collated and maintained by Laura White in the [Hesselberth Lab](https://hesselberthlab.org).

{: .warning }
> Note: This documentation has been written for RNA002 chemistry. ONT's RNA004 direct RNA sequencing kit is expected to be released in early access mode in the 2nd half of 2023, and will use a different nanopore and helicase.

## Nanopore sequencing basics
 Nanopore direct RNA sequencing attaches specific adapters to the 3´ end of native RNA molecules, enabling them to be threaded through a pore in a charged membrane. As the nucleic acid passes through the pore, it differentially occludes the flow of ions through the aperture in a sequence and modification-dependent fashion. These changes in current over time can be converted to nucleotide sequence, and also used to infer the presence of RNA modifications. The RNA002 sequencing protocol from Oxford Nanopore also includes an optional reverse transcription step that is thought to help linearize structured molecules and increase library throughput; however, this cDNA molecule is discarded when the native RNA strand is threaded through the pore.

## Sequencing tRNA
 tRNAs are highly structured nucleic acids that are decorated with many RNA modifications (an average of 13 RNA modifications per tRNA molecule in budding yeast). A major limitation of previous tRNA sequencing methods was the necessity for reverse transcription to generate cDNA for Illumina sequencing, despite the fact that reverse transcriptases often stall on these molecules. Moreover, the size (70-100 nt) and structure of tRNAs require additional considerations when enriching for these molecules in sequencing libraries.

 Many tRNA sequencing workflows, including all nanopore tRNA sequencing protocols published to-date, have taken advantage of the unique molecular properties of tRNAs to add specific adapters to these molecules. All mature tRNAs have a 5´ phosphate and an NCCA overhand on their 3´end, to which the amino acid is added. This aminoacyl group will rapidly deacylate under non-acidic conditions, or can be specifically removed with base treatment. In the absence of an amino acid, the mature tRNA stem is then competent for ligation to a double stranded adapter using [T4 RNA ligase 2](https://www.neb.com/products/m0239-t4-rna-ligase-2-dsrna-ligase#Product%20Information).

## What you’ll find here
This site provides an overview of all published strategies for generating nanopore tRNA sequencing libraries, as well as differences between these protocols and practical considerations for tRNA sequencing, alignment, and analysis. The **Sequencing Settings** section describes our implemention of a simpler RNA short read mode for the MinKNOW sequencing software to enable running and basecalling tRNA sequencing libraries in real time, without the need to save out fast5 bulk files for downstream simulation. 

## Associated files & code
On our [GitHub repository](https://github.com/lkwhite/trnaseq) you will find reference files for aligning budding yeast and _E. coli_ tRNA libraries prepared using each of the described workflows.

## Acknowledgements
Thanks to: 
- members of the [Hesselberth Lab](https://hesselberthlab.org) for listening to me vent about my library woes and providing useful suggestions
- Androo Markham at Oxford Nanopore for advice on implementing live short read capture of RNAs in MinKNOW
- the Novoa Lab for pointing the way to higher tRNA-seq yields with [nano-tRNAseq](https://github.com/novoalab/Nano-tRNAseq)
- Jake Armstrong for troubleshooting Jekyll asset management