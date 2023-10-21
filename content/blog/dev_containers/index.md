---
title: "Dev Containers"
subtitle: ""
excerpt: ""
date: 2023-06-09T17:39:39+02:00
author: ""
draft: true
series:
tags:
categories:
layout: single # single or single-sidebar
---

### Pitch

Dev containers are a useful tool that could avoid you the pain of setting up an environment for project development.
A dev container is simply a Docker container used for development purposes: Instead of running your code in a local virtual environment, you run it or debug it inside a Docker container. 


### When you need it?
If you are working on a project by yourself you might not need it.  
This tool is usually useful for big projects, where a lot of people need to put their hands on the core code, and these people may vary.  
This team might be the kind of team that changes over time, and you want to be sure that everyone within it is able to setup the project in the least amount of time as possible, in such a way they can focus on the important things.

### Why you need it?
Imagine that you are working on Project X. You are working on it with A, B, C, D, E, F.   
A and B are Linux users, C and D are Windows users, while E and F are MacOs users.  




## Installation

To get started, follow these steps:

1. Install [VS Code](https://code.visualstudio.com/) or [VS Code Insiders](https://code.visualstudio.com/insiders/) and this extension.

2. Install and configure [Docker](https://www.docker.com/get-started) for your operating system, using one of the paths below or an [alternative Docker option](https://code.visualstudio.com/remote/advancedcontainers/docker-options), like Docker on a remote host or Docker compliant CLI.

   **Windows / macOS:**

   1. Install [Docker Desktop for Mac/Windows](https://www.docker.com/products/docker-desktop).
   2. If not using WSL2 on Windows, right-click on the Docker task bar item, select **Settings / Preferences** and update **Resources > File Sharing** with any locations your source code is kept. See [tips and tricks](https://aka.ms/vscode-remote/containers/troubleshooting) for troubleshooting.
   3. To enable the [Windows WSL2 back-end](https://aka.ms/vscode-remote/containers/docker-wsl2): Right-click on the Docker taskbar item and select **Settings**. Check **Use the WSL2 based engine** and verify your distribution is enabled under **Resources > WSL Integration**.

   **Linux:**

   1. Follow the [official install instructions for Docker CE/EE](https://docs.docker.com/install/#supported-platforms). If you use Docker Compose, follow the [Docker Compose install directions](https://docs.docker.com/compose/install/).
   2. Add your user to the `docker` group by using a terminal to run: `sudo usermod -aG docker $USER` Sign out and back in again so this setting takes effect.





fas tutorial

https://youtu.be/9TM4Ry986oY





### Setup

Install dev container plugin

open dev container for project

install poetry utils at system level

create venv

activate venv

make installAllPython
