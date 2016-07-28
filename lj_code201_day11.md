## LJ Code 201 - Day 11
##### 6/27/16

*From my homework submission:*

This lab was teeth-grindingly frustrating. I *think* that I managed to get everything working, but every step seemed to take forever--and I spent a *lot* of time planning what to do. The approaches that I laid out for myself worked...about half the time.

The getImages function that I wrote was originally nested for loops, then two for loops in sequence--which worked about 95% of the time. After much frustration, Nick finally figured out that what I'd written was choking if the last of the three items was a repeat, and starting the count over again, and he helped me restructure it into the working version.

Then the function that I'd written to count the clicks worked except when the image at imagesArray[0] was clicked, because apparently js doesn't accept '0' as a valid value that can be assigned to an id.

I planned the hell out of this lab, and I don't want to think about how long it would have taken without that. (And without existing bits of code from last week (like the buildElement function) that I could repurpose for this lab.)

### Code Sample that Vexed Me Today

Here's the final version of the getImages function:

```
function getImages() {
  ulEl.innerHTML = '';
  var choicesCounter = 0;
  console.log('previous choices', prevChoicesArray);
  while(choicesCounter < 3) {
    var isRepeatNumber = true;
    while(isRepeatNumber === true) {
      isRepeatNumber = false;
      var newInt = getRandomInt(0, 20);
      // console.log('newInt', newInt);
      for(var j = 0; j < prevChoicesArray.length; j++) { // Make a function?
        if(newInt === prevChoicesArray[j]) {
          isRepeatNumber = true;
        }
      }
      for(var k = 0; k < choicesArray.length; k++) { // Make a function!
        if(newInt === choicesArray[k]) {
          isRepeatNumber = true;
        }
      }
    }
    var liEl = document.createElement('li');
    choicesArray[choicesCounter] = newInt;
    imagesArray[newInt].timesShown++;
    buildElement('img', '', liEl, 'src', imagesArray[newInt].imgFilePath, imagesArray[newInt].imgName);
    ulEl.appendChild(liEl);
    choicesCounter++;
    // console.log('counter', choicesCounter);
  }
  for(var i = 0; i < choicesArray.length; i++) {
    prevChoicesArray[i] = choicesArray[i];
  }
  console.log('current choices', choicesArray);
};

var checkRefs = function() {
  for(var i = 0; i < imagesArray.length; i++) {
    console.log('image reps', imagesArray[i].timesShown);
  }
};
```

**Things to Remember:**

* console.log *everything*. Then do it again. SERIOUSLY.
* When I write pseudocode, make sure that it goes into its own commit, so that I can refer back to it when I get hopelessly lost on a bit of code or a function, and can start over again without having to try and remember where the hell I was going with it.
