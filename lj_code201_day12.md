## LJ Code 201 - Day 12
##### 6/28/16

I'm VERY glad that Sam went over one way to go about building part of the lab from yesterday. It made me realize that as much as I worked on simplifying what I was working on, I was still over-complicating things. I think that I may still be doing that, though.

I stuck with trying to create all three image list items on the fly, rather than explicitly creating them like Sam did. I spent a *lot* of today's lab reworking my functions, and trying to make them less convoluted, and I'm not entirely sure that I succeeded.

I've also noticed that I have a real problem with getting frustrated with myself when I can't adequately put something into words. Stupid brain chemistry.

### Code Sample I'm Proud of/that Vexed Me Today

Actually nothing today really stood out. I felt like I was reworking things so much that it was more of a slow slog than any particular moments of note.

That said, I really think that I should be able to make this simpler...

```
function getImages() {
  ulEl.innerHTML = '';
  var choicesCounter = 0;
  while(choicesCounter < 3) {
    var newInt = getRandomInt(0, 20);
    while(checkContent(newInt, prevChoicesArray) || checkContent(newInt, choicesArray)) {
      newInt = getRandomInt(0, 20);
    }
    choicesArray[choicesCounter] = newInt;
    imagesArray[newInt].views++;
    choicesCounter++;
  }
  displayImages();
  for(var i = 0; i < choicesArray.length; i++) {
    prevChoicesArray[i] = choicesArray[i];
  }
};
```
It's all pretty self-explanatory, except this bit that checks for items in an array:

```
var checkContent = function(index, array) {
  var result = false;
  for(var i = 0; i < array.length; i++) {
    if(index === array[i])
      result = true;
  }
  return result;
};
```

**Things to Remember:**

* If something is the same across all instances of an object, MAKE THAT THE DEFAULT IN THE CONSTRUCTOR.
* If something breaks, take a few moments (or a few minutes) to stop and really think about what could have caused the error. Don't immediately dive back in and try to fix it--that leads to chasing your own tail around in the code, and losing track of what, exactly, went wrong first...
*
