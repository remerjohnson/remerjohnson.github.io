---
layout: post
title: An OpenRefine Tutorial, Part 2
---

## Facets
Facets are the main method of using OpenRefine on data. They allow you to take temporary slices of the data, and from there you can perform a variety of actions on that subset of data, all while being able to see that slice visually.

Facets are basically 'views' of the data that you can isolate, and as you close facets, you will return to the original overview of the data. Even if you do make changes at this point, changes have a clear trail, so that you can revert to previous states of the data.  

### Your First Facet
As a simple scenario, let's say we want to check if a column has any blank (non-null) values (In a column with potentially thousands of rows, it can be very helpful to see blanks instantly). First we need to select the column by clicking the down arrow next to the column header. A menu that presents a 'Facet' choice will display, and hovering over that, we see choices for what kind of facet we want. Since this is a text column, we'll select 'Text facet'.  

Note: If the column has thousands of unique row values, OpenRefine will complain that the choice count is too high upon faceting. To fix this, simply change the choice count to higher than the 1000 default. 5000 is a safe number: any higher and performance can be seriously compromised.  

The result of this faceting will show up in the left toolbar. You can have many facets active at the same time, and you can sort them by name or by count. Clicking on the values in that left toolbar will show the relevant rows on the right.  

If you were to find blanks by faceting, clicking upon the '(blank)' value in the facet would then present a data view where only those rows are presented. This would allow you to make decisions on why the cells are blank, and then you could edit the cell right there if you knew the value.  

## Clusters
Once we utilize facets on the data, we can get a clearer picture of the anomalies present. But it won't catch everything, and for that we would need to use algorithms. Fortunately, OpenRefine has a very powerful feature for use with facets called 'Clustering' that has built in algorithms to find anomalies.  

First, create a facet like before. Now, all we have to do is select 'Cluster' from the Facet / Filter window. This brings up the results of the cluster function.  

Obvious variations can now be seen that would have been very difficult to spot visually. We can then go to each set of values, select to merge values or not, and then 'Re-Cluster' values to make sure our new values can then be clustered again.  

There are other methods and algorithms that clustering can use than the default 'key collision' method, like 'nearest neighbor'. In that case, you would specify the proper amount of character 'distance' that you want OpenRefine to look for. Experiment with different parameters and see what kinds of clusters that result.  

Once you make decisions about merging and edit the cluster interface, OpenRefine will report on how many edits it made to the data.  

Next time, we'll get even more complex and talk about how OpenRefine can utilize scripting and import other sources of data into your data.  
