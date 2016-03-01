---
layout: post
title: Reconciling Metadata to FAST Linked Data
---

Last year, our unit decided to tackle an issue we've been meaning to address for a while. That is: our subjects are bad. What do I mean by 'bad'?  

First of all, our subjects are [LCSH](https://en.wikipedia.org/wiki/Library_of_Congress_Subject_Headings) strings. As anyone versed in data entry or metadata knows, typed strings are error-prone. This resulted in a 'Subject Browse' of our repository that was ugly. Multiple subjects with typos, subjects that varied only slightly, and straight up messes: it was clear browsing by subjects was not doable. And of course, these problems still affected a normal object view.  

While having something like 'Papua New Guinea--Women--Social Customs' would help someone in a _physical_ library to track down a particular book, it is not good for anyone browsing subjects in an online environment, and there is little chance you could locate similar items. Further, because this mixes different 'types' of subjects (geographic with topical), the data representation in RDF became cumbersome. Ultimately, [this is not really linked data we're doing](http://www.thedigitalshift.com/2016/02/roy-tennant-digital-libraries/broken-furniture-and-blood-on-the-floor/), even if this is data represented as triples. We need URIs.  

In certain environments (no judgments), this situation is tolerable because the case can be made that there is no funding or adequately-trained staff to do otherwise. But our unit had no good excuse: we were, after all, a Fedora and Hydra shop that had been creating linked data for years. Our small but capable unit is tasked with handling these sorts of challenges. So, we examined ways in which we could not only fix the issue, but perhaps implement an honest-to-goodness linked data solution.  

We determined the first change would be that we would move from LCSH subjects to [FAST](http://fast.oclc.org/). In the MARC world, this conversion is actually fairly easy to do, using [MarcEdit](http://marcedit.reeset.net/). The subjects are queried directly against the [FAST API](https://www.oclc.org/developer/develop/web-services/fast-api/linked-data.en.html) and you are returned data with the FAST subjects intact.  

Non-MARC metadata is in a trickier position. This is where I came in. I had to basically do the same as what was happening with the MARC data, except use our RDF data.  

My first attempt was a script that would do it all. It would clean up the strings, then query the FAST API and return the subject label along with the URI and MARC tag. As is often the case with my early coding adventures, I realized after the script was complete that I should instead try to do one thing at a time. Although I produced a script that functioned fairly well, I realized later that without the ability to automatically match high-confidence matches (as well as not automatically match low-confidence matches), my script was sort of pointless. That is, it would involve someone going over thousands of matches to determine if they were really 'close enough' or not. There has to be some level of automation to save everyone's time.    

So instead, I pivoted to the much easier goal of setting up the subjects in such a way so that they could be used in an OpenRefine reconciliation service, much as [Ruth Tillman has done](http://journal.code4lib.org/articles/11179), and likewise as others in the library world have done. The specific reconciliation service is [fast-reconcile](https://github.com/cmh2166/fast-reconcile) by [Christina Harlow](https://github.com/cmh2166), who has been looking a lot into these kinds of services for library data.  

My first step was to try to clean up and break up our subjects. I re-used a lot of my previous script that basically just utilized regular expressions to replace hyphens with a space, and try to capture some common errors (as well as conform to the API expectations for queries).  

So now I needed these 'clean' subjects to be represented along with the 'original' subjects and their ID, which in our case is an ARK URI. Instead of a pretty nasty `for` loop, I found that creating a series of single column .csv files for each type of data, then creating a separate function via the Python library `pandas` that would concatenate those multiple .csv files into a single .csv file would be much easier. The result was a much leaner and easier [script](https://github.com/remerjohnson/FAST_times).    

With the concatenated master .csv looking good, it was time to load it into OpenRefine. Utilizing reconciliation services requires the [extension simply named 'RDF'](http://refine.deri.ie/). I then [forked fast-reconcile](https://github.com/remerjohnson/fast-reconcile) so that instead of 'score' reporting a percentage of match closeness, it would instead report the MARC tag. This would help us determine what type of subject was being returned (if a complex subject is broken down into facets, we'd like to know which types they are). I had to take 'score' because there were no other types to take, and there is no way to create 'new' types. This is an unfortunate result of the 'RDF' extension being abandoned.  

Running the reconciliation service locally, and then plugging that information into OpenRefine (just specifying the local port instead of pointing it at a web service), the reconciliation process runs on the 'clean' subjects, and high confidence matches bring back nice blue hyperlinked FAST subjects. Less-confident matches bring back several suggestions, which have to be manually selected. Luckily, OpenRefine has a feature to apply that match to all other matching cells, which could save a lot of time if your dataset has a lot of common subjects.  

Once the reconciliation decisions were made, it was simply a matter of extracting the FAST URIs, labels, and the MARC tag from the results (after all, the result hyperlinks aren't stored data).  

This 'first pass' on our somewhat long, complex subjects didn't yield a lot of results (about 5% matched), which was not surprising. The result was exported as an Excel sheet, and my colleague in my unit helped to iteratively chop unreconciled subjects into smaller chunks. Those smaller chunks eventually came down to a sheet with only single subjects, which is the sheet that predictably got the highest results (around 90% matched).  

So, once we move to our new data model, we will be able to add actual authority URIs to our local RDF data. Since our data also contains lots of names and geographic areas, we are looking into reconciling to NAF, GeoNames, and other possibilities (like Getty vocabularies).  

If any of this seems too daunting or time-consuming, you're not alone. However, I would recommend just diving in and finding a solution that works. It will involve failure, but I feel like linked data is in a spot now where we know further discussions, while helpful, don't do the actual work. It's best to dive in and have fun.  
