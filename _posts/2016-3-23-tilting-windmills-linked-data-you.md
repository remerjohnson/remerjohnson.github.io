---
layout: post
title: Tilting at Windmills of Linked Data
---

![](https://upload.wikimedia.org/wikipedia/commons/a/a4/The_adventures_of_Don_Quixote_abridged_from_the_original_edition_by_W.M._Thackeray_%281912%29_%2814764731554%29.jpg "See those thirty or so technologists?")
[*Source: By Internet Archive Book Images [No restrictions], via Wikimedia Commons*](https://upload.wikimedia.org/wikipedia/commons/a/a4/The_adventures_of_Don_Quixote_abridged_from_the_original_edition_by_W.M._Thackeray_%281912%29_%2814764731554%29.jpg)

>"What giants?" Asked Sancho Panza.  
>"The ones you can see over there," answered his master, "with the huge arms, some of which are very nearly two leagues long."  
>"Now look, your grace," said Sancho, "what you see over there aren't giants, but windmills, and what seems to be arms are just their sails, that go around in the wind and turn the millstone."  
>"Obviously," replied Don Quixote, "you don't know much about adventures.”  

Let me start off by saying I am not now, nor have I ever been a member of the Commu--, er, a technologist.  

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/kshockey04">@kshockey04</a> I often feel like metadata creators and library technologists are talking past each other.</p>&mdash; Erin Leach (@erinaleach) <a href="https://twitter.com/erinaleach/status/712291193682526209">March 22, 2016</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>  

The original post that is referenced by the above tweets, and what got me thinking about how we are starting to deteriorate in regards to linked data is Roy Tennant's [Broken Furniture and Blood on the Floor](http://www.thedigitalshift.com/2016/02/roy-tennant-digital-libraries/broken-furniture-and-blood-on-the-floor/). In it, Roy sets out what he sees as steps back from 'good' linked data (one example of what is meant by 'good' would be the now super-old-by-Internet-standards [5 Stars of Open Linked Data](https://www.w3.org/DesignIssues/LinkedData.html)).  

Roy argues that the move to better linked data is a bit more revolutionary than some in the library world realize. Although there are other concepts Roy does not mention (like the Open World Assumption vs. Closed World Assumption), Roy calls out that the concept of a 'record' needs to be disposed of and replaced with knowledge of graphs, which would anticipate the need for services tied to what he calls the 'Bibliographic Graph'.    

Kevin Shockey then wrote a rebuttal to Roy's post, called [Wherefore art thou, linked data?](https://kshockey.github.io//2016/03/22/wherefore-linked-data). In it, he claims that records are still important. In fact, he asserts records are _even more important_ in a linked data environment.     

As the tweets above show, there's already a false "us vs. them" dichotomy set up between "metadata creators" and "technologists". Interestingly, Shockey has accused _me_ of creating a false dichotomy, except in his mind, it's between records and graphs. What's strange is that the issues brought up with Shockey's post have been limited to myself and Roy, who cannot be easily classified as merely "metadata creator" or the dreaded "technologist". Look, I have been in Metadata Services for almost 2 years now. IT is a separate department. But it would be silly for us to rope ourselves into imaginary tribes of metadata vs. tech. We are not different people, and that mental divide contributes to a lot of the inertia and rot that has occurred in academic libraries. Roy throughout his career has highlighted that unnecessary divide that acts against the mission of academic libraries. He has also been one of the people in libraries to discard with an old way of thinking, as in his seminal work _MARC Must Die_.     

So, we're supposed to just agree that the graph, or a resource composed of various statements from a graph, is a record? Or that a record is now composed of records? Neither of those statements are accurate. What I believe Shockey is getting at here is that, to take an example from my institution, the page you can see for the digital object at [http://library.ucsd.edu/dc/object/bb6213187w](http://library.ucsd.edu/dc/object/bb6213187w): you could call that a record and call it a day, right? But what is the data behind that object? How was the data model underlying that object determined?  

The data behind that object is in RDF. And our data model (which is ever-evolving) is a radical departure from the MODS-based model that preceded it. The reason is because we are moving from records to a graph. Everything we assert in this object is a series of triples and part of a giant triplestore.    

To highlight how records and graphs of entities differ, let's use an example of the PI on this object, Newell Booth. In a MODS or any kind of record-based system, let's say we find out there's a typo on his name on this one object. Since this hypothetical is a records-based environment, I have to assume that this typo could appear in multiple other records: or, it may not. I suppose we would query the database in order to find that typo in any other records and update them accordingly.  

In a linked data environment, however, I know that the typo must be at the URI (in our case, an ARK) for the name/entity 'Newell Booth'. That's at http://library.ucsd.edu/ark:/20775/bb49503739 (Don't bother trying to navigate to that). I can use a handy tool we have to visit that ARK, and edit the value. Once that occurs, the change will disseminate to any object that contains that URI. In fact, the object I linked initially may display the name as a hyperlink, but that text _does not actually occur in the object's data_. The system pulls the text via the URI. You could imagine the same thing happening if we had a LoC URI, except I can't really edit those, can I? Can I just ask LoC for this 'record'?      

We could wave our hands and say, well, this doesn't matter: that object is still a record. Fine. [I disagree with you](https://youtu.be/hdT6SH0QzZ0?t=6m35s), but fine. However, you _cannot_ deny that conforming to the records-based environment will prevent you from designing good linked data models and ontologies. Because you will make assumptions that eventually run counter to the underlying RDF model. It has occurred in BIBFRAME multiple times, as when they had a property _\<bf:authorizedAccessPoint\>_ but then realized, why not just use _\<rdfs:label\>?_ And it will continue to occur as people realize, wait, why do we keep saying there should be more FRBR in BIBFRAME, when FRBR and RDF concepts are different in important ways? As Karen Coyle points out:  

>The main point is that there are so many contradictions within FRBR that we really must see it as a flawed model, something that needs to be fixed before we try to do anything with it. Yet, for much of the library world it is being taken as gospel - and not just gospel, but the model for our future data standards.    

And yet, we have _\<bf:hasExpression\>_. Is it crazy to suggest this has arisen out of conformance to past thinking, accepting that past mentality as gospel, and not incorporating enough new ways of thinking? I don't.  

So, call it a record if you like. But heed Roy's overall message regardless, because he's making very good points.  
