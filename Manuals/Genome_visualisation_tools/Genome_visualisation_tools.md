<img src="https://coursesandconferences.wellcomeconnectingscience.org/wp-content/themes/wcc_courses_and_conferences/dist/assets/svg/logo.svg" width="200" height="200">

# Genome Visualisation tools - Paraguay 2023 <!-- omit in toc -->

## Table of contents <!-- omit in toc -->
- [Introduction](#introduction)
  - [Genomic visualisation](#genomic-visualization)
  - [Artemis](#artemis)
- [Practical Exercise](#practical-exercise)
  - [Artemis exercise 1](#artemis-exercise-1)
  - [Artemis exercise 2](#artemis-exercise-2)
  - [Artemis exercise 3](#artemis-exercise-3)
  - [Artemis exercise 4](#artemis-exercise-4)

## Module Overview and Aims
The aim of this Module is for you to become familiar with the basic functions of Artemis using a series of worked examples. These examples are designed to take you through the most immediately useful functions. However, there will be time, and encouragement, for you to explore other menus; features of Artemis that are not described in the exercises in this manual, but which may be of particular interest to some users.

# [Introduction](#introduction)

## [Genomic visualisation](#genomic-visualization)

With the advent of Next Generation Sequencing technologies, the amount of genomic data generated has notably increased. Extracting biologically meaningful results from genomic data and communicating this information remains challenging. Visualisation is a key tool to make sense of the trillions of rows of data generated every day. Genome visualisation, e.g. DNA sequence assemblies and annotations and read mappings, is essential for data integration and exploration, interpretation of results and enables scientific discovery and hypothesis generation by providing new insights that may not otherwise be obvious. Additionally, genome visualisation is a valuable aid in expanding and communicating knowledge to both specialized and broad audiences.

Over the last two decades, hundreds of visualisation tools for genomic data have been published. The large number of tools are an indicator for the broad application of genomic data and a sign that visualisation of genomic data is a complex problem and active research domain. Some examples include Tablet, Integrative Genomics Viewer (IGV), GView, CGView, BRIG and Artemis. In this course we will be using Artemis.

## [Artemis](#artemis)

Artemis is a DNA viewer and annotation tool, free to download and use, written by Kim Rutherford from the Sanger Institute (Rutherford et al., 2000). The program allows the user to view a range of files, from simple sequence files (e.g. fasta format) to EMBL/Genbank entries, as well as the results of sequence analyses, in a highly interactive and intuitive graphical format. Artemis is routinely used by the Pathogen Genomics group for annotation and analysis of both prokaryotic and eukaryotic genomes, and can also be used to visualize mapped data from next generation sequencing. Several types/sets of information can be viewed simultaneously within different contexts. For example, Artemis gives you the two views of the same genome region, so you can zoom in to inspect detailed DNA sequence motifs, and also zoom out to view local gene architecture (e.g. operons), or even an entire chromosome or genome, all within one screen. It is also possible to perform analyses within Artemis and save the output for future reference.

# [Practical exercise](#practical-exercise)

## [Artemis exercise 1](#artemis-exercise-1)

**1. Starting up the Artemis software**

To launch Artemis, double click the Artemis icon on the desktop.

A small start-up window will appear (see figure below). The directory for Module 3 `(?)` contains all files you will need for this module. Please ask if you cannot find it on your computer. Now follow the sequence of numbers in hte figure below to load up the *Salmonella* Typhi chromosome sequence. Ask a demonstrator for help if you have any problems.

`ADD FIGURE`

**2. Loading an annotation file (entry) into Artemis**

Hopefully you will now have an Artemis window like this! If not, ask a demonstrator for assistance.

`ADD FIGURE`

Now follow the numbers in hte figure below to load the annotation file for the *Salmonella* Typhi chromosome.

`ADD FIGURE`

**3. The basics of Artemis**

Now you have an Artemis window open let’s look at what is in there:

`ADD FIGURE`

1- **Drop-down menus**: There’s lots in there so don’t worry about all the details right now.

2- **Entry (top line)**: shows which entries are currently loaded with the default entry highlighted in yellow (this is the entry into which newly created features are created). Selected feature: the details of a selected feature are shown here; in this case gene STY0004 (yellow box surrounded by thick black line).

3- **Main sequence view panel**: The central 2 grey lines represent the forward (top) and reverse (bottom) DNA strands. Above and below those are the 3 forward and 3 reverse reading frames. Stop codons are marked on the reading frames as black vertical bars. Genes and other annotated features (eg. Pfam and Prosite matches) are displayed as coloured boxes. We often refer to predicted genes as coding sequences or CDSs.

4- This panel has a similar layout to the main panel but is zoomed in to show nucleotides and amino acids. Double click on a CDS in the main view to see the zoomed view of the start of that CDS. Note that both this and the main panel can be scrolled left and right (7, below) zoomed in and out (6, below).

5- Feature panel: This panel contains details of the various features, listed in the order that they occur on the DNA. Any selected features are highlighted. The list can be scrolled (8, below).

6- Sliders for zooming view panels.

7- Sliders for scrolling along the DNA.

8- Slider for scrolling feature list.

**4. Getting around in Artemis**

 There are three main ways of getting to a particular DNA region in Artemis: 
 
-the Goto drop-down menu
-the Navigator and 
-the Feature Selector (which we will use in Exercise 4) 

The best method depends on what you’re trying to do. Knowing which one to use comes with practice.


