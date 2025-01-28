---
title: How to improve C++ application portability
date: 2025-01-27
last_modified_at: 2025-01-27
tags: c++ programming portability 
excerpt: Practical steps to support application portability across Windows versions
---

# Introduction
Application portability is an important consideration for software developers. Ensuring that an application is compiled with all its required dependencies and is capable of running seamlessly on all versions of Windows offers significant advantages. First and foremost, it simplifies the deployment process by eliminating the need for additional software installations or dependency management. This leads to a more streamlined and user-friendly experience, particularly for those who may not have technical expertise. 

Furthermore, it enhances the application's compatibility and reliability across diverse Windows environments, reducing potential runtime errors and support issues. Ultimately, this approach can save time and resources for both developers and end-users, creating a more efficient and accessible software ecosystem.

In this article, we will explore practical steps to improve the portability of Windows C++ applications in Visual Studio. 

# Include dependencies
Embedding required resources within your project and extracting them at runtime is a powerful technique for ensuring your application has everything it needs to run smoothly, regardless of the environment. This approach involves integrating essential files—such as configuration files, images, or other assets—directly into your application's binary during the build process. At runtime, your application can then extract these resources to the appropriate locations on the user's system.

## Add resources

1.	Open Solution Explorer
2.	Add a New Resource:
    - Right-click on your project and select Add > Resource....
3.	Click Import button:
    - In the Open File dialog, select `All files (*.*)` filter 
4.	Import the File:
    - Navigate to the location of resource file that you want to add, select it, and click Open.
5.	Define the Resource Type:
    - In the Custom Resource Type dialog, enter a type name (e.g., RCDATA for binary data) and click OK.
6.	Assign a Resource ID:
    - Visual Studio will automatically assign a resource ID (e.g., IDR_FOO). You can change it if needed.
7.	Update Resource Header:
    - Ensure that the resource ID is defined in your `resource.h` file. For example:

Visual Studio should auto generate your `resource.rc` and `resource.h` files. 

Example `resource.rc` file:

```cpp
#include "resource.h"
IDR_FOO RCDATA "foo.exe"
```

Example `resource.h` file:

```cpp
#define IDR_FOO 101
```


## Extract resources

1.	Find the Resource:
	- FindResource locates the resource with the specified ID (resourceId) and type (RT_RCDATA).
	- If the resource is not found, the function returns false.
2.	Load the Resource:
    -	LoadResource loads the specified resource into memory.
    -	If the resource cannot be loaded, the function returns false.
3.	Lock the Resource:
    - LockResource locks the resource in memory, returning a pointer to the resource data.
    - SizeofResource retrieves the size of the resource.
    - If the resource cannot be locked or its size is zero, the function returns false.
4.	Write the Resource to a File:
    - An std::ofstream is used to write the resource data to the specified output file (outputPath).
    - The resource data is written in binary mode.
    - The file is then closed.
5.	Return Success:
    - If all steps are successful, the function returns true.

The complete code for the `extractResource` function is shown below.

```cpp
bool extractResource(int resourceId, const std::string& outputPath) {
    HRSRC hResource = FindResource(NULL, MAKEINTRESOURCE(resourceId), RT_RCDATA);
    if (!hResource) return false;

    HGLOBAL hLoadedResource = LoadResource(NULL, hResource);
    if (!hLoadedResource) return false;

    LPVOID pLockedResource = LockResource(hLoadedResource);
    DWORD dwResourceSize = SizeofResource(NULL, hResource);
    if (!pLockedResource || dwResourceSize == 0) return false;

    std::ofstream outputFile(outputPath, std::ios::binary);
    outputFile.write(reinterpret_cast<const char*>(pLockedResource), dwResourceSize);
    outputFile.close();

    return true;
}
```

You can call the `extractResource` function as follows:

```cpp
   std::string outFile = myPath + "foo.exe";
   if (!extractResource(IDR_FOO, outFile)) {
       std::cerr << "Failed to extract foo" << std::endl;
       return 1;
   }
```

# Statically link runtime libraries
Statically linking run time libraries minimizes reliance on external installations. To make your application truly portable, you can statically link the C++ runtime library so that the required DLLs are included in your executable.

For example, a common error `msvcp140.dll was not found` indicates that the Microsoft Visual C++ Redistributable is not installed on the target machine.

Here are the steps to statically link the C++ runtime library in Visual Studio 2022:

1.	Open your project in Visual Studio 2022.
2.	Open the project properties:
	- Right-click on your project in the Solution Explorer and select "Properties".
3.	Change the runtime library to static:
    - In the "Configuration Properties" section, expand "C/C++" and select "Code Generation".
    - Change the "Runtime Library" option to "Multi-threaded (/MT)" for Release configuration and "Multi-threaded Debug (/MTd)" for Debug configuration.
  
After following these steps, your application should no longer depend on external runtime DLLs, making it more portable. You can then distribute the resulting executable without worrying about missing dependencies on the target machine.

# Best coding practices 
Below is a short list of suggested best practices to consider when building applications with a focus on portability. 

## Static Linking
Whenever possible, use static linking to include all necessary libraries and dependencies within your executable. This minimizes reliance on external installations.

## Avoid Platform-Specific Code
Write code that adheres to standard C++ practices and avoids using platform-specific features unless absolutely necessary. If platform-specific code is unavoidable, use conditional compilation to handle different environments.

## Runtime Checks
Implement runtime checks to determine the operating system version and adapt the application's behavior accordingly. This ensures compatibility with various Windows versions.

## Keep Dependencies Updated
Regularly update all third-party libraries and dependencies to their latest versions to benefit from improved portability and security fixes.

## Modular Design
Structure your codebase using a modular design approach, making it easier to isolate and manage specific components.

## Comprehensive Testing
Test your application on multiple Windows versions and configurations to identify and resolve compatibility issues before deployment.

## Use Environment Variables
Utilize environment variables for configuration settings, allowing the application to adjust its behavior based on the runtime environment without requiring hard-coded paths.

## Clear Documentation
Provide clear documentation for your application, specifying any system requirements and detailed instructions for deployment on different Windows versions.

# Conclusion
In conclusion, mastering application portability techniques is crucial for ensuring seamless operation across different Windows versions. By embedding necessary resources and including runtime libraries within the application, developers can create self-contained executables that minimize dependency issues and simplify the deployment process. This approach not only enhances user experience by reducing compatibility problems but also streamlines maintenance and updates, ultimately fostering a more efficient and robust software ecosystem. Embracing these practices helps developers deliver reliable and versatile applications that can adapt to the diverse Windows environment.

# References
[[1] RCDATA resource - Microsoft Learn](https://learn.microsoft.com/en-us/windows/win32/menurc/rcdata-resource)

[[2] Understanding the Dependencies of a Visual C++ Application](https://learn.microsoft.com/en-us/cpp/windows/understanding-the-dependencies-of-a-visual-cpp-application?view=msvc-170)

[[3] C runtime (CRT) and C++ standard library (STL) .lib files](https://learn.microsoft.com/en-us/cpp/c-runtime-library/crt-library-features?view=msvc-170)

[[4] Embedding (and Extracting) Binary Files like DLLs into an EXE as Resources](https://giodicanio.com/2024/03/25/embedding-and-extracting-binary-files-like-dlls-into-an-exe-as-resources/)

[[5] Building Portable C++ Executables](https://mandeepsingh.hashnode.dev/building-portable-c-executables-creating-standalone-exe-files-for-all-systems)