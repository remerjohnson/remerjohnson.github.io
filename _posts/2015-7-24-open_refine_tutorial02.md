---
layout: post
title: An OpenRefine Tutorial, Part 2
---

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
