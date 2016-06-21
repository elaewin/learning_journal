# LJ Code 201 - Day 6
6/20

Today's lab was complicated, but not overwhelming, although I did feel really pressed for time. 

About halfway through the lab today, I tried to start writing the functions and completely hit a wall as to how to proceed. So I put them into pseudocode, and after that, it was much, much easier. 

For example,

```
function generateHourlyTraffic(store) {
  for each hour that the store is open
  generate a random number of customers
  store that number in an array
  update that array in the store object
}
 ```

I hadn't really appreciated just how much easier this would make writing the code. I've used pseudocode before, but not in such a way that it translated so easily into code. I think actually this was less a matter of the readings on the problem domain, and actually because I read one of the links in the SP article. It led to an article called "Solving Problems, Breaking It Down" (https://simpleprogrammer.com/2011/01/08/solving-problems-breaking-it-down/), which I've bookmarked for future reference. The combination of the two articles really gave me a better handle for a way to approach problems.

It's frustrating/illuminating, because none of the things discussed in the breaking it down article were new concepts--many of them were common sense things, actually. So I'm not sure exactly what it was that made things click a bit for me today, but I'm sure as hell glad it did.
 
### Code Sample I'm Proud of

Or, at least, it made me feel accomplished. :)

For all of my functions, I passed in the name of the store as the variable, and then used dot notation within the function to get to the variables in the store objects.

For example:

```
// Updates a store's array of hourlyProjectedCustomers with a random number of customers per hour for each hour that the store is open.

function generateHourlyTraffic(store) {
  var openHours = store.storeCloses - store.storeOpens;
  for (var i = 0; i < openHours; i++) {
    var customers = getRandomIntInclusive(store.minHourlyCustomers, store.maxHourlyCustomers);
    console.log('hourly customers at ' + (i + 6) + ' to ' + (i + 7) + ': ' + customers);
    store.hourlyProjectedCustomers.push(customers);
  }
}
```
The rather detailed console.log came about because I kept getting a double list of numbers, and was trying to figure out why. It turns out that if you call the same function twice, you get twice as many numbers. Who knew? But at least I figured out what was wrong. 

I was also trying to list out all of the hours that the stores were open explicitly, since the data was collected for each hour the store is open, not all of the hours between 6am and 8pm (which gives an extra hour.)

**Things to Remember:**

* Break down code into little pieces. Seriously. Now make them even smaller. Seriously.
* Pseudocode is your friend.