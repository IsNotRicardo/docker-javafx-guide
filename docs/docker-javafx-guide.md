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

- [Through Chocolatey](#through-chocolatey), a package manager for Windows.
- [Through the Xming installer](#through-the-xming-installer).

### Through Chocolatey

1. Using the Windows search bar, search for `Windows Powershell` and run it as an administrator.

   <img src="./images/powershell-admin.png" alt="Running Windows Powershell as an administrator" width="70%"/>

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

### Through the Xming installer

1. Download the Xming installer from [sourceforge](https://sourceforge.net/projects/xming/).

2. Run the installer and follow the installation instructions. You can leave the default settings as they are
   and click `Next` until you reach the final window.

   <img src="./images/xming-install-1.png" alt="Xming initial installation window" width="50%"/>

3. Once you reach the final window, click the `Install` button to finish the installation.

    <img src="./images/xming-install-2.png" alt="Xming final installation window" width="50%"/>

## XLaunch Configuration