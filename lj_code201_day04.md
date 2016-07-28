## LJ Code 201 - Day 4
##### 6/16/16

Yesterday I felt like I was clinging madly to my Python knowledge, because I was very frustrated with the process of writing loops in js. Today was much better--I felt like I have a much better handle on things, although I'm sure that a lot of that was the pair/group programming work for the lab in the afternoon.  I was working with Derek and David, and we really blazed through the work.  I was even able to get the stretch goals done after we turned in the assignment, which was awesome.

CSS layout stuff continues to be frustrating. I really feel kind of directionless as far as knowing where to start with design decisions. I'm hoping that this will change once we starting talking more about design.

I'm still trying to get a handle on how relative and absolute positioning relate. (Although I haven't yet watched the stuff that Brian put in the Slack channel yet, and hopefully that will help.)

(ETA: I went over the relative/absolute review at
http://codepen.io/briannations/pen/OXXoxX and I get how to *use* relative and absolute together, but I'm still not clear on why.)

I felt yesterday like my solution to the lab for day three was unreasonably clunky and there should have been some way to simplify it--but the code review solution this morning was almost exactly like mine.

### Things I need to remember:
* get used to using ```console.log()``` within the code so that debugging is easier.
* when testing, test strings, negative numbers, zero, float vs int, numbers where strings are expected and vice versa.

### Bit of code I'm proud of:
(Putting the first 5 questions from lab into one function.)

```
// Array that holds questions 1-5
var myQuestions = ['Does Erica have 2 cats?', 'Is Erica from Seattle?', 'Does Erica hate cheese?', 'Has Erica lived in London?', 'Did Erica go to the University of Washington?'];

// Array that holds the answers to questions 1-5 in simple y/n format
var comparisonAnswers = [['y', 'yes','n', 'no'], ['y', 'yes', 'n', 'no'], ['n', 'no', 'y', 'yes'], ['n', 'no', 'y', 'yes'], ['y', 'yes', 'n', 'no']];

// Array that holds the responses to correct answers to questions 1-5
var correctAnswers = ['You\'re right! Erica has two cats, named Aonghus and Murdoch.\n\nShe calls them her \'Scottish Buddy-Cop Show\'.', 'Correct! Erica was born in Seattle, (although she grew up in Olympia,) and moved back in the mid-90\'s.', 'That\'s right! Erica does NOT hate cheese.\nWhat kind of person hates cheese!?', 'Right! Erica has never lived in London, although she has lived in Boston, MA, Chapel Hill, NC, and Aberdeen, Scotland.', 'She did! Erica is a third-generation Husky grad.'];

// Array that holds the responses to incorrect answers to questions 1-5
var wrongAnswers = ['Wrong! Erica does have two cats. One is orange and one is black, and both are awesome!', 'Wrong! Erica is, in fact, from Seattle.', 'Actually, Erica loves cheese, sorry.', 'Wrong! Erica loves London, but she\'s never lived there. Places she HAS lived: Boston, MA, Chapel Hill, NC, and Aberdeen, Scotland.', 'Wrong! Erica is actually a 3rd Generation UW grad!'];

function my5Questions() {
  // Loop that asks 5 questions
  for(var i = 0; i < myQuestions.length; i++) {
    var userAnswer = prompt(myQuestions[i]).toLowerCase();
    console.log('Question ' + i + ': userAnswer = ' + userAnswer);
    if(userAnswer === comparisonAnswers[i][0] || userAnswer === comparisonAnswers[i][1]) {
      alert(correctAnswers[i]);
      userTotalCorrect++;
    } else if(userAnswer === comparisonAnswers[i][2] || userAnswer === comparisonAnswers[i][3]) {
      alert(wrongAnswers[i]);
    } else {
      alert('That\'s not a valid answer. No points for you!');
    }
  }
}
```

Putting the answers into a multi-layer array and then pulling the answers out really helped me understand how to get info from that kind of array.
