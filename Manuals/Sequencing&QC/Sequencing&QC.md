<img src="https://coursesandconferences.wellcomeconnectingscience.org/wp-content/themes/wcc_courses_and_conferences/dist/assets/svg/logo.svg" width="200" height="200">

# Sequencing&QC - Paraguay 2023 <!-- omit in toc -->

## Table of contents <!-- omit in toc -->
- [Introduction](#introduction)
  - [Commonly used file formats for NGS data](#commonly-used-file-formats-for-NGS-data)
  - [The command line](#the-command-line)
  - [Useful commands](#useful-commands)
- [Practical Exercise](#practical-exercise)
  - [Additional exercises](#additional-exercises)

## Module Overview and Aims

In this module, we are going to get familiar with several common file formats used for sequence data and then we are going to perform some quality control (QC) on some FASTQ-formatted sequence data.

# [Introduction](#introduction)

## [Commonly used file formats for NGS data](#commonly-used-file-formats-for-NGS-data)

### FASTA

Among the most common and simplest file formats for representing nucleotide sequences is FASTA.  Essentially, each sequence is represented by a 'header' line that begins with a '>', followed by lines containing the actual nucleotide sequence. By convention, the first 'word' in the header line is a unique identifier, which is usually the accession number. Consider this portion of the whole genome of *Staphylococcus aureus* MRSA252 as an example of a FASTA-formatted nucleotide sequence:

```
  >NC_002952.2 Staphylococcus aureus subsp. aureus MRSA252, complete sequence
  CGATTAAAGATAGAAATACACGATGCGAGCAATCAAATTTCATAACATCACCATGAGTTTGATCCAAAGCATGAGTGTTT
  ACAATGTTTGAATACCTTATACAGTTCTTATACATACTTTATAAATTATTTCCCAAGCTGTTTTGATACACACACTAACA
  GATACTCTATAGAAGGAAAAGTTATCCACTTATGCACACTTATACTTTTTAGAATTGTGGATAATTAGAAATTACACACA
  AAGTTATACTATTTTTAGCAACATATTCACAGGTATTTGACATATAGAGAACTGAAAAAGTATAATTGTGTGGATAAGTC
  GTCCAACTCATGATTTTATAAGGATTTATTTATTGATATTTACATAAAAATACTGTGCATAACTAATAAGCAGGATAAAG
  TTATCCACCGATTGTTATTAACTTGTGGATAATTATTAACATGGTGTGTTTAGAAGTTATCCACGGTTGTTATTTTTGTG
  TATAACTTAAAAATTTAAGAAAGATGGAGTAAATTTATGTCGGAAAAAGAAATTTGGGAAAAAGTGCTTGAAATTGCTCA
  AGAAAAATTATCAGCTGTAAGTTACTCAACTTTCCTAAAAGATACTGAGCTTTACACGATCAAAGATGGTGAAGCTATCG
  TATTATCGAGTATTCCTTTTAATGCAAATTGGTTAAATCAACAATATGCTGAAATTATCCAAGCAATCTTATTTGATGTT
  GTAGGCTATGAAGTAAAACCTCACTTTATTACTACTGAAGAATTAGCAAATTATAGTAATAATGAAACTGCTACTCCAAA
  AGAAGCAACAAAACCTTCTACTGAAACAACTGAGGATAATCATGTGCTTGGTAGAGAGCAATTCAATGCCCATAACACAT
  TTGACACTTTTGTAATCGGACCTGGTAACCGCTTCCCACATGCAGCGAGTTTAGCTGTGGCCGAAGCACCAGCCAAAGCG
  TACAATCCATTATTTATCTATGGAGGTGTTGGTTTAGGAAAAACCCATTTAATGCATGCCATTGGTCATCATGTTTTAGA
  TAATAATCCAGATGCCAAAGTGATTTACACATCAAGTGAAAAATTCACAAATGAATTTATTAAATCAATTCGTGATAACG
```

- The first line begins with '>' indicating that it is the header line.
- This is immediately followed by 'NC_002952.2', which is the accession number for [this sequence in the NCBI Assembly database](https://www.ncbi.nlm.nih.gov/assembly/GCF_000011505.1).
- Then follows the actual nucleotide sequence, split over several lines.

It is very common to combine multiple sequences into a single multi-FASTA file like this:

```
>ctxB1
ATGATTAAATTAAAATTTGGTGTTTTTTTTACAGTTTTACTATCTTCAGCATATGCACAT
GGAACACCTCAAAATATTACTGATTTGTGTGCAGAATACCACAACACACAAATACATACG
CTAAATGATAAGATATTTTCGTATACAGAATCTCTAGCTGGAAAAAGAGAGATGGCTATC
ATTACTTTTAAGAATGGTGCAACTTTTCAAGTAGAAGTACCAGGTAGTCAACATATAGAT
TCACAAAAAAAAGCGATTGAAAGGATGAAGGATACCCTGAGGATTGCATATCTTACTGAA
GCTAAAGTCGAAAAGTTATGTGTATGGAATAATAAAACGCCTCATGCGATTGCCGCAATT
AGTATGGCAAATTAA
>ctxB10
ATGATTAAATTAAAATTTGGTGTTTTTTTTACAGTTTTACTATCTTCAGCATATGCACAT
GGAACACCTCAAAATATTACTGATTTGTGTGCAGAATACCCCAACACACAAATATATACG
CTAAATGATAAGATATTTTCGTATACAGAATCTCTAGCTGGAAAAAGAGAGATGGCTATC
ATTACTTTTAAGAATGGTGCAATTTTTCAAGTAGAAGTACCAGGTAGTCAACATATAGAT
TCACAAAAAAAAGCGATTGAAAGGATGAAGGATACCCTGAGGATTGCATATCTTACTGAA
GCTAAAGTCGAAAAGTTATGTGTATGGAATAATAAAACGCCTCATGCGATTGCCGCAATT
AGTATGGCAAATTAA
>ctxB11
ATGATTAAATTAAAATTTGGTGTTTTTTTTACAGTTTTACTATCTTCAGCATATGCACAT
GGAACACCTCAAAATATTACTGATTTGTGTGCAGAATACCCCAACACACAAATACATACG
CTAAATGATAAGATATTTTCGTATACAGAATCTCTAGCTGGAAAAAGAGAGATGGCTATC
ATTACTTTTAAGAATGGTGCAACTTTTCAAGTAGAAGTACCAGGTAGTCAACATATAGAT
TCACAAAAAAAAGCGATTGAAAGGATGAAGGATACCCTGAGGATTGCATATCTTACTGAA
GCTAAAGTCGAAAAGTTATGTGTATGGAATAATAAAACGCCTCATGCGATTGCCGCAATT
AGTATGGCAAATTAA
>ctxB12
ATGATTAAATTAAAATTTGGTGTTTTTTTTACAGTTTTACTATCTTCAGCATATGCACAT
GGAACACCTCAAAATATTACTGATTTGTGTGCAGAATACCACAACGCACAAATATATACG
CTAAATGATAAGATATTGTCGTATACAGAATCTCTAGCTGGAAACAGAGAGATGGCTATC
ATTACTTTTAAGAATGGTGCAACTTTTCAAGTAGAAGTACCAGGTAGTCAACATATAGAT
TCACAAAAAAAAGCGATTGAAAGGATGAAGGATACCCTGAGGATTGCATATCTTACTGAA
GCTAAAGTCGAAAAGTTATGTGTATGGAATAATAAAACGCCTCATGCGATTGCCGCAATT
AGTATGGCAAATTAA
>ctxB2
ATGATTAAATTAAAATTTGGTGTTTTTTTTACAGTTTTACTATCTTCAGCATATGCACAT
GGAACACCTCAAAATATTACTGATTTGTGTGCAGAATACCACAACACACAAATACATACG
CTAAATGATAAGATATTGTCGTATACAGAATCTCTAGCTGGAAAAAGAGAGATGGCTATC
ATTACTTTTAAGAATGGTGCAACTTTTCAAGTAGAAGTACCAGGTAGTCAACATATAGAT
TCACAAAAAAAAGCGATTGAAAGGATGAAGGATACCCTGAGGATTGCATATCTTACTGAA
GCTAAAGTCGAAAAGTTATGTGTATGGAATAATAAAACGCCTCATGCGATTGCCGCAATT
AGTATGGCAAATTAA
```

If you want a more detailed history of the FASTA file format, then you could take a look at the Wikipedia page here: https://en.wikipedia.org/wiki/FASTA_format.

### FASTQ

The widely used FASTA file format has the great advantage of simplicity. However, this simplicity can be restrictive if we want to include additional data/metadata in addition to the sequence.

Given the non-negligible error rates of NGS technologies, often we need to accompany our sequence data with quality scores that estimate our confidence in the accuracy of the sequence data. As we will see later, this allows us to perform quality control checks and filter-out poor-quality data before performing analyses.

**FASTQ** is a simple text-based format that allows us to include quality scores. A single sequence is represented by four lines of text:

    @ERR8261968.1 1 length=97
    ACTTTCGATCTCTTGTAGATCTGTTCTCTAAACGAACTTTAAAATCTGTGTGGCTGTCACTCGGCTGCATGCTTAGTGCACTCACGCAGTATAATTA
    +ERR8261968.1 1 length=97
    CCCCCFDDFFFFGGGGGGGGGGHHHHHHHHHHHGGGGHHHHHHHHHHHHHHHGHHGHHIIHHGGGGGGHHHHHHHHHHHHHHHHHHHGGGHHHHHHH

- The first line is a 'header' containing a unique identifier for the sequence and, optionally, further description.
- The second line contains the actual nucleotide sequence.
- The third line is redundant  and can be safely ignored. Sometimes it simply repeats the first line. Sometimes it is blank or just contains a '+' character.
- The fourth line contains a string of characters that encode quality scores for each nucleotide in the sequence on [ASCII code](https://en.wikipedia.org/wiki/ASCII). 

Each single character encodes a score, typically a number between 0 and 40; this score is encoded by a single character.

| Character | ASCII | FASTQ quality score (ASCII – 33) 
| --|--|--
| ! | 33 | 0
| “ | 34 | 1
| # | 35 | 2
| $ | 36 | 3
| % | 37 | 4
| ... | ... | ...
| C | 67 | 34
| D | 68 | 35
| E | 69 | 36
| F | 70 | 37
| G | 71 | 38
| H | 72 | 39
|40 | 73 | 40

So, in the example above, we can see that most of the positions within the 97-nucleotide sequence have scores in the high 30s, which indicates a high degree of confidence in their accuracy.
- A score of 30 denotes a 1 in 1000 chance of an error, i.e. 99.9 %accuracy.
- A score of 40 denotes a 1 in 10,000 chance of an error, i.e. 99.99 %accuracy.

You can read more about the FastQ file format and quality scores here:
Cock, P. J., Fields, C. J., Goto, N., Heuer, M. L., & Rice, P. M. (2010). The Sanger FASTQ file format for sequences with quality scores, and the Solexa/Illumina FASTQ variants. *Nucleic Acids Research*, **38**, 1767–1771. https://doi.org/10.1093/nar/gkp1137.
