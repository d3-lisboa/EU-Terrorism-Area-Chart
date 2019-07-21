# Terrorism in EU

Multi Area Chart with time axis showing terrorist incidents in EU 1970-2014

### Block

https://bl.ocks.org/cerico/9b23469eb1d72b6fc73feb8ae3e07b3e

### Wide Data Issue

I had to convert the "Wide Data" to "Long Data" for this to work. This seems to be a common problem, with d3 datasets so it may be worth knowing - see also here

http://jonathansoma.com/tutorials/d3/wide-vs-long-data/

```
  var orig_data = dsv.parse(raw);
    var data = [];
    orig_data.forEach( function(row) {
    
      Object.keys(row).forEach( function(colname) {
      // Ignore 'State' and 'Value' columns
      if(colname == "iyear" || colname == "price") {
        return
      }
      data.push({"date": row["iyear"], "price": row[colname], "country": colname});
    });
  console.table(orig_data)
  console.table(data)
```

### Colours /  Keys with spaces

I set the colour from an array of colours using the key. The problem was with "United Kingdom", as a key shouldn't have spaces. I fixed this with

```
  symbols.forEach(function(s) {
      var key = s.key.replace(/\s+/g, '');
      s.colour = colours[key]
  })
```

### Dates

Parsing the date with `d.date = parseDate(d.date)`  didn't work for me as my dates were like "2002" and the original dates were like "Jan 2002", so i added a "Jan" like this

```
d.date = parseDate(`Jan ${d.date}`); 
```

### console.table()

look in the inspector and we can see

1) the original data from the csv
2) the data transformed from 'wide data' to 'long data'
3) the data then transformed by d3.nest


