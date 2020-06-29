---
title: How to install Virtualbox in ChromeOS
path: /how-to-install-virtualbox-in-chromeos
tags:
  - General
metaImage: assets/vbox.png
featuredImage: ./assets/vbox.png
excerpt: In this guide, I assume you are familiar with @sebac brunch, Crouton,
  Chroot, and obviously Virtualbox. If you are not familiar with anyone of these
  first go through the following links and get a brief idea for conceptual
  clearance in your head.
created: 2020-06-29T05:05:31.694Z
updated: 2020-06-29T05:05:31.739Z
---
In this guide, I assume you are familiar with @sebanc  [brunch](https://github.com/sebanc/brunch), [Crouton](https://github.com/dnschneid/crouton), [Chroot](https://www.youtube.com/watch?v=2wSJREC7RV8), and obviously [Virtualbox](https://www.virtualbox.org/). If you are not familiar with anyone of these first go through the following links and get a brief idea for conceptual clearance in your head. 

These are the steps we cover in this Guide.

* Install ChromeOS in your PC
* Installing a Chroot based Ubuntu Instance
* **Setting up the Environment in Ubuntu**
* Installing Virtual Box

### Installing ChromeOS in your PC

I guess you are familiar with the Brunch of this master branch, with which you can use Install the ChromeOS in any PC - provided your PC meets the [hardware requirements](https://github.com/sebanc/brunch#hardware-support-and-added-features). 

> Any quires in this section, you are free to browse through the existing issues or to open a new issue.

### Installing a Chroot based Ubuntu Instance

Follow these instructions, in case of any errors stop it - do some research or comment it below.

1. Download crouton
2. Open a shell (Ctrl+Alt+T, type `shell`, and hit enter)
3. Copy the installer to an executable location by running `sudo install -Dt /usr/local/bin -m 755 ~/Downloads/crouton`
4. Now that it's executable, run the installer itself: `sudo crouton -r xenial -t xfce`
5. Wait patiently and answer the prompts like a good person. At the end of the installation, you need to provide username and password for the Ubuntu installation.
6. Done! You can jump straight to your Xfce session by running `sudo enter-chroot startxfce4` or, as a special shortcut, `sudo startxfce4`
7. Cycle through Chromium OS and your running graphical chroots using **Ctrl+Alt+Shift+Back(F1)** and **Ctrl+Alt+Shift+Forward(F2)**.
8. Exit the chroot by logging out of Xfce.

Step 6,7,8 are optional steps, which will provide you an idea about the usage of [crouton](https://github.com/dnschneid/crouton)

### Setting up the Environment in Ubuntu

After successful completion of Step 5, you can launch the Ubuntu using Xfce using Step 6 or you can use this command: `sudo enter-chroot` to access the Ubuntu terminal. It's up to you how you want to access the Ubuntu terminal.

In the **ubuntu terminal**, use this command before installing anything. `sudo mount -o remount,rw /lib/modules/*`

### Installing Virtual Box

The above step, which focuses on setting up of environment is a must. The command: `sudo mount -o remount,rw /lib/modules/*` should be executed without any error. **If you have no error proceed further**.

> **crostini** needs to be disabled in ChromeOS settings

1. `sudo apt install virtualbox` to install VirtualBox
2. Before using VirtualBox, run `sudo modprobe vboxdrv`

We are all set, now you have a working VirtualBox in ChromeOS, If you have any suggestion or issue feel free to comment.

- - -

New updates: None for now

- - -

If you are in search of a **detailed guide on how to install ChromeOS on any PC**, let me know it through the comment section.