---
title: How to emulate your own mainframe computer
date: 2025-03-06
last_modified_at: 2025-03-06
tags: mainframe ibm hercules mvs-tk5
excerpt: Learn how to emulate your own mainframe computer using modern hardware and software.

---

# Introduction

For those interested in exploring mainframe computing, the MVS-TK5 package provides a turnkey environment to emulate IBM's MVS operating system on your personal computer [1]. 

Paired with the Hercules emulator, this setup allows you to experiment with a simulated mainframe environment without needing access to expensive hardware. Here's a technical guide to get started. 

# What Is Hercules and MVS-TK5?

Hercules is an open-source software emulator that allows you to simulate IBM mainframe hardware on a modern computer [2]. 

MVS-TK5 is a package that integrates Hercules with a ready-to-run version of the MVS 3.8j operating system, a classic version of IBM's MVS (Multiple Virtual Storage) system.

The combination of Hercules and MVS-TK5 offers an accessible way to learn about mainframe architecture and operating systems, practice skills useful for working on legacy systems and explore historical computing technologies in a hands-on manner.

# MVS-TK5 Installation Guide

Here's a step-by-step guide to setting up MVS-TK5 with Hercules on your computer:

1. Download the MVS-TK5 Package

You can download the MVS-TK5 package [here](https://www.prince-webdesign.nl/tk5).

2. Extract the Files

Unzip the downloaded package to a directory of your choice. The `mvs-tk5` folder will typically contain:

   - The Hercules emulator.
   - MVS-TK5 system files, including DASD (Direct Access Storage Device) images.
   - Configuration files and documentation.

3. Boot the MVS System

Start MVS by executing the batch or script file provided in the package - `mvs.bat` on Windows or `mvs` shell script on Linux or macOS.

You'll see the MVS system loading in the console window. This process may take a few minutes. Once completed, you should see the following message:

```Script 5: file scripts/tk5.rc processing ended```

![Emulate your own mainframe 2](/assets/images/2025-03-06-emulate-your-own-mainframe-1.png)

# What is TSO? 

TSO, or Time Sharing Option, is a key component of the MVS operating system. It allows multiple users to access and interact with the mainframe concurrently in a time-sharing environment. With TSO, users can log into the system, execute commands, edit datasets, and submit jobs using a command-line interface.

One of TSO's most powerful features is its integration with the Interactive System Productivity Facility (ISPF), which provides a menu-driven interface for various administrative and development tasks. 

TSO and ISPF are essential tools for mainframe users to navigate the system and perform day-to-day operations.

# How to access the MVS System

Once the MVS system is up and running, you can access it using a terminal emulator. x3270 is a popular terminal emulator used to access and interact with mainframe systems via the TN3270 protocol [3]. x3270 is available in several different forms, including wc3270, a Windows version of the emulator.

Follow these steps to connect to the MVS system using wc3270:

- Download and install wc3270 from [here](http://x3270.bgp.nu/).
- Open wc3270, type ```open localhost:3270``` and hit Enter.
- You should now see the mainframe login screen as shown below.
  
![Emulate your own mainframe 2](/assets/images/2025-03-06-emulate-your-own-mainframe-2.png)

**Note**
If the text appears garbled or unreadable, try maximizing the wc3270 window to adjust the display settings. This issue can occur due to the default font size or window dimensions.

- Enter `HERC01` as the username and press Enter.
- Enter the default password ```CUL8TR```and press Enter.
- Hit Enter a couple of times to bypass the initial messages.
- You should now see the ISPF screen as shown below.
  
![Emulate your own mainframe 3](/assets/images/2025-03-06-emulate-your-own-mainframe-3.png)


# Testing COBOL Programs

 MVS-TK5 includes sample COBOL programs that you can compile and run to familiarize yourself with mainframe development.

To test a COBOL program, follow these steps:

- From the main ISPF menu, Hit M to access TSOAPPLS.
 
![Emulate your own mainframe 4](/assets/images/2025-03-06-emulate-your-own-mainframe-4.png)

- Select option 1 to access the RFE (Review Front End) tool.
  
![Emulate your own mainframe 5](/assets/images/2025-03-06-emulate-your-own-mainframe-5.png)

- Select option 3 to access Utilites.
  
![Emulate your own mainframe 6](/assets/images/2025-03-06-emulate-your-own-mainframe-6.png)

- Select option 4 to access DSLIST (Data set List). 

![Emulate your own mainframe 7](/assets/images/2025-03-06-emulate-your-own-mainframe-7.png)

- Type ```SYS2``` for ```Data set name prefix``` and hit Enter.

![Emulate your own mainframe 8](/assets/images/2025-03-06-emulate-your-own-mainframe-8.png)

- Use the down arrow key to navigate to ```SYS2.JCLIB```, press V, then hit Enter to view the data set.

![Emulate your own mainframe 9](/assets/images/2025-03-06-emulate-your-own-mainframe-9.png)
  
- Use the F8 key to scroll down. Find the sample COBOL program called ```TESTCOB```. Press the V key, then press Enter to view the file. 

 ![Emulate your own mainframe 10](/assets/images/2025-03-06-emulate-your-own-mainframe-10.png)
- Type ```SUBMIT``` in the Command field, then hit Enter. 

 ![Emulate your own mainframe 11](/assets/images/2025-03-06-emulate-your-own-mainframe-11.png)

- You should see the output of the COBOL program in the ```Hercules - System Status``` window, shown on the left hand side.
 
![Emulate your own mainframe 12](/assets/images/2025-03-06-emulate-your-own-mainframe-12.png)

# Conclusion

Setting up MVS-TK5 with Hercules isn't just a technical exercise; it's an opportunity to engage with a pivotal era of computing history. By following these steps, you can build your own mainframe environment and gain valuable insights into the world of enterprise computing.
For further exploration, you can check out the documentation included with MVS-TK5.

# References

[[1] MVS Turnkey 5 Update 4](https://www.prince-webdesign.nl/tk5)

[[2] The Hercules System/370, ESA/390, and z/Architecture Emulator](http://www.hercules-390.org/)

[[3] wc3270 Terminal Emulator](http://x3270.bgp.nu/)

[[4] Introduction to the New Mainframe: z/OS Basics](https://www.redbooks.ibm.com/redbooks/pdfs/sg246366.pdf)

[[5] COBOL programming - tutorials, lectures, exercises, examples](https://www.csis.ul.ie/cobol/)

[[6] Using the function keys and command line with the ISPF control panels on z/OS](https://www.ibm.com/docs/en/ibm-mq/9.4?topic=uocpz-using-function-keys-command-line-ispf-control-panels-zos)

# Appendix
```/s shutdown``` to shutdown system from Hercules status window

```logon herc01 recon``` to reconnect to existing session

```F3``` to return to previous ISPF panel

``` Shift + Esc``` to exit wc3270 terminal emulator