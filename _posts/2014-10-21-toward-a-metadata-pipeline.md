---
layout: post
title: Toward a Metadata Pipeline
---

![Water Pipeline](http://img.photobucket.com/albums/v412/ejones6286/water-pipeline.jpg~original)

Now that I've been in my first librarian gig for almost 5 months (whoa), I've got a solid grasp on how things are done with regards to our digital repository and how metadata gets "made". I also of course bring baggage with me, both good and bad, from library school and elsewhere. This baggage contains thoughts, theories, dreams, ambitions of where I've been and where I want the metadata to go. Where the present of "how we do this now" and the baggage collide is a perhaps idealistic notion of how the whole process should work. I wanted this post to frame out that process broadly, into a blueprint or pipeline. Much of the inspiration comes from a wonderful and healthy IT department, its connections to the larger open source community (especially Hydra), and the recent DCMI Conference in Austin.   

The downside is that this pipeline really only works specifically for my institution. However, I hope it is broad enough to make it applicable to most small-to-midsize academic libraries. Another caveat is that this isn't a new thing I invented (it synthesizes concepts from [Free Your Metadata](freeyourmetadata.org) and [RDF Application Profiles](http://wiki.dublincore.org/index.php/RDF_Application_Profiles), merely it is a decent framework that I think should get more attention and could help many institutions jump into the modern non-MARC world, such as it is. The goal is cleaner metadata, while at the same time achieving efficiency. A side benefit is that this data will be Linked Data friendly in that it sets out to contain [strings not things](http://youtu.be/GDApdVcCQ9A?t=14m44s) and can be further enhanced any number of ways.   

## The opening of the pipe 

Anyone who has worked with XML metadata for any amount of time knows that although an XML document won't render if it is syntactically incorrect, a system will still accept 'bad' or inconsistent metadata values. It's merely a serialization of metadata, which means the underlying data is often laden with errors, as any human-created data likely is. We could paraphrase this with the old adage **G**arbage **I**n, **G**arbage **O**ut (GIGO). The fortunate thing is that the ridiculously time-consuming task of fixing bad metadata can be aided immensely by computers. 

In my current situation, my department doesn't actually create metadata: we merely handle it and get it into a state where it can be ingested with digital objects into a repository. So, even if we were perfect metadata-entering robots (sad fact: no one is), we are not in control over the opening of the pipe. We can, however, throw a nice sieve into the pipe to filter out all the messy stuff.  

This filtering can be achieved through programs like [OpenRefine](http://openrefine.org/)(formerly GoogleRefine). OpenRefine is extremely powerful at presenting slices and layers of the data in ways that make anomolies and errors much more visible than staring at a spreadsheet. This makes data cleanup much more manageable.  

## Data flows  

Now that we have cleaned metadata, we can go about making our digital objects and plugging it all in, right? Well, yes, but it's time to do some forethought. Is our metadata going to be used by other people? I would hope the answer is 'yes'. So we need to think about that. Going back to XML, sure, we have stylesheets and harvesters that can be used to get our data into other places, but it's just not good enough. And simply adding RDF into the mix so that it is RDF in XML doesn't necessarily mean we're done.  

Trying to match RDF data from different sources in notoriously difficult. RDF is such a general framework: it is not a vocabulary. We use a mix of different local or otherwise vocabularies. What we *can* do is create Application Profiles. This will tell a human basically what our model is, and how it relates to other models. It also tells applications what languages they already are using  Usually it all ties back to Dublin Core, which is widely understood and dispels confusion that often happens when we apply labels to things (fun experiment: see what happens when you ask people what they think a field named "description" means).  
