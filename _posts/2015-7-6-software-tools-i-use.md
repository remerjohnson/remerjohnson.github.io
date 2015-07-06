---
layout: post
title: Software Tools That I Use
---

Whenever I talk to non-MARC metadata people outside of my library, invariably we come to a point where we get specific about what software we use. Well, let me back up: first we might complain about Windows and how much better Mac OSX and Linux are, but *then* we move onto software. I realized that there's so many choices and personal decisions involved that I would just post a list of what I use and maybe that will help someone, or at least pique their curiosity.  

For reference, I am running Linux Mint Rebecca, which affects some of the software I choose.  

## Text Editing
+  **Windows: Notepad++**
+  **Linux: Whatever you want (nano, vim, Sublime Text, diff)**

Now, I'm going to be one of those people that delineates between text editors and IDEs. Yes, you could have one IDE that handles both, but I tend to run a different tool depending on the task at hand.  

For very simple text editing and diffing in Windows, Notepad++ just covers it all. It's very simple to drop text into there and manipulate it, diff it, and paste it back somewhere else. You can use an IDE if you want, but it's a bit overkill for most of these mundane tasks.  

In Linux of course you can just use whatever editor comes with your distro or install new ones, then use a typical sudo at the command line (this example will make a new file called 'filename' in nano):  
```
sudo nano filename
```  

Also, don't forget to use ```diff``` to be able to compare two different pieces of text. This is needed a lot in metadata to ensure consistency and accuracy in metadata values.  

## IDEs, or Integrated Developer Environments
+  **Windows: Atom, Sublime Text**
+  **Linux: Atom, Sublime Text, vim, Geany**

IDEs are everywhere, and odds are that if you are already proficient at coding, you have a preferred IDE. Furthermore, certain IDEs tend to work better with certain languages. This is quickly changing as the push for great cross-platform and cross-language IDEs continues. One such new IDE is Atom:  
![Atom 1.0 with a nice green theme](/images/2015-07-0615:59:32_post01.png)
