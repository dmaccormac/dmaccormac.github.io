---
title: Getting Started with Azure CLI
date: 2025-09-14
last_modified_at: 2025-09-14
tags: microsoft azure cli cloud
excerpt: Azure CLI is a cross-platform command-line tool for managing Azure resources.
---


# Introduction

Here's a quick how-to guide for using Azure CLI, based on Microsoft's official documentation
[[1 - 3]](#references).

Azure CLI is a cross-platform command-line tool for managing Azure resources. You can run it:
- Locally (Windows, macOS, Linux)
- In a Docker container
- In the browser via **Azure Cloud Shell** (no installation required)

---

# Installation

Choose your platform:

## [Windows](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?view=azure-cli-latest)
```bash
winget install --exact --id Microsoft.AzureCLI
```

## [macOS](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-macos?view=azure-cli-latest)
```bash
brew update && brew install azure-cli
```

## [Linux](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?view=azure-cli-latest)
```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

## [Docker](https://learn.microsoft.com/en-us/cli/azure/run-azure-cli-docker?view=azure-cli-latest)
```bash
docker run -it mcr.microsoft.com/azure-cli:azurelinux3.0
```

Or use [Azure Cloud Shell](https://azure.microsoft.com/en-us/get-started/azure-portal/cloud-shell/) directly in your browser.

---

# Authentication

To sign in:
```bash
az login
```

When you use `az login` interactively, it opens a browser window and requires multi-factor authentication (MFA). This is fine for manual use, but not suitable for automation (CI/CD pipelines, scripts, etc) because MFA requires human interaction and it's not secure to store credentials in scripts. 

If you're using automation, consider switching to **service principals** or **managed identities**, especially with upcoming MFA requirements.

---

# Managing Subscriptions

To view your current subscription:
```bash
az account show --output table
```

To switch subscriptions:
```bash
az account set --subscription "MySubscriptionName"
```

---

# Finding Commands

Use:
```bash
az find "vm"
```
Or:
```bash
az vm --help
```
To explore subgroups and parameters.

---

# Interactive Mode

Launch with:
```bash
az interactive
```
This mode provides inline help, autocomplete, and command suggestions.

---

# Examples

## Create a VM
```bash
az vm create -g MyResourceGroup -n MyVm --image UbuntuLTS
```

## List storage accounts
```bash
az storage account list --output table
```

## Set default location and resource group
```bash
az config set defaults.location=westus2 defaults.group=MyResourceGroup
```

---

# References 
[[1] Get started with Azure CLI](https://learn.microsoft.com/en-us/cli/azure/get-started-with-azure-cli?view=azure-cli-latest)

[[2] Azure Command-Line Interface (CLI) documentation](https://learn.microsoft.com/en-us/cli/azure/?view=azure-cli-latest)

[[3] Azure CLI onboarding cheat sheet](https://learn.microsoft.com/en-us/cli/azure/cheat-sheet-onboarding?view=azure-cli-latest)

