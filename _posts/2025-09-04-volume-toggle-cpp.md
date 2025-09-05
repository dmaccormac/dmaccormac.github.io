---
title: How to toggle Windows system volume mute using C++ 
date: 2025-09-04
last_modified_at: 2025-09-04
excerpt: In this post, we create a small console application in C++ which toggles the Windows system volume on and off when executed. 
tags: 
    - c++
    - windows core audio
---

# Introduction
I like to have an easy method to toggle the system volume on and off when using a keyboard that doesn't have media control buttons. To achieve this, I found that you can use the Windows Core Audio APIs [[1]](#references). 

In this post, we will create a small console application in C++ which toggles the Windows system volume on and off when executed. As an example usage; I setup keyboard shortcuts in PowerToys [[2]](#references) to control volume.


# Creating the toggleMute() function
To toggle the system volume on and off we can use`IMMDeviceEnumerator` and `IAudioEndpointVolume` COM interfaces within the Windows Core Audio API.

Here is how we can implement the function in C++:

## Initialize function variables:

```cpp
   HRESULT hr;
   bool result = false;
```

## Initialize COM:

Initialize the COM library with CoInitialize(NULL), which is required for using COM interfaces.

```cpp
   hr = CoInitialize(NULL);
   if (FAILED(hr)) {
       return false;
   }

   IMMDeviceEnumerator* pEnumerator = nullptr;
   IMMDevice* pDevice = nullptr;
   IAudioEndpointVolume* pEndpointVolume = nullptr;
```

## Device Enumerator:

Create instance of IMMDeviceEnumerator using CoCreateInstance. This object is used to find audio devices.

```cpp
   hr = CoCreateInstance(__uuidof(MMDeviceEnumerator), NULL, CLSCTX_ALL,
                         __uuidof(IMMDeviceEnumerator), (void**)&pEnumerator);
   if (FAILED(hr)) {
       CoUninitialize();
       return false;
   }
```

## Get Default Audio Endpoint:

Retrieve the default audio playback device with GetDefaultAudioEndpoint.

```cpp
   hr = pEnumerator->GetDefaultAudioEndpoint(eRender, eConsole, &pDevice);
   if (FAILED(hr)) {
       pEnumerator->Release();
       CoUninitialize();
       return false;
   }
```

## Get Volume Control Interface:

Activate the IAudioEndpointVolume interface for the device, which allows control over the volume and mute state.

```cpp
   hr = pDevice->Activate(__uuidof(IAudioEndpointVolume), CLSCTX_ALL, NULL, (void**)&pEndpointVolume);
   if (FAILED(hr)) {
       pDevice->Release();
       pEnumerator->Release();
       CoUninitialize();
       return false;
   }
```

## Get Current Mute State:

Query the current mute state using GetMute.

```cpp
   BOOL bMute = FALSE;
   hr = pEndpointVolume->GetMute(&bMute);
   if (FAILED(hr)) {
       pEndpointVolume->Release();
       pDevice->Release();
       pEnumerator->Release();
       CoUninitialize();
       return false;
   }
```

## Toggle Mute:

Set the mute state to the opposite of the current state using SetMute(!bMute, NULL).

```cpp
   hr = pEndpointVolume->SetMute(!bMute, NULL);
   if (SUCCEEDED(hr)) {
       result = true;
   }
```

## Cleanup:

Release all COM objects and uninitialize COM with CoUninitialize().

```cpp
   pEndpointVolume->Release();
   pDevice->Release();
   pEnumerator->Release();
   CoUninitialize();
```

## Return Result:

Return true if the mute toggle was successful, otherwise false.

```cpp
   return result;
```


# Building the release executable
Here are some notes on building the release executable in Visual Studio.

##  Required libraries
The code uses Windows system libraries `Ole32.lib` and `Uuid.lib`. 

- Ole32.lib:
Provides implementations for COM functions such as CoInitialize, CoCreateInstance, and CoUninitialize. These are essential for COM initialization and object creation in the toggleMute() function.

- Uuid.lib:
Contains definitions for GUIDs (Globally Unique Identifiers) like __uuidof(MMDeviceEnumerator) and __uuidof(IMMDeviceEnumerator). These are used to identify COM interfaces and classes.

These are part of Windows, so no extra DLLs are needed for them.

### How to link in Visual Studio:

Visual Studio should link these libraries automatically, but here are the steps to do it manually if needed:

1.	Right-click the project in Solution Explorer and select Properties.
2.	Go to Configuration Properties > Linker > Input.
3.	Add `Ole32.lib; Uuid.lib;` to the Additional Dependencies field.

This ensures linking of the required libaries that interact with Windows COM and audio endpoint APIs.


## Using Static Runtime
Using a static runtime means your application includes the C++ runtime libraries directly in the executable, rather than relying on them being installed on the target system. 

1. In Project Properties > C/C++ > Code Generation > Runtime Library
2. Select a static option (e.g., /MT or /MTd) 

This avoids requiring the Visual C++ Redistributable on the target machine. If you use /MD, the target machine must have the correct redistributable installed.

# Summary
Windows Core Audio API offers a convenient way to access audio controls from C++. Using a static runtime when building the release ensures that we can redistribute the executable file to wide range of target computers. The result is a small, lightweight application that can be linked to various triggers (e.g a keyboard shorcut) to quickly toggle system volume on and off. 

The complete project code and release executables can be found on the GitHub repo [here](https://github.com/dmaccormac/volctl).

# References

[[1] About the Windows Core Audio APIs](https://learn.microsoft.com/en-us/windows/win32/coreaudio/about-the-windows-core-audio-apis?redirectedfrom=MSDN)

[[2] Microsoft PowerToys](https://docs.microsoft.com/en-us/windows/powertoys/) 