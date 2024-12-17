---
title: Exploring the Tiny C Compiler
date: 2024-12-16
last_modified_at: 2024-12-16
tags: c programming compilers
excerpt: A minimalist approach to C Programming
---

# Introduction
The world of C programming can often seem overwhelming due to the variety of compilers and
development environments available. While many modern compilers are feature-rich and offer a wealth of
optimizations, there’s something uniquely satisfying about using a simpler, more minimalist tool.

One such tool is the Tiny C Compiler (TCC) [1, 2]. As its name suggests, TCC is designed to be a tiny, fast,
and lightweight C compiler that is ideal for both beginners and those who prefer a no-frills
experience.
 
In this tutorial, let's take a look at what the Tiny C Compiler is, why you might want to use it, and how
to download and use it.

# What is the Tiny C Compiler?
The Tiny C Compiler (TCC) is a small, portable, and incredibly fast C compiler that’s designed to
provide a lightweight alternative to more traditional compilers like GCC [3]. Despite its small size, TCC
is highly functional and supports most of the standard C features, making it an excellent choice for
quick compilation tasks, learning the C language, or for use in resource-constrained environments.

TCC stands out for several reasons:
- **Size**: TCC’s source code is compact, and the resulting binary is often smaller than other C
compilers. The entire compiler package is less than 2MB in disk size.
- **Speed**: TCC compiles code very quickly, often at the expense of some optimizations, but it’s
still quite efficient for most use cases.
- **Portability**: TCC works on a variety of platforms, including Linux, macOS, and Windows.
- **Easy to Use**: The compiler has a simple command-line interface, making it easy to integrate
into scripts or build processes.


# Why use TCC?
TCC might not be the best choice for production-level code, but it excels in a few important areas:

- **Learning**: Its simplicity makes it an excellent choice for beginners who want to understand
how C compilers work without the complexity of modern compilers.
- **Rapid Prototyping**: If you’re writing simple programs or just need to quickly test snippets of code, TCC can save you time compared to more heavyweight compilers.
- **Embedded Development**: TCC can be useful in low-resource environments, where the full
power of GCC or Clang might not be needed.

Now that we have covered the basics, let's walk through how to download and use the Tiny C
Compiler.

# How to Download and Use TCC

## Step 1: Download TCC
The first step is to get the compiler. TCC is open-source and available for free, so you can
download it from the official mirror [here](https://download.savannah.gnu.org/releases/tinycc/)

### On Windows
For Windows users, download the latest x64 binary release [here](https://download.savannah.gnu.org/releases/tinycc/tcc-0.9.27-win64-bin.zip), extract the files to a folder and you're ready to start using TCC.

### On Linux (apt)

```bash
sudo apt-get update
sudo apt-get install tcc
```

### On macOS (homebrew)

```bash
brew install tcc
```

## Step 2: Install TCC
On Linux or macOS, if you used a package manager like `apt` or `brew`, TCC will be installed
automatically. You can verify the installation by running:

```bash
tcc --version
```

If you downloaded a precompiled binary, you can install tcc by copying the files to a directory of your choice.

## Step 3: Create a C Program
Now that TCC is installed, let's write a simple C program to test the compiler. Open a text editor and create a file called `hello.c` with the following code:

```c
#include <stdio.h>
int main() {
    printf("Hello, world!\n");
    return 0;
}
```

## Step 4: Compiling with TCC
Once you have your C file ready, you can compile it using TCC. Open a terminal (or Command
Prompt on Windows) and navigate to the directory where your `hello.c` file is saved.

To compile the code, run the following command:

```bash
tcc hello.c -o hello.exe
```

TCC will compile your code into an executable file.

## Step 5: Running the Program
After the compilation is complete, you can run the program by typing:

On Linux or macOS:
```bash
./hello
```
On Windows:

```bash
hello.exe
```

This should display the message: `Hello, world!`

## Step 6: Exploring Further
TCC is a very simple compiler, but it does support some interesting features, such as:
- Inline assembly: You can embed assembly code within your C programs.
- Dynamic loading: You can link with shared libraries dynamically at runtime.
- Fast compilation: TCC’s main selling point is its speed. You can compile large programs in just
a fraction of the time it might take other compilers.

You can also experiment with TCC’s many compiler flags to see how they affect the output. For
instance, you can use the -O flag for optimizations or the -g flag to include debugging symbols.

### Example 1: Compiling a Program with Optimization
To compile with optimizations enabled:

```bash
tcc -O2 hello.c -o hello_opt.exe
```

This will use the optimization level -O2 , which improves performance (at the cost of some
additional compilation time).

### Example 2: Compiling Hello Windows
The Tiny C compiler includes some example source code which can be found in the `examples` folder.

The file `hello_win.c` contains source code for an example 'hello world' program using the Windows GUI.

To compile `hello_win.c` on Windows; open a command prompt, navigate to the `tcc` folder and run:

```bash
tcc .\examples\hello_win.c -o hello_win.exe
```

The default output of `hello_win.exe` is shown below. The program can also take command line arguments which are displayed instead of the default greeting. This can serve as a useful graphical equivelant to the `echo` command.

![example](/assets/images/2024-12-16-tiny-c-compiler.png){: .align-center}

# Conclusion
The Tiny C Compiler is an excellent tool for anyone looking for a lightweight, fast, and easy-to-use
C compiler. Whether you're a beginner looking to learn C programming or an experienced
developer looking for a simple way to quickly compile small programs, TCC offers a straightforward
solution. Its minimalist approach can help you understand the basics of C compilation and is perfect for
learning environments, small projects, or rapid prototyping.

# References
[[1] Tiny C Compiler](https://www.bellard.org/tcc/)

[[2] Tiny C GitHub - Unofficial mirror of mob development branch](https://github.com/TinyCC/tinycc)

[[3] GCC, the GNU Compiler Collection]((https://gcc.gnu.org/))
