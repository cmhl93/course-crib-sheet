# New Variables - Creating, Updating, and Scoping


##  var Scoping Refresher

can reassign and update var

scope - where are these variables available to me?

var variables are function scope - only available inside the function they are created
var variables can also be globally scoped
should store variables local to a function
need something outside a function? return it and store that value in a variable
var variables not scoped to if statements (will leak to global variables)

let and const variables are scoped to the code block (will apply to if statments, functions, etc.)
  will not leak to global variables

##  let VS const

cannot redeclare const and let variables more than once
let variables can be updated
const variables cannot be updated
const attributes can change, cannot wipe out the whole object

const wes = Object.freeze(person);

##  let and const in the Real World

IIFE example:
  ```
  (function(){
    var name = 'wes';
  })();
  ```
//console returns blank
console.log(name); returns wes. No longer leaking into the global scope

instead,
  ```
  {
    const name = 'wes';
    console.log(name);
  }
  ```

for(let i = 0; i<10; i++){
  console.log(i);
  setTimeout(function(){
    console.log('The number is ' + i);
  }, 1000);
}

i value will be scoped each time

##  Temporal Dead Zone

var variables can be accessed before they are declared.  They return a value of undefined

const variables will return a reference error.

console.log(value);
var value = 'Deep Dish';

##  Is var Dead. What should I use?

use const by default
only use let if rebinding is needed
var shouldn't be used in ES6
