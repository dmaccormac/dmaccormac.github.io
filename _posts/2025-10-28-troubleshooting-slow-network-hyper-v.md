---
title: Troubleshooting Slow Network Performance in Hyper-V
date: 2025-10-28
last_modified_at: 2025-10-28
tags: hyper-v, networking, virtualization
excerpt: Wi-Fi + External Virtual Switch = Trouble
---


# **Introduction**

I recently setup a Hyper-V virtual machine and created a new external virtual switch in the process. After creating the new virtual switch, I started to run into frustratingly slow network speeds on the host machine. Digging into the issue, I found that the problem is related to using Wi-Fi to bridge the connection between the guest and the host.

## **The Problem: Wi-Fi + External Virtual Switch = Trouble**

The issue was dicussed here on Reddit [[1]](#references): when configuring an **external virtual switch** in Hyper-V using a **Wi-Fi adapter**, both the host and guest machines experience severe network degradation. This setup works well with Ethernet, but Wi-Fi introduces complications.

Hyper-V creates a network bridge between the host and the virtual machines. This bridge allows both the host and guest systems to access the same physical network interface

## **Why It Happens**

The root of the issue lies in how Hyper-V handles network traffic. Hyper-V relies on **promiscuous mode** to detect and manage MAC addresses from virtual machines. Unfortunately, most Wi-Fi adapters **do not support promiscuous mode**, making them unsuitable for bridged networking in Hyper-V.

This limitation causes the virtual switch to struggle with routing traffic correctly, resulting in slow speeds or dropped connections.

## **Solutions and Workarounds**

From my research on this issue so far, I was able to find a few workable solutions.  

### 1. **Use the Default NAT Switch**
Instead of creating an external switch, use Hyper-V’s built-in **NAT switch**. It’s designed to work seamlessly with Wi-Fi and avoids the limitations of promiscuous mode. While NAT doesn’t allow inbound connections from the host to the VM by default, it’s generally sufficient for most internet access needs.

**Note** Even after removing the External Switch in Hyper-V, I still had to remove the **bridge adapter** created by Hyper-V in **Network connections** to restore normal network speeds.

### 2. Wi-Fi Settings
A user on this thread [[1]](#references) reported that they found a solution by by adjusting settings on the Wi-Fi adapter as follows:

#### Slow download
Disable packet coalescing on the Wi-Fi card settings in device manager

![Disable packet coalescing screenshot](/assets/images/2025-10-28-troubleshooting-slow-network-hyper-v-1.png)

#### Slow upload 
Disable large send offload (for IPV4 and IPV6) from the external vethernet switch that is bridged (not the default vethernet switch). 

![Disable large send offload screenshot](/assets/images/2025-10-28-troubleshooting-slow-network-hyper-v-2.png)

### 3. **Share the Host Network Differently**
Some users have had success by **sharing the host’s internet connection** with the VM through Windows Internet Connection Sharing (ICS), rather than relying on Hyper-V’s external switch. 

### 4. **Use Ethernet for Bridging**
If you need full bridged networking with reliable performance, **use a wired Ethernet connection**. Ethernet adapters support promiscuous mode, making them suitable for external virtual switches in Hyper-V.


## **Conclusion**

The external virtual switch setup relies on hardware capabilities that most Wi-Fi adapters don’t support. As a result, network performance is severely degraded when attempting to bridge Wi-Fi connections via Hyper-V. However, there are a few workarounds for the issue including Wi-Fi connection settings and ICS.  



# References
[[1]Slow network when sharing Wi-Fi with virtual switch](https://www.reddit.com/r/HyperV/comments/tyyyun/slow_network_when_sharing_wifi_with_virtual_switch/)

[[2] https://www.tenforums.com/virtualization/183576-very-slow-up-download-speeds-hyperv-external-switch-setup.html](https://www.tenforums.com/virtualization/183576-very-slow-up-download-speeds-hyperv-external-switch-setup.html)

[[3] Creating an external virtual switch on Hyper-V causes host to experience very slow networking](https://superuser.com/questions/1371759/creating-an-external-virtual-switch-on-hyper-v-causes-host-to-experience-very-sl)