---
title: How to setup Eclipse for C++ development on Windows
tags:
  - eclipse
  - c++
  - development
excerpt: A guide to configuring the necessary tools and plugins and running an example Hello World program.  
---
# Introduction
Eclipse IDE is a free and open-source integrated development environment. It is primarily used for Java programming, but it also supports other languages like C, C++, Python, and more [1]. To setup Eclipse for C++ development, we need to install the necessary tools and plugins first. This article is a step-by-step guide to setting up C++ in Eclipse.

# Setup the C++ compiler
First, we need to install a C++ compiler for Eclipse to use. GCC (GNU Compiler Collection) is a free and open source C++ compiler. The MinGW-w64 is a version of GCC that is compatible with Microsoft Windows [2]. 

Download the latest standalone build from WinLibs.com [here](https://winlibs.com/#download-release). 

![Download MinGW-w64 WinLibs.com](/assets/images/2024-11-21-eclipse-cpp-1.png){: .align-center}

From the downloaded archive, extract the `mingw64` folder and copy it to your C drive. 

It contains a `bin` folder, which holds development related binaries. 


## Set PATH environment variables
We need to add this location to the system PATH variable. The system PATH variable is an environment variable that specifies a set of directories where executable programs are located, allowing the operating system to find and run these programs. 

Open a Command Prompt and run `start sysdm.cpl` to launch System Properties.

![Set Environment Variables](/assets/images/2024-11-21-eclipse-cpp-2.png){: .align-center}

Click on the `Advanced` tab and then click on the `Environment Variables` button. 

![Set Environment Variables](/assets/images/2024-11-21-eclipse-cpp-3.png){: .align-center}

Edit the system `PATH` variable and add the location of your `mingw64\bin` folder. 

![Set Environment Variables](/assets/images/2024-11-21-eclipse-cpp-4.png){: .align-center}

Restart your computer for the changes to take effect. 

# Setup Eclipse 
Download Eclipse IDE for C/C++ Developers from [here](https://www.eclipse.org/downloads/packages/)

Launch Eclipse and setup a new default workspace. 

Create a new Hello World project as follows:
  - File → New C/C++ Project
  - C++ Managed Build 
  - Project type → Executable → Hello World 
  - ToolChains → MinGW GCC
  - All other settings default

![Create Hello World Project](/assets/images/2024-11-21-eclipse-cpp-5.png){: .align-center}

Now build and run the project...


From the `Project` menu, select `Build Project`.

![Build Project](/assets/images/2024-11-21-eclipse-cpp-6.png){: .align-center}


From the `Run` menu, select `Run As` → `2 Local C/C++ Application`.

![Run Project](/assets/images/2024-11-21-eclipse-cpp-7.png){: .align-center}

The first time we run the application, Eclipse sets up a Run Configuration for the project so that we can simply click Run or (CTRL + F11) to launch the application in future. The output of the Hello World program is shown in the Console window at the bottom of the Eclipse IDE.

![Project output](/assets/images/2024-11-21-eclipse-cpp-8.png){: .align-center}

## CDT Plugin
If you downloaded the C++ version of Eclipse, the C/C++ Development Tools (CDT) plugin should already be included. If you need to install CDT manually you can go to  Help > Eclipse Marketplace, search for CDT and install it [4]. 

# Conclusion
With a little configuration, Eclipse proved to be a usable C++ development environment on Windows. The IDE provides good support for C++ via the Marketplace and CDT plugin [4]. However, we must provide a C++ compiler to use. The process of setting up the compiler was greatly simplified thanks to the work of the  MinGW-w64 and WinLibs.com projects [2, 3]. Once the compiler was sucessfully installed, we were able to build and run C++ projects in Eclipse with minimal effort. 

# References

[[1] Eclipse Packages](https://www.eclipse.org/downloads/packages/)

[[2] MinGW-w64](https://www.mingw-w64.org/)

[[3] WinLibs standalone build of GCC and MinGW-w64 for Windows](https://winlibs.com/#download-release)

[[4] Eclipse CDT (C/C++ Development Tooling)](https://projects.eclipse.org/projects/tools.cdt)

