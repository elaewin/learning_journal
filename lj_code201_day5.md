# #LJ Code 201 - Day 5
6/17

I think my brain melted after the long lecture today. Note to self: bring snacks. Also note to self: Cat shirt Friday.

I also need to remember to check js problems from quizzes in the console. During the first quiz, I got caught up on the last question (and got it wrong the first time) because I didn't recognize ```*=``` as a valid expression, and so I didn't catch that the negative in the quiz was ```=!``` (which is invalid) vs. ```!=``` which is correct.

Today's lab was complicated, but I feel like going over pulling answers out of an array in yesterday's homework gave me a real leg up when working on the later questions from the lab (making functions that call variables from other functions based on their locations in arrays from the earlier functions.)

For example:

```
function sum(a,b){
  var result = a + b;
  var message = 'The sum of ' + a + ' and ' + b + ' is ' + result + '.';
  // console.log(message);
  // console.log('The sum of 4 and 7 is 11.');
  return [result, message];
}

testArray = [2,3,4];
function sumArray(testArray){
  var addsArray = sum(sum(testArray[0], testArray[1])[0], testArray[2])[0];
  var message = testArray[0] + ',' + testArray[1] + ',' + testArray[2] + ' was passed in as an array of numbers, and ' + addsArray + ' is their sum.';
  // console.log(addsArray);
  // console.log('Message is: ' + message);
  return [addsArray, message];
}
```

I worked too fast this afternoon, too, and forgot to pull info down from the repo before creating one of my new branches. To fix this: 

* switch back to master branch
* pull updates from the github repo
* switch back to newbranch
* ```git merge master newbranch```

