## LJ Code 201 - Day 16
##### 7/05/16

First day of project week. The group git flow is still a bit shaky, but we haven't had any major conflicts (I think maybe only one merge conflict at all). Partly because we're all sitting around the same table and so we never really get to 5 PRs before a PR gets merged and we keep going. Fervent desire to avoid horrific merge conflicts is a good motivator, apparently.

Most of the day was spent pair programming with Logan, which was awesome. We got a lot done, and the fact that we're all sitting right there is incredibly helpful. Much less stressful than over the weekend when we were just communicating via Slack.

Pair programming also really makes me slow down and put my thoughts into actual coherent words, which is good. It keeps me from trying to move forward too fast and fucking something up by trying to fix things without considering a problem carefully.

I'm really liking using Waffle so far. It seems like an *incredibly* useful tool.

### Code Sample I'm Proud of

Nothing terribly complicated, but Logan and I put the location page together today, and it's working, so that's pretty satisfying.

```
var selectedRest = '';
var restName = document.getElementById('loc_name');
var address = document.getElementById('loc_address');
var phone = document.getElementById('loc_phone');
var type = document.getElementById('loc_type');
var cost = document.getElementById('loc_cost');
var rating = document.getElementById('loc_rating');
var gfc = document.getElementById('loc_gfc');
var ulEl = document.getElementById('user_reviews');
var details = document.getElementById('details');
var wholeList = document.getElementById('all_restaurants');
var restList = document.getElementById('rest_list');

// Checks if a restaurant is in local storage.
function checkLocalStorage() {
  if(localStorage.storedSelection) {
    details.style.display = 'block';
    selectedRest = JSON.parse(localStorage.storedSelection);
  } else {
    wholeList.style.display = 'block';
    showAllRestaurants();
  }
};

// Builds an element and adds it to another element
function buildNewElement(kind, content, where) {
  var x = document.createElement(kind);
  x.innerHTML = content;
  where.appendChild(x);
}

// loads restaurant information into the DOM.
var loadDetails = function() {
  if(selectedRest) {
    restName.textContent = selectedRest.name;
    address.textContent = selectedRest.address;
    phone.textContent = selectedRest.phone;
    for(var i = 0; i < selectedRest.type.length; i++) {
      buildNewElement('li', selectedRest.type[i], type);
    }
    rating.textContent = selectedRest.reviews[0].rating;
    cost.textContent = selectedRest.reviews[0].cost;
    gfc.textContent = selectedRest.reviews[0].code;
    for(var i = 0; i < selectedRest.reviews.length; i++) {
      buildNewElement('li', '<p>' + selectedRest.reviews[i].name + ' says:' + '</p>' + '<p>"' + selectedRest.reviews[i].comment + '"</p><p>Favorite thing to order: ' + selectedRest.reviews[i].faveDish + '</p>' , ulEl);
    }
  }
};

// Displays all of the restaurants in the array as a formatted list.
var showAllRestaurants = function() {
  restList.innerHTML = '';
  for(var i = 0; i < restaurants.length; i++) {
    buildNewElement('li', '<div class="tooltip"><h4>' + restaurants[i].name + '</h4><p>' + restaurants[i].address + '</p><p>' + restaurants[i].phone + '</p><p>' + restaurants[i].type + '</p><a href="location.html"><button>More Info</button></a></div>', restList);
  }
};

checkLocalStorage();
loadDetails();
```

We did a bunch of CSS work as well, and I'm still amused by our ridiculous logo (although the brackets are white on our site):

# &#x276e;&#x1f357;&#x276f;

**Things to Remember:**

* Get up. Move around.
* It's been an hour. Do it again.
