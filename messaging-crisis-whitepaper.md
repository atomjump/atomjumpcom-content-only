
# Messaging during a global crisis - Whitepaper

AtomJump Foundation3 April 2020,  Updated 20 April 2021


## Summary


The AtomJump Foundation, based in New Zealand, offers a free, open source, and non-profit alternative to the ubiquitous commercial messaging/video solutions on the market, which, today, includes the US-owned Facebook (who also own WhatsApp, Instagram), Twitter, Google Meet, Microsoft (including Teams / Skype), Apple Facetime, Zoom, and the Chinese-owned WeChat.The world is currently in the middle of the global Covid-19 pandemic, and the relevance of these services have gone from being a ‘nice-to-have’ to being an essential part of our business and family interactions. Any down-time from the above services, due to unforeseencircumstances, could have a serious impact on our capabilities to function as a society.This Whitepaper explains how the atomjump.com service is built differently to existing commercial entities, and why it should be considered, at the very least, as a fall-back option to the commercial services, in this C19 crisis, and any other crisis situation.

The advantages are:

* Continuity under pandemic / war / power outage situations
* 100% transparent, downloadable and reproducible software
* Configurable and expandable by local staff, who are not connected with the original developers.

## Scenarios


In planning the design of atomjump.com, we had to consider several possible scenarios:

1. Facebook’s servers go down, during, either an internal misconfiguration, or the company suffers financial ruin, due to a lack of advertising demand. Potentially, they don’t come back up, preventing WhatsApp, Facebook and Instagram from being used.
2. The United States loses it’s mains power, nationally.
3. New Zealand (which is our home country) loses its international internet connections,potentially due to war / or other blockades. This scenario can be applied to other respective nations.


## Architecture


* Hosted on commodity hardware (Raspberry Pi servers which cost approx NZ$100, US$60, and/or existing desktops)
* Separated islands of server clusters in small numbers from 1 - 30, distributed in any country, and pointed at separately by the global Domain Name System (DNS).
* Separated islands of data. Every server only serves it’s own small collection of forums. If one goes down, only that island is affected.
* 100% open source, written in a language most entry-level web developers understand (PHP), both on the server and on the phone/desktop, with a capability forany third party to extend or change the functionality with small ‘plugins’.
* No USA-based (critical) dependencies
* Servers can be run from a home fibre network
* Browser based software, so there is no need to download an app


## Reasoning behind the Architecture


1. To be able to cope with the traffic levels of Facebook, who have approximately 1 million servers across 8 sites around the globe, AtomJump have had to design for massive scalability. However, during a time of crisis, if one of the above scenarios has occurred, AtomJump will not have much time to ramp up its own hardware capabilities, and the availability of hardware may be limited.  Therefore a server silo should be able to be put together with very little financial resource from commodity components. A basic single server setup of AtomJump, would cost approx. NZ$220 and can serve up to approx. 5000 people.

2. The other option AtomJump have is to operate the servers from existing PCs, as a virtual machine, with users providing their own server-compute resources. There still needs to be a route to download the virtual server, initially (currently a 3GB file), but this option provides a high-speed ramp-up of hardware.

3. Since communication is live on atomjump.com on a per-topic basis, and visible globally, but not shared across a global view of all communication (so, in this sense itis closer to a WhatsApp forum, not a Facebook or Twitter post), each topic can be contained on a single isolated server, provided there is an appropriate local backup. This means that there is no requirement for a central global server that, if misconfigured or removed from action, would prevent continued operation of the individual server farm.

4. Most of the existing commercial services have a heavy dependency on USA-based servers, or proprietary software or programming interfaces (APIs) that are USA-based. If the USA loses it’s mains power, for whatever reason, the rest of the world will also suffer a global outage, across all walks of life. While the early Internet was designed to cope with these scenarios (e.g. during a nuclear war), by distributing the risk across numerous servers around the world, the heavy dependency on proprietary live services such as Facebook, which have the functionality heavily centralised, now make it considerably more likely that our internet services can go down due to the smallest of issues.  E.g. At the time of writing, you would only have to look back one day, on the 2 April 2020, to find Facebook, WhatsApp and Instagram services going down around the world collectively for about an hour, during the Corona virus crisis. (1)

5. AtomJump have specifically taken away all their dependencies on any large technology companies, and any USA-based servers. The current majority of it’s messaging servers are based in New Zealand. New Zealand power is supplied by approx 82% renewable electricity, much of which is hydro-powered, and the country is relatively isolated, so it is well suited to surviving a global crisis.

6. Should the service need to be tweaked in a time of crisis e.g. to prevent certain typesof message from being shared in particular languages, it would only take the input of a local entry-level website developer to make adjustments, without the need for a specialist developer from the AtomJump Foundation to provide input. During a pandemic, these specialist developers may not be available, or even alive. PHP is a language that around 80% of Web developers understand, world-wide.

7. The software can be used, along with a list of steps to rebuild it, by anyone, with only a single computer and an internet connection. No licenses are required.

8. There may be limited availability of server farms during a crisis, and AtomJump uses an ‘organic’ server farm approach, that can be expanded like Lego, and duplicated without the need for any specialist staff or equipment. These ‘organic’ server farms physically flex like trees, and are designed to cope with an earthquake. (2)

9. Presently, should network connections go down from e.g. New Zealand to the outside world, NZ’s own internal country web-based messaging communications to, largely USA-owned, servers, will currently shut off instantly (note: NZ does still have texting capability held locally). Effectively, most countries have exported their most popular means of communication (instant messaging) to another nation state, and to a very limited number of commercial entities. To continue to be able to use instant messaging, locally within NZ, there would need to be servers operating from within New Zealand. AtomJump.com does provide this capability, and any other country is welcome to suggest a site for hosting their own local servers for their own population,as a part of the atomjump.com network.


## How to use the AtomJump Service


Practically, the atomjump.com service, which makes use of the free open source software, manifests as a shareable link e.g. 

https://yourservicename.atomjump.com

That does not need anything to be downloaded, and runs in either a desktop or a phone’s browser in a few seconds.This live service is free for public forums. AtomJump charges a nominal NZ$15 / year (US$10 / year) to host private, password-protected forums. Further services are available for larger individual traffic requirements and special hosting set-ups. Being a non-profit, any revenue that the Foundation earns goes back exclusively into further development of the product and the staff / equipment needed to maintain the service.


## References

1. Facebook/Instagram/Whatsapp are down together 2 April 2020: 

https://www.cnet.com/news/facebook-and-instagram-are-down-for-some-users/

2. Organic server farm used by AtomJump.com

https://youtu.be/XovHlXskzyk

Expanding with an extra lattice:

https://youtu.be/m3tUzRH6upU


## Contacts

Peter Abrahamson, Director, AtomJump Ltd. Christchurch, New Zealand.Email:  peter AT atomjump.comHardip Abrahamson, Secretary, AtomJump Ltd. Christchurch, New Zealand.Email: hardy AT atomjump.comAtomJump Reception Tel: +64 3 242 0252Further informationhttp://atomjump.orghttps://atomjump.com
