---
layout: post
title: Software Tools That I Use
---

Whenever I talk to non-MARC metadata people outside of my library, invariably we come to a point where we get specific about what software we use. Well, let me back up: first we might complain about Windows and how much better Mac OSX and Linux are, but *then* we move on to software. I realized that there's so many choices and personal decisions involved that I would just post a list of what I use and maybe that will help someone, or at least pique their curiosity.  

For reference, I am running Linux Mint Rebecca, which affects some of the software I choose.  

## Team Communication
+  **Slack, Confluence**

![Slack](/images/2015-07-06_post02.png)
{: .center}

Sadly, not everyone will be able to use Slack at work. But I'm so glad my library decided to take the plunge. Skype for Business (formerly Lync) just had no buy-in from people, and it didn't succeed in lessening the need for email. While you can never truly get rid of the need for email, Slack handles so much of the communication, file creation and sharing, and link sharing that you can start shaving down email usage.  

The ability to create channels aimed at certain people on the fly also gives some purpose and structure to the communication, and makes it feel less like an 'anything goes' chat. I really cannot recommend Slack enough.  

Confluence is... meh. It's good for making wikis, but I find myself not needing wikis for anything besides recording meeting notes. Or for getting some internal processes outlined. The problem with Confluence in general is it's not portable at all, unless exporting to PDF or Word is your idea of 'portable.'

## Text Editing
+  **Windows: Notepad++**
+  **Linux: Whatever you want (nano, vim, Sublime Text, diff)**

Now, I'm going to be one of those people that delineates between text editors and IDEs. Yes, you could have one IDE that handles both, but I tend to run a different tool depending on the task at hand.  

For very simple text editing and diffing in Windows, Notepad++ just covers it all. It's very simple to drop text into there and manipulate it, diff it, and paste it back somewhere else. You can use an IDE if you want, but it's a bit overkill for most of these mundane tasks.  

In Linux of course you can just use whatever editor comes with your distro or install new ones, then use a typical sudo at the command line (this example will make a new file called 'filename' in nano):  

~~~ shell
# Create a new file 'filename' using nano editor:
sudo nano filename
~~~  

Also, don't forget to use ```diff``` to be able to compare two different pieces of text. This is needed a lot in metadata to ensure consistency and accuracy in metadata values.  

## IDEs, or Integrated Developer Environments
+  **Windows: Atom, Sublime Text**
+  **Linux: Atom, Sublime Text, vim, Geany**

IDEs are everywhere, and odds are that if you are already proficient at coding, you have a preferred IDE. Furthermore, certain IDEs tend to work better with certain languages. A good example is that people proficient in R undoubtedly use R-Studio as an IDE.  

There has been a push lately for great cross-platform and cross-language IDEs, however. One such new IDE is Atom:  

![Atom 1.0 with a nice green theme](/images/2015-07-06_post1.png)
{: .center}

Since Atom was made by GitHub, it has very good GitHub integration. Changed files will be highlighted (reminding you to commit them), the current branch will be indicated, etc. And because there are so many packages, you can easily mimic other IDEs, or install better support (like syntax highlighting) for your preferred languages. In general, it is the most malleable modern IDE and it works well on any OS.

## Metadata / Data Cleaning
+  **OpenRefine**

I've harped on endlessly about OpenRefine, formerly Google Refine. At least in the library world, there is no real competitor when it comes to data cleaning. The problem with trying to clean data in Excel is that:

+  Find and Replace is not robust enough to be efficient with large replacements
+  You have to know what you're looking for to find things!

OpenRefine groups and clusters things in a way that makes it obvious to spot errors that would be impossible to notice even when looking at an Excel file line by line. Metadata accuracy is very important when it comes to turning strings into things in the spirit of Linked Data, so data cleanup becomes mandatory.

## Note Taking Software
+  **Windows: Evernote (web client and application)**
+  **Linux: Evernote web client**

Much like IDEs, note taking software can get pretty partisan. If you are sticking to only Windows, then OneNote seems like a good choice, *but* keep in mind that a big feature of OneNote is collaborative note-taking, and so if only one person on the team has a Mac, they are stuck using the web client version, which is pretty clunky. Of course the numerous options in Google Drive are good alternative if the team has different types of machines but need to collaborate.  

I use Evernote, even though it doesn't have a dedicated Linux application. I've just never stuck with any other note taking software, and the phone app is too handy for making short personal lists that I have no urge to find greener pastures.  

## Task and Productivity Software
+  **GTasks, Evernote, Slack**

I like GTasks as a task app because of how simple it is. I can have my phone near me that pops up reminders for tasks that may or may not be work related. Done.  

Slack interestingly has a /remind command that works well, also. It's good for when you're already in Slack, and you just set what time you want the reminder to ding, and what the reminder message will be.  

There are big sprawling apps when it comes to task management, but I don't see why I should spend more time and money on something that should be as quick as possible. Taking too much time to enter a task usually results in me not recording the task in the first place.

## Publishing (Documentation, Blogging Software)
+  **GitHub Pages, ReadTheDocs**

It's no secret I'm a huge fan of GitHub Pages. While it's perfectly suited as a streamlined blogging platform, it can also handle documentation fairly well. Another option for documentation is [ReadTheDocs](https://readthedocs.org/), which will also use a GitHub repository to generate a web page, except it will look really nice as documentation, and you don't have to mess too much with HTML and CSS. You simply drop in your documentation, link it via ReadTheDocs, and voila: it's up.  

What's also great about this is you have a version-controlled document repository that you can serve up to people who want to just get at the source documentation.  
