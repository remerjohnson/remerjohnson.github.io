---
layout: page
title: Excel Input Stream
permalink: /docs/
---

## Summary
This documentation is a guide for DOMM (Digital Object Metadata Management Unit) and IT as well as external audiences regarding the Excel Standard Input Stream. This input stream is meant to take existing metadata that has been mapped to Excel spreadsheets, and ingest them along with associated files into the UC San Diego Digital Collections. 
Some tips specifically for DOMM Unit members:   

+ [The latest version of the Excel Input Stream template/spreadsheet](https://illiad.ucsd.edu:8443/download/attachments/33719826/xls_standard_input_template_2015-01-16.xlsx?version=1&modificationDate=1421423565000&api=v2). If a mapping changes, it is important to inform IT of this in JIRA, and point them to the updated mapping file(s). It's good practice to include the date the mapping was updated in the file name(s), in order to avoid confusion.  It's also important to remove older mappings to avoid versioning issues going forward. It is also possible that IT will modify the mapping document rather than just DOMM, so DOMM and IT should be aware of which document to work from, with JIRA's being the definitive latest document.  
+ The excel standard input stream accommodates simple objects and objects with components. Work is being done to support subcomponents for an additional level of hierarchy.  
+ Order of components will be taken from the order of the components in the spreadsheet.  
+ Ingest for Excel will live on the first worksheet of the Excel document: other information not essential to mapping can live on additional sheets. This other information will not be actionable by IT.  
+ DOMM should ensure column names match the template exactly, including:  
  + Exact spelling
  + Exact case
  + No whitespace, especially trailing whitespace
+ File derivatives will not be described by DOMM in the Excel spreadsheet, even if they already exist.  

## Version Information
v0.5 - First publish on 11/25/2014  
v1.0 - Added table version on Confluence 11/26/2014  
v1.1 - Merged content from DOMM Workflow page 12/18/2014  
v1.2 - Added Related Resource row 12/23/2014  
v1.3 - (de)normalized, merging column content, tweaked formatting 01/15/2015   
v1.4 - Changed Related Resource delimiter from " || " to " @ "  
v1.5 - Changed wording to be more appropriate for external audiences 02/04/2015    

## Internal Resources
[Current Data Dictionary](https://illiad.ucsd.edu:8443/display/DOMM/Data+Dictionary+-+DRAFT)  
[Controlled Value Lists](https://illiad.ucsd.edu:8443/display/DOMM/Controlled+Value+Lists)   

## To do:  

+ Languages CV list on spreadsheet uses the iso code + an understandable label for the user's benefit.  Either DOMM needs to change the values to just the iso code before ingest, or IT needs to change the mapping to convert he iso + label automatically.
+ Add all CV lists in the 'preview' style so they are viewable without following Confluence links.
+ Be aware of status of the component/subcomponent request (JIRA DM-72)  

## Ingest Process Workflow
+ Place all files and ingest metadata spreadsheet in the staging area: \\lib-storage\digital-staging
+ Name the spreadsheet like this: xls_standard_input_Ping_2014-12-17.xls
+ Open a JIRA ticket in the DAMS Ingest Project space: [https://lib-jira.ucsd.edu:8443/browse/DI](https://lib-jira.ucsd.edu:8443/browse/DI)  
  + Attach the spreadsheet to the ticket.
  + Enter the [JIRA ticket description](https://illiad.ucsd.edu:8443/display/DOMM/JIRA).  

## Which Items are required? Which items are repeatable?
+ **Header Name** (Required) - Item is required for DAMS ingest. Otherwise, item is not necessary for DAMS ingest (thus optional). However, it is recommended to provide that metadata if it exists.
+ **Header Name** (Repeatable) - Item is repeatable. Otherwise, item cannot be repeated (Note: in case of multiple values for an item, see below).
+ If there are multiple instances of a value (e.g. multiple topical subjects), these can either be:
  + Placed in a single column, with values separated by a "space pipe space" (example: value &#124; value)
  + Placed in multiple columns with the same column names.
  + DOMM will ensure these criteria are met.

# The Excel Input Stream Elements  

|Column Header Name|Description|Internal|Controlled Values Format Restrictions|
|------------------|-----------|--------|-------------------------------------|
|**Object Unique ID** (Required)|An object and its components share the same Object ID. These are usually supplied by the data provider.  It is not mapped to DAMS, but you can copy it in "Identifier:other" if it is useful.|Used by IT to delineate objects from components. Used by DOMM simply to keep track of which things are objects and components visually. If not provided, DOMM must create.| | 


Object/Component
(Required)
A complex object would have one row listed as 'Object', with its files in the next rows as 'Component' values. A simple object would just have a value of 'Object'. "Component" rows must be in the intended order (DAMS display order is determined by row count).	
'Object' or 'Component'
File Name

For simple objects, a file name must be provided. For complex objects, file names must be provided for all of its components and possibly the object.

Used by IT to match resource file to metadata.
Files must be copied to \\lib-storage\digital-staging\[project folder]. FIle name format is not important for ingest, IT will generate ARKs from the file names.
File extensions must be included.
File Use

File Use will normally be left blank, to be later filled in once the system determines its function (determined by filetype/MIMEtype). Sometimes a default value needs to be overwritten, e.g.: if a data provider has an .mp4 file as a source file, the default ('video-service') can be overridden with the value 'video-source'.	
File use CV list

Unit
(Required)
Unit identifies a library unit or non-library data provider that is responsible for supplying content to the DAMS, and for administering that content over time.
The Excel template uses the easy to understand values "RCI/RDCP" and "Library Digital Collections", but these must be change to the appropriate ARK before Object Build.

RCI/RDCP:
http://library.ucsd.edu/ark:/20775/bb6827300d
Library Digital Collections: 
http://library.ucsd.edu/ark:/20775/bb09910635
Assembled collection or
Provenance collection
(Required) (Repeatable)
This field identifies whether this is an assembled or provenance collection.
Assembled collection: a collection assembled from two or more collections or groups of items to form a distinct collection on a subject or theme.
Provenance collection: a collection representing a single entity or source.
Providers will use the collection Title, but this must be changed to the appropriate ARK before Object Build. If the collection does not yet exist, create it first, then use it's ARK.	Collection name or URI
Provenance collection part 
(Repeatable)
This field denotes that there is a sub-part to a provenance collection.	Providers will use the collection Title, but this must be changed to the appropriate ARK before Object Build. If the collection does not yet exist, create it first, then use it's ARK.	Collection name or URI
Title
(Required)
Title is supplied by the data provider.	

Subtitle	Subtitle	

Part name	Title part	

Part number	Title part number	

Translation 
(Repeatable)
Title Translation	

Variant 
(Repeatable)
Title Variant	

ARK
(Required)
Create the column but leave blank. 

After object ingest, a developer can then populate this column with the appropriate ARK numbers for each object.
For existing DAMS3 objects, this will be populated by IT with the existing DAMS3 ARK.
If file ingest has already occurred, and thus file ARKS created, this will contain arks for the files. If not, file name is required and the ARK column will be populated after the items are ingested.
URI
Date:[type]
(Required)
The name of the column is determined by the type, e.g. "Date:created".

Warning: Check to make sure Excel does not format the date column as 'Date'. Causes formatting issues. Set format to 'Text'
Single date format: YYYY-MM-DD
Multiple dates format: "between YYYY-MM-DD"
For more scenarios, see http://tpot.ucsd.edu/metadata-services/mas/bp-providers.html#date 
Date type CV list
Begin date or End date	
These fields are used if the collection has a beginning and/or ending date

If beginDate or endDate don't exist, parse from Date.
When there is only one date display value, the machine actionable dates (begin date and end date) will be encoded together in a single instance of the date class.  If there are multiple date display values, the begin and end dates will be encoded as separate instances of the date class.
Warning: Check to make sure Excel does not format the date column as 'Date'. Causes formatting issues. Set format to 'Text'
YYYY or YYYY-MM, or YYYY-MM-DD 
Person:[type]
(Repeatable)
Person represents names of people involved in creating the collection.	Maps to dams:Relationship (creator).  The name of the column is determined by the person's role, e.g. "Person:author".	
Person role CV list
Separate names by a pipe or, if needed, add another column.
Corporate:[type]
(Repeatable)
Corporate represents departments, companies, or other groups involved in creating the collection.	Maps to dams:Relationship (creator).  The name of the column is determined by the entity's roles, e.g. "Corporate:publisher".	
Often times the value will be "UC Regents". Has the same role CVs as Person role CV list.
Separate names by a pipe or, if needed, add another column.
Note:[type]
(Repeatable)
If the note is of the "identifier" type, it gets its own column and type. (See Identifier).	
If the note type isn't in the Note type CV list, it should go into the general note type, <Note:note>
Identifier:[type]
(Repeatable)
This is used if the collection has other types of identifiers other than the Object Unique ID.	
For the type CV list, look under 'identifier' in the Note type CV list. New identifier types should be discussed within DOMM/DMPS
Type of Resource
(Required) (Repeatable)
Type of Resource is used to describe the nature of the digital resource being ingested, NOT the original object, if the ingested object is a derivative.	
Type of resource CV list.
Language	
Language indicates the language of the object.

Spreadsheet CV uses 3 letter code + label for readability. DOMM must remove the label before ingest.	Images (thus no language content) are assigned a value of 'zxx'.  Use ISO 639-2B for language codes, e.g. "eng" for english.
Subject:[type]
(Repeatable)
The name of the column is determined by the type of subject, e.g. "Subject:genre".	

Related resource:[type]
(Repeatable)
Cells contain values for description and uri separated by " @ " (space @ space).
Cell must always contain " @ " so values are mapped correctly.
Examples:
both description and uri = "Manga social organization @ http://library.ucsd.edu/dc/object/bb1229906d"
only description = "Manga social organization @ "
only uri = " @ http://library.ucsd.edu/dc/object/bb1229906d"


Rights status
(Required)
Rights status Indicates the status of the use/access rights for the object.	
Allowable values are: "Under copyright", "Public domain", or "Unknown"
Jurisdiction
(Required)
Jurisdiction indicates the country that has jurisdiction over the copyright of the object.	
Use ISO 3166-1 for country codes, e.g. "US" for United States.
Copyright holder personal or Copyright holder corporate name
(Required)

This field indicates the person or entity that holds the copyright for the resource.	
Typically would be UC Regents (and thus a column name of "Copyright holder corporate name"), but other possibilities. Can also contain the value "Unknown"
Access override	
This field is a single value that maps several rights, permission, restriction and license values. Only needed to override the overall status of the collection (i.e., this is at the object level).
Boilerplate rights notes will be added by IT in processing based on the rights fields included in the spreadsheet. These do not need to be supplied in the spreadsheet.
Info: Access Override Mapping
 
