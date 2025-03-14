# Create a Docker image for a JavaFX application

Made by: [Ricardo de Sousa](https://github.com/IsNotRicardo)

## Introduction

This guide will show you how to create a Docker image for a JavaFX application. It will not, however,
show you how to create a JavaFX application. The following steps assume that you have a working JavaFX
application that you want to containerise.

## Prerequisites



## Dockerfile Configuration



## X Server Setup

In order to run a JavaFX application in a Docker container, you need to have an [X.org Server](https://en.wikipedia.org/wiki/X.Org_Server)
installed on your machine. This will allow the JavaFX application to display its GUI on your device. This
process is different for each operating system, so make sure to follow the correct guide for your OS.

### Windows

Follow the steps in the [Windows X server guide](windows-x-server.md).

### macOS

Follow the steps in the [macOS X server guide](macos-x-server.md).

## Running the Docker Container

> [!IMPORTANT]
> Make sure that you have followed all the previous steps before running the Docker container.
> Failure to do so will likely result in an error.

1. Open any terminal window (Windows Powershell, Command Prompt, Git Bash, etc.) and navigate to the directory
   where your JavaFX application is located. If you are **using IntelliJ IDEA**, you can just open the terminal
   window within the IDE in your project directory.

2. If you have not done so yet, build the Docker image by running the following command:

   ```powershell
   docker build -t <image-name>:<tag> .
   ```
   
   Replace `<image-name>` with the name you want to give to your Docker image and `<tag>` with the image version.

> [!NOTE]
> The tag is optional, although it is recommended.

3. Run the Docker container by executing the following command:

   ```powershell
   docker run -e DISPLAY=host.docker.internal:0.0 <image-name>:<tag>
   ```
   
   Replace `<image-name>` and `<tag>` with the same values you used when building the Docker image.