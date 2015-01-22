---
layout: page
title: Test
permalink: /test2/
--- 

<body markdown="block">

<h1 markdown="span" id=ExcelInputStream-DocumentationForExcelInputStreamMetadata><span
style='font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman";
color:black'>Documentation <span class=GramE>For</span> Excel Input Stream
Metadata<o:p></o:p></span></h1>

<h3 id=ExcelInputStream-Summary><span style='font-family:"Arial",sans-serif;
mso-fareast-font-family:"Times New Roman";color:black'>Summary<o:p></o:p></span></h3>

<p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>This
documentation is an internal guide for&nbsp;</span><strong><span
style='font-size:10.0pt;font-family:"Arial",sans-serif;color:green'>DOMM</span></strong><span
style='font-size:10.0pt;font-family:"Arial",sans-serif;color:green'>&nbsp;</span><span
style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>and&nbsp;</span><strong><span
style='font-size:10.0pt;font-family:"Arial",sans-serif;color:#993300'>IT</span></strong><span
style='font-size:10.0pt;font-family:"Arial",sans-serif;color:#993300'>&nbsp;</span><span
style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>regarding
the &quot;Excel Standard Input Stream&quot;.<o:p></o:p></span></p>

<ul type=disc>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l2 level1 lfo1;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'><a
     href="https://illiad.ucsd.edu:8443/download/attachments/33719826/xls_standard_input_template_2014-12-23.xlsx?version=1&amp;modificationDate=1419353060000&amp;api=v2">The
     latest version of the Excel Input Stream template/spreadsheet</a>.&nbsp;
     If a mapping changes, it is important to inform IT of this in JIRA, and
     point them to the updated mapping file(s). It's a good practice to include
     the date when the mapping was updated in the file name(s), in order to
     avoid confusion.&nbsp; It's also important to remove older mappings to
     avoid versioning issues going forward. It is also possible that IT will
     modify the mapping document rather than just DOMM, so DOMM and IT should
     be aware of which document to work from, with JIRA being the definitive
     latest document.<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l2 level1 lfo1;tab-stops:list .5in'><span class=GramE><span
     style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
     "Times New Roman"'>The excel</span></span><span style='font-size:10.0pt;
     font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>
     standard input stream accommodates simple objects and objects with child
     components (one level of hierarchy), but not grandchildren, etc.<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l2 level1 lfo1;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>Order
     of components will be taken from the order of the components in the
     spreadsheet.<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l2 level1 lfo1;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>Ingest
     for Excel will live on the first worksheet of the Excel document: other
     information not essential to mapping can live on additional sheets. This
     other information will not be actionable by&nbsp;</span><strong><span
     style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
     "Times New Roman";color:#993300'>IT</span></strong><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>.</span><span
     style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
     "Times New Roman";color:green'>&nbsp;</span><span style='font-size:10.0pt;
     font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'><o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l2 level1 lfo1;tab-stops:list .5in'><strong><span
     style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
     "Times New Roman";color:green'>DOMM</span></strong><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman";
     color:green'>&nbsp;</span><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
     mso-fareast-font-family:"Times New Roman"'>should ensure column names
     match the template exactly, including:<o:p></o:p></span></li>
 <ul type=circle>
  <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
      auto;mso-list:l2 level2 lfo1;tab-stops:list 1.0in'><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman"'>Exact spelling<o:p></o:p></span></li>
  <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
      auto;mso-list:l2 level2 lfo1;tab-stops:list 1.0in'><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman"'>Exact case<o:p></o:p></span></li>
  <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
      auto;mso-list:l2 level2 lfo1;tab-stops:list 1.0in'><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman"'>No whitespace, especially trailing whitespace<o:p></o:p></span></li>
 </ul>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l2 level1 lfo1;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>File
     derivatives will not be described by&nbsp;</span><strong><span
     style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
     "Times New Roman";color:green'>DOMM</span></strong><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman";
     color:green'>&nbsp;</span><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
     mso-fareast-font-family:"Times New Roman"'>in the Excel spreadsheet, even
     if they already exist.<o:p></o:p></span></li>
</ul>

<h3 id=ExcelInputStream-Version><span style='font-family:"Arial",sans-serif;
mso-fareast-font-family:"Times New Roman";color:black'>Version<o:p></o:p></span></h3>

