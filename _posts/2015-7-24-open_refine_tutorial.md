---
layout: post
title: An OpenRefine Tutorial
---

## Introduction to OpenRefine
There are a lot of ways to clean tabular data files. Excel has formulas, Find & Replace, and other useful features. Programming scripts and code libraries can accomplish similar tasks with text manipulation using regular expressions, and have the additional advantage of iterative looping and conditional statements (if/then, for/each, etc.).  

But if you want to combine powerful scripting functions with a visual interface for data cleanup, as well as the ability to reconcile metadata to Linked Data sources, OpenRefine is an excellent tool. It was previously known as GoogleRefine, but Google has since turned the project over to the open source community.  

## Installation
Although it runs in a browser window, OpenRefine is not a web service, and needs to be installed as a program. It can be found at a couple different sources:  
+ The OpenRefine Web site: [http://openrefine.org/](http://openrefine.org/)
+ OpenRefine GitHub repo: [https://github.com/OpenRefine/OpenRefine](https://github.com/OpenRefine/OpenRefine)

The simplest way to install it on a Windows machine is to go to the [Downloads](http://openrefine.org/download.html) page on the OpenRefine site and selecting the Windows installer version called the 'Windows kit'.  

Alternatively, it can be downloaded from Github at the [OpenRefine repository](https://github.com/OpenRefine/OpenRefine). Follow the normal way that you clone existing repos to your local system. Then follow the [installation instructions](https://github.com/OpenRefine/OpenRefine/wiki/Installation-Instructions) appropriate to your OS.  

For most uses, the 'stable' version will suffice. If you wish to contribute to the code (which is mostly Java based), you can download the more recent 'developer' version.

## Getting Started Using OpenRefine
Once you install and open the program, a terminal window will launch. Don't panic: this window doesn't need to be interacted with, and will only periodically give status updates for the program (you'll see basic REST calls and extension reports). Everything takes place in a browser window. In fact, you can have multiple instances running by opening extra browser tabs, which launches and should look similar to:  

Digital Object Metadata Management Unit > OpenRefine Documentation and Tutorial > 2014-12-04-OpenRefine01.png

Choose 'Create Project' to get started (once a project has been created, you would select 'Open Project' to get into it). As you can see, OpenRefine supports a wide variety of file formats, and can handle more through the use of extensions (we'll talk about extensions at the end). OpenRefine will then show you a preview of the data, and will ask how you want the data to be parsed. For example, you can specify on how blanks and nulls get interpreted. You may then create the project.
Once created, you will see the imported data that will look something like:  

Digital Object Metadata Management Unit > OpenRefine Documentation and Tutorial > 2014-12-04-OpenRefine02.png

You are now ready to dive in and manipulate the data!

## Facets and Filters
Facets and filters are the main method of using OpenRefine on data. They allow you to take temporary slices of the data, and from there you can perform a variety of actions on that subset of data, all while being able to see that slice visually. GitHub has some screencasts from an older version of GoogleRefine, but it remains a good high level overview of the 'how and why' of OpenRefine.  

These slices are temporary, and are basically 'views' that you can isolate, and as you close facets, you will return to the original data.
Even changes have a clear trail, so that you can revert to previous states of the data:  

Digital Object Metadata Management Unit > OpenRefine Documentation and Tutorial > OpenRefine010.png  

As a simple scenario, let's say we want to check if a column has any blank values. First we need to select the Title column by clicking the down arrow next to the column header. A menu that presents a 'Facet' choice will display, and hovering over that, we see choices for what kind of facet we want. Since this is a text column, we'll select 'Text facet':

Digital Object Metadata Management Unit > OpenRefine Documentation and Tutorial > 2015-01-08-OpenRefine04.png

Note: If the column has thousands of unique row values, OpenRefine will complain that the choice count is too high upon faceting. To fix this, simply change the choice count to higher than the 1000 default. 5000 is a safe number: any higher and performance can be seriously compromised.
The result of this faceting will show up in the left toolbar. You can have many facets active at the same time, and you can sort them by name or count:
Digital Object Metadata Management Unit > OpenRefine Documentation and Tutorial > 2015-02-26 16_56_35-single_metal_by_species_cr_2 xlsx - Google Refine.png

Right away, we can see that Column 3 has 1 blank. In a column with potentially thousands of rows, it can be very helpful to see blanks instantly. Clicking upon the '(blank)' value in the facet would then present a data view where only those rows are presented. This would allow the user to make decisions on why the cells are blank, and what the best solution to cleaning up the data is (if any).

## Tutorial
So now that we've loaded in some data and know something about facets and filters, we are ready to dive in more deeply. Free Your Metadata has an excellent multi-part process that I will take inspiration from, using actual UC San Diego Digital Collections metadata as a test.

### Step 1: Cleaning the Data
Once we have some faceted data, we can get a clearer picture of the anomalies present.
Going back to the picture above, there's something else that should be apparent besides blank values for Column 3. If we look closely, we see that a column that contains only alphabetic characters has a '50' in it. From context, we can infer that this should actually be 'SO', and that this was likely an error from the OCR process. You'll notice this was easy to spot both visually and through the facet feature.
However, in a large dataset, even this faceting can be simply too difficult for a human to visually process in order to catch errors. In this case, OpenRefine has a very powerful feature for use with facets called 'Clustering'.
First, we need to create a facet. Let's facet on the 'TITLE' field:

Digital Object Metadata Management Unit > OpenRefine Documentation and Tutorial > OpenRefine009.png

Now, all we have to do is select 'Cluster' from the Facet / Filter window. This brings up the results of the cluster function:

Digital Object Metadata Management Unit > OpenRefine Documentation and Tutorial > OpenRefine011.png
Obvious variations can now be seen, that would have been impossible to spot manually. We can then go to each case, select to merge values, or not, and then 'Re-Cluster' values to make sure our new values can then be clustered.
There are other methods that clustering can use than the default 'key collision' method, like 'nearest neighbor'. In that case, you would specify the proper amount of character 'distance' that you want OpenRefine to look for.

### Regular Expressions (GREL)

Some Handy GREL Recipes:
Capitalizing only the first character of an entire (possibly multi-word) value:
`toUppercase(cell.value[0])+substring(cell.value, 1)`

### Step 2: Reconciliation
Linked Data sources
----
## A Word About APIs
Reconciling against Linked Data sources is great, but not all or even most of the data on the Internet is structured and accessible via a SPARQL endpoint. RESTful APIs, or Application Programming Interfaces, remain a viable method to retrieve data from resources. Luckily, OpenRefine supports importing data using API calls, based on the data that exists in your sheet.
First, think of the column you want, and then find the API of the service you want. Examples in the library world would be VIAF for names, LCSH for subject headings, or GeoNames for geographic information. But there are many more!
So, now we have two relatively unstructured sources of information: our sheet's data and some data reachable via API calls. How do the two hook up with each other, using OpenRefine?
The answer is through regular expressions. In programming, this usually requires calling a library or module. Fortunately, GoogleRefine has a relatively simple language for regular expressions called GoogleRefine Regular Expression Language (GREL). It has a syntax and built-in functions that will look familiar to you if you have experience in Python.

### Step 3: Entity Extraction


Digital Object Metadata Management Unit > OpenRefine Documentation and Tutorial > 2014-12-04-OpenRefine03.png

### Step 4: Publishing and Access


## Additional Resources
For a helpful resource on a librarian's perspective on OpenRefine, see: http://acrl.ala.org/techconnect/?p=3276
A great blog post on the overall utility of OpenRefine: Using OpenRefine to Perform Text Mining On Your Data
For the full OpenRefine Documentation, visit the GitHub Documentation. Pro Tip: install this Google Chrome extension that will enable you to search GitHub wikis.
Extensions
RDF Refine - An essential extension, this allows you to import RDF vocabularies, reconcile against SPARQL endpoints or RDF dumps, and more.
Named Entity Recognition (NER) - A service to utilize other services in order to recognize and extract entities from unstructured data (like Description fields). Allows configuration using API keys.
Refine Stats - Allows you to quickly run stats on a column of data using OpenRefine's existing filters.
Alternatives
RStudio - An application (technically an IDE) built around the R statistical package, RStudio adds new features constantly that can handle data similarly to OpenRefine: RStudio Data Viewer Improvements
Karma - A 'data integration tool' that allows for inferencing and matching data to ontologies, as well as many other features.
