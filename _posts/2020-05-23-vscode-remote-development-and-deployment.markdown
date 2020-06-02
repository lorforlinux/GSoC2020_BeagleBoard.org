---
layout: post
title:  vscode (Visual Studio Code) for Remote C/C++ Development and Deployment (Fedora Linux)
---

In this post I have listed all the programs and commands I used to develop C/C++ programs, compile them using `arm-linux-gnueabihf-gcc/g++` and then deploy them on my BeagleBone. Debugging is not discussed in this post, If I find a way to perform that I will share it with you guys.

<span style="color:red"> Node: I am using Fedora Linux here, the commands/programs shown below might have different name/location for your distribution.</span>

## Developmement

### 1. Install the required software

1. Download and install the [Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux). Now, install the [Remote - SSH]([Remote - SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)) Extention by pressing `ctrl+shift+x` OR by choosing Extentions from Side Bar and searching for the extention.
2. Install [fedy](https://www.tecmint.com/fedy-install-third-party-software-in-fedora/) on your fedora machine. Under development tools you'll find option for `arm-linux-gnueabihf-toolchain` hit install for that. If you are using diffrent distro find and install the same.
3. Install development tools on your Fedora by running  `sudo dnf groupinstall "Development Tools"`. This will install tools like make, gcc, etc. If you have all the development tools already installed separately you can skip this.
4. Install other missing tools if prompted...

### 2. Compiling your C/C++ code

1. Open up your source directory in vscode.
2. Create a new C/C++ "Hello World" program.
3. Open up a new terminal using ``ctrl + ` ``.
4. Now compile your program for BeagleBone using either,
   - `arm-linux-gnueabihf-g++ HelloWorld.cpp`
   - `arm-linux-gnueabihf-gcc HelloWorld.c`.

### 3. Using vscode Remote - SSH

1. Click on `Remote Explorer` Button on vscode Side Bar.
2. Click on `+` button to Add New connection.
3. Enter `ssh debian@192.168.7.2 -A`
4. choose ssh configuration, Both `/home/yourname/.ssh/config` and `/etc/ssh/ssh_config` worked just fine for me.
5. Enter password for you BeagleBone, default is `temppwd`.
6. By Using the Explorer from the Side Bar you can open BeagleBone folders and files.
7. For using Termainl press ``ctrl + ` ``.

## Deployment
Deployment is very easy, you just have to drag the executable binary you just created by comiling your source and drop it into your desired directory on BeagleBone. Now you you have to make it executable on your BeagleBone by running `chmod +x a.out` (replace `a.out` with your binary name).
