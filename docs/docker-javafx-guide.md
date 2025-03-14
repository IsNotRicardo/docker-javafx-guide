# Create a Docker image for a JavaFX application

Made by: [Ricardo de Sousa](https://github.com/IsNotRicardo)

> [!IMPORTANT]  
> This guide is exclusive for Windows devices.

## Introduction

This guide will show you how to create a Docker image for a JavaFX application. It will not, however,
show you how to create a JavaFX application. The following steps assume that you have a working JavaFX
application that you want to containerise.

## Prerequisites



## Dockerfile



## Xming Installation

In order to run a JavaFX application in a Docker container, you need to have an X server installed on
your machine. This will allow the JavaFX application to display its GUI on your device. In this guide,
we will use Xming as our X server. You can install Xming by:

- [Using Chocolatey](#using-chocolatey), a package manager for Windows.
- [Using the Xming installer](#using-the-xming-installer).

### Using Chocolatey

1. Using the Windows search bar, search for `Windows Powershell` and run it as an administrator.

2. Check if you have Chocolatey installed by running the following command:

   ```powershell
   choco -v
   ```

   If you have Chocolatey installed, you can skip to the next step.

   Otherwise, you can install it by running the following command:

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
   ```
   
   > [!NOTE]
   > This command comes from Chocolatey's [installation guide](https://chocolatey.org/install).
   
3. Install Xming by running the following command:

   ```powershell
   choco install xming
   ```

   This command will install Xming on your machine.

### Using the Xming installer

1. Download the Xming installer from [sourceforge](https://sourceforge.net/projects/xming/).



## XLaunch Configuration