---
title: Robocopy guide with examples
date: 2025-04-06
last_modified_at: 2025-04-07
tags: robocopy windows
excerpt: Examples of using Robocopy for file and folder backup tasks.
---

# Introduction
Robocopy (Robust File Copy) [1] is a command-line utility in Windows that provides advanced file and folder copying capabilities. It is particularly useful for copying large amounts of data, mirroring directories, and performing incremental backups. Robocopy was first introduced in Windows NT 4.0 Resource Kit and has been included in Windows Vista and later versions of Windows.

Robocopy is designed to be more efficient and reliable than traditional copy commands, such as `xcopy` or `copy`, especially when dealing with network shares or large file sets. Robocopy is capable of resuming interrupted copies, preserving file attributes, and providing detailed logging options. It can also handle long file names and paths, making it a powerful tool for system administrators and users who need to manage large volumes of data.

This guide provides examples of how to use Robocopy effectively. It covers basic syntax, common options, and provides example use cases for file and folder backup tasks.


# Basic Syntax
```bash
robocopy <source> <destination> [options]
```

- `<source>`: The path to the source directory you want to copy from.
- `<destination>`: The path to the destination directory you want to copy to.
- `[options]`: Optional parameters that modify the behavior of the copy operation.
  
## Common Options
Robocopy has a wide range of options that can be used to customize the copy operation. Here are some of the most commonly used options:

| **Option** | **Description** |
| --- | --- |
| `/E`| Copies all subdirectories, including empty ones |
| `/S`| Copies subdirectories, excluding empty ones |
| `/MIR`| Mirrors a directory tree (equivalent to `/E` and `/PURGE`) |
| `/COPY:DAT`| Specifies the file attributes to copy (Data, Attributes, Timestamps) |
| `/COPYALL`| Copies all file information, including timestamps and security attributes |\
| `/DCOPY:DAT` | Specifies the directory attributes to copy (Data, Attributes, Timestamps)|
| `/MT[:n]` | Do multi-threaded copies with n threads (default 8)|
| `/R:n`| Specifies the number of retries on failed copies (default is 1 million) |
| `/W:n`| Specifies the wait time between retries in seconds (default is 30 seconds) |
| `/LOG:file`| Outputs the log to a specified file |
| `/V`| Produces verbose output, showing skipped files |
| `/NP`| No progress output (suppress percentage copied) |
| `/XD dirs`| Excludes directories matching the specified names |
| `/XF files`| Excludes files matching the specified names |


# Examples
Robocopy is a powerful tool with many options, and it can be used in various scenarios. Below are some examples of how to use Robocopy for different tasks.

## Example #1: Default copy
This is the simplest form of the Robocopy command, which copies files only from one location to another without any additional options. It uses the default parameters:

```bash
robocopy C:\Source D:\Destination
```

Even when you provide the bare minimum, Robocopy still includes several parameters by default as shown below:

|  Parameter | Description |
|-|-|
| `*.*`	| Returns all files.|
| `/DCOPY:DA`	| Returns directory data and attributes.|
| `/COPY:DAT`	| Returns data, attributes, and timestamps for files.|
| `/R:1000000`	| Retries one million times.|
| `/W:30`	| Waits 30 seconds between retries.|

## Example #2: Basic Copy
The above command is useful for copying files, but it may not be sufficient for more complex tasks. For example, if you want to copy all files and subdirectories from `C:\Source` to `D:\Destination`, you can use the `/S` option to include sub directories. You can also use the `/E` option to include empty directories:

```bash
robocopy C:\Source D:\Destination /E /DCOPY:DAT /COPY:DAT /R:3 /W:5
```

I've also added the `/R` and `/W` options to specify the number of retries and wait time between retries, respectively. This is useful for handling temporary file locks or network issues.


## Example #3: Multi threaded Copy
Robocopy supports multi-threaded copying, which can significantly speed up the process when dealing with large files or directories. By default, Robocopy uses 8 CPU threads when copying files. You can use the `/MT` parameter to specify the use of more CPU threads.

```bash
robocopy C:\Source D:\Destination /E /DCOPY:DAT /COPY:DAT /R:3 /W:5 /MT:16
```

In this example, I've set the number of threads to 16. You can adjust this number based on your system's capabilities and the size of the files being copied. Keep in mind that using too many threads may lead to performance degradation, so it's essential to find a balance that works for your specific use case.


Thea above command will monitor the source directory for 10 changes and wait 30 minutes before performing another copy pass. This is useful for keeping the destination up to date with changes in the source directory.

## Example #4: Monitoring backups
Robocopy can be used to monitor backups by using the `/MON` and/or `/MOT` options. The `n` parameter specifies the number of changes to monitor before starting a copy operation.

`/MON:n` Monitor source; run again when more than n changes seen.
`/MOT:m` Monitor source; run again when more than m minutes have passed.

```bash
robocopy C:\Source D:\Destination /E /MON:10 /MOT:30
```

The above command will monitor the source directory for 10 changes and wait 30 minutes before performing another copy pass. This is useful for keeping the destination up to date with changes in the source directory.


## Example #5: Mirror Copy
The `/MIR` option is used to create a mirror image of the source directory in the destination directory. This means that any files or directories that exist in the destination but not in the source will be deleted. This is useful for maintaining an exact copy of a directory structure.

However, be cautious when using this option, as it can lead to data loss if not used correctly. If you think you will ever need to restore a file that may have accidentally been deleted from the source, you should consider using the `/E` option instead of `/MIR`. The `/E` option will copy all files and subdirectories, including empty ones, but will not delete any files or directories in the destination.

Below is an example of using the `/MIR` option to create a mirror copy of a directory:

```bash
robocopy C:\Source D:\Destination /MIR /B /R:0 /COPYALL /DCOPY:DAT /XD '$Recycle.bin' 'System Volume Information' /XF 'thumbs.db' /MT:16 /NP /LOG:'C:\Users\Dan\Desktop\robocopy.log' 
```

In this example, I've added several options to customize the behavior of the command:

|  Parameter | Description |
|-|-|
| `/B` | Copies files in backup mode, which can help avoid access denied errors.|
| `/R:0` | Sets the number of retries to zero.|
| `/COPYALL` | Copies all file data and metadata.|
| `/DCOPY:DAT` | Copies all directory data and regular metadata.|
| `/XD` | Excludes specific directories from the copy operation.|
| `/XF` | Excludes specific files from the copy operation. |
| `/MT:16` | Sets the number of threads to 16 for multi-threaded copying.|
| `/NP` | Suppresses the progress output to help clean up the log file.|



# Conclusion
Robocopy is a powerful and flexible tool for copying files and directories in Windows. By using the various options available, you can customize the behavior of the copy operation to suit your specific needs. Whether you're performing a simple file copy or creating a complex backup solution, Robocopy can help with your data copying goals.

# References

[[1] Robocopy Documentation](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/robocopy)

[[2] Hitchhiker's Guide to Robocopy](https://www.pdq.com/blog/hitchhikers-guide-to-robocopy/)

[[3] Robocopy command for making an exact copy](https://www.reddit.com/r/sysadmin/comments/z0wzod/robocopy_command_for_making_an_exact_copy/)

[[4] 21 Robocopy Examples With Screenshots](https://activedirectorypro.com/robocopy-examples/)
    
[[5] Robocopy: The Ultimate Guide](https://www.windowscentral.com/robocopy-ultimate-guide)