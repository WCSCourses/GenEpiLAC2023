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

## [Genomic visualisation](#genomic-visualisation)

With the advent of Next Generation Sequencing technologies, the amount of genomic data generated has notably increased. Extracting biologically meaningful results from genomic data and communicating this information remains challenging. Visualisation is a key tool to make sense of the trillions of rows of data generated every day. Genome visualisation, e.g. DNA sequence assemblies and annotations and read mappings, is essential for data integration and exploration, interpretation of results and enables scientific discovery and hypothesis generation by providing new insights that may not otherwise be obvious. Additionally, genome visualisation is a valuable aid in expanding and communicating knowledge to both specialized and broad audiences.

Over the last two decades, hundreds of visualisation tools for genomic data have been published. The large number of tools are an indicator for the broad application of genomic data and a sign that visualisation of genomic data is a complex problem and active research domain. Some examples include [Tablet](https://ics.hutton.ac.uk/tablet/), [Integrative Genomics Viewer (IGV)](https://igv.org/), [GView](https://server.gview.ca/), [CGView](https://cgview.ca/), [BLAST Ring Image Generator (BRIG)](https://bmcgenomics.biomedcentral.com/articles/10.1186/1471-2164-12-402) and [Artemis](http://sanger-pathogens.github.io/Artemis/Artemis/). In this course we will be using Artemis.

## [Artemis](#artemis)

Artemis is a DNA viewer and annotation tool, free to download and use, written by Kim Rutherford from the Sanger Institute (Rutherford et al., 2000). The program allows the user to view a range of files, from simple sequence files (e.g. fasta format) to EMBL/Genbank entries, as well as the results of sequence analyses, in a highly interactive and intuitive graphical format. Artemis is routinely used by the Pathogen Genomics group for annotation and analysis of both prokaryotic and eukaryotic genomes, and can also be used to visualize mapped data from next generation sequencing. Several types/sets of information can be viewed simultaneously within different contexts. For example, Artemis gives you the two views of the same genome region, so you can zoom in to inspect detailed DNA sequence motifs, and also zoom out to view local gene architecture (e.g. operons), or even an entire chromosome or genome, all within one screen. It is also possible to perform analyses within Artemis and save the output for future reference.

# [Practical exercise](#practical-exercise)

## [Artemis exercise 1](#artemis-exercise-1)

### 1. Starting up the Artemis software

To launch Artemis, open your terminal window and type:

```
art &
```

A small start-up window will appear (see figure below). The directory for Module 3 contains all files you will need for this module. Please ask if you cannot find it on your computer. Now follow the sequence of numbers in the figure below to load up the *Salmonella* Typhi chromosome sequence. Ask a demonstrator for help if you have any problems.

![Artemis1](https://user-images.githubusercontent.com/65819144/231214046-58289d81-5d3d-4e9c-9bc9-dfbb49e111c9.png)

![Artemis2](https://user-images.githubusercontent.com/65819144/231215229-7dd5451b-d172-4c1e-8f15-a61727e795e5.png)


### 2. Loading an annotation file (entry) into Artemis

Hopefully you will now have an Artemis window like this! If not, ask a demonstrator for assistance.

![Artemis3](https://user-images.githubusercontent.com/65819144/231216039-4d8d6287-e631-41d3-a4da-be047a4140d6.png)

Now follow the numbers in the figure below to load the annotation file for the *Salmonella* Typhi chromosome.

![Artemis4](https://user-images.githubusercontent.com/65819144/231219005-22657063-b697-4c4b-92b3-d76f42b3f9b0.png)

**What is an entry?**

ENTRY=FILE

It’s a file of DNA and/or features which can be overlaid onto the sequence information displayed in the main Artemis view panel.

### 3. The basics of Artemis

Now you have an Artemis window open let’s look at what is in there:

`ADD FIGURE`

1- **Drop-down menus**: There’s lots in there so don’t worry about all the details right now.

2- **Entry (top line)**: shows which entries are currently loaded with the default entry highlighted in yellow (this is the entry into which newly created features are created). Selected feature: the details of a selected feature are shown here; in this case gene STY0004 (yellow box surrounded by thick black line).

3- **Main sequence view panel**: The central 2 grey lines represent the forward (top) and reverse (bottom) DNA strands. Above and below those are the 3 forward and 3 reverse reading frames. Stop codons are marked on the reading frames as black vertical bars. Genes and other annotated features (eg. Pfam and Prosite matches) are displayed as coloured boxes. We often refer to predicted genes as coding sequences or CDSs.

4- This panel has a similar layout to the main panel but is zoomed in to show nucleotides and amino acids. Double click on a CDS in the main view to see the zoomed view of the start of that CDS. Note that both this and the main panel can be scrolled left and right (7, below) zoomed in and out (6, below).

5- **Feature panel**: This panel contains details of the various features, listed in the order that they occur on the DNA. Any selected features are highlighted. The list can be scrolled (8, below).

6- **Sliders** for zooming view panels.

7- **Sliders** for scrolling along the DNA.

8- **Slider** for scrolling feature list.

### 4. Getting around in Artemis

 There are three main ways of getting to a particular DNA region in Artemis: 
 
- Goto drop-down menu
- Navigator 
- Feature Selector (which we will use in Exercise 4) 

The best method depends on what you’re trying to do. Knowing which one to use comes with practice.

*4.1 Goto menu*

The functions on this menu (below the Navigator option) are shortcuts for getting to locations within a selected feature or for jumping to the start or end of the DNA sequence. This is really intuitive so give it a try!

`ADD FIGURE`

It may seem that `Goto > Start of Selection` and `Goto > Feature Start` do the same thing.
Well they do if you have a feature selected but `Goto > Start of Selection` will also work for a region which you have selected by click-dragging in the main window. So yes, give it a try!

**Suggested tasks:**
  
1- Zoom out, select/highlight a large region of sequence by clicking the left hand button and dragging the cursor then go to the start and end of this selected region.
  
2- Select a CDS then go to the start and end.
  
3- Go to the start and end of the genome sequence.
  
4- Select a CDS. Within it, go to a base (nucleotide) and/or amino acid of your choice.
  
5- Highlight a region then, from the right click menu, select "Zoom to Selection". 

*4.2 Navigator*

The Navigator panel is fairly intuitive so open it up and give it a try.

`ADD FIGURE`

**Suggestions about where to go:**

1- Think of a number between 1 and 4809037 and go to that base (notice how the cursors on the horizontal sliders move with you).

2- Your favourite gene name (it may not be there so you could try *fts*).

3- Use `Goto Feature With This Qualifier value` to search the contents of all qualifiers for a particular term. For example, using the word "pseudogene" will take you to the next feature with the word "pseudogene" in any of its qualifiers. Note how repeated clicking of the `Goto` button takes you to the following pseudogene in the order that they occur on the chromosome.

4- Look at Appendix VI which is a functional classification scheme used for the annotation of S. Typhi. Each CDS has a class qualifier best describing its function. Use the `Goto Feature With This Qualifier value` search to look for CDSs belonging to a class of interest by searching with the appropriate class values.

5- tRNA genes. Type "tRNA" in the `Goto Feature With This Key`.

6- Regulator-binding DNA consensus sequence (real or made up!). Note that degenerate base values can be used (Appendix VIII).

7- Amino acid consensus sequences (real or made up!). You can use "x"s. Note that it searches all six reading frames regardless of whether the amino acids are encoded or not.

**What are Keys and Qualifiers?** See Appendix IV

Clearly there are many more features of Artemis which we will not have time to explain in detail. Before getting on with this next section it might be worth browsing
the menus. Hopefully you will find most of them easy to understand.

## [Artemis exercise 2](#artemis-exercise-2)

This part of the exercise uses the files and data you already have loaded into Artemis from Part I. By a method of your choice go to the region from bases 2188349 to 2199512 on the DNA sequence. This region is bordered by the *fbaB* gene which codes for fructose-bisphosphate aldolase. You can use the Navigator function discussed previously to get there. The region you arrive at should look similar to that shown below.

`ADD FIGURE`

Once you have found this region have a look at some of the information available:

**Annotation**

If you click on a particular feature you can view the annotation associated with it: select a CDS feature (or any other feature) and click on the `Edit` menu and select `Selected Feature in Editor`. A window will appear containing all the annotation that is associated with that CDS. The format for this information is constrained by that which can be submitted to the EMBL database.

**Viewing amino acid or protein sequence**

Click on the `View` menu and you will see various options for viewing the bases or amino acids of the feature you have selected, in two formats i.e. EMBL or fasta. This can be very useful when using other programs that are not integrated into Artemis e.g. those available on the Web that require you to cut and paste sequence into them.

**Plots/Graphs**

Feature plots can be displayed by selecting a CDS feature then clicking `View > Feature Plots`. The window which appears shows plots predicting hydrophobicity,
hydrophilicity and coiled-coil regions for the protein product of the selected CDS.

**Load additional files**
You should be able to see the results from Prosite searches, run on the translation of each CDS, as pale-green boxes on the grey DNA lines. The results from the Pfam
protein motif searches are not yet shown, but can be viewed by loading the appropriate file. Click on `File > Read an Entry` and select the file PF.tab. Each Pfam match will appear as a coloured blue feature in the main display panel on the grey DNA lines. To see the details click the feature then click `View > Selection` or click `Edit > Selected Features in Editor`. Please ask if you are unsure about Prosite and Pfam.

Further information on specific Prosite or Pfam entries can be found on the web at: http://ca.expasy.org/prosite and http://xfam.org/

In addition to looking at the fine detail of the annotated features it is also possible to look at the characteristics of the DNA covering the region displayed. This can be done by adding various plots to the display, showing different characteristics of the DNA. Some of the plots can be used to look at the protein coding potential of translation frames within the DNA, such as GC frame plot, and others can be used to search for horizontally acquired DNA.

The plot information is generated dynamically by Artemis and although this is a relatively speedy exercise for a small region of DNA, on a whole genome view (we will move onto this later) this may take a little time, so be patient.

**To view the graphs:**

Click on the `Graph` menu to see all those available. Perhaps some of the most useful plots are the (1) **GC Content (%)** and (2) **GC Deviation** as shown below. To adjust the smoothing of the graph you change the window size over which the points on the graph are calculated, using the sliders shown below. If you are not familiar with any of these please ask.

`ADD FIGURE`

Notice how several of the plots show a marked deviation around the region you are currently looking at. To fully appreciate how anomalous this region is move the genome view by scrolling to the left and right of this region. The apparent unusual nucleotide content of this region is indicative of laterally acquired DNA that has inserted into the genome.

Your Artemis window should now look similar to the one shown.

As well as looking at the characteristics of small regions of the genome, it is possible to zoom out and look at the characteristics of the genome as a whole. To view the entire genome you can use the sliders indicated below. However, be careful zooming out quickly with all the features being displayed, as this may temporarily lock up the computer.

1- To make this process faster and clearer, switch off stop codons by clicking with the right mouse button in the main view panel. A menu will appear with
an option to de-select "Stop Codons" (see below).

2. You will also need to temporarily remove all of the annotated features from the Artemis display window. In fact if you leave them on, which you can, they would be too small to see when you zoomed out to display the entire genome. To remove the annotation click on the S_typhi.tab entry button on the grey entry line of the Artemis window shown above.

`ADD FIGURES`

3. One final tip is to adjust the scaling for each graph displayed before zooming out. This increases the maximum window size over which a single point for each plot is calculated. To adjust the scaling click with the right mouse button over a particular graph window. A menu will appear with an option "Set the Window size" (see above), set the window size to ‘20000’. You should do this for each graph displayed (if you get an error message press continue).

4. You are now ready to zoom out by dragging or clicking the slider indicated above. Once you have zoomed out fully to see the entire genome you will need to adjust the smoothing of the graphs using the vertical graph sliders as before, to have a similar view to that shown below.

`ADD FIGURE`

## [Artemis exercise 3](#artemis-exercise-3)

There are many examples where anomalous regions of DNA within a genome have been shown to carry laterally acquired DNA. In this part of the exercise we are going to
look at several of these regions in more detail. Starting with the whole genome view, note down the approximate positions and characteristics of the three regions indicated above. Remember the locations of the peaks are given in the graph window if you click the left mouse button within it.

`ADD FIGURES`

We will now zoom back into the genome to look in more detail at the first of these three peaks. Using the left mouse button, highlight the anomalous region of the graph - this will also highlight the region in the main display. You can then use the right mouse button menu in the main display to `Zoom to selection` - you may need to zoom out from there. Remember that in order to see the CDS features lying within this region you will need to turn the annotation (S_typhi.tab) entry back on.

The region you should be looking at is shown below and is a classical example of a *Salmonella* pathogenicity island (SPI). The definitions of what constitutes a
pathogenicity island are quite diverse. However, below is a list of characteristics which are commonly seen within these regions, as described by Hacker et al., 1997.

1. Often inserted alongside stable RNAs

2. Atypical G+C contents.

3. Carry virulence-related functions

4. Often carry genes encoding transposase or integrase-like proteins

5. Unstable and self-mobilisable

6. Of limited phylogenetic distribution

Have a look in and around this region and look for some of these features

`ADD FIGURE`

Next go to Region 2.

`ADD FIGURE`

As with region 1, this region is also defined as a *Salmonella* pathogenicity island (SPI). SPI-7, or the major Vi pathogenicity island, is ~134 kb in length and contains ~30 kb of integrated bacteriophage. Have a look at the CDSs within this region. As before notice any stable RNAs that may have acted as the phage integration site.

## [Artemis exercise 4](#artemis-exercise-4)

Continuing on from the analysis of Region 2 or SPI-7 (the major Vi-antigen pathogenicity island) we are going to extract this region from the whole genome sequence and perform some more detailed analysis on it. We will aim to write and save new EMBL format files which will include just the annotations and DNA for this region.
Follow the numbers on the figure below to complete the task:

`ADD FIGURE`

A new Artemis window will appear displaying only the region that you highlighted:

`ADD FIGURE`

Note that the two entries on the grey "Entry" line are now denoted "no name". They represent the same information in the same order as the original Artemis window but
simply have no assigned "Entry" names. As the sub-sequence is now viewed in a new Artemis session, this prevents the original files (S_typhi.dna and S_typhi.tab) from
being over-written.

We will save the new files with relevant names to avoid confusion. So click on `File > Save An Entry As > New File`. Another menu will ask you to choose one of the entries listed. At this point they will both be called "no name". Left click on the top entry in the list. A window will appear asking you to give this file
a name. Save this file as spi7.dna

Do the same again for the second unnamed entry and save it as spi7.tab

`ADD FIGURE`
