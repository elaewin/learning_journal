## LJ Code 201 - Day 3
##### 6/15/16

Today's lab was very frustrating, mostly because I was *so close* to figuring out what was wrong, and knew it, and couldn't figure out what was wrong. Fortunately, I got it to work eventually, with help. I still feel like my code for question 7 is much more complicated than it needs to be, but I can't figure out how to simplify it.


### The frustrating bit:
```
// Asks the user to guess answers stored in an array.
var answersArray = ['sushi',
                    'ice cream',
                    'lemon bars',
                    'mac and cheese',
                    'pomegranates',
                    'cheese'
                  ];
var tries = 0;
var guessedRight = false;

while (tries < 6 && guessedRight === false) {
  var answer7 = prompt('Guess one of Erica\'s favorite foods! (You have ' + (6 - tries) + ' guesses left.)').toLowerCase();
  for (var i = 0; i < answersArray.length; i++) {
    if (answer7 === answersArray[i]) {
      guessedRight = true;
      correctAnswers += 1;
      alert('You guessed one!\n\nErica\'s favorite foods are:\nsushi\nice cream\nlemon bars\nmac and cheese\npomegranates\ncheese');
      break;
    }
  }
  if (guessedRight === false) {
    alert('Nope, that isn\'t one of Erica\'s favorite foods.');
    tries += 1;
  }
}
if (guessedRight === false) {
  alert('Alas, you ran out of guesses!\n\nErica\'s favorite foods are:\nsushi\nice cream\nlemon bars\nmac and cheese\npomegranates\ncheese');
}
```
