# LJ Code 201 - Day 17
7/06

Today was a lot of little bits of things. 

The nice thing about all four of use working by ourselves is the ability to pick something off of the issues list, work it out, and then move on to the next thing. The problem with all four of us working on stuff by ourselves is that I feel like I didn't really accomplish anything concrete--even though I know that I did.

The process of working on our project has hit that point where we're *almost* at MVP, and keep finding bugs/something that got set aside and still needs to actually be tweaked before MVP. I expect that tomorrow will actually be mostly getting rid of bugs, and we won't be able to get much of the stretch goal stuff finished.

Still, the process of checking out new branches for each issue is becoming fairly automatic. I may be doing too much of that, but we only had one 'serious' merge conflict today, and it only took about 10 minutes to get straightened out.

### Code Sample I'm Proud Of:

It feels like I spent the whole day fixing little bitty things, but I did build another event listener on the list of locations that pulls up the information for a specific restaurant when clicked. I was very pleased with myself for two reasons: 1) It was simple to reuse the function that I created yesterday to update local storage and show a restaurant, so it was a lot of effect for (relatively) little work, and 2) I spent most of the afternoon feeling pretty thoroughly nauseous, so actually putting this together felt like a big victory.

```
// Add a selected restaurant to local storage and update the page
var handleNewRest = function(event) {
  var clicked = event.target.name;
  console.log('clicked on:', clicked);
  handleRestSelect(clicked);
  main();
};

wholeList.addEventListener('click', handleNewRest);
```

**Things to Remember:**

* This is like being at that stage in moving where the big stuff is all gone, and you're going from room to room that you *thought* were empty, and yet you still manage to fill another half-dozen or more boxes with random crap that **somehow** didn't get packed elsewhere. It's tedious, but necessary.