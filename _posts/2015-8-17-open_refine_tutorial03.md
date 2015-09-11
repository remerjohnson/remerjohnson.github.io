---
layout: post
title: An OpenRefine Tutorial, Part 3
---

## A Quick Analysis of Intentions

This part of the tutorial is all about the scripting and more complex aspects of OpenRefine, but since this aspect is a potential rabbit hole, we should figure out what it is we want to 'do'. In general, I want to avoid throwing everything advanced into the scary 'programming' box because this isn't really programming, simply determining which functions of the tool (and its extensions) to harness.

If you want to simply continue with the data cleanup aspects, there will be some scripting-like things (specifically using [GREL](https://github.com/OpenRefine/OpenRefine/wiki/General-Refine-Expression-Language)) that will come in handy that I'll outline further in this post.
If you want to start to reconcile your metadata in the sense of adding structure to your data via [APIs](https://en.wikipedia.org/wiki/API), and incorporating Linked Data through the 'Named Entity Recognition' extension, that will be handled as well.

## Regular Expressions and Other GREL Stuff

Regular expressions are a skill all its own. If you get really into this data cleaning and transformation stuff, I highly recommend diving into regular expressions separately from OpenRefine. Learn it in your favorite programming language (for example the built in '[re](https://docs.python.org/2/library/re.html#regular-expression-syntax)' library in Python), learn it in the shell via `grep`, etc. The basics of regular expressions are the same in each case, and can get you doing some seriously powerful stuff with data.  

In OpenRefine, regular expressions are used via GREL, or the General Refine Expression Language. A [helpful list of recipes here](https://github.com/OpenRefine/OpenRefine/wiki/Recipes) will cover a ton of common use cases. The only unique thing besides the syntax is the importance of substrings. And a feature in OpenRefine is that you can craft the GREL, and the updated values will be previewed as you type. Once you get the GREL to give you the desired result, you can also Favorite that recipe, which can then be used again at a later date.  

An easy, handy GREL exaple:  
Capitalizing only the first character of an entire (possibly multi-word) value:  
`toUppercase(cell.value[0])+substring(cell.value, 1)`  

## Reconciliation

So we have sufficiently cleaned our data. But our data is probably just a bunch of strings. We could manually go through and provide URIs that point to authoritative data for our data, but that would take a very long time. So if we can reconcile our data against those authorities, the process would be automated, and then we as humans could make decisions about whether the machine correctly matched the sources.  

## A Word About APIs
Reconciling against Linked Data sources (such as a SPARQL endpoint or a massive RDF file) is great, but not all or even most of the data on the Internet is structured and accessible through these methods. RESTful APIs, or Application Programming Interfaces, remain a viable method to retrieve data from resources. Luckily, OpenRefine supports importing data using API calls, based on the unstructured data that exists in your sheet.  

First, think of the column you want to work on, and then find the API of the service you want to pull from. Examples in the library world would be VIAF for names, LCSH for subject headings, or GeoNames for geographic information. But there are many more, so look around! The plus side of APIs is that there are so many out there, since developers have a relatively easy time constructing them. There are many APIs for every domain out there.

So, now we have two relatively unstructured sources of information: our sheet's data and some data reachable via API calls. How do the two hook up with each other, using OpenRefine?  

The answer is through regular expressions, but luckily we already know about those from our data cleaning.  

Now for the bad news: every API has its own set of rules. So the first step is: read the documentation. Being very general, you need to construct your calls so that the API is searched, using *your* data as the search query. Also very generally, the server will take that query and return [JSON](https://en.wikipedia.org/wiki/JSON). Now you will have a column with (likely) nasty JSON data.  

The next step is to base a column on that JSON data, using GREL to isolate only the attributes/values you want. For example, querying GeoNames for a latitude/longitude point will likely return paragraphs of information for each coordinate set. You can then make a column that uses GREL to put in values that only have the preferred name, and its country.

## Entity Extraction

It can be a bit difficult delineating between reconciliation and entity extraction. But let's not get too involved with that, because this will specifically deal with using the [Named Entity Recognition extension](http://freeyourmetadata.org/named-entity-extraction/) from Free Your Metadata. In this case, we don't have to structure our API calls because the server is already expecting a certain type of request. Instead, we need to set up the service initially, adding an API key if needed, and setting some parameters.

Since we're heading into the realm of semantics, most services will need a confidence value. This means you are telling the machine whether to be lazy or very stringent in the results it returns for recognizing your data. Obviously, if you tell the service to be 90% (.9) sure that a value matches, it will return far fewer results than a lower confidence score. In the end, you will likely need to do some review of the matches to tell OpenRefine which matches are acceptable.

## Additional Resources
+ [A librarian's perspective on OpenRefine](http://acrl.ala.org/techconnect/?p=3276)
+ [GoogleRefine Youtube channel](https://www.youtube.com/channel/UCqwSVsJ8CWD9pQUZDbJC1ew)  
+ A great blog post on the overall utility of OpenRefine: Using OpenRefine to Perform Text Mining On Your Data  
+ For the full OpenRefine Documentation, visit the GitHub Documentation. Pro Tip: install this Google Chrome extension that will enable you to search GitHub wikis.  

## Extensions

+ RDF Refine - An essential extension, this allows you to import RDF vocabularies, reconcile against SPARQL endpoints or RDF dumps, and more.
+ Named Entity Recognition (NER) - A service to utilize other services in order to recognize and extract entities from unstructured data (like Description fields). Allows configuration using API keys.  
+ Refine Stats - Allows you to quickly run stats on a column of data using OpenRefine's existing filters.  

## Alternatives
+ RStudio - An application (technically an IDE) built around the R statistical package, RStudio adds new features constantly that can handle data similarly to OpenRefine: RStudio Data Viewer Improvements  
+ Karma - A 'data integration tool' that allows for inferencing and matching data to ontologies, as well as many other features.  
