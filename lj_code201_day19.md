## LJ Code 201 - Day 19
##### 7/08/16

I cannot believe that it's been four weeks already. I almost feel like I know less now, although, as Nick says, that's partly because now I know more of the depth of my ignorance when it comes to things like js.

Today was spent squashing the few remaining bugs in our project--I didn't put in a redirect when someone added a new restaurant, for example, or error handling for someone adding an already existing restaurant. Fortunately, that was relatively simple.

However, when we first tried to fix the second problem, we started getting stuck in never-ending loops. At first we thought it was because David used '=' instead of '===' to compare objects, but after that didn't fix the problem, it became clear that the problem was *what* he was comparing, as well. I'm not sure what it is about how js creates objects, but once he was comparing the value that was being passed into the new object, rather than the value from *within* the new object, everything was golden.

### Code Sample I'm Proud of

One of the last changes I made to the project was fixing the gap underneath the "Reviews" header after a new restaurant was created. Originally, the new restaurant form was going to include a place to leave a review, but I scrapped it due to lack of time. However, this meant that when a new restaurant was added, there was an awkward looking, overly large blank space on the page.

My original plan was to hide that header if ```reviews.length``` was 0 for the restaurant being shown on the page. But when I added that to the function that generates the details page, it removed the 'add review' form as well, since they were both in the same ```div```. So instead, I just did this:

```
if(selectedRest.reviews.length < 1) {
  buildNewElement('li', 'No reviews yet! Leave one below.', ulEl, 'class', 'no_reviews');
} else {
  for(var i = 0; i < selectedRest.reviews.length; i++) {
    buildNewElement('li', '<p>' + selectedRest.reviews[i].name + ' says:' + '</p>' + '<p>"' + selectedRest.reviews[i].comment + '"</p><p>Favorite thing to order: ' + selectedRest.reviews[i].faveDish + '</p>' , ulEl);
  }
}
```

(The if is the only new part, the else was already there.) I'm not proud of this code because it's complicated. Instead, I'm proud of it because when I realized that what I wanted to do wouldn't work, this was the simplest fix in the short time we had left.

**Things to Remember:**

* Don't compare values from an existing object to another object that is being created--compare to the values that are being passed in to create the new object.
