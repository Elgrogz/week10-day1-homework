#JS Day 1 Homework

Go through each sample code and work out what the output will be and explain what happened.

### Episode 1
```js
var name = 'Keith';

var printName = function() {
  console.log('My name is ' + name );
};

printName();

Output: 'My name is Keith'.

```

### Episode 2
```js
score = 5;

var result = function() {
  var score = 3;
  return score;
};

console.log(result());


Output: 3. The global variable is set to 5 but the function prioritizes variables within it.

```

### Episode 3
```js
var myAnimals = ['Chickens', 'Cats', 'Rabbits'];

var listAnimals = function() {
  myAnimals = ['Ducks', 'Dogs', 'Lions'];
  for(var i=0;i<myAnimals.length; i++){
    console.log(i + ": " + myAnimals[i]);
  }
}

listAnimals();


Output:
1: Ducks
2: Dogs
3: Lions

myAnimals is set outside the function but javascript allows you to change variables after they have been declared. This is done within the function, and the loop iterates through the new array. The new variable is a global variable so it can be seen by other functions.

```

### Episode 4

```js
var suspectOne = 'Jay';
var suspectTwo = 'Val';
var suspectThree = 'Keith';
var suspectFour = 'Rick';

var allSuspects = function() {
  var suspectThree = 'Harvey'
  console.log('Suspects include: ' + suspectOne + ', ' + suspectTwo + ', ' + suspectThree + ', ' + suspectFour)
};

allSuspects();
console.log( 'Suspect three is:' + suspectThree );



Output: 
'Suspects include: Jay, Val, Harvey, Rick.'
'Suspect three is: Keith'

Suspect three is changed to Harvey within allSuspects() so when it is called Harvey is listed. However when outputting the variables we see the original suspect, Keith.


```

### Episode 5

```js
var detective = {
  name : 'Ace Ventura',
  pet : 'monkey'
};

var printName = function(detective) {
  return detective.name
};

var detectiveInfo = function() {
  detective['name'] = 'Poirot'
  return printName(detective);
};

console.log(detectiveInfo());

Output: 'Poirot'

detectiveInfo is called so the name is changed to Poirot and printName is called within that function so the name is printed to screen.


```

### Episode 6
```js
var murderer = 'rick';

var outerFunction = function() {
  var murderer = 'marc';

  var innerFunction = function() {
    murderer = 'valerie';
  }

  innerFunction();
}

outerFunction();
console.log('the murderer is ', murderer);


Output: 
'the murderer is rick'

outerfunction is called which in turn calls inner function so valerie is the murderer, however it is not saved to a variable and it isn't outputted to screen. The next line prints out the original variable as it is left outside the function.

```

### Episode 7 - Make up your own episode/s!

var theHardyBoys = ["Frank", "Joe"];

var whippersnappers = function() {
  for (boy of theHardyBoys) {
    return boy + " has a knack for solving mysteries!"
  }
}

console.log(theHardyBoys());


// Episode 8 

var solveMystery = function(murderer) {
  if (murderer.length > 4) {
  return theHardyBoys[0] + " has solved the mystery!"
  } else {
    return theHardyBoys[1] + " has solved the mystery!"
  }
}


var murderer = outerFunction();
console.log(solveMystery(murderer));



// Episode 9

function getWeapons() {
  var weapons = [];
  for (var i = 0; i < arguments.length; i++) {
    weapons[i] = arguments[i];
  }
}

console.log(getWeapons("Revolver", "Candlestick", "Rope", "Lead Pipe", "Knife", "Wrench"));




