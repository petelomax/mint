# mint
web app demo.

Simple web application by Pete Lomax.
Loads an xml file and displays it as a table, which can be filtered and sorted on any column.
Clicking on an entry does not open a new page, but does update the details area.
Never done anything quite like this before, it was quite a fun little challenge.

Notes:

Ideally I would rather say onclick("RANK") at the top of filterList(), but the syntax escaped me.<br>
Likewise I suspect there is an easier way to initialise tags. (I am not a Javascript expert!)<br>
I will also admit that I do not really understand the [0].childNodes[0].nodeValue part.<br>
I might be tempted to factor out fetching as something like
<pre>
function getElem(i,name) {
  return x[i].getElementsByTagName(name)[0].childNodes[0].nodeValue;
}</pre>
I might add var click, rank, entries to filterList(), so that the line becomes
<pre>
  table += "&lt;tr " + click + "&gt;&lt;td&gt;" + rank + "&lt;/td&gt;&lt;td&gt" + lang + "&lt;/td&gt;&lt;td&gt;" + entries + "&lt;/td&gt;&lt;/tr&gt;";
</pre>
and likewise displayDetails():
<pre>
  "Rank: " + rank + "&lt;br&gt;Name: " + name + "&lt;br&gt;Entries: " + entries;
</pre>
xSorter should now be renamed tagSorter(), and it should test for ti==tj and fetch/compare on names rather than yield 0.

Obviously the output is very spartan and would be vastly improved with some formatting, images and explanatory text.
