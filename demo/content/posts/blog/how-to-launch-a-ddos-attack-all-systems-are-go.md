---
title: How To Launch a DDoS Attack, All systems are go
path: /launching-ddos-attack
tags:
  - Cyber Security
metaImage: assets/launchingddos.jpeg
featuredImage: ./assets/launchingddos.jpeg
excerpt: Now that we’ve got a good understanding on the what DDoS is, let’s take
  a look at how it’s practically done. Although I won’t get into the technical
  details, here is an example of a fairly popular DOS tool - HULK
created: 2020-07-27T08:43:00.847Z
updated: 2020-07-27T08:43:00.917Z
---
Now that we’ve got a good understanding of [what DDoS is](https://blog.leewardslope.com/introduction-to-ddos), let’s take a look at how it’s practically done.

Most servers are built to handle a fairly large bandwidth and even the smaller ones can give maximum speeds to several hundreds of clients. Keeping this in mind, it is very difficult and for the most part impossible to actually bring down a website using DOS from a single computer. Where your internet speed might be 1Mbps, your target server might have several 100Mbps. This is the reason that most DOS attacks are actually DDOS, which is Distributed-Denial of Service.

DDOS attacks can easily bring down the majority of websites. In DDOS, Botnets are used which are just a bunch of compromised systems that have been infected with a virus or trojan. A simple trojan can be sent out as a public download, and if the unsuspecting victims download it the trojan may silently settle down somewhere deep in the system and startup in the background without the user or the system ever knowing. When enough systems have been compromised in this way the master of the Botnet, the hacker who wants to DDOS a website may send out a message to the dormant trojans on several systems around the world, which may then individually begin attacking a server. This can be very harmful to the website, which due to lack of resources, may shut down for a long time and even get corrupted due to overloading. Further, since the requests for transactions are coming from seemingly random IP addresses all at once(the botnet), the victim may never find out the identity of the mastermind.

Although I won’t get into the technical details, here is an example of a fairly **popular DOS tool - HULK**. Hulk is just a simple python script that continuously sends out large packets from randomly generated IDs so as to fool the server. Again, using it from just one computer may not actually do anything to any big websites, but it may be able to bring down a small website, for example, your school’s website in about a minute.

**To perform this attack you need two things:**

1. The python Engine (v2.x) - To run and compile the hulk script. You can get it here: http://www.python.org/getit/

NOTE: Download the 2nd version only (for example the current one is 2.7.13), this script does not work with the 3.x version of python.

2. Hulk.py script - This will run like a normal cmd.exe window. It’s a small zip file, Get it here :

For technical details, The official website is: http://www.sectorix.com/2012/05/17/hulk-web-server-dos-tool/

When all is done, you should have python installed, and hulk.py file extracted. It would be easier if you installed Python to a root directory, for example: C:\PYTHON27.

Also, put the hulk.py file which you just extracted in the same root directory alongside the PYTHON27 folder(In my case, I put the hulk.py file in the C:\ directory). Again, both the python folder and the hulk.py file are now in the C:\ ). With all that done, let’s launch our DOS attack!

1. Open Run, type cmd to start cmd.exe window.
2. Change directory to where you installed PYTHON and put hulk.py, Type ‘cd’ then the directory (Case sensitive) (cd= change directory)

`cd C:\PYTHON27`

1. Now start up the hulk.py script as follows :

`C:\hulk.py http://www.google.com`

(Write the directory of the hulk.py file followed by a space followed by the website you want to attack (Don’t actually try this with google, since they tend to block IPs with weird requests like the ones we are sending. You may be blocked from google for some time. If you want to try it out, consider setting up a small website on your own, or ask someone’s permission.)

You should now see something like: **HULK ATTACK STARTED**

Give it a few seconds then it will show how many requests it has sent. A few more seconds and if the attack was successful you will see something like: ‘Response Code 500’

As soon as you spot this, try opening the website which may say: ‘Resource Limit Reached’ or ‘Service Unavailable’ meaning you have successfully brought down the website.

Technically, most servers may temporarily deny all requests from your ISP (internet service provider) and hence your IP address meaning that you’ve not actually brought down the website for the world but only for yourself(The website banned you). This is why DOS isn’t as effective as DDOS. When the server has to repeatedly deny several IP addresses, it truly runs out of resources for anyone wanting to open the website.