<p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>v0.5
- First publish on 11/25/2014<br>
v1.0 - Added table version on Confluence 11/26/2014<br>
v1.1 - Merged content from DOMM Workflow page 12/18/2014<br>
v1.2 - Added Related Resource row 12/23/2014<br>
v1.3 - (de)normalized, merging column content, tweaked formatting
01/15/2015&nbsp;<br>
v1.4 - Changed Related Resource delimiter from <span class=GramE>&quot; @</span>
&quot; to &quot; @ &quot;&nbsp;<o:p></o:p></span></p>

<h3 id=ExcelInputStream-Resources><span style='font-family:"Arial",sans-serif;
mso-fareast-font-family:"Times New Roman";color:black'>Resources<o:p></o:p></span></h3>

<p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'><a
href="https://illiad.ucsd.edu:8443/display/DOMM/Data+Dictionary+-+DRAFT">Current
Data Dictionary</a><br>
<a href="https://illiad.ucsd.edu:8443/display/DOMM/Controlled+Value+Lists">Controlled
Value Lists</a><o:p></o:p></span></p>

<h3 id="ExcelInputStream-Todo:"><span style='font-family:"Arial",sans-serif;
mso-fareast-font-family:"Times New Roman";color:black'>To do:<o:p></o:p></span></h3>

<ul type=disc>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l1 level1 lfo2;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>Clarify
     if we ever have to use Begin and End Date (or automatically derived from
     Date)?<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l1 level1 lfo2;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>When
     there are changes to the element set, should we create a new JIRA to
     modify the existing mapping?<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l1 level1 lfo2;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>Languages
     CV list on spreadsheet uses the <span class=SpellE>iso</span> code + an
     understandable label for the user's benefit.&nbsp; Either DOMM needs to
     change the values to just the <span class=SpellE>iso</span> code before
     ingest, or IT needs to change the mapping to convert he <span
     class=SpellE>iso</span> + label automatically.<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l1 level1 lfo2;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>Add
     all CV lists in the 'preview' style so they are viewable without following
     Confluence links<o:p></o:p></span></li>
</ul>

<h3 id=ExcelInputStream-IngestProcessWorkflow><span style='font-family:"Arial",sans-serif;
mso-fareast-font-family:"Times New Roman";color:black'>Ingest Process Workflow<o:p></o:p></span></h3>

<ul type=disc>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l0 level1 lfo3;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman";
     color:red'>Place all files and ingest metadata spreadsheet in the staging
     area: \\lib-storage\digital-staging</span><span style='font-size:10.0pt;
     font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'><o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l0 level1 lfo3;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>Name
     the spreadsheet like this: xls_standard_input_Ping_2014-12-17.xls<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l0 level1 lfo3;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>Open
     a JIRA ticket in the DAMS Ingest Project space:&nbsp;<a
     href="https://lib-jira.ucsd.edu:8443/browse/DI">https://lib-jira.ucsd.edu:8443/browse/DI</a>
     <o:p></o:p></span></li>
 <ul type=circle>
  <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
      auto;mso-list:l0 level2 lfo3;tab-stops:list 1.0in'><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman"'>Attach the spreadsheet to the ticket.<o:p></o:p></span></li>
  <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
      auto;mso-list:l0 level2 lfo3;tab-stops:list 1.0in'><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman"'>Enter the&nbsp;<a href="../../../display/DOMM/JIRA">JIRA
      ticket description</a>.&nbsp;<o:p></o:p></span></li>
 </ul>
</ul>

<h3 id="ExcelInputStream-WhichItemsarerequired?Whichitemsarerepeatable?"><span
style='font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman";
color:black'>Which Items are required? Which items are repeatable?<o:p></o:p></span></h3>

