<img src="https://coursesandconferences.wellcomeconnectingscience.org/wp-content/themes/wcc_courses_and_conferences/dist/assets/svg/logo.svg" width="200" height="200">

# Sequencing&QC - Paraguay 2023 <!-- omit in toc -->

## Table of contents <!-- omit in toc -->
- [Introduction](#introduction)
  - [Commonly used file formats for NGS data](#commonly-used-file-formats-for-NGS-data)
    - [FASTA](#fasta)
    - [FASTQ](#fastq)
    - [SAM and BAM](#sam-and-bam)
  - [Quality control for FastQ data](#quality-control-for-FastQ-data)
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

### SAM and BAM

A **SAM file** (usually named *.sam) is used to represent aligned sequences. It is particularly useful for storing the results of genomic or transcriptomic sequence reads aligned against a reference genome sequence. The **BAM file** format is a compressed form of SAM. This has the disadvantage that it is not readable by a human but has the advantage of being smaller than the corresponding SAM file and thus easier to share and copy between locations.

You can read about SAM and BAM formats here:
 - Li, H., Handsaker, B., Wysoker, A., Fennell, T., Ruan, J., Homer, N., Marth, G., Abecasis, G., Durbin, R., & 1000 Genome Project Data Processing Subgroup (2009). The Sequence Alignment/Map format and SAMtools. *Bioinformatics*, **25**, 2078–2079. https://doi.org/10.1093/bioinformatics/btp352
-  [https://samtools.github.io/hts-specs/SAMv1.pdf](https://samtools.github.io/hts-specs/SAMv1.pdf).

We can view BAM files graphically using specialised genome browsers software such as (we will be working with one of them in the Genome Visualization Tools module):
- [IGV](https://igv.org/)
- [Tablet](https://ics.hutton.ac.uk/tablet/)
- [Artemis / BAMview](http://sanger-pathogens.github.io/Artemis/BamView/) 

An example **SAM file** is shown in the image below, along with the 11 mandatory fields of this standard:

![SAMformat](https://user-images.githubusercontent.com/65819144/230166077-264a6161-ec8c-47d7-87b7-8e073080a548.jpg)

(_Image from [Data Wrangling and Processing for Genomics](https://datacarpentry.org/wrangling-genomics)_)

The meaning of each of these mandatory fields are detailed below:

![SAMformat_fields](https://user-images.githubusercontent.com/65819144/230166180-fb086380-413a-4eef-8781-d0ba2b7e215b.jpg)

## [Quality control for FastQ data](#quality-control-for-FastQ-data)

# [Practical Exercise]

Open your terminal window and go to the Linux directory

Type:
```
cd Linux
```

In the directory, we have 10 compressed fastq files as fastq.gz. You can check that the files are there. Do you remember how to do that?

We will work with files:
```
ARIMSS995-11_1.fastq.gz
ARIMSS995-11_2.fastq.gz
```

As we saw in the introduction, this is the format we will get from the Illumina sequencer. To have a better look at them, we will uncompressed them:
```
gzip -d ARIMSS995-11_1.fastq.gz
```
wait until the command line is shown again on the screen and then
Type:
gzip -d ARIMSS995-11_2.fastq.gz
The files should be decompressed now and ready to work. Let’s have a look at one of
the fastq files.
Type:
head ARIMSS995-11_1.fastq
@M03346:10:000000000-AL260:1:1101:28195:9448 1:N:0:3
CCTCATCAGCCGCATTGCGACCAACTTCTGGATTAGCGCCAGCGCCCAGTCCTTTG
GTGATACCGCTACCGATTTGAATCGTCTGTCCAACCGCTGTTTTACGCAGCGCTTGT
GCATCGGTATTTACCGCGAAGAATTCAACACCTTCAATACGCTCGCGCACCATGTGT
TCAACAGCATTACCGCCGCCGCCGCCGACGCCGATGACTTTAATCACCGCGTCATT
GGTAAGTTCCATTGGTTCAAACATA
+
ABCCCFFFFFFCGGGGGGGGGGGHGHHHHHGHHHHHHGGGGGGGGGGGHHHHH
HHHHHGHHHHHGGGGGHGGGGGHHHHHHHHHGHHHHHHGGGGGFHHHHHGGG
GGGGGGGHHHHHHGGFHGHHHHHGGGGGGGHHHHHHHHGGHHHHHHGHEGGG
GGGGGGGGGGGGGGGGGGGGGGGFFFFFFFFFFFFFFFFFCFFFFFFAFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFBFFFFB
@M03346:10:000000000-AL260:1:1101:5008:22354 1:N:0:3
TCTGTGTGGGGCGCTGATTATAGACGTTACGGCTGCAATCTTCATCTGTTTGTATGG
ATATCGCTTCTCGGGTATTGTTCTCACCCGGTGCTATCGCCGTTTTTCCTGCAAGGT
TTTATTTTCATGTCACAGTCTACATCCGTGCTTCGTCGTAATGGATTTACTTTTAAACA
GTTTTTTGTTGCTCACGATCGCTGTGCGATGAAAGTGGGAACGGATGGCATTTTGC
TGGGCGCATGGGCACCGGTGGG
+
AAABAFDFAAB>EAEGEGGFGGHHHFFFHAFGGGGGGHHHHHHGHGHHHHHHHHH
HHBFFHGGFHEEGGGEG?/GHHHHGHFFHH1EEEEGHFHFGE?EBDGFGHDHFFHH
HGGGHGGHHHHGDHHH?<<GHFHFHHDGHFDGGGGHHDGDGGHFEHHEHHHDDD
HGHGFCCFCGHHHGGGGGGFGFFFE?E.ADFGG/0.CEFFGGFFF/EEF.AD.DBFFFFF
FFF/;/FF.;@-ADFE99..;B--;-
@M03346:10:000000000-AL260:1:1101:15632:28918 1:N:0:3
GGTTCGCCTGCGGATGCCCCGTCAGCACAATTCGTCGTCCCGGCCATATC
In the fastq file, each sequence read is represented by 4 lines:
1. Is the name of the sequence, where /1 or /2 indicates forward and reverse
(paired ends) reads.
2. The read sequence
3. Sequence/quality separator
4. Sequence quality. There is one character for each nucleotide. The character is
related to a sequence quality scores on ascii code.
Now, lets check how many reads we have, and double check we have the same
number in the R1 and R2 files. We can use the wc command (stands for word count)
with the -l (letter elle) option to count the number of lines in the file.
Type
wc -l ARIMSS995-11_1.fastq
wait for the result and then
Type
wc -l ARIMSS995-11_2.fastq
Question – how many paired reads are in the sample?
PS: Think about how many lines a single read takes up in FASTQ format
Quality control of obtained fastq files.
To have an idea of how sequencing files can vary, and the importance of assessing their
quality, we are going to compare different pair-ended sequencing reads. We will use the
two fastq files we have been working with and two additional ones located in the same
directory name Linux. The file names are: untrimmed_1.fastq.gz and
untrimmed_2.fastq.gz. As with the files we are working with, they need to be
decompressed. Please do so before proceeding. The instructions are the same as for
the fastq files you previously decompressed using the command gzip.
Once you have all four files as fastq files, launch FASTQC
Type:
fastqc
This will launch the main FASTQC window. From there: select File from the menu bar,
then Open, navigate to the Linux folder and open the two fastq files we have being
working with (ARIMSS995-11_1.fastq and ARIMSS995-11_2.fastq); hold down the
control button for selecting both files. FASTQC essentially treats each of the paired files
separately and will launch a separate tab for each FASTQ file.
Have a look at the information FASTQC is given for both file contents. Overall, this
dataset is of good quality.
Repeat for the second pair of fastq files.
Besides sequence differences, are there any other differences related to run quality
between these pair of files and the other file pair?
Please familiarize yourself with the term “trimming” and why it is important
to trimm sequences obtained by NGS.
so we only need to do some minor trimming (quality 25, length 50) using trim_galore,
as well as checking/removing Illumina adapter sequences.
First quit FASTQC to regain your command line prompt
Then run trim_galore:
trim_galore -q 25 --length 50 --paired SRR1553467_1.fastq SRR1553467_2.fastq
-q 25 = trim the 3’ end of the reads – remove nucleotides less than Phred Quality 25
--length 50 = after adapter and quality trimming, remove reads less than length 50bp
--paired = the names of the paired FASTQ files to analyses in order
If you now do a list of the directory contents:
ls -lrt
You should see that two new FASTQ (.fq) files have been created by trim_galore:
SRR1553467_1_val_1.fq
SRR1553467_2_val_2.fq
Question – how many paired reads are left in the sample after trimming
