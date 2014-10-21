---
layout: post
title: Toward a Metadata Pipeline
---

![Water Pipeline](http://img.photobucket.com/albums/v412/ejones6286/water-pipeline.jpg)

Now that I've been in my first librarian gig for almost 5 months (whoa), I've got a solid grasp on how things are done with regards to our digital repository and how metadata gets "made". I also of course bring baggage with me, both good and bad, from library school and elsewhere. This baggage contains thoughts, theories, dreams, ambitions of where I've been and where I want the metadata to go. Where the present of "how we do this now" and the baggage collide is a perhaps idealistic notion of how the whole process should work (in my opinion, naturally). I wanted this post to frame out that process broadly, into a blueprint or pipeline. Much of the inspiration comes from a wonderful and healthy IT department, its connections to the larger open source community, and the recent DCMI Conference in Austin.   

The downside is that this pipeline really only works specifically for my institution. However, I think and hope it is broad enough to make it applicable to most small-to-midsize academic libraries. Another caveat is that this isn't a new thing I invented (it synthesizes concepts from [Free Your Metadata](freeyourmetadata.org) and [RDF Application Profiles](http://wiki.dublincore.org/index.php/RDF_Application_Profiles), merely it is a decent framework that I think should get more attention and could help many an institution jump into the modern non-MARC world, such as it is. The goal is cleaner metadata, while at the same time achieving efficiency. A side benefit is that this data will be Linked Data friendly and can be further enhanced any number of ways.   

### The opening of the pipe 

Anyone who has worked with XML metadata for any amount of time knows that although an XML document won't render if it is syntactically incorrect, it doesn't really do anything about bad or inconsistent metadata values. It's merely a serialization of metadata, which means the underlying data is often laden with errors, as any human-created data likely is. The fortunate thing is that we can take the ridiculously time-consuming task of fixing bad metadata and be helped by computers. 

In my current situation, my department doesn't actually create metadata: we merely handle it and get it into a state where it can be ingested with digital objects into a repository. So, even if we were perfect metadata-entering robots (hint: no one is), we are not in control over the opening of the pipe. We can, however, throw a nice sieve into the pipe to filter out all the messy stuff. 

