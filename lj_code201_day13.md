# LJ Code 201 - Day 13
6/29

I did what felt like a *lot* of reworking code today, but overall I'm pretty happy with it. I was able to clean up a lot in my lab, although there were times when I thought it'd be better to scrap huge chunks of what I was working on. I think that I have a much better handle on how everything works after today, though. Full of frustration though it was.

### Code Sample I'm Proud of

I originally built my BusMall app with an idea in the back of my head that I would track both the information from the current iteration of clicks, and the overall stats for every iteration. But when we got to the local storage part, what I'd built wasn't going to work. At all. 

So I tried creating six arrays (3 for each version of the data I was collecting), but the logistics of putting all three into storage and pulling them back out again meant writing the same thing over and over (and over...)

Finally, at the end of the day, Sam helped me hash out the details of a way to keep both sets of information, with relatively painless writing to local storage.

The app builds two arrays that hold the image objects. One array is rebuilt every time (```imagesArray```), and one is built once, and updated from local storage every time the page loads (```ongoingArray```). Then I build the arrays needed for the charts only at the end, and don't try to save that information, because it's all in the two arrays.

This is the rewritten function that builds those arrays:

```
function buildImageObjects(array) {
  for(var i = 0; i < array.length; i++) {
    imagesArray[i] = (new ProductImage(array[i]));
    var itemName = imagesArray[i].imgFilePath.split('.')[0];
    namesArray[i] = itemName;
  }
  if(!localStorage.storedOngoingArray) {
    for(var i = 0; i < array.length; i++) {
      ongoingArray[i] = (new ProductImage(array[i]));
      var itemName = ongoingArray[i].imgFilePath.split('.')[0];
    }
  }
}
```

**Things to Remember:**

* When dealing with localStorage, if I'm not explicitly using .getItem() or .setItem(), the key for the item I'm handling DOES NOT have to be a string. 
* OVERESTIMATE when trying to predict how long something will take to build. By a LOT, for now. 
* Transitions that are too fast (under the 350ms standard) don't look fast, they look like a slow page is unable to do something instantaneously.