---
layout: post
title: An OpenRefine Tutorial, Part 1
---

## Introduction to OpenRefine
There are a lot of ways to clean tabular data files. Excel has formulas, Find & Replace, and other useful features. Programming scripts, utilities like csvkit, and code libraries can accomplish similar tasks with text manipulation using regular expressions, and have the additional advantage of iterative looping and conditional statements (if/then, for/each, etc.).  

But if you want to combine powerful scripting functions with a visual interface for data cleanup, as well as the ability to reconcile metadata to Linked Data sources, OpenRefine is an excellent tool. It was previously known as GoogleRefine, but Google has since turned the project over to the open source community.  

Although OpenRefine serves my particular work needs, since I deal with a large amount of tabular data that I did not author and need to clean, OpenRefine can be broadly used in the data lifecycle after the acquisition of data.  

## Installation
Although it runs in a browser window, OpenRefine is not a web service, and needs to be installed as a program. It can be found at a couple different sources:  

+ The OpenRefine Web site: [http://openrefine.org/](http://openrefine.org/)  
+ OpenRefine GitHub repo: [https://github.com/OpenRefine/OpenRefine](https://github.com/OpenRefine/OpenRefine)  

The simplest way to install it on a Windows machine is to go to the [Downloads](http://openrefine.org/download.html) page on the OpenRefine site and selecting the Windows installer version called the 'Windows kit'. For Windows, I would recommend installing the [7-zip](http://www.7-zip.org/) program to unzip the archive correctly.  

Alternatively, if you are familiar and comfortable with GitHub, it can be downloaded/cloned at the [OpenRefine GitHub repository](https://github.com/OpenRefine/OpenRefine). Follow the normal way that you clone existing repos to your local system. Then follow the [installation instructions](https://github.com/OpenRefine/OpenRefine/wiki/Installation-Instructions) appropriate to your OS.  

For most uses, the 'stable' version will suffice. If you wish to contribute to the code, you can download the more recent 'developer' version.  

## Getting Started Using OpenRefine
Once you install and open the program, there will be some terminal activity but it doesn't need to be interacted with, and will only periodically give status updates for the program (you'll see basic REST calls and extension reports). Everything takes place in a browser window, which will launch on your default browser (fair warning: this won't work with Internet Explorer). In fact, you can have multiple instances running by opening extra browser tabs.  

One Refine is opened, you're asked if you want to Create, Open, or Import a Project.  

Choose 'Create Project' to get started (once a project has been created, you would select 'Open Project' to get into your existing project). As you can see, OpenRefine supports a wide variety of file formats, and can handle more through the use of extensions. By default you can use TSV, CSF, \*SV, Excel (.xls .xlsx), JSON, XML, RDF as XML, or Google Data documents.  

OpenRefine will then show you a preview of the data, and will ask how you want the data to be parsed. For example, you can specify on how blanks and nulls get interpreted, and whether the first row is a header or contains data. You may then create the project.  

Once created, you will see the imported data. You are now ready to dive in and manipulate the data!  

Next time, we'll cover the basics of working with OpenRefine.  
