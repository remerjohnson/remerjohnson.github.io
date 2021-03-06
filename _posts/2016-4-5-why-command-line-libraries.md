---
layout: post
title: Why Use the Command Line in Libraries?
---

_tldr:_ Navigating on the command line and using common CLI (Command Line Interface) utilities can save tremendous amounts of time, and can introduce less human error into certain processes. You're also almost guaranteed to learn things about computer science, scripting, and gain experience in OSX/Linux environments. And lastly, sometimes it is **the only way**, as some programs or abilities simply do not have a GUI (Graphical User Interface).    

Looking at a recent metadata job posting, it included the following:  

>and [the librarian] is expected to write scripts (e.g. Python, Perl) for repurposing existing metadata  

It's unavoidable that scripting and data analysis will become a large part of the profession moving forward, and the basis of all that is being comfortable on the command line. Organizations like Code4Lib are starting to provide boot camps[^1] and papers[^2] focusing on the command line. So let's look at some examples.    

## Fair Warning

All the examples here will _not_ be using the Windows shells, `cmd.exe` or PowerShell. Please install a proper shell through [GNU on Windows](https://github.com/bmatzelle/gow/releases), Git Shell via [GitHubDesktop](https://desktop.github.com/), etc. The bash or zsh shells are great, although there are newer ones you can experiment with. Use whatever is most comfortable or offers you the most features you need.     

In order to simulate the shell prompt, I will use code blocks that begin with a `$` (as is the case in bash), but your shell may vary (it could be a `#` or a `~` ).  

## Use cases

I'll attempt to break this into 'simple' and 'advanced' (advanced cases tend to save more time or have unique capabilities, but require more homework).  

# Simple Uses

### Make a File Listing
Let's say I have a file directory with hundreds of files, and I need a list of all the files in that directory. Crtl+A (select all) and Ctrl+C (copy) in Windows Explorer won't help here. You could hunt around on the internet for tools with a GUI that will do this... or you could just write one line on the CLI:    

~~~ shell
$ ls > filelist.txt
~~~

This simple line did something a bit complex: It used the output of one command (`ls`, which simply lists the contents of your current directory) and wrote it out to a file because it used a `>`: the result is that this directory will now have a `filelist.txt` file with the entire file list. We could talk about things like `stdout` but all you need to know is you can put the the results (output) of commands into files.    

### Make a Bunch of Files or Directories

In our unit at work, every single project lives in a staging area with all the project's data and metadata. We decided this structure would be the same for every project, and would be composed of 6 predetermined folder names. While this could be accomplished by making sure an existing directory structure were _completely_ empty, and copying/pasting that into each new project, what if you begin a project that will have 10 subcollections, each needing those 6 folders? Let's automate this with a small shell script:  

~~~ shell
#!/bin/sh

# Make the 6 directories (no spaces in the folder names!)
mkdir Admin CLR Final_files Final_metadata Working_files Working_metadata
~~~

You might ask what that nonsense at the top is. This is simply telling the computer where our shell is located. I've named this script `folder_pro.sh` and added it to my computer's PATH (This can be difficult in Windows). So in the future, when I want those folders to be created somewhere, I simply run the script by typing it as a command while in the desired directory: `folder_pro.sh`. Then type `ls` to make sure it worked.  

### Batch Delete Certain Files

Sometimes a collection has a certain directory structure that we want to modify so that we can batch upload it using repository tools. Let's say we have a directory with a thousand .tif files, but also a .jpg derivative that we don't need. We can simply run:  

~~~ shell
$ rm *.jpg
~~~

This deletes any file ending in .jpg. The asterisk (`*`) is a wildcard character, and translates to 'anything', so we're saying 'delete anything that ends in .jpg'. For more complex tasks, you might need to make a script, and might also want to see the section on Regular Expressions.  

### Dealing with Large Files

Let's say I have a month's worth of MARC files in a directory. I want to concatenate them (perhaps to edit them in one place? perhaps to simply have a merged monthly file? Maybe analyze them all in one file in OpenRefine? Perhaps to run through MarcEdit to get FAST headings?). I could fire up a text editor, and copy and paste each one into a new master file. And I would then hope that line endings were uniform, my mouse hand were steady, and that if the files were huge, my computer memory were up to the task (text editors frequently crash when large files are loaded into memory). Or you could write one line on the CLI:  

~~~ shell
# Combine the two files, then output to merged file
$ cat marcfile1.mrx marcfile2.mrx > mastermarcfile.mrx
~~~

So now I have a giant file. I want to get a sense of what the data looks like, but once again, I do not want to open it with an and slow down my system, or even crash programs. Let's use `head`:  

~~~ shell
# Read the first 10 lines in the terminal
$ head mastermarcfile.mrx
~~~

To read the _last_ 10 lines of the file in the terminal, use `tail` instead of `head`. If you need more than 10 lines, e.g. 100, specify in a `-n` flag: `head -n 100 mastermarcfile.mrx`  

If I want to do more, we can use `more` and `less`. This will bring us to another text interface. This may seem counterintuitive, but you actually can do more in `less`, like scrolling. Let's do that on our big file:       

~~~ shell
# View the file a bit more interactively
$ less mastermarcfile.mrx
~~~

Once you've seen enough, you can exit by pressing 'q' to quit.  

# Advanced Uses

### Use Regular Expressions to Search and Replace

I've placed regular expressions in the 'Advanced' section because regular expressions are their own language. It takes time to learn, and is initially not a very readable language. Regular expressions are very powerful, though, and especially useful to metadata people. You can accomplish things with regular expressions in a variety of programming languages (such as the built in `re` library in Python, or the Java-like GREL language in OpenRefine), but in the shell, the utilities `grep` `sed` and `awk` excel at text processing and pattern matching. The intricacies of each are beyond this post's scope, but as an example, let's say recently we determined the word 'Internet' should be lowercase from now on ('internet'). I have a file (file.txt) that's filled with occurrences of 'Internet'. Of course we know of GUI ways to Search and Replace in certain text editors like SublimeText, but we can do it from the shell like so:  

~~~ shell
# Replace all 'Internet' with 'internet'
$ sed -i 's/Internet/internet/' file.txt
~~~     

Without that `-i` flag, it only would have replaced the first occurrence of 'Internet' in each line. This should give you some idea about how complex and thus how powerful some of the combinations of regular expressions can be in massaging and cleaning data.  

### Piping

You may have noticed above that utilities can be used interchangeably, and in fact, that is one of the most powerful uses of the command line. When we separate two commands with a pipe separator, `|`, the _output_ of the previous command becomes the _input_ of the following command. The possibilities here are endless. Experiment to see which ones work the best. Once you have that complex command as one line and it works, you can now save that for future use. This differs from a GUI process, where you would have to document all the steps and clicks you performed, and might have to include screenshots (and then specify all the versions of the programs as well as the operating system you were using).      

## Wrap Up

It's a simple fact that many programs and tools that are useful in libraries do not have a GUI ([twarc](https://github.com/edsu/twarc), [scrapy](http://doc.scrapy.org/en/latest/intro/overview.html), [pybibframe](https://github.com/zepheira/pybibframe), [csvkit](https://csvkit.readthedocs.org/en/540/) to name a few). They only work on the command line, and knowing how to use the CLI in combination with arguments, options, and knowing a little about scripting and programming languages will enable you to use new tools.  


[^1]: Command Line Bootcamp, Code4Lib 2016 Workshop, March 7th 2016: [Google Slides](https://docs.google.com/presentation/d/1I_KA3piFb-ptTO6TWfGFtVnc8iYpUDb8UaXi7kE7cS0/edit#slide=id.g10bfb93dd7_0_0)
[^2]: Metadata Analysis at the Command-Line, Code4Lib Journal, Issue 19, 2013-01-15: [link](http://journal.code4lib.org/articles/7818)
