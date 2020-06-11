---
title: Application Flooder, Annoy the hell out of your victims
path: /application-flooder
tags:
  - Cyber Security
metaImage: assets/application-flooder.jpg
featuredImage: ./assets/application-flooder.jpg
excerpt: Application Flooder is one of the most simplest and oldest viruses out
  there and unlike the fork bomb we just saw, the “Application flooder” although
  technically harmless, is a really annoying virus.
created: 2020-06-11T13:08:47.709Z
updated: 2020-06-11T13:08:47.793Z
---
Not unlike the [fork bomb](https://blog.leewardslope.com/fork-bomb) we just saw, the “Application flooder” although technically harmless, is a really annoying virus. Here’s how it looks:

```powershell
@echo off
:begin
start mspaint
start notepad
start write
start cmd
start explorer
start control
start calc
goto begin
```

Like all the other batch file virus tutorials, I recommend trying this one out [in a virtual machine](https://blog.leewardslope.com/setting-up-a-virtual-machine-to-practice-hacking).

Let’s go through it line by line:

* `@echo off`- This simply stops the command prompts from appearing when the batch file is executing. When you start a batch file, a command prompt process (cmd.exe) is opened and that batch file’s instructions are piped through. We use`@echo off`when we don’t want to notify the user about what the running batch file is doing.
* `:begin`- This is a label. It’s like a marker or a checkpoint, a position in the program that we’ve given a name to.
* `start`- This is used to start an executable, similar to what happens when you double click an application. You can see that we have a bunch of these commands and they’re all starting something different. These are just a handful of the default programs that come with all installations of windows. This is where we’re*flooding applications*. Specifically we’re starting up the applications: Paint, Notepad, WordPad, a command window, file explorer, control panel and a calculator. You can start up any executable (.exe) by using `start <PATH-TO-EXECUTABLE>`.
* `goto`- Remember the label we just defined above? (`:begin`) Using the goto command, we*go to*the label ‘begin’, and the program continues execution from there. This is an infinite loop. So all the above applications are started again and again until there are hundreds of open windows or until the operating system crashes or a good antivirus intervenes.

- - -

So there you have it. This is one of the most simplest and oldest viruses out there. But the story isn’t over yet. The viruses that actually infect and harm the systems in this day and age are vastly more complicated However, you are now one step closer to a better understanding of the big picture. Head over to the [next virus](https://blog.leewardslope.com/overloading-memory) to continue.