<ul type=disc>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l4 level1 lfo4;tab-stops:list .5in'><strong><span
     style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
     "Times New Roman"'>Header Name&nbsp;</span></strong><span
     style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
     "Times New Roman"'>(Required)&nbsp;- Item is required for DAMS ingest.
     Otherwise, item is not necessary for DAMS ingest (thus optional). However,
     it is recommended to provide that metadata if it exists.<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l4 level1 lfo4;tab-stops:list .5in'><strong><span
     style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
     "Times New Roman"'>Header name</span></strong><span style='font-size:10.0pt;
     font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>&nbsp;(Repeatable)
     - Item is repeatable. Otherwise, item cannot be repeated (Note: in case of
     multiple&nbsp;<em><span style='font-family:"Arial",sans-serif'>values</span></em>&nbsp;for
     an item,<em><span style='font-family:"Arial",sans-serif'>&nbsp;</span></em>see
     below).<o:p></o:p></span></li>
 <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
     auto;mso-list:l4 level1 lfo4;tab-stops:list .5in'><span style='font-size:
     10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>If
     there are multiple instances of a value (i.e. multiple topical subjects),
     these can either be: <o:p></o:p></span></li>
 <ul type=circle>
  <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
      auto;mso-list:l4 level2 lfo4;tab-stops:list 1.0in'><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman"'>Placed in a single column, with values separated by a
      &quot;space pipe space&quot; (example: value | value)<o:p></o:p></span></li>
  <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
      auto;mso-list:l4 level2 lfo4;tab-stops:list 1.0in'><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman"'>Placed in multiple columns with the same column names.<o:p></o:p></span></li>
  <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;margin-bottom:
      12.0pt;mso-list:l4 level2 lfo4;tab-stops:list 1.0in'><strong><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman";color:green'>DOMM</span></strong><span
      style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
      "Times New Roman";color:green'>&nbsp;</span><span style='font-size:10.0pt;
      font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'>will
      ensure these criteria are met.<o:p></o:p></span></li>
 </ul>
</ul>

<h1 id=ExcelInputStream-TheExcelInputStreamElements><span style='font-family:
"Arial",sans-serif;mso-fareast-font-family:"Times New Roman";color:black'>The
Excel Input Stream Elements<o:p></o:p></span></h1>

<div>

