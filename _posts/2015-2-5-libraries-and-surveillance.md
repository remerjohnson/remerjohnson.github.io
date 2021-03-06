---
layout: post
title: Libraries and Surveillance
---

![Postcards and magnifying glass](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Postcards_and_magnifying_glass.jpg/1280px-Postcards_and_magnifying_glass.jpg "We're talking the digital version of this")
[*Source: Image CC0 Wikimedia Commons*](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Postcards_and_magnifying_glass.jpg/1280px-Postcards_and_magnifying_glass.jpg)  


This post is inspired by Kade Krockford of [Privacy SOS](http://privacysos.org/) and Alison Macrina of [Library Freedom Project](https://libraryfreedomproject.org/). They're doing good work, so support them and show up whenever they host stuff!  

For a long time, I have been deeply interested in how libraries can counteract, or at the very least, educate people on how they are being spied upon. This of course flared up in a big way after the Snowden and PRISM revelations. The latest news seems continually worse than the last, and the responses from the government indicate they are not truly concerned with implementing new policies. As an aside, it was interesting that during my long job search, I was told by people I respect to pipe down about this topic. It's unfortunate because as librarians, we are by default public people with names attached to our outspokenness or activism. I cherish anonymity but it is not a choice for me. It's hard to accept the idea that a library would not hire a librarian because they are adamantly opposed to their government spying on them.     

At first, librarians and their visitors might feel like this issue does not affect them: after all, they are not a spook who blew the whistle, or a journalist who saw something the government didn't want them to see. But sadly, part of being an informed citizen today is realizing we are all being spied upon via a worldwide dragnet. Even if you have nothing to hide today, the fact that everything you do online is being stored means if suddenly you *do* have something to hide, it will be dug up, and you will be compromised. We also now know that that 'something' to hide encapsulates things that are supposedly protected in America, like protesting or other forms of expression.    

Responding to such a pervasive problem is never easy. Beyond education, are there things the library can do *right now*? Some suggestions seem small, like libraries hosting a [Tor relay](https://www.torproject.org/getinvolved/volunteer.html.en). While it does seem trivial, as this could be hosted on a small headless device like a [Raspberry Pi](http://www.raspberrypi.org/help/faqs/), it does raise some issues. What exactly are the rights of the library when, say, the government asks about the traffic on that Tor relay? Is that a simple risk assessment? Will admin be comfortable with that potential scenario? Is this easier (in a risk assessment way, not a technical skills way) to accomplish in an academic library by the IT department? These kinds of issues need to be addressed by the library community, but they also need not wait for resolution before we take action.  

A lot of these projects can be tackled piecemeal, but there are some more holistic systems we can consider. I personally would love to see a ground-up approach that is not just implemented, but put on display to library visitors as a collection in its own right, and followed up on via ongoing assessment and revision. It could be integrated alongside existing hacker or makerspaces.  

There are lots of options depending on comfort and knowledge level:  


* A router running [OpenWRT](https://openwrt.org/) or other open source firmware. Besides just giving librarians better control over their networks, it can allow some pretty neat stuff.
* Implementing HTTPS with appropriate standards and certificates. Honestly, people. It's no longer cool to ever have a         non-encrypted website. Ever.
* The aforementioned Tor. Also offering people the [Tor Browser Bundle](https://www.torproject.org/projects/torbrowser.html.en) or [Tails](https://tails.boum.org/).
* Encrypted email. This will probably be more about education, because I'm not expecting libraries to set up email             services. It would be awesome, but man it's hard. That said, even telling people about                                       [PGP](https://en.wikipedia.org/wiki/GNU_Privacy_Guard) and how traditional email providers are not secure is a good          start.
* Non-vendor locked content and clouds. Things like [Library Box](http://librarybox.us/) allow you to put a lot of local       and customized content people can access in an easy way. An alternative cloud solution can be accomplished with              [OwnCloud](https://owncloud.org/) (this is also something available to implement on the Raspberry Pi).
* A VPN service? Why not?  

I can see how some of the above seems daunting. You just don't have the expertise or the funds. It's true: [you don't have enough tech](http://www.thedigitalshift.com/2013/11/roy-tennant-digital-libraries/dont-enough-tech/). And that's okay, libraries still have that educational role to play; even basic things like what a cookie is (or even what a [zombie cookie is](http://www.propublica.org/podcast/item/podcast-why-tracking-is-scarier-with-zombie-cookies/)). You can scaffold the education out and go from the basic to the advanced depending on the needs of your community. But trust me, you are more than capable of learning this stuff without being a computer scientist. Except maybe the email server setup :smile:  

If we look closer, we can see that this software is not neutral: it has *values* behind it that align with the mission of libraries. These are free and open sources of software, aligning with the freedom and openness of libraries. Also like libraries, we can point out that while free, this software should be supported financially whenever possible by government organizations and people with the money to spare. There's almost a crisis in how [little funding](http://www.propublica.org/article/the-worlds-email-encryption-software-relies-on-one-guy-who-is-going-broke) privacy and encryption projects receive. It echoes the financial crises libraries face, even though they provide immeasurable value to the world.    
