---
layout: post
title: Adding Structured Data With APIs, Reconciliation, and Entity Recognition
--- 

Recently at work I was tasked with presenting [OpenRefine](http://openrefine.org/) to my unit. Since it's such a complicated, dense piece of software, I had to prioritize what I would present. I wanted to present aspects that would benefit our unit right away. The most obvious benefits are the many data [cleanup](http://freeyourmetadata.org/cleanup/) features.  
  
When it came to the structured data and enrichment features, I decided to focus on what we would most likely use the most often: [reconciliation](http://freeyourmetadata.org/reconciliation/http://freeyourmetadata.org/reconciliation/) and [named-entity extraction](http://freeyourmetadata.org/named-entity-extraction/). 
   
These two processes are part of what have been termed the ["low hanging fruits of Linked Data"](http://www.dublincore.org/resources/training/ASIST_Webinar_20140521/vanHoolandVerborgh.pdf) by Ruben Verborgh and Seth van Hooland. What that means is that libraries shouldn't wait around for a 100% complete Linked Data solution to start getting involved with Linked Data. They can add structured data to their objects and metadata right now, using low-cost, low barrier tools like OpenRefine. They can benefit and contribute to the Linked Data ecosystem right now.    
  
But I've also been working on things that would be too difficult to make a part of my unit's workflow or that aren't a part of that "low hanging fruit" paradigm. The most interesting activity was working with APIs in OpenRefine. It can be a bit of work, since every API is different with their standards. And we're not guaranteed there's going to be a Linked Data light at the end of the tunnel. It would be nice if most APIs gave you hypermedia instead of IDs: it makes providing URIs all but impossible.  
  
That said, using APIs to add structure to our data has been very productive with my limited experience so far, such as using [GeoNames'](http://www.geonames.org/) API to take our data, query GeoNames to run a search, and return the results in a new column. Often, this would disambiguate place names. I could see similar helpful functions by feeding GeoNames coordinates. 
   
Another API I used was [VIAF](https://platform.worldcat.org/api-explorer/VIAF), which will be no stranger to librarians. I used it to take our existing creator and composer names on a name column, and it would return suggested and alternate name forms. 
   
Working with the APIs involved using [GREL](https://github.com/OpenRefine/OpenRefine/wiki/Understanding-Regular-Expressions), or Open (Google) Refine Expression Language. You use a regular expression-like syntax to make variables, pull data, and format it. This was a more effective intro to regular expressions than I've had in the past, and it is very satisfying that first time you successfully populate a column with JSON pulled from an API.  
  
There's so many ways to add structured data to our metadata, that we're almost paralyzed by choice. It's nice, but it doesn't fit the common perception that Linked Data is this mythical goal that will never be reached.  
