# LJ Code 201 - Day 6
6/20

Today's lab was complicated, but not overwhelming, although I did feel really pressed for time. 

### 'Code Sample' I'm Proud of
About halfway through the lab today, I tried to start writing the functions and completely hit a wall as to how to proceed. So I put them into pseudocode, and after that, it was much, much easier:

```
function generateHourlyTraffic(store) {
  for each hour that the store is open
  generate a random number of customers
  store that number in an array
  return the array
}

function projectedHourlySales(store) {
  for each item in the array of hourly customers
  multiply that number by the average cookies sold per hour
  store that number in an array
  return the array
}

function projectedDailySales(store) {
  for each item in an array of hour sales
  add that number to a total number
  return the total number at the end.
}
 ```
 
For all of my functions, I passed in the name of the store as the variable, and then used dot notation within the function to get to the variables in the store objects.

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

**Things to Remember:**

* BREAK THINGS DOWN INTO LITTLE PIECES
* PSEUDOCODE IS YOUR FRIEND!