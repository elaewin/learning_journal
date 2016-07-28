## LJ Code 201 - Day 18
##### 7/07/16

Typos are the bane of my existence.

### Code Sample I'm Proud of and that Vexed Me Today
This is the js that I wrote today to add a new restaurant to our project. Originally it was going to have a section to add a review as well, but it took so long to get the new restaurant part working that I decided not to keep that part, even though a lot of it was already written.

```
'use strict';

var form = document.getElementById('add_restaurant');
var cuisineType1 = document.getElementById('cuisine1');
var cuisineType2 = document.getElementById('cuisine2');
var cuisineType3 = document.getElementById('cuisine3');

function handleAddRest(event) {
  event.preventDefault();

  var cuisinesArray = [];

  console.log(event);
  console.log('this is a string');

  var newName = event.target.rest_name.value;
  var newAddress = event.target.rest_addy.value;
  var newPhone = event.target.rest_phone.value;
  var newVegan = event.target.vegan_check.value;
  var newImage = event.target.rest_image.value;
  var addType1 = event.target.cuisine1.value;
  var addType2 = event.target.cuisine2.value;
  var addType3 = event.target.cuisine3.value;
  var newType = event.target.new_cuisine.value;

  if(!checkVsFoodTypes(newType) && newType !== '') {
    cuisinesArray.push(newType);
  };

  if(addType2 === addType1) {
    if(addType1 && addType1 !== 'Add a kind of food') {
      cuisinesArray.push(addType1);
    };
  } else {
    if(addType1 && addType1 !== 'Add a kind of food') {
      cuisinesArray.push(addType1);
    }
    if(addType2 && addType2 !== 'Add a kind of food'){
      cuisinesArray.push(addType2);
    }
  }

  if(addType3 !== addType1 && addType3 !== addType2) {
    if(addType3 && addType3 !== 'Add a kind of food') {
      cuisinesArray.push(addType3);
    }
  }

  cuisinesArray.sort();
  console.log('cuisinesArray', cuisinesArray);

  addNewRest(newName, newAddress, newPhone, cuisinesArray, newVegan, 'img/delicious.jpg');
};

//Build food type dropdowns
var populateTypeList = function(target) {
  typesOfFood.sort();
  for(var i = 0; i < typesOfFood.length; i++) {
    buildNewElement('option', typesOfFood[i], target, 'value', typesOfFood[i]);
  }
};

// Check if a type of food is already in the typesOfFood array
var checkVsFoodTypes = function(input) {
  for(var i = 0; i < typesOfFood.length; i++) {
    if(typesOfFood[i] === input.toLowerCase()) {
      return true;
    }
  }
  return false;
};

form.addEventListener('submit', handleAddRest);

populateTypeList(cuisineType1);
populateTypeList(cuisineType2);
populateTypeList(cuisineType3);

```

**Things to Remember:**

* Check ABOVE where something is displaying oddly in Atom.
* So. Many. Typos. Are inevitable, and having someone else look over the code helps a hell of a lot.
* I need to remember to be more patient with myself when debugging--or just get someone to help me out, because I get really damn frustrated.
* event listeners on a submit button have to listen for submit, NOT click.
