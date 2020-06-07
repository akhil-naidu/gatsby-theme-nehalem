---
title: Introduction to Batch File Viruses
path: /introduction-to-batch-file-viruses
tags:
  - Cyber Security
metaImage: assets/intro-to-virus.jpeg
featuredImage: ./assets/intro-to-virus.jpeg
excerpt: In the following few tutorials, we’ll be learning about batch file
  viruses. We’ll look at various techniques to bring down a computer using small
  and simple scripts. Even if you have no background in programming, you’ll find
  it very easy to follow along.
created: 2020-06-07T10:25:13.618Z
updated: 2020-06-07T10:25:13.671Z
---
In the following few tutorials, we’ll be learning about batch file viruses. We’ll look at various techniques to bring down a computer using small and simple scripts. Even if you have no background in programming, you’ll find it very easy to follow along.

I recommend you use a virtual machine running a Windows OS if you want to follow along yourself. This is **as much for safety as it is for convenience**. This tutorial is pretty safe but from the next one we’ll start building viruses. The first virus we’ll look at will overload the computer’s memory. That is, the computer will run out of RAM and likely freeze up and shut down. While this is unlikely to cause any lasting damage, using a virtual machine will still be more convenient simply because you won’t have to keep restarting your computer because it crashed. Soon after this we will get to viruses that can do some very real and permanent damage to your system. You don’t want to hack yourself, right? So you might as well[l earn how to setup a virtual machine for hacking practice before continuing](https://blog.leewardslope.com/setting-up-a-virtual-machine-to-practice-hacking).

Now let us begin.

## What are batch files?

A **batch file**is the name given to a type of script file, a text file containing a series of commands to be executed by the command interpreter. Batch files have the extension `.bat` (or`.cmd`). They can be easily created using any text editor such as notepad.

Now let’s see some of these commands.

```powershell
echo Hello World
```

The `echo` command is used to print out a message, in this case “Hello World”. Type up the above in a text editor and save it as`something.bat`. Now open it and a command window pops up. But you’ll notice that it closes before we get a chance to see what it outputs. Let’s fix that.

```powershell
echo Hello World
pause
```

The`pause`command pauses the execution of the batch file until a user presses a key. You should now see the following output:

```powershell
C:\Users\Akhil\Desktop>echo Hello World
Hello World
C:\Users\Akhil\Desktop>pause
Press any key to continue . . .
```

`C:\Users\Akhil\Desktop>` is where the execution is happening. In my case, I’ve saved the batch file on the desktop. The batch file seems to be printing the commands before executing them. It first prints `echo Hello World` then actually executes it to output `Hello World`. Let’s see if we can clean this up a bit.

```powershell
@echo off
echo Hello World
pause
```

And this outputs…

```powershell
Hello World
Press any key to continue . . .
```

Much better.`@echo off` is used to stop the commands from being printed and leaves only the output of those commands. Now let’s add a little dynamic behavior.

```powershell
@echo off
set a=Akhil
echo Hello %a%
pause
```

The`set`command is used to define **variables** that can hold different values, in this case the string “Akhil”. The variable name enclosed within `%%` is how we access the value stored in the variable. Run the above and you should see

```powershell
Hello Xeus
Press any key to continue . . .
```

Be careful here, the set command is pretty sensitive about the use of spaces:

* `set a=Akhil` means`a`has the value ‘Akhil’
* `set a= Akhil` (with a space after the`=`) means ‘a’ has the value ‘ Akhil’ (with a space before it) and
* `set a =Akhil` with a space before`=`) means that the variable is not defined as`a`but as`a`(‘a’ followed by a space).

Some commands come with modifiers that slightly alter their behavior:

```powershell
@echo off
set /a a=5
set /a b=10
set /a c=%a% + %b%
echo %c%
pause
```

In `set /a`, the`/a`part is telling `set` that it should treat the value of the variable as a number, allowing us to perform mathematical operations on it.

```powershell
@echo off
set /p a=Enter your name: 
echo Hello %a%
pause
```

The `/p` modifier tells the `set` command that it should take in some input from the user and store that in the variable `a`. When you run the batch file, you will be prompted to enter something. The output looks like:

```powershell
Enter your name: Emily
Hello Emily
Press any key to continue . . .
```

## Examples of Batch Files

That was pretty easy, now let’s take a look at a couple more batch files that might actually be useful and then we’ll go and make some viruses.

### Pinger

```powershell
@echo off
title Pinger
set /p target=Enter IP address or URL: 
ping %target% -t
pause
```

This outputs:

```powershell
Enter IP address or URL: google.com
Pinging google.com [216.58.220.206] with 32 bytes of data:
Reply from 216.58.220.206: bytes=32 time=26ms TTL=57
Reply from 216.58.220.206: bytes=32 time=25ms TTL=57
Reply from 216.58.220.206: bytes=32 time=27ms TTL=57
Reply from 216.58.220.206: bytes=32 time=25ms TTL=57
Reply from 216.58.220.206: bytes=32 time=26ms TTL=57
```

Pretty handy if you want to quickly ping an IP address/URL or check your internet connection.

*P.S: Pressing CTRL+C forcefully stops any running command (like `ping -t` which likes to run forever).*

### Shutdown timer

The batch file schedules a shutdown after X minutes.

```powershell
@echo off
title Shutdown Input
set /p mins=Enter number of minutes to wait until shutdown:
set /a mins=%mins%*60
shutdown -s -t %mins%
```

- - -

This was but a glimpse of what batch files can do. Almost anything your operating system does for you can be done through batch files. You can even use them to automate repetitive and boring tasks. The limit is only your imagination.

One of these imaginative uses is creating batch file viruses and that is just what we’re going to learn now. Let’s start with the famous [fork bomb](https://blog.leewardslope.com/fork-bomb).