<table class=MsoNormalTable border=1 cellpadding=0 style='mso-cellspacing:1.5pt;
 border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;mso-yfti-tbllook:
 1184;mso-padding-alt:0in 5.4pt 0in 5.4pt;mso-border-insideh:.5pt solid windowtext;
 mso-border-insidev:.5pt solid windowtext'>
 <tr style='mso-yfti-irow:0;mso-yfti-firstrow:yes'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal align=center style='text-align:center'><b><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'>Column Header Name<o:p></o:p></span></b></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal align=center style='text-align:center'><b><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'>Description<o:p></o:p></span></b></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p align=center style='text-align:center'><b><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'>Controlled Values /<o:p></o:p></span></b></p>
  <p align=center style='text-align:center'><b><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'>Format Restrictions<o:p></o:p></span></b></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:1;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Object Unique ID</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>An
  object and its components share the same Object ID. These are usually
  supplied by the data provider.&nbsp; It is not mapped to DAMS, but you can
  copy it in &quot;<span class=SpellE>Identifier<span class=GramE>:other</span></span>&quot;
  if it is useful.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:2;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Object/Component</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>A complex object would
  have one row listed as 'Object', with its files in the next rows as
  'Component' values. A simple object would just have a value of 'Object'.
  &quot;Component&quot; rows must be in the intended order (DAMS display order
  is determined by row count).<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>'Object' or
  'Component'<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:3;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>File Name</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'><o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Used
  by </span><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:#993300'>IT</span></strong><span style='font-size:10.0pt;font-family:
  "Arial",sans-serif;color:black'> to match resource file to metadata.&nbsp;
  For simple objects, a file name must be provided. For complex objects, file
  names must be provided for all of its components.<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Files
  must be copied to \\lib-storage\digital-staging\[<em><span style='font-family:
  "Arial",sans-serif'>project folder</span></em>]. <span class=SpellE>FIle</span>
  name format is not important for ingest, </span><strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;color:#993300'>IT</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'> will
  generate ARKs from the file names.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>File extensions must
  be included.<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:4;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>File Use</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'><o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Use will normally be
  left blank, to be later filled in once the system determines its function
  (determined by <span class=SpellE>filetype</span>/<span class=SpellE>MIMEtype</span>).
  Sometimes a default value needs to be overwritten, e.g.: if a data provider
  has an .mp4 file as a source file, the default ('video-service') can be
  overridden with the value 'video-source'.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'><a
  href="https://illiad.ucsd.edu:8443/display/DOMM/File+use+controlled+value+list">File
  use CV list</a><o:p></o:p></span></p>
  <div>
  <div>
  <p class=MsoNormal><b><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>File use controlled
  value list</span></b><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'> <o:p></o:p></span></p>
  </div>
  <div>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>image-source (.<span
  class=SpellE>tif</span>) <br>
  image-service (.jpg, .<span class=SpellE>png</span>) <br>
  image-huge <br>
  image-large <br>
  image-preview <br>
  image-thumbnail <br>
  image-icon <br>
  image-alternate <br>
  document-source <br>
  document-service (.pdf) <br>
  document-alternate <br>
  audio-source (.wav) <br>
  audio-service (.mp3) <br>
  audio-alternate <br>
  video-source (.<span class=SpellE>mov</span>, .<span class=SpellE>avi</span>)
  <br>
  video-service (.mp4) <br>
  video-alternate <br>
  data-source <br>
  data-service (.tar, .<span class=SpellE>tgz</span>, .tar.gz, .zip) <br>
  data-alternate <o:p></o:p></span></p>
  </div>
  </div>
  </td>
 </tr>
 <tr style='mso-yfti-irow:5;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Unit</span></strong><span style='font-size:10.0pt;font-family:
  "Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Identifies
  a library unit or non-library data provider that is responsible for supplying
  content to the DAMS, and for administering that content over time.<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>The
  Excel template uses the easy to understand values &quot;RCI/RDCP&quot; and
  &quot;Library Digital Collections&quot;, but these must be change to the
  appropriate ARK before Object Build.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>RCI/RDCP:<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'><a
  href="http://library.ucsd.edu/ark:/20775/bb6827300d">http://library.ucsd.edu/ark:/20775/bb6827300d</a><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Library
  Digital Collections:&nbsp;<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'><a
  href="http://library.ucsd.edu/ark:/20775/bb09910635">http://library.ucsd.edu/ark:/20775/bb09910635</a><o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:6;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Assembled collection</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'> or<o:p></o:p></span></p>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Provenance collection</span></strong><span style='font-size:
  10.0pt;font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)
  (Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Identifies whether
  this is an assembled or provenance collection. Providers will use the
  collection Title, but this must be change to the appropriate ARK before
  Object Build. If the collection does not yet exist, create it first then use <span
  class=GramE>it's</span> ARK.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Collection name / URI<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:7;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Provenance collection part </span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Denotes there is a
  sub-part to a provenance collection. Providers will use the collection Title,
  but this must be change to the appropriate ARK before Object Build. If the
  collection does not yet exist, create it first then use <span class=GramE>it's</span>
  ARK.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Collection name / URI<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:8;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Title</span></strong><span style='font-size:10.0pt;font-family:
  "Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Supplied by the data
  provider.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:9;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Subtitle</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'><o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Subtitle<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:10;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Part name</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'><o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Title part<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:11;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Part number</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'><o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Title part number<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:12;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Translation </span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Title Translation<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:13;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Variant </span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Title Variant<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:14;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>ARK</span></strong><span style='font-size:10.0pt;font-family:
  "Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Create
  the column but leave blank. <s>After object ingest, a developer can then
  populate this column with the appropriate ARK numbers for each object</s>.<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>If
  file ingest has already occurred, and thus file ARKS created, this will
  contain arks for the files. If not, file name is required and the ARK column
  will be populated after the items are ingested. For existing DAMS3 objects,
  this will be populated by </span><strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:green'>IT</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'> with the
  existing DAMS3 ARK.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>URI<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:15;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Date:[type]</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>The
  name of the column is determined by the type, e.g. &quot;<span class=SpellE>Date<span
  class=GramE>:created</span></span>&quot;.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Warning: </span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'>Check to make sure Excel does not
  format the date column as 'Date'. Causes formatting issues. Set format to
  'Text'<o:p></o:p></span></p>
  <ul type=disc>
   <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
       auto;mso-list:l3 level1 lfo5;tab-stops:list .5in'><span
       style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
       "Times New Roman"'>Single date format: YYYY-MM-DD<o:p></o:p></span></li>
   <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
       auto;mso-list:l3 level1 lfo5;tab-stops:list .5in'><span
       style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
       "Times New Roman"'>Multiple dates format: &quot;between YYYY-MM-DD&quot;<o:p></o:p></span></li>
   <li class=MsoNormal style='color:black;mso-margin-top-alt:auto;mso-margin-bottom-alt:
       auto;mso-list:l3 level1 lfo5;tab-stops:list .5in'><span
       style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
       "Times New Roman"'>For more scenarios, see <a
       href="http://tpot.ucsd.edu/metadata-services/mas/bp-providers.html#date">http://tpot.ucsd.edu/metadata-services/mas/bp-providers.html#date</a></span><span
       style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
       "Times New Roman";color:red'>&nbsp;</span><span style='font-size:10.0pt;
       font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman"'><o:p></o:p></span></li>
  </ul>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'><a
  href="https://illiad.ucsd.edu:8443/display/DOMM/Date+type+controlled+value+list">Date
  type CV list</a><o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:16;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Begin date</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'> or <strong><span style='font-family:"Arial",sans-serif'>End
  date</span></strong><o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>If
  <span class=SpellE>beginDate</span> or <span class=SpellE>endDate</span>
  don't exist, parse from Date.<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>When
  there is only one date display value, the machine actionable dates (begin
  date and end date) will be encoded together in a single instance of the date
  class.&nbsp; If there are multiple date display values, <span class=GramE>the
  begin</span> and end dates will be encoded as separate instances of the date
  class.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Warning: </span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'>Check to make sure Excel does not
  format the date column as 'Date'. Causes formatting issues. Set format to
  'Text'<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>YYYY
  or YYYY-MM, or YYYY-MM-DD</span><span style='font-size:10.0pt;font-family:
  "Arial",sans-serif;color:red'> </span><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:17;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Person:[type]</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Maps to <span
  class=SpellE>dams<span class=GramE>:Relationship</span></span>
  (creator).&nbsp; The name of the column is determined by the person's role,
  e.g. &quot;<span class=SpellE>Person<span class=GramE>:author</span></span>&quot;.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'><a
  href="https://illiad.ucsd.edu:8443/display/DOMM/role+controlled+value+list">Person
  role CV list</a><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Separate
  names by a pipe or, if needed, add another column.<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:18;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Corporate:[type]</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Maps to <span
  class=SpellE>dams<span class=GramE>:Relationship</span></span>
  (creator).&nbsp; The name of the column is determined by the entity's roles,
  e.g. &quot;<span class=SpellE>Corporate<span class=GramE>:publisher</span></span>&quot;.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Often
  times the value will be &quot;UC Regents&quot;. Has the same role CVs as <a
  href="https://illiad.ucsd.edu:8443/display/DOMM/role+controlled+value+list">Person
  role CV list</a>.<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Separate
  names by a pipe or, if needed, add another column.<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:19;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Note:[type]</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>If the note is of the
  &quot;identifier&quot; type, it gets its own column and type. (See
  Identifier).<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>If the note type isn't
  in the&nbsp;<a
  href="https://illiad.ucsd.edu:8443/display/DOMM/Note+type+controlled+value+list">Note
  type CV list</a>, it should go into the general note type, &lt;<span
  class=SpellE>Note:note</span>&gt;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:20;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Identifier:[type]</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>For the type CV list,
  look under 'identifier' in the <a
  href="https://illiad.ucsd.edu:8443/display/DOMM/Note+type+controlled+value+list">Note
  type CV list</a>. New identifier types should be discussed within DOMM/DMPS<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:21;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Type of Resource</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)
  (Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'><a
  href="https://illiad.ucsd.edu:8443/display/DOMM/typeOfResource+controlled+value+list">Type
  of resource CV list</a>.<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:22;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Language</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'><o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span class=GramE><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>iso639-2b</span></span><span style='font-size:10.0pt;font-family:
  "Arial",sans-serif;color:black'> 3 letter code.<br>
  Spreadsheet CV uses 3 letter code + label for readability. </span><strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;color:green'>DOMM</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;color:green'> </span><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>must
  remove the label before ingest.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Images (thus no
  language content) are assigned a value of '<span class=SpellE>zxx</span>'.<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:23;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Subject:[type]</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>The name of the column
  is determined by the type of subject, e.g. &quot;<span class=SpellE>Subject<span
  class=GramE>:genre</span></span>&quot;.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:24;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Related resource:[type]</span></strong><span style='font-size:
  10.0pt;font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Repeatable)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Cells
  contain values for description and <span class=SpellE>uri</span> separated by
  <span class=GramE>&quot; @</span> &quot; (space @ space).<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Cell
  must always contain <span class=GramE>&quot; @</span> &quot; so values are
  mapped correctly.<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Examples:<br>
  both description and <span class=SpellE>uri</span> = &quot;Manga social
  organization @&nbsp;<a href="http://library.ucsd.edu/dc/object/bb1229906d">http://library.ucsd.edu/dc/object/bb1229906d</a>&quot;<br>
  only description = &quot;Manga social organization @ &quot;<br>
  only <span class=SpellE>uri</span> = &quot; @&nbsp;<a
  href="http://library.ucsd.edu/dc/object/bb1229906d">http://library.ucsd.edu/dc/object/bb1229906d</a>&quot;<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <div>
  <div>
  <p class=MsoNormal><b><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Related resource type controlled
  value list</span></b><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'> <o:p></o:p></span></p>
  </div>
  <div>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>artifact <br>
  basket <br>
  depiction <br>
  journal entry <br>
  news release <br>
  online exhibit <br>
  online finding aid <br>
  related <o:p></o:p></span></p>
  </div>
  </div>
  </td>
 </tr>
 <tr style='mso-yfti-irow:25;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Rights status</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Allowable values are:
  &quot;Under copyright&quot;, &quot;Public domain&quot;, or
  &quot;Unknown&quot;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:26;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Jurisdiction</span></strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:black'><o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>(Required)<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Indicates the country
  that has jurisdiction over the copyright of the object.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Use&nbsp;<a
  href="http://en.wikipedia.org/wiki/ISO_3166-1">ISO 3166-1</a>&nbsp;for
  country codes, e.g. &quot;US&quot; for United States.<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:27;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  color:black'>Copyright holder personal</span></strong><span style='font-size:
  10.0pt;font-family:"Arial",sans-serif;color:black'> or <strong><span
  style='font-family:"Arial",sans-serif'>Copyright holder corporate name</span></strong><o:p></o:p></span></p>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>(Required)<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>&nbsp;<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Indicates the person
  or entity that holds the copyright for the resource<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Typically would be UC
  Regents (and thus a column name of &quot;Copyright holder corporate
  name&quot;), but other possibilities. Can also contain the value
  &quot;Unknown&quot;<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:28;mso-yfti-lastrow:yes;page-break-inside:avoid'>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><strong><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Access override</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;mso-fareast-font-family:
  "Times New Roman";color:black'><o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Single
  value that maps several rights, permission, restriction and license
  values.&nbsp; Only needed to override the overall status of the collection
  (i.e., this is at the object level).<o:p></o:p></span></p>
  <p><span style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'>Boilerplate
  rights notes will be added by </span><strong><span style='font-size:10.0pt;
  font-family:"Arial",sans-serif;color:purple'>IT</span></strong><span
  style='font-size:10.0pt;font-family:"Arial",sans-serif;color:black'> in processing
  based on the rights fields included in the spreadsheet.&nbsp; These do not
  need to be supplied in the spreadsheet.<o:p></o:p></span></p>
  </td>
  <td style='border:solid windowtext 1.0pt;mso-border-alt:solid windowtext .5pt;
  padding:.75pt .75pt .75pt .75pt'>
  <p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif;
  mso-fareast-font-family:"Times New Roman";color:black'>Info: <a
  href="../../../display/DOMM/Access+Override+Mapping">Access Override Mapping</a><o:p></o:p></span></p>
  </td>
 </tr>
</table>

</div>

<h2 id=ExcelInputStream-><span style='font-family:"Arial",sans-serif;
mso-fareast-font-family:"Times New Roman";color:red'>&nbsp;</span><span
style='font-family:"Arial",sans-serif;mso-fareast-font-family:"Times New Roman";
color:black'><o:p></o:p></span></h2>

</div>

</body>
