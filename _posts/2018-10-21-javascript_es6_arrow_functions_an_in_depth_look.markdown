---
layout: post
title:      "Javascript ES6 Arrow Functions: An In Depth Look"
date:       2018-10-22 00:49:19 +0000
permalink:  javascript_es6_arrow_functions_an_in_depth_look
---

The release of Javascript ECMA2015, or ES6, brought with it the addition of a plethora of new features and syntactical changes to the language. One of the most significant (and one of my favorite) is arrow functions, which offers a shortened, streamlined syntax over the traditional function expression. Below is the same function written in both the traditional and ES6 arrow function syntaxes.

ES5 function expression:

```
var nums = [2, 4, 6, 8];

var timesTen = function(num) {
    return num * 10;
}

nums.map(timesTen);  //  [20, 40, 60, 80]


```


ES6 arrow function:

```
const nums = [2, 4, 6, 8];

const timesTen = num =>  num * 10;

nums.map(timesTen);  //  [20, 40, 60, 80]


```

Looking at the differences between the two function syntaxes, the arrow function lacks the `function` keyword, instead extending a `=>` from the function's parameters to the body. In the ES6 syntax of this specific example, the body consists of a single statement that gets returned. Note that when using arrow functions, if the function's body is enclosed in only parentheses, `()` or is not enclosed in any brackets or parentheses, the statement following the arrow gets returned. If the function's body is enclosed in brackets, `{}`, the `return` keyword is required for the function to return. 

Another important difference of arrow functions is the handling of the `this` keyword. Take the following example:

ES5:

```
var friend = {
    name:  'Matt',
		age: 27,
		hobbies: ['soccer', 'hiking', 'reading'],
		displayHobbies: function() {
		    this.hobbies.forEach(function(hobby) {
				    console.log(this.name + ' enjoys ' + hobby + '.');
				    }.bind(this))
		    }
}

friend.displayHobbies();  
// Matt enjoys soccer.
// Matt enjoys hiking.
// Matt enjoys reading.
```

ES6:

```
const friend = {
    name:  'Matt',
		age: 27,
		hobbies: ['soccer', 'hiking', 'reading'],
		displayHobbies ()  {
		    this.hobbies.forEach((hobby) => {
				    console.log(this.name + ' enjoys ' + hobby + '.');
				    })
		    }
}

friend.displayHobbies();  
// Matt enjoys soccer.
// Matt enjoys hiking.
// Matt enjoys reading.
```
As you can see, the object method `displayHobbies()` is simplified greatly when using arrow functions. Also, in the old ES5 function, `.bind(this)` is required for the inner function of the object's method. This is because `this` in this inner function is equal to the window object, not the object `friend`, as it is for the outer object method itself. The ES6 arrow function fixes this complication: in the inner function, `this` refers to the object itself, so the bind is no longer required.


