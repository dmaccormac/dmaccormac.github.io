---
title: How to Log Into Windows Using Microsoft Entra ID
date: 2025-03-02
last_modified_at: 2025-03-03
tags: microsoft, windows, entra 
excerpt: User your Entra ID to log into Windows and take advantage of features like Single Sign-On, MFA, and more.
---

# Introduction

Logging into Windows using Entra ID is a straightforward process that enhances security while providing seamless access to Windows devices and services. This article will guide you through the steps needed to log into Windows using Entra ID.

---

# What is Entra ID?

Microsoft Entra ID is a cloud-based identity management service that allows organizations to manage users, devices, applications, and other resources centrally. Entra ID supports authentication for a variety of services, including Microsoft 365 and Windows, as well as third-party applications.

The key benefits of Entra ID include:

1. **Simplified Access**: By using Entra ID to log into Windows, you eliminate the need for managing separate local usernames and passwords.
2. **Enhanced Security**: With features like Multi-Factor Authentication and Conditional Access, your device login becomes significantly more secure.
3. **Streamlined Management**: IT administrators can manage device access, policies, and users centrally through the Entra ID portal.
4. **Unified Authentication**: Entra ID enables seamless access to cloud services and apps, all with one set of credentials.

---

# Prerequisites

Before you can log into Windows using Entra ID, there are a few prerequisites that need to be met:

1. Windows 10 Pro or later.
2. Administrative rights on the computer.
3. An active Entra ID.
4. An active internet connection.

---

# Join device to Entra ID

Before you can log into Windows using Entra ID, your device must be registered with your Entra ID. This can either be done during the Windows setup process or after you've set up the machine. 

Below are the steps required to join your device to Entra ID after Windows setup.

1. Click on the **Start menu**, then select **Settings**.

2. In the Settings window, select **Accounts**.
![Windows Login Entra ID Image 1](/assets/images/2025-03-02-windows-login-entra-id-1.png)

3. Under the **Accounts** section, click **Access Work or School**. 
![Windows Login Entra ID Image 2](/assets/images/2025-03-02-windows-login-entra-id-2.png)

4. If you have any work address listed here, disconnect it and restart the computer. Come back to this page, click on **Connect**.
![Windows Login Entra ID Image 3](/assets/images/2025-03-02-windows-login-entra-id-3.png)

5. Don't sign into your work email yet. Instead, click on "Join this device to Microsoft Entra ID".
![Windows Login Entra ID Image 4](/assets/images/2025-03-02-windows-login-entra-id-4.png)

6. Follow the on-screen instructions to complete the setup process.
![Windows Login Entra ID Image 5](/assets/images/2025-03-02-windows-login-entra-id-5.png)


Once your device is successfully joined to Entra ID, you are ready to use it for login purposes. 

From the Windows login screen click **Other User** and then enter your Entra ID credentials using the format ```jdoe@example.com```.

---

# Adding Entra ID to local groups

To add an Entra ID account to the local groups on a Windows machine, you can use either PowerShell or the `net` command, as shown below:

## Option 1: PowerShell
```powershell
Add-LocalGroupMember -Group "Administrators" -Member "AzureAD\JohnDoe"
```

## Option 2: Command Prompt
```bat
net localgroup Administrators AzureAD\JohnDoe /add
```

**Note**: This is the user's display name, which you can find by checking the %USERNAME% environment variable.

---

# Remote Desktop Access

If you need to access the computer using RDP; first add the Entra ID account to the **Remote Desktop Users** group, then use the following format for username in the Remote Desktop Client:

```AzureAD\jdoe@example.com```

---

# Conclusion

Logging into Windows using **Entra ID** is an efficient, secure, and scalable solution for businesses and individuals who want to centralize their identity management. By following the steps outlined in this article, you'll be able to easily log into your Windows device with your Entra ID credentials and take advantage of features like Single Sign-On, MFA, and more.


# References

[[1] What is Microsoft Entra ID?](https://learn.microsoft.com/en-us/entra/fundamentals/whatis)

[[2] How to manage the local administrators group on Microsoft Entra joined devices](https://learn.microsoft.com/en-us/entra/identity/devices/assign-local-admin#manually-elevate-a-user-on-a-device)

[[3] Adding a work account and login to a personal computer running Windows 10 Home](https://learn.microsoft.com/en-us/entra/identity/devices/assign-local-admin#manually-elevate-a-user-on-a-device)

[[4] How do I add Azure Active Directory User to Local Administrators Group](https://superuser.com/questions/982336/how-do-i-add-azure-active-directory-user-to-local-administrators-group)

[[5] Azure AD users and local admins](https://community.spiceworks.com/t/azure-ad-users-and-local-admins/733779)


