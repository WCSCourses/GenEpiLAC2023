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

Bourne Shell

Bourne Again Shell – BASH (variant is Z Shell)

C Shell (variant is T Shell)

K Shell

Among these Bourne Again Shell (BASH) is the most popular one. This is the default shell on the
system, and we will be using it throughout this course. 

You should see a window labelled "Terminal" which will be empty except for a '$' character at the top left. The '$' character is the prompt, similar to "C:\" in DOS. 
You can type commands directly into the terminal at the prompt. The default location on the terminal is your “home directory”. It is represented with ~ (tilde) symbol.
