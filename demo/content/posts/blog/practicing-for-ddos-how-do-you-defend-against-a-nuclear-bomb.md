---
title: Practicing For DDOS, How do you defend against a nuclear bomb?
path: practicing-for-ddos
tags:
  - Cyber Security
metaImage: assets/keyddos.jpg
featuredImage: ./assets/keyddos.jpg
excerpt: What we’ll attempt to do in this article is similar to testing a
  nuclear bomb (okay, not really). But still, there’s no way to tell exactly
  what will happen, other than to blast the damn thing because more often than
  not that’s just the way it is with DDOSing.
created: 2020-08-02T02:41:24.086Z
updated: 2020-08-02T02:41:24.147Z
---
What we’ll attempt to do in this article is similar to testing a nuclear bomb (okay, not really). But still, there’s no way to tell exactly what will happen, other than to blast the damn thing because more often than not that’s just the way it is with DDOSing.

To refresh your memory, DDOS Attacks involve saturating the target machine with external communications requests (packets) so much so that it cannot respond to legitimate traffic. In most cases, this presents an obvious obstacle - Where to get massive amounts of bandwidth? By definition, servers are designed to handle huge quantities of traffic and when we are trying to attack it with traffic, it’s going to be very difficult (or is it?).

The usual way to DDOS is to slowly build up a botnet for example, by spreading a trojan (or RAT) that installs the DDOSing software and sets up a backdoor listener. When the infection has spread to thousands of systems, the hacker then activates the trojan and the DDOSing begins. Clearly, breaking into several thousand systems is not very legal or ethical, so even if some genuine website administrator wants to perform a dummy DDOS just to see what will happen and what’s the best way to handle it, they won’t be able to do it. This is another reason why small websites particularly are very vulnerable to attack - they don’t practice because apparently, the only way to practice is illegal. So, when they are hit by an actual DDOS they simply don’t stand a chance. So, below we take a look at a possible solution that works for both good and bad guys. An alternative practice methods for website admins and a shortcut for DDOSing for hackers.

The method described below is quite unpopular. In a sentence, we use online services to DDOS for us. These are called “stressers” or “booters” and are simply services which provide large internet bandwidth for the purposes of simulating a DDOS attack. Before moving on, some of the websites mentioned below do offer trials but most of them are fully unlocked only after a payment. So, these may be useful mainly for serious networking administrators or website owners only.

Clearly, doing an actual BlackHat DDOS using this is very much possible if done correctly. But that would require using a VPN or TOR browser to hide your identity. Even with that, since you would have to make a payment, it could potentially lead back to you making this a very dangerous alternative if not done exactly right. Hence, I recommend using this method only for what it’s meant for, as simply fooling around can get you into very serious legal trouble.

You can search yourself for “website stressers” to find a few good ones.

For some reasons, the majority of these websites appear quite dull on first look. Perhaps they don’t want to attract a lot of attention. Anyways, In most of the above websites you’ll simply see a login page with a “Register” option. So, pretty much the only way to get inside is to make an account. Pick anyone and create an account. (Again, this tutorial is mainly for online service/website owners who want to make sure their website is well protected) Once you’ve registered for the first time. You will see several packages of boot time and strength. Whether you’re trying to DDOS someone else (which you shouldn’t) or your own online website or service, I recommend having several (2-3) booters or Stressers with moderate time instead of just 1 large DDOSer.

On The websites you will see a control panel-like window, where you can initiate your DDOS Attacks after selecting a package. To DDOS a home connection or a server, you will first need the (host) IP address. Many Booters Contain a built in Skype resolver and Domain Resolver. For “Port” option, the usual choice is Port 80 (Directed at home modems).

You will then be able to set your Boot time anywhere from 0 to the maximum time you paid for. Generally, UDP(User Datagram Protocol) is used for targeting a PC. For website and larger servers, SSYN attack is usually used which is considerably more powerful. You can think of these as DDOS attacks in which different types of optimal requests are sent for different situations and targets. Anything more than this will get a bit too technical than required here.

So that’s that for configuring and optimizing the DDOS attack. After this you will be able to start your DDOS attack as and when you please. Below you will find some useful relevant information that is frequently required for DDOSing using stressers and/or booters:

Skype Beta Resolver - [http://www.iSkypeResolve.com](http://www.iskyperesolve.com/)

**Other Ports:**

**(Home Connections)**

53 - DNS Port

80 - Default Internet Port

**(Xbox Connections)**

80 - Default Internet Port

88 - Authentication Port

3074 - Xbox Default Port

**(Web Servers)**

21 - FTP Port

25 - SMTP/Mail

53 - DNS Port/Nameserver

80 - Default Internet Port

3306 - MySQL Port