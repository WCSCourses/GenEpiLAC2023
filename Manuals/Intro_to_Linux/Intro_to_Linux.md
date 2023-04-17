<img src="https://coursesandconferences.wellcomeconnectingscience.org/wp-content/themes/wcc_courses_and_conferences/dist/assets/svg/logo.svg" width="200" height="200">


[<<< Go back to Manual Contents Page](https://github.com/WCSCourses/GenEpiLAC2023/blob/main/Manuals/README.md)

<br>

# Introduction to Linux - Paraguay 2023 <!-- omit in toc -->

## Table of contents <!-- omit in toc -->
- [Introduction](#introduction)
  - [The terminal](#the-terminal)
  - [The command line](#the-command-line)
  - [Useful commands](#useful-commands)
- [Practical Exercise](#practical-exercise)
  - [Additional exercises](#additional-exercises)

## Module Overview and Aims

The aim of this module is to recap some of the concepts you´ve learnt in the pre-course "Introduction to Linux for biologists April 23" and to practice a bit more the use of Linux command line, directory structure of the file system and manipulation of files/directories.

# [Introduction](#introduction)


## [The terminal](#the-terminal)
We use the terminal (command line interface) to interact with the operating system. The terminal by default runs one of the “shells”. Shell is a program that sits between the user and the kernel and translates user commands into machine code. There are some advantages of using the command line when working with genome analysis such as greater control and flexibility over the system or software, and multiple commands can be saved in a file and executed as a program. 

The most common shells are:

- Bourne Shell

- Bourne Again Shell – BASH (variant is Z Shell)

- C Shell (variant is T Shell)

- K Shell

Among these Bourne Again Shell (BASH) is the most popular one. This is the default shell on the system, and we will be using it throughout this course. 

You should see a window labelled "Terminal" which will be empty except for a '$' character at the top left. The '$' character is the prompt, similar to "C:\" in DOS. 
You can type commands directly into the terminal at the prompt. 

## [The command line](#the-command-line)

When you open a terminal, you will see a command prompt, ready to take commands. The command line tells the computer what to do. The default location on the terminal is your “home directory”. It is represented with ~ (tilde) symbol. 

Typing any command (e.g. `ls`, `mv` or `cd`) at the prompt with the appropriate variables such as files names or directories, will result in the tasks being performed after pressing the enter key.

Directories are the equivalent of folders on a PC or Mac. They are organised in a hierarchy, so directories can have sub-directories and so on. Directories are very useful for organising your work and keeping your account tidy. For example, if you have more than one project, you can organise the files for each project into different directories to keep them separate. You can think of directories as rooms in a house. You can only be in one room (directory) at a time. When you are in a room you can see everything in that room easily. To see things in other rooms, you have to go to the appropriate door and crane your head around. Linux works in a similar manner, moving from directory to directory to access files. 

## [Useful commands](#useful-commands)
All Linux commands are single words (can be alpha-numeric), with optional parameters followed by arguments. For historical reasons, some of the early commands are only two-letter long and case sensitive. Most of the command options are single letters. They should be specified after the command before giving any input. For example:
```
ls /home/manager/Linux
```

All Linux commands have manual pages. To check these manuals, use man or info command. The manual page gives a detailed explanation of the command, all available options and sometimes, also provides examples. For example, to view the manual page for `ls` command type: 
```
man ls 
```

Below you can find a list of frequently used commands for you to become familiar with them: 

| Command | What it does |
| ------ | ------------ |
| ls | Lists the contents of the current directory  |
| mkdir  | Makes a new directory  |
| mv | Moves or renames a file  |
| cp  | Copies a file  |
| rm | Removes a file  |
| mkdir  | Makes a new directory  |
| cat | Concatenates files  |
| more  | Displays the contents of a file one page at a time  |
| head | Displays the first ten lines of a file  |
| tail  | Displays the last ten lines of a file  |
| cd | Changes current working directory  |
| pwd	 | Prints working directory  |
| find  | Finds files matching an expression  |
| grep | Searches a file for patterns  |
| wc  | Counts the lines, words, characters, and bytes in a file  |
| kill | Stops a process  |
| jobs | Lists the processes that are running  |

# [Practical Exercise](#practical-exercise)

Open a terminal window and go to the following directory /home/manager/Linux. Do you remember how to do this? Use the `cd` command. Don't forget to press the [Enter] key for running a command: commands are not sent to the computer until this is done!

**How many files do you see in this directory?**

**Do you see different colors for each file? What do you think each color means?**

We will start working with the fasta file reference_Ss046.fasta. The location or “full pathname” of this file in the Linux directory can be expressed as: 
/home/manager/Linux/reference_Ss046.fasta

If we were interested in cutting a section from this file, we would use the command `cut`.

Remember you could see a command’s options using the `man` command, in this case:  

```
man cut
```

Press “q” when you are ready to close the help manual for the command `cut`.

To cut a section of a file use "-c" (characters). In the following example, the option “-c1-10” will output the first 10 characters of each line from the input file. 

Type:

```
cut -c1-10 reference_Ss046.fasta
```

Depending on the window size you are working, something similar to this will show up in your screen: 

```
GTTAAGAATT
AGAAGAGTGG
GGCGCGGGCA
GCCACCCGCT
AATCGTTACA
CACGCCAGTA
GGTCGCGAAG
TGGCGGATTA
ACAACAACCG
GCATTGCTGA
TTTTAGAGCA
AAAAACGCCT
```

Let´s take a look at another file named “Ssonei.txt” with some information regarding Latin American *Shigella sonnei* genome sequences. These fields are separated by “|” symbol. 

**How would you see the first 10 lines of “Ssonei.txt” file?** 

> Hint: Remember that there are several commands available that you can use.

You should see something like this:

```
|Sample name|ID |Accession (run) number |Accession (sample) number|Assembly accessions|Study |Year|Country
3626STDY6095476|53827|ERR1009118|ERS710307|FTXR01000001-FTXR01000440|Latin America|1998|Venezuela
3626STDY6095485|61034|ERR1009127|ERS710316|FTXZ01000001-FTXZ01000442|Latin America|2000|Venezuela
3626STDY6095486|60903|ERR1009128|ERS710317|FTYA01000001-FTYA01000402|Latin America|1999|Venezuela
3626STDY6095487|61015|ERR1009129|ERS710318|FTYC01000001-FTYC01000438|Latin America|2000|Venezuela
3626STDY6095488|61017|ERR1009130|ERS710319|FTYB01000001-FTYB01000442|Latin America|2000|Venezuela
3626STDY6095489|61022|ERR1009131|ERS710320|FTYD01000001-FTYD01000459|Latin America|2000|Venezuela
3626STDY6095490|61026|ERR1009132|ERS710321|FTYE01000001-FTYE01000432|Latin America|2000|Venezuela
3626STDY6095491|61027|ERR1009133|ERS710322|FTYF01000001-FTYF01000428|Latin America|2000|Venezuela
3626STDY6095493|61046|ERR1009134|ERS710324|FTYG01000001-FTYG01000426|Latin America|2000|Venezuela
```

Let’s say we need to order this file according to the year in which the sequences were uploaded. As you´ve seen previously, the `sort` command is used to sort the input content. 

Type: 

```
sort -t “|” -nrk7 Ssonei.txt
```

You should get something like this:

```
3626STDY6095526|844948|ERR1009158|ERS710357|FTZE01000001-FTZE01000440|Latin America|2014|Venezuela
3626STDY6095524|844939|ERR1009157|ERS710355|FTZD01000001-FTZD01000384|Latin America|2014|Venezuela
sh1347|sh1347_5735439|ERR212327|ERS157983|FTZF01000001-FTZF01000424|Latin America|2012|Peru
2090STDY5488137|ETA_160 7212449|ERR316394|ERS222732|FTXJ01000001-FTXJ01000381|Latin America|2012|Guatemala
2090STDY5488135|ETA_156 7212520|ERR316392|ERS222730|FTXI01000001-FTXI01000508|Latin America|2012|Guatemala
2090STDY5488134|ETA_152 7212508|ERR316391|ERS222729|FTXH01000001-FTXH01000377|Latin America|2012|Guatemala
2090STDY5488133|ETA_149 7212496|ERR316390|ERS222728|FTXG01000001-FTXG01000410|Latin America|2012|Guatemala
2090STDY5488132|ETA_53 7212484|ERR316389|ERS222727|FTXF01000001-FTXF01000367|Latin America|2012|Guatemala
2090STDY5488131|ETA_52 7212472|ERR316388|ERS222726|FTXE01000001-FTXE01000373|Latin America|2012|Guatemala
```

**How did we order the information?**

Let's assume that for our project, we need from this list of sequences, only the ones submitted from Paraguay, that appear with the word “Paraguay” in the text file. We will need a command that searches the input for a given pattern, in this case, the word “Paraguay”. **Do you remember which one?**

**How many *S. sonnei* genome sequences from Paraguay are in this dataset?**

This dataset is part of a joint effort between several Latin American countries and the Sanger Institute,  aimed to demonstrate the possibility and advantages of transitioning to whole-genome sequencing (WGS) for surveillance within existing networks across the continent, where *S. sonnei* is endemic. The publication, named “Whole-genome sequencing of *Shigella sonnei* through PulseNet Latin America and Caribbean: advancing global surveillance of foodborne illnesses” can be accessed here: https://www.clinicalmicrobiologyandinfection.com/article/S1198-743X(17)30190-8/fulltext

Let’s take a look at the the Metadata.csv file. 

Type:

```
head Metadata.csv
```

And also, type:

```
tail Metadata.csv
```

```
Pipes: piping in Linux is a very powerful and efficient way to combine commands. They act as connecting links between commands. Pipe redirects output of the first command as an input to the next command. We can nest as many commands as we want using pipes. They ensure smooth running of the command flow and reduce the execution time.
```

For your project, you also need to extract the accession run number of each *S. sonnei* sequence present in the “Ssonei.txt” file. Let’s use the previously learned cut command to do it. 

Type: 

```
sed '1d' Ssonei.txt | cut -d "|" -f3
```

You should get something like this:

```
ERR1009118
ERR1009127
ERR1009128
ERR1009129
ERR1009130
ERR1009131
ERR1009132
ERR1009133
ERR1009134
ERR1009135
ERR1009119
ERR1009136
ERR1009137
ERR1009138
ERR1009139
ERR1009140
```

Let’s take a closer look to these commands:

The ```sed``` command is used to perform basic text transformations on a file. The parameter ‘1d’ tells the sed command to apply the ‘d’ (delete) action on line number ‘1’ (to avoid headers and just keep the accession run numbers that we are interested in). Considering the following cut command, the -d option is used to cut based on a delimiter, in this case the pipe “|”. The -f is used for the field number, in the “Ssonei.txt” file the accession run number was on field 3 separated by “|”.

Going back to the Metadata.csv file, if we want to know how many sequences were submitted, we can count the lines. Do you remember how to do this?

So now we know we have 322 metadata from genome sequences of Latin American *Shigella sonnei* within this dataset (the first line contains the headers).

Now, let’s say we want to know which countries have reported sequences in this dataset. We will use the `uniq` command that extracts unique lines from the input. Do you remember this command? It is usually used in combination with sort to count unique values in the input. 

Type: 

```
sed ‘1d’ Metadata.csv|cut -f3 -d ";"|sort| uniq
```

```
Process control 
Some commands take time to finish the assigned job. For example, if you would like to compress a huge file with gzip command that takes a few minutes to finish running, you can run it in the background by appending the command with “&” (Another way is to suspend a command by pressing Ctrl+Z and typing “bg”). The completion of the task is indicated by “Done”. 
Type: 
gzip list & 
```

```
Command line shortcuts 
●	Up/Down arrows: Previous commands 
●	!!: Reruns previous command 
●	Tab: Auto complete 
●	Tab+Tab: All available options 
●	Ctrl+a: Move cursor to start of line 
●	Ctrl+e: Move cursor to end of line 
●	Alt+: Alternates between terminals 
●	Ctrl+l: Clear screen (or Command+k on Mac) 
●	Ctrl+c: Terminates the running program 
●	Ctrl+z: Suspends the running program 
●	Ctrl+w: Removes a previous word 
●	Ctrl+d: Logout 
●	Ctrl+d(in a command): Removes a character 
●	Ctrl+u: Removes till the beginning 
```

## [Additional exercises](#additional-exercises)

1. Extract the first 15 lines from file “reference_Ss046.fasta” and save the output into “output.fa” 
2. How many files are there in the Linux directory? 
3. Create a new file called “Linux_directory.txt” which contains a list of the file names present in the Linux directory.
4. Get the list of countries that contributed *S. sonnei* genome sequences for the publication previously mentioned and save it to “countries.txt” 
5. Extract the Assembly accessions of the sequences in “Ssonei.txt” and save it to “assemblies.txt”. How many are there?
6. Given a file with different sequences of Latin America, how do you count the ones submitted by Chile? (we know they should have the word “CHI” in the line).
7.  .............is the command used to create a new directory.
8. Command used to create an empty file.
9. Which is the command used to remove or delete files without a confirmation prompt?
10. "cat" is the command used to ...................
11. ............. command is used to count the total number of lines, words and characters in a file. 
12. Which command would you use to know the location of your current working directory?

<br>


[<<< Go back to Manual Contents Page](https://github.com/WCSCourses/GenEpiLAC2023/blob/main/Manuals/README.md)

<br>

[>>> Go to Sequencing QC](https://github.com/WCSCourses/GenEpiLAC2023/blob/main/Manuals/Sequencing%26QC/Sequencing%26QC.md)

<br>
