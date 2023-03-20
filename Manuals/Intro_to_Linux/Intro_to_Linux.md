# Introduction to Linux - Paraguay 2023 <!-- omit in toc -->

## Table of contents <!-- omit in toc -->
- [Module Overview and Aims](#module-overview-and-aims)
- [Introduction](#introduction)
  - [Linux Operating System](#linux-operating-system)
  - [The terminal](#the-terminal)
  - [The command line](#the-command-line)
  - [Useful commands](#useful-commands)
- [Practical Exercise](#practical-exercise)

## Module Overview and Aims
- Become familiar with Linux Operating System and understand why it is widely used in bioinformatics
- Understand Linux command line and the directory structure of the file system
- Learn how to manipulate files/directories

# [Introduction](#introduction)

## [Linux Operating System](#linux-operating-system)
Linux is an open-source operating system (OS) based on the kernel created by Linus Benedict Torvalds and was first released in 1991. An OS is a computer program which manages how you connect to various pieces of hardware (screen, keyboard, mouse etc.) and also manages your files and allows you to run software applications.

Linux is a powerful, robust and stable operating system that allows dozens of people to run programs on the same computer at the same time. It runs on all kinds of machines, from desktop PCs, mobile phones to supercomputers.

Increasingly, the output of lab-based biology exists as large text files, for example the data files from sequencing machines. Linux has a range of powerful and flexible commands which can be used to edit and manipulate these files. This is why it is the preferred operating system for large-scale scientific computing.

During this course, we will work on a local Linux machine running Ubuntu but most of the commands specified in this manual can be used in any other distribution (i.e. CentOS, Debian, etc) of Linux OS. 

## [The terminal](#the-terminal)
We use the terminal (command line interface) to interact with the operating system. The terminal by default runs one of the “shells”. Shell is a program that sits between the user and the kernel and translates user commands into machine code. There are some advantages of using the command line when working with genome analysis such as greater control and flexibility over the system or software, and multiple commands can be saved in a file and executed as a program. 

The most common shells are:

- Bourne Shell

- Bourne Again Shell – BASH (variant is Z Shell)

- C Shell (variant is T Shell)

- K Shell

Among these Bourne Again Shell (BASH) is the most popular one. This is the default shell on the
system, and we will be using it throughout this course. 

You should see a window labelled "Terminal" which will be empty except for a '$' character at the top left. The '$' character is the prompt, similar to "C:\" in DOS. 
You can type commands directly into the terminal at the prompt. 

## [The command line](#the-command-line)

When you open a terminal, you will see a command prompt, ready to take commands. The command line tells the computer what to do. The default location on the terminal is your “home directory”. It is represented with ~ (tilde) symbol. 

Typing any command (e.g. ls, mv or cd) at the prompt with the appropriate variables such as files names or directories, will result in the tasks being performed after pressing the enter key.

Directories are the equivalent of folders on a PC or Mac. They are organised in a hierarchy, so directories can have sub-directories and so on. Directories are very useful for organising your work and keeping your account tidy. For example, if you have more than one project, you can organise the files for each project into different directories to keep them separate. You can think of directories as rooms in a house. You can only be in one room (directory) at a time. When you are in a room you can see everything in that room easily. To see things in other rooms, you have to go to the appropriate door and crane your head around. Linux works in a similar manner, moving from directory to directory to access files. 

## [Useful commands](#useful-commands)

| Command | | What it does |
| ------- | ------------ |
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

	
	
	
	
	
	
	
	

	
	
	
	
	




