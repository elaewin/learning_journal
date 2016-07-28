## LJ Code 201 - Day 14
##### 6/30/16

We got the very first start on our projects for next week, and my group had a pretty good brainstorming session. We plan to shamelessly crib ideas off of the Hour Long Lunch project, at least insofar as we all like their interface, and it seems like a great place to start.

I have a feeling I'm going to be looking into the Google Maps API a lot this weekend.

No code sample today - I didn't write much code today, and so don't really have much to show here.

**Things to Remember:**

* When doing CSS animations: the item that is being affected by the animation must contain an initial state in the CSS before any animations  will have an affect on it. i.e. If trying to move something from the left to the right, the object must be explicitly placed on the left (as in the in-class demo):

```
#box {
  position: absolute;
  left: 0;       <-- this bit here
  height: 100px;
  width: 100px;
  background: #888;
  transition: 2000ms all;
}
```

* When estimating time for something, quadruple the amount of time you think it will take, at least for now, when giving estimates.
* Check the assets *before* starting the project, not on the fly. I had a serious facepalm moment today when I was working with Val on the design comp, and we realized that some of the questions we had could have been answered by, basically, paying better attention to what we had.
* Keep talking with Liz about the HAL-et project idea.
