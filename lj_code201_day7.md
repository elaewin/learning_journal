# LJ Code 201 - Day 7
6/21

I think that the pace of class is starting to catch up with me.  I'm exhausted tonight.

Lots of stuff today, and while I'm not sure that I have constructors down completely, having a clear template to follow to change an object into a constructor makes them a lot less frightening. Once again, step by step is key.

I wound up 'out-clevering' myself between yesterday and today. Yesterday I wrote my functions so that they took the hours each store opened and closed, and used those hours to generate the array of hours needed for the lab. Except that today, I found that by doing that, I would have to populate the header for the tables we were creating by picking one of the stores, and using the hours from that store as the headers. Which kind of defeated the purpose of allowing for stores being open for different times. So I scrapped those parts of my code, and just built an array with the hours in it. 

I would up staying late, but finished the js stretch goals, so yay! Or as much yay as I have the energy for, which isn't much right now.

### Code Sample I'm Proud of

Here's my version of the stretch goal footer:

```
// Generate footer row
function makeFooterRow() {
  var trEl = document.createElement('tr');
  var tdEl = document.createElement('td'); // blank space in footer row
  tdEl.textContent = 'Totals';
  trEl.appendChild(tdEl);
  var tdEl = document.createElement('td');
  grandTotal = 0;
  for(var i = 0; i < allStoresArray.length; i++) {
    grandTotal += allStoresArray[i].dailySalesTotal;
  }
  tdEl.textContent = grandTotal;
  trEl.appendChild(tdEl);
  // the complicated bit!
  for(var i = 0; i < openHoursArray.length; i++) {
    var tdEl = document.createElement('td');
    var totalByHour = 0;
    for(var j = 0; j < allStoresArray.length; j++) {
      totalByHour += allStoresArray[j].cookiesPerHourArray[i];
    }
    tdEl.textContent = totalByHour;
    trEl.appendChild(tdEl);
  }
  salesTable.appendChild(trEl);
};
```
The complicated part, or at least the part that was hardest to wrap my brain around, was the section that ran through a for loop of the hours each store was open (var i), then inside that, ran a for loop through all of the store objects in my array of the stores (var j), and pulled out the number of cookies sold in a given hour based on the iteration index number of the *outer* loop (var i).

**Things to Remember:**

* Read over variable and function names the next day and make sure that they still make sense.
* Make a new branch for weekly project code for each day's lecture to practice more branching/merging--and try to remember to ONLY TAKE NOTES about things I want to change/remove/think about. Trying to make changes based on examples leads to a) fucked up code, and/or b) missing bits of lecture.
