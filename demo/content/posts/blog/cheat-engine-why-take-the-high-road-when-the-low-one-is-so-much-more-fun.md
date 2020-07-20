---
title: Cheat Engine, Why take the high road when the low one is so much more fun?
path: /cheat-engine
tags:
  - Cyber Security
metaImage: assets/cheatengine.jpg
featuredImage: ./assets/cheatengine.jpg
excerpt: Cheat Engine is an open source tool designed primarily to help you to
  tweak stuff in a running game. This allows us to make the game harder or
  easier or get free coins etc. It’s mainly about hacking games, but we’ll see
  there’s quite a bit more to it
created: 2020-07-20T05:36:39.268Z
updated: 2020-07-20T05:36:39.336Z
---
Here’s a seemingly atypical tutorial on **[Cheat Engine](http://www.cheatengine.org/)**. It’s mainly about hacking games, but we’ll see there’s quite a bit more to it than just games. So, let’s check out the cheat engine.

## What is Cheat Engine?

Cheat Engine is an [opensource](https://github.com/cheat-engine/cheat-engine) tool designed primarily to help you to tweak stuff in a running game. This allows us to make the game harder or easier or get free coins etc. If you find that 100HP is too easy on a particular game, you can try playing a game with a maximum of 10 HP as a challenge. Cheat Engine also contains several other useful tools to help debugging and really just messing around with games and pretty much any application. For this reason, it is also an excellent tool for modders, programmers who make modifications to existing games.

Cheat Engine comes with a memory scanner to scan for variables used within a game (or again, any running task) and allows you to change them. It also comes with a debugger, disassembler, trainer maker, system inspection tools, etc. - the ultimate tool for a mischievous **gamer** or an aspiring **modder**. So let’s take a look at how Cheat Engine does its thing.



## How Does Cheat Engine Work?

Although Cheat Engine can do quite a bit more, let’s take a look at an example of “hacking” a game. Now, all applications put some stuff in memory (RAM), variables containing the data needed for their execution. In a game, for example, the player’s health, ammunition, position, etc. - are all stored in variables that have actual addresses, their location in the memory. All games make use of what’s called the game loop, an infinite loop of some function that goes on and on until the player exits/pauses the game. This is typically run at the same rate as your monitor’s frame rate, for example, 60 times a second for a 60Hz monitor. This is also the reason why your game may begin to lag if the computer isn’t fast enough to compute all those statements within time (in this case, 1/60th of a second).

Inside the game loop, the code checks to see if, for example, any user event has occurred. Did the user press the arrow keys? If so, then update their position accordingly. Did they click the left mouse button? If so, call the function to fire the gun and so on. Certain aspects of games often rely completely on a particular variable and trust it to maintain a legit value. It is these variables that Cheat Engine allows us to tweak to our hearts' content. And when the game “sees” the new value of, say your health or coins, it simply follows along, and the hack is complete.

Protecting a game from tampering from a tool like Cheat Engine would involve implementing encryption and a sealed environment of sorts (the same kind that today’s antiviruses use). This would undoubtedly affect the game’s performance ruining the gameplay. **This leaves almost all offline games vulnerable to nosy software** such as Cheat Engine. For online games such as MMORPGs like Runescape or World of Warcraft, the game’s state (all the critical variables like health or coins) are maintained at the server, so tampering with them on the client-side has no effect on the “real” values.

What Cheat Engine does is try to find out what all variables an application is using and the location at which they are stored in the RAM. Once this is known, the in-memory variables can be directly edited to have any values. For gamers, this tool is simply god sent. You can increase your speed in “Need for speed”, get infinite ammo in “Call of Duty” and avoid killing a thousand people or typing cheat codes for money in “Grand theft Auto” and much *much* more.

Stepping back for a moment, how is any of this relevant to hacking? It’s all about the journey and the experience that you gain from it. Cheat Engine teaches you how to find out exactly what the problem is and how to solve it. Cheat Engine gives you the thrill of cracking a seemingly impossible problem and teaches you how to look for an open window when the door is locked - which is pretty much what hacking is. Cheat Engine gives you a hint, a glimpse of advanced hacking procedures to which we shall get to later on.

In my experience, I’ve noticed that the biggest reason beginners giving up learning hacking is simply because it just gets a little boring. Outside of movies, that’s just the way it is. But for those willing to make the journey, **the reward is more than worth it**. Hacking depends on, more than anything else, practice because the only practice can give you the experience needed to truly hack like what you see in movies.

- - -

Now we didn’t actually get to using Cheat engine, that’s because it comes with its very own built-in tutorial. Fair warning, it could be a handful for people not familiar to programming, but certainly doable. Think you’re up for it?

* Head over to [cheatengine.org](http://www.cheatengine.org/)
* Download Cheat Engine
* Do the tutorial (if you can)
* Take your favorite game for a spin in a whole new dimension