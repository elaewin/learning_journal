# LJ Code 201 - Day 8
6/22

Today was kind of rough. 

I volunteered for code review this morning, and it was very validating, since the feedback I got was that my code was great and looked exactly like it should. However, Sam's prediction that I would have a much easier time of the day's assignment because my code was well put together was not so true...

The afternoon was code review, and not great. Alison and I got started, and I was navigating first. We were able to follow the examples from class pretty easily, and get everything set up...and then the arrays in my code started growing every time we tried to add a new store to the table. After several *hours* of work, and stopping to get Alison's code working, Nadia finally figured out what was wrong.

Here's one of the functions that had to be changed: 
```
this.generateHourlyTraffic = function() {
    for (var i = 0; i < openHoursArray.length; i++) {
      var customers = getRandomIntInclusive(this.minCustsPerHour, this.maxCustsPerHour);
      // console.log('Customers per hour:', customers);
      this.custsPerHourArray.push(customers);
    }
  };
  ```
  
Turns out it was the last line that was the problem, and was repushing the list of random numbers to the custsPerHourArray every time the table was updated. Fortunately, the fix was simple. Change the last line to:
```      this.custsPerHourArray[i] = customers;``` in the and the function that generated fake sales numbers, and everything worked finally.

**Things to Remember:**

* If I am pushing information to an array with .push(), and the information in the array grows in a way I didn't expect, try replacing it with ```arrayName[i] = dataToAddToArray;```, so that the data added erases any former data at that index number, and the array doesn't get any bigger.
* If I declare the same variable more than once in a function (e.g. ```tdEl``` multiple times, I don't have to put the ```var``` in front of the variable name after the first time.)
