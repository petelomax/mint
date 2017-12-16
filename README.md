# mint
web app demo.

Simple web application by Pete Lomax.
Loads an xml file and displays it as a table, which can be filtered and sorted on any column.
Clicking on an entry does not open a new page, but does update the details area.
Never done anything quite like this before, it was quite a fun little challenge.

Notes:

Ideally I would rather say onclick("RANK") at the top of filterList(), but the syntax escaped me.

Likewise I suspect there is an easier way to initialise tags. (I am not a Javascript expert!)

I will also admit that I do not really understand the [0].childNodes[0].nodeValue part.

I might be tempted to factor out fetching as something like

function getElem(i,name) {
  return x[i].getElementsByTagName(name)[0].childNodes[0].nodeValue;
}

I might add var click, rank, entries to filterList(), so that the line becomes
  table += "<tr " + click + "><td>" + rank + "</td><td>" + lang + "</td><td>" + entries + "</td></tr>";

and likewise displayDetails() ==> "Rank: " + rank + "<br>Name: " + name + "<br>Entries: " + entries;

xSorter should now be renamed tagSorter(), and it should probably test for ti==tj and fetch/compare 
on names rather than yield 0.

Obviously the output is very spartan and would be vastly improved with some formatting, images and
introductory/explanatory text.
