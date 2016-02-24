---
layout: post
title: An OpenRefine Tutorial, Part 3
---

## A Quick Analysis of Intentions

This part of the tutorial is all about the scripting and more complex aspects of OpenRefine, but since this aspect is a potential rabbit hole, we should figure out what it is we want to 'do'. In general, I want to avoid throwing everything advanced into the scary 'programming' box because this isn't really programming, simply determining which functions of the tool (and its extensions) to harness.  

If you want to simply continue with the data cleanup aspects, there will be some scripting-like things (specifically using [GREL](https://github.com/OpenRefine/OpenRefine/wiki/General-Refine-Expression-Language)) that will come in handy that I'll outline further in this post.
If you want to start to reconcile your metadata in the sense of adding structure to your data via [APIs](https://en.wikipedia.org/wiki/API), and incorporating Linked Data through the 'Named Entity Recognition' extension, that will be handled as well.  

## Regular Expressions and Other GREL Stuff

Regular expressions are a skill all its own. If you get really into this data cleaning and transformation stuff, I highly recommend diving into regular expressions, separately from OpenRefine. Learn it in the context of your favorite programming language (for example the built in '[re](https://docs.python.org/2/library/re.html#regular-expression-syntax)' library in Python), learn it in the shell via `grep`, etc. The basics of regular expressions are the same in each case, and can get you doing some seriously powerful stuff with data.  

In OpenRefine, regular expressions are used via GREL, or the Google (or General) Refine Expression Language. A [helpful list of recipes here](https://github.com/OpenRefine/OpenRefine/wiki/Recipes) will cover a ton of common use cases. The only unique thing to GREL besides the syntax is the importance of substrings. And a feature in OpenRefine is that you can craft the GREL, and the updated values will be previewed as you type. Once you get the GREL to give you the desired result, you can also Favorite that recipe, which can then be used again at a later date.  

A super simple yet handy GREL example:  
```
# Capitalize only the first character of an entire value:  
toUppercase(cell.value[0])+substring(cell.value, 1)
```  

This command might look similar to the Python `re.sub` command, and that's the point: since regular expressions are the same concept, it is only the exact syntax that differs.    

## Reconciliation

So we have sufficiently cleaned our data. Although our data is probably just a bunch of strings, we can reasonably assume some fields will have relatively structured data. We could manually go through and provide URIs that point to authoritative data for our data, but that would take a very long time. So if we can _reconcile_ our data against those authorities, the process would be semi-automated, and then we as humans could make decisions about whether the machine correctly matched the sources. This is what the Reconciliation process is all about.  

### Reconcilation via the RDF Extension

For the easiest/most automated way to reconcile your data, you will need the [RDF Extension](http://lab.linkeddata.deri.ie/2010/grefine-rdf-extension/). Once installed, you will have to use the 'RDF' pulldown in OpenRefine to configure the services you want, using methods like SPARQL endpoints, local RDF files, etc. A good SPARQL endpoint in general is [DBpedia](http://wiki.dbpedia.org/), which is the structured data underlying Wikipedia, but also links to other Linked Data sources like VIAF and LCCN.  

A fair warning here: the RDF extension is no longer under active development. What this means is that for many 'new' reconciliation services that are created, the process to get them running occurs in a 'hacky' way. Usually this entails downloading a script that you will have to run locally, which will then use a port on your computer to create the service. Then, you will have to go into OpenRefine, and point to that address/port in order to reconcile your data. It is unfortunate, but this is the current state of things.  

Once you have reconciled your, you can then use GREL to extract the URIs, labels, and other data that the reconciliation service found.    

### Using APIs

Reconciling with services is great, but sometimes you need other methods for when there isn't an existing service. RESTful APIs (Application Programming Interfaces) remain a viable method to retrieve data from the Internet. Luckily, OpenRefine supports importing data using API calls, based on the unstructured data that exists in your sheet.  

First, think of the column you want to work on, and then find the API of the service you want to pull from. An example in the library world would be [VIAF](https://viaf.org/) for names. But, do dig around in GitHub first: you might be surprised at how many reconciliation services exist out there for common library authorities.  

So, now we have two relatively unstructured sources of information: our sheet's data and some data reachable via API calls. How do the two hook up with each other, using OpenRefine?  

The answer is through regular expressions, but luckily we already know about those from our data cleaning.  

Now for the bad news: every API has its own set of rules. So the first step (and the second and last step) is: read the documentation. Being very general, you need to construct your calls so that the API is searched, using *your* data as the search query. Also very generally, the server will take that query and return [JSON](https://en.wikipedia.org/wiki/JSON). Now you will have a column with (likely) nasty JSON data.  

The next step is to base a column on that JSON data, using GREL to isolate only the attributes/values you want. For example, querying GeoNames for a latitude/longitude point will likely return paragraphs of information for each coordinate set. You can then make a column that uses GREL to put in values that only have the preferred name, and its country (or whatever attributes you want to isolate).  

## Entity Extraction / Named Entity Recognition

It can be a bit difficult delineating between reconciliation and entity extraction. But let's not get too involved with that, because this will specifically deal with using the [Named Entity Recognition extension from Free Your Metadata](http://freeyourmetadata.org/named-entity-extraction/). In this case, we don't have to structure API calls because the server is already expecting a certain type of request. Instead, we need to set up the service initially, adding an API key if needed, and setting some parameters. Most sites will have some sort of simple API request process, where you register and are warned about how intensely you can query their server.  

Since we're heading into the realm of semantics, most services will require a confidence value. This means you are telling the machine whether to be lazy or very stringent in the results it returns for recognizing your data. Obviously, if you tell the service to be 90% (.9) sure that a value matches, it will return far fewer results than a lower confidence score, but the results tend to be accurate and require less manual review. Ultimately, you will likely need to do *some* manual review of the matches to tell OpenRefine which matches are acceptable. You must determine the trade off between both approaches. The deciding factor always boils down to time.     

## Additional Resources
+ [A librarian's perspective on OpenRefine](http://acrl.ala.org/techconnect/?p=3276)
+ [GoogleRefine Youtube channel](https://www.youtube.com/channel/UCqwSVsJ8CWD9pQUZDbJC1ew)  
+ A great blog post on the overall utility of OpenRefine: [Using OpenRefine to Perform Text Mining On Your Data](http://blog.spaziodati.eu/en/2014/07/24/using-openrefine-to-perform-text-mining-on-your-data-food-for-thoughts/)  
+ For the full OpenRefine Documentation, visit the [GitHub Documentation](https://github.com/OpenRefine/OpenRefine/wiki). Pro Tip: install [this Google Chrome extension](https://chrome.google.com/webstore/detail/github-wiki-search/gdifdhnjmjaidbajhapmbcbnoocoeooc) that will enable you to search GitHub wikis.  

## Extensions

+ [RDF Refine](http://lab.linkeddata.deri.ie/2010/grefine-rdf-extension/) - An essential extension, this allows you to import RDF vocabularies, reconcile against SPARQL endpoints or RDF dumps, and more.
+ [Named Entity Recognition](http://software.freeyourmetadata.org/ner-extension/) (NER) - A service to utilize other services in order to recognize and extract entities from unstructured data (like Description fields). Allows configuration using API keys.  
+ [Refine Stats](https://github.com/OpenRefine/refine-stats) - Allows you to quickly run stats on a column of data using OpenRefine's existing filters.  

## Alternatives
+ [RStudio](https://www.rstudio.com/) - Built around the R statistical package, RStudio adds new features constantly that can handle data similarly to OpenRefine: [RStudio Data Viewer](https://support.rstudio.com/hc/en-us/articles/205175388-Using-the-Data-Viewer)
+ [Karma](https://usc-isi-i2.github.io/karma/) - A 'data integration tool' that allows for inferencing and matching data to ontologies, as well as many other features.  
