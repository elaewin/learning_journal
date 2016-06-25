# LJ Code 201 - Day 10
6/24

Working on the group project design comp today.

I felt really uncertain working on this project. I feel like I should have had a better handle on the questions that needed to be answered to set a baseline that all of us could work from. 

Sam went over creating a function to append items to the DOM in our js for the cookie stand project. I've been trying to figure out how to adapt that function so that I can use it for the places where I append something that has a class or id. 

### Code Sample I'm Proud of

```
function buildElement(kind, content, where, attName, attValue) {
  var x = document.createElement(kind);
  x.textContent = content;
  if(attName && attValue) {
    x.setAttribute(attName, attValue);
  }
  where.appendChild(x);
}
```

It's not all that much different than the one that Sam built in class, but it does work, which is nifty.
