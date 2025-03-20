---
title: Setup COBOL Development Environment on Windows
date: 2025-03-19
last_modified_at: 2025-03-19
tags: cobol windows development
excerpt: Learn how to set up GnuCOBOL for Windows and compile a sample application.
---

# Introduction
COBOL (Common Business-Oriented Language) is one of the oldest high-level programming languages, developed in the late 1950s. It was designed for business applications, making it particularly strong in handling large volumes of data and performing batch processing.

Despite its age, COBOL remains relevant due to the critical systems it supports. It is often called the "language that won't die" because of its enduring presence in the tech world. This guide will walk you through setting up a COBOL development environment on a Windows system.

# COBOL Overview
COBOL is known for its readability and ease of use, making it accessible to non-programmers. It is widely used in industries such as banking, insurance, and government, where legacy systems still rely on COBOL programs for critical operations.

Some key features of COBOL include:

- English-Like Syntax: COBOL is designed to be highly readable, with a structure resembling natural English, making it easier for non-technical users to understand.

- Business-Oriented: It is specifically tailored for business applications, excelling in handling large-scale data processing and transaction systems.

- Portability: COBOL programs can run on various hardware and operating systems with minimal modifications, making it versatile.

- Strong Numeric Capabilities: It provides robust support for precise arithmetic and handling of monetary data, crucial for banking and financial applications.


# GnuCOBOL Compiler
I've created an installer package for GnuCOBOL for Windows which you can download [here](/assets/uploads/GnuCOBOL.exe).

The packages installs the compiler to the `C:\Program Files\GnuCOBOL` directory and sets the necessary environment variables.

It is based on the GnuCOBOL 3.2 BDB package by Arnold Trembley [1].

For other versions and platforms, you can visit the GnuCOBOL Project on SourceForge [2].


# VSCode Extension
If you use Visual Studio Code, you can add the COBOL extension to enable language support. Go to the Extensions tab, search for "COBOL" and install the extension provided by bitlang.


# Example COBOL Program
Create `hello.cob` file with the example code shown below:

```cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. HELLO-WORLD.   
PROCEDURE DIVISION.
    DISPLAY 'Hello, World!'.
    STOP RUN.
```


# Compile and Run
To compile and run the COBOL program, follow these steps:

## 1. Set environment variables

Open a terminal and run the `cob` command.

This sets **non persistent** environment variables for GnuCOBOL. 

`Note: cob is an alias for set_env.cmd file in GNUCobol directory.`

## 2. Compile program
Navigate to the directory containing your COBOL program and run the following command:

```bash
gcx hello.cob
```

## 3. Run the program
This will generate an executable file named `hello.exe`. Run the program by executing:

```bash
hello
```

You should see the output `Hello, World!` displayed on the console.


# Conclusion

Setting up a COBOL development environment on Windows allows you to write, compile, and run COBOL programs for various business applications. With the GnuCOBOL compiler and Visual Studio Code extension, you can leverage the power of COBOL for modern development tasks. For futher information, refer to the GnuCOBOL documentation and resources (see Appendix) to explore more advanced features and capabilities of the language.

# References

[[1] GnuCOBOL/OpenCOBOL Downloads, Binaries, and Links - Arnold Trembley](https://www.arnoldtrembley.com/GnuCOBOL.htm)


[[2] GnuCOBOL Project on SourceForge](https://sourceforge.net/projects/gnucobol/)


# Appendix

## Sample program with variables

```cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. SAMPLE-PROGRAM.
DATA DIVISION.
WORKING-STORAGE SECTION.
01 WS-NAME PIC X(20) VALUE 'John Doe'.
01 WS-AGE PIC 99 VALUE 30.
PROCEDURE DIVISION.
DISPLAY 'Name: ' WS-NAME.
DISPLAY 'Age: ' WS-AGE.
STOP RUN.
```

## Sample program with user input

```cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. READ-USER-INPUT.
DATA DIVISION.
WORKING-STORAGE SECTION.
01 WS-NAME PIC X(20).
01 WS-AGE PIC 99.
PROCEDURE DIVISION.
DISPLAY 'Enter your name: '.
ACCEPT WS-NAME.
DISPLAY 'Enter your age: '.
ACCEPT WS-AGE.
DISPLAY 'Name: ' WS-NAME.
DISPLAY 'Age: ' WS-AGE.
STOP RUN.
```


## Documentation

- `GNUCobol\STARTHERE.txt`
- `GNUCobol\GnuCOBOL 3.2 Manual.pdf`
- `GNUCobol\docs`

## Resources

Beginning COBOL for Programmers by Michael Coughlan. ISBN: 978-1430262534