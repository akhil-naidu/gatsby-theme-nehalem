---
title: Protecting Against DDoS, How do you protect against a nuke?
path: /protecting-against-ddos
tags:
  - Cyber Security
metaImage: assets/pddos.jpg
featuredImage: ./assets/pddos.jpg
excerpt: While DDoS has historically been just an annoyance, there is usually a
  financial impact, such as lost sales or a spike in bandwidth costs.<<<
created: 2020-07-30T03:46:12.184Z
updated: 2020-07-30T03:46:12.265Z
---
The goal of any DDoS attack is to overwhelm a service to the point where it no longer works. While DDoS has historically been just an annoyance, there is usually a financial impact, such as lost sales or a spike in bandwidth costs. Cloud-hosted services, which charge by usage, are especially financially vulnerable to an onslaught of traffic.

DDoS attacks use large numbers of computers simultaneously targeting a single service. The attack often comes from botnets, which are composed of PCs infected by a virus. Recently, DDoS has been used by political protesters, who crowdsource attackers through downloadable software.

Older DoS attacks like SYN floods used limited numbers of attackers, so it was possible to use automatic per-client rate-limiting, or to block the IPs. Modern DDoS techniques try to avoid large amounts of traffic per attacker, and rely purely on large numbers.

Many sites may think they’re too small to attract attention. However, DDoS isn’t a hard attack to perform. Ironically, DDoS is even available as a service. If your site is big enough to attract any business, it’s big enough to attract a potential attacker.

Reducing the cost of an attack starts with early detection. There are simple techniques you can use to alert yourself to an attack. Run a script on your server that sends a message periodically with the recent traffic count: You’ll get a warning either if the count jumps significantly, or the message doesn’t arrive. Additionally, use a remote monitoring program that periodically checks the service’s availability.

A large DDoS attack may block your management access if the site is remote. Try to make sure there’s a cost-effective out-of-band management solution.

Once you detect a DDoS attack, the first step is to identify its unique characteristics. Despite the availability of cleverer techniques, DDoS usually relies on brute force – which means that the traffic from all of the attackers will have unique similarities. Because large numbers of attackers will be involved, scattered across the Internet, blocking the IP addresses will be nearly impossible.

Instead, do a quick packet capture of the attack. Finding examples will be relatively easy, since most of the traffic will be DDoS traffic. Commonalities can often be found in the URI, user agent, or referrer. What you’re looking for is a pattern that you can block with your firewall, router ACL, IDS, etc. It will often be an ASCII or hex pattern at an offset. Become familiar with the capabilities of your equipment, and try some tests in preparation.

Once you have identified the attack fingerprint, it is time to set up a block within your firewall or router to drop the majority of packets. However, a high-bandwidth attack may simply exhaust your WAN link: You’ll have a clean LAN, but your service will still be unreachable. Contact your carrier now to figure out how to work with them during a DDoS attack, in case they need to do the blocking for you.

Some service providers offer “clean pipe” hosting with automatic DDoS squelching. There are also companies who offer products and services to detect and prevent DDoS. Depending on the specifics of your service, it may make financial sense to pay for one of these solutions. Don’t forget the option of simply hosting the service somewhere large enough to absorb the attack – but remember that DDoS against sites that charge by bandwidth can result in unexpectedly high bills.

During and after a DDoS attack, ask for help. Your regional CSIRT (Computer Security Incident Response Team) should be alerted, as they have expertise and contacts that can not only help you during the attack, but also start the process of figuring out who did it and how. A global list is available here:

As cyber crimes get more sophisticated, businesses must be able to constantly adapt to these new security threats. While there are no methods or tools that can completely prevent DDoS attacks from happening, having a security “insurance policy” in place is the first step in ensuring that you are completely prepared. The ability to quickly suspend this new level of attack is tantamount to protecting company data as well as your business as a whole.