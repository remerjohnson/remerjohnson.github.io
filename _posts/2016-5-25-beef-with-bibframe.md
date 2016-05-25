---
layout: post
title: Beef With BIBFRAME
---

Now that [BIBFRAME 2.0](https://www.loc.gov/bibframe/docs/index.html) has slowly been rolling out, it feels as if we are moving from the alpha phase to the beta phase. And in that regard, we can begin to critique BIBFRAME and have it not seem unfair. Believe me, it was hard to hold back over the many, many glaring problems with BIBFRAME 1.0. As I'll go over in this post, although 2.0 makes a lot of steps in the right direction, I still think that BIBFRAME has a FRBR-sized hole in it, and is driving a lot of the remaining problems that could keep BIBFRAME from achieving its stated goals.    

To put my critique into context, let's look at some of the [stated goals of BIBFRAME](https://www.loc.gov/bibframe/faqs/):  
1. [I]ntegrate with and engage in the wider information community and still serve the very specific needs of libraries.  
2. Differentiate clearly between conceptual content and its physical/digital manifestation(s).  
3. Leverage and expose relationships between and among entities.

Let's dig in, out of order of course!     

# Concepts Vs. Manifestations

Now, let me first say that I don't consider \#2 to be a necessary goal in a Linked Data environment. That is, everything in a Linked Data environment, from the concept of Postmodernism to the physical SEGA Genesis game console, is assigned a unique identifier (a URI). Everything you can conceive of, real or imagined, is quite logically under the domain of 'Thing'. This is about as deep as we want to go here: not because we're lazy, but because making distinctions between what is 'real' or 'physical' versus conceptual at a high level gets us into trouble in a modeling sense. For instance, in the binary choice between concept vs. reality, what is a fictional character? You would have good cause to say it's a concept; however, since flesh-and-blood people are 'real', we now have created a situation where we have to sort people into boxes of real vs. imagined. Let's go even further, like the representation of Abraham Lincoln in _Abraham Lincoln: Vampire Hunter_. This is a fictional portrayal of a person who actually existed, making classification in this case all but impossible. We've boxed ourselves into a situation where maybe we can't describe or make authorities for fictional entities.      

But the point here is this mental gymnastics is unneeded. In a Linked Data environment, we have a URI for Abraham Lincoln, which if we or a machine visited, would let the agent figure out who we're talking about. Maybe it's the [LCNAF URI for Lincoln](http://id.loc.gov/authorities/names/n79006779.html), which if we look at, makes it quite clear we're talking about the former U.S. President. If we pointed to a different URI, it might even contain a reference to the other (fictional) representations, if it wants to. But there's _no_ need to model all of this out at a high level and force that intellectual work upon people, when computers will ignore it anyway.        

I might be doing a lot of assumption here, but I believe this problem is borne from FRBR. Just as FRBR wants us to try to sort things out at a high level before it's really needed (and will indeed end up occurring at another lower level, like say how relational databases are modeled), we are jumping the gun on organizing and describing things, instead of letting context and lower levels of description do the work. Crucially, computers simply cannot handle high level, abstract ideas. They can only operate with the lowest-of-the-low-level data, returned from a simple URI. That URI has the appropriate properties that contain the statements and bits of description we need.     

# Relationships and Properties Shouldn't Be So Hierarchical and Siloed

In past data formats like XML and MARC, hierarchy was critical. Indeed, attempting to put random XML fields where they didn't adhere to the schema was fatal, and the data were invalid. With Linked Data, which is represented in RDF; it's not that hierarchy is unimportant, but it does become a hindrance to have too much of it. I say this because, once again, since we are imposing a rather high level of organization on what 'things' must be (Work, Instance, Item), we are already creating separate pyramids of data with their own sort of data model. Furthermore, there is almost no 'borrowing' of predicates/properties between Work, Instance, and Item. We cannot simply have something like 'hasTitle':

This violates BIBFRAME's own [RDF conventions](https://www.loc.gov/bibframe/docs/bibframe2-rdf-conventions.html):  

>7) Proliferation of Properties  
>Avoid proliferation of properties by defining a single general property when multiple potential properties have the same meaning.  

Once again, I think this way of looking at things stems from FRBR. We are at a high level forced to sort things into a Work, Expression, etc. Although BIBFRAME simplified this somewhat, it still exists, but common properties are still needlessly delineated. Instead of a simple `bf:title`, we have a title for each superclass: `bf:InstanceTitle`, `bf:WorkTitle`. Well, each superclass except for Item!  

No one has been able to point my to why 'title' can't just be used across resources. Which could spell trouble if/when we decide we want BIBFRAME to describe a website: is a website a Work or an Instance or an Item?  

_Note: BIBFRAME's ontology has been [updated](http://id.loc.gov/ontologies/bibframe.html#p_title) and seems to now allow the common 'title' property for Works, Instances, and Items. We'll see if they then deprecate WorkTitle and InstanceTitle..._   

# A Hyperfocus on Bibliographic Materials Ensures it Will Remain Niche

I really held out hope that BIBFRAME's name was a bit of a misnomer, and that the scheme would be relatively neutral and broad enough to describe any kind of digital resource. However, it seems that dream is over, as only now have the planners hinted that now that the book stuff is done, people can figure out how to represent other 'digital' stuff (which they might refer to as 'digital manifestations'). This is incredibly disappointing to many of us in the now-termed 'non-MARC' world of metadata. It all but assures that other communities will struggle to come up with their own ontologies, which will most likely not be a part of BIBFRAME itself.    

While this situation was generally acceptable in our non-MARC world, as we would just make another XML schema, it is disastrous in an RDF world. If we want non-library communities to actually use our data, we cannot have overly complicated, hundred-flavored versions of BIBFRAME going on. People will simply ignore our data, much as they do now. We must put pressure on people to sit down and make BIBFRAME able to describe _any digital resource_ as a prime objective. Otherwise, the new paradigm will be the same as the old, except instead of MARC and non-MARC worlds, we'll have BIBFRAME and non-BIBFRAME worlds. And the larger world will continue to ignore it all.   

Blaming this situation on FRBR would be warranted, but it's actually a symptom of a larger problem, and that is libraries' hyperfocus on bibliographic materials. The philosophy at the beginning of BIBFRAME was quite literally "Let's figure out how to describe digital representations of books" and not "let's figure out how to describe digital resources that libraries own". That philosophy drove us to the disappointing position we're in. And until that philosophy changes, we'll be having a ton of conversations about how BIBFRAME will discuss the next type of material, or creating separate ontologies for each kind of digital media in libraries.     
