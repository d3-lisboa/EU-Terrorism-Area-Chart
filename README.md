# Terrorism in EU

Multi Area Chart with time axis showing terrorist incidents in EU 1970-2014

### Block

https://bl.ocks.org/cerico/9b23469eb1d72b6fc73feb8ae3e07b3e

### Version 1 (done)

Forked 'Multi Area Chart with time axis' block\
Replaced data set with one found from internet\
Removed the symbols and d3.nest code as data isn't doing that\
Formatted the data to fit the existing scheme with

```
data.forEach(function(d) {
  d.date = new Date(d.iyear)
  d.Belgium = parseInt(d.Belgium)
});
```

Made the 'number' into an integer here or d3.max got confused and thought 7 was larger than 20\
Removed the maxPrice stuff and made the y domain based on Belgiums highest number\
Altered the `data(symbols).onEnter()` code as not using the symbols and it didn't work\ 
Got a line and area for Belgium showing\
Made a div for the svg and gave it a class to position and style it\
Added a little css

### Version 2 (done)

Got 4 more countries to show\ 
Click to add/remove countries from view\


### Version 3 (to do)

Find highest value dynamically for axis\
Redraw axis when adding/removing a country\
Transitions\








