#LJ Code 201 - Day 5
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
* then ```git merge master newbranch```

### Code I'm proud of:

Brian gave us a CSS layout exercise, and I'm pretty happy with how I solved it. 

He gave us a layout to attempt, which I've tried to replicate here:

```
|-------------------------------------------------------|
|           |                                           |
|           |                 400 x 100                 |
|           |                                           |
|           |                                           |
|           |-------------------------------------------|
|           |                     |                     |
|           |      200 x 100      |      200 x 100      |
|           |                     |                     |
|           |                     |                     |
| 100 x 400 |-------------------------------------------|
|           |          |          |          |          |
|           |   100 x  |   100 x  |   100 x  |   100 x  |
|           |    100   |    100   |    100   |    100   |
|           |          |          |          |          |
|           |-------------------------------------------|
|           |                                           |
|           |                 400 x 100                 |
|           |                                           |
|           |                                           |
|-------------------------------------------------------|
```

I looked at the layout, and figured that every box had at least one dimension of 100px. So I set the body size to 500 x 400, and the divs to 100 x 100 and float: left. Then I created 3 classes: 400px wide, 200px wide, and 400px high. After that, applying the classes to the divs was pretty straightforward.

**My CSS:**

```
/* clear browser formatting, outline all elements so it's easier to see what's going on */
* { 
  margin: 0;
  padding: 0;
  outline: 1px dotted green;
}

/* Body width limited so elements don't float outside the square */
body {
  width: 500px;
}

div {
  float: left;
  height: 100px;
  width: 100px;
}

.h400 {
  height: 400px;
}

.w400 {
  width: 400px;
}

.w200 {
  width: 200px;
}

/* Paragraph styling is not really necessary for the exercise, but makes it look cleaner */
p {
  text-align: center;
  padding-top: 20px;
}
```

**And the html:**

```
<!DOCTYPE html>
<html>
<head>
  <title>CSS Layout Exercist</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="h400">
    <p>100 x 400</p>
  </div>
  <div class="w400">
    <p>400 x 100</p>
  </div>
  <div class="w200">
    <p>200 x 100</p>
  </div>
  <div class="w200">
    <p>200 x 100</p>
  </div>
  <div>
    <p>100 x 100</p>
  </div>
  <div>
    <p>100 x 100</p>
  </div>
  <div>
    <p>100 x 100</p>
  </div>
  <div>
    <p>100 x 100</p>
  </div>
  <div class="w400">
    <p>400 x 100</p>
  </div>
</body>
</html>
```

