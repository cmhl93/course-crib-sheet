# The Full JavaScript & ES6 Tutorial

# Document Contents
[JavaScript Language and Essentials](#javascript-language-and-essentials)

[Setting up an ES6 Development Environment](#setting-up-an-es6-development-environment)

[Understanding ES6 Essentials Part 1](#understanding-es6-essentials-part-1)

[Understanding ES6 Essentials Part 2](#understanding-es6-essentials-part-2)

[Classes and Prototypes](#classes-and-prototypes)

[Data Structures in ES6](#data-structures-in-es6)

[Closures in ES6](#closures-in-es6)

[ES6 Generators](#es6-generators)

[Asynchronous Programming, Promises, and APIs](#asynchronous-programming-promises-and-apis)

[ES7 and ES8 Proposals](#es7-and-es8-proposals)

##  JavaScript Language and Essentials

  * Syntax, Statements, and Data Types
    * syntax - set of rules that define how we write programs
    * Program - runs off services of instructions called statements
    * Data type - classification of data that defines what operations can be performed with it.
    
  ```
  // Comments are not excuted
  ```
  
  ```
  /*
  Multi-line
  Comment
  */
  ```
  
  * Variables and Assignment
  ``` 
  var a = 30;
   * var - the declaration, data type
    * a - identifier
    * = - assignment
    * 30 - value
    * Rules for naming identifiers: no reserved keywords, numbers, no spaces in between
    * Snake casing -> first_time
    * Camel casing -> firstTime
  ```
  * Operators
    * `+ - / *`
    * String concatentation
      `var a = "Good " + "day"; //Good Day`
    * Modulus - returns remainder
      `var b = 11 % 3; // 2`
      * Why? Useful checks on numbers, 2 = even, 1 = odd
      
  * Functions
    * A block of code that performs a specific task
    * Executed when called
    ```
    var print = function print(){
      console.log("Hi");
    }
    print();
    ```
    
  * Objects
    ```
    var dog = {
      name: 'Buddy',
      breed: 'Golden Retriever',
      weight: 60,
      bark: function(){
        console.log("Woof!");
      }
    };
    dog.bark(); //Woof!
    console.log(dog["breed"]); //Golden Retriever
    ```
  * Array and Array Methods  
    * Multiple values in one variable
    `var points = [25,16,7,9,31];`
    * add new element:
      `points.push(8); //[25,16,7,9,31,8]`
    ```
    var last = points.pop();
    console.log(points, last); //[25, 16, 7, 9] 31
    ```
    * arrays start at 0
    * length method returns the number of indexes
  
  * Boolean and Comparison Operators
    ```
    var a = 5 == 7;
    console.log(a); //false
    ```
    * <, >, >=, <=
  
  * If Statements
    ```
    var check = function(number){
      if(number % 2 == 0){
        console.log(number + " is even!");
      }else{
        console.log(number + " is odd.");
      }
    }
    check(4); //4 is even!
    check(7); //7 is odd.
    check(10); //10 is even!
    ```
  
  * Switch Statements
    ```
    var x = 13;
    
    switch(x){
      case 1:
        console.log("The number is one");
        break;
      case 2:
        console.log("The number is two");
        break;
      case 3:
        console.log("The number is three");
        break;
      default:
        console.log("The number is " + x);
        break;
    }
    ```
    
  * For Loops
    ```
    var names = ["Frodo", "Sam","Merry","Pippin"];
    for(var i=0; i<names.length; i++){
      console.log(names[i]);
    }
    /*
      Frodo
      Sam
      Merry
      Pippin
    */
    ```
    
  * While Loops
    ```
    var i = 0;
    while{i<names.length}{
      console.log(names[i]);
      i++;
    }
    
    do{
      console.log(names[i]);
      i++;
    }while(i < names.length);
    ```
    
##  Setting up an ES6 Development Environment

  * Presenting ES6, Babel, and Webpack
    * Babel and Webpack help create an ES6 development environment (Not all browsers support ES6)
  * Why we need Babel and Transpilers
    * What is a transpiler?
      * A transpiler reads code written in one language and produces the equivalent code in another
    * Why do we need transpilers?
      * Browsers only currently have widespread support of older JS
      * Transpilers convert advanced TypeScript and CoffeScript code back into the original JS
    * Babel
      * Transpiles es6 back into the supported pre-es6 JS
  * How does Babel work?
    `https://babeljs.io/`
  * Benefits of Webpack  
    * It bundles modules into one .js file
    * Comes with a dev-server
  * Setting Up with Webpack
    * Create project:
      `npm init -y`
      `npm install --save-dev webpack`
    * Create a new "build" folder
      * add `index.html`
      * add script to body tag named `bundle.js`
    * Create an "app" folder next to the "build" folder  
      * Create an `index.js` file
       * write javascript code
    * To get webpack to work, create a `webpack.config.js` file
       * add to the file:
      ```
      module.exports = {
       entry: ['./app/index.js'],
       output: {
        path: './build',
        filename: 'bundle.js'
       }
      }
      ```
    * In package.json file, change scripts code to:
      ```
      "scripts":{
       "build": "webpack"
      }
      ```
    * To test webpack, type npm build run into the console.  Should return "webpack"
    * Webpack updates when changing code? No, you need Babel as well.
     
  * Adding Babel to Webpack
    `npm install babel-core babel-loader webpack-dev-server babel-preset-es2015 babel-polyfill --save-dev`
     * Update `webpack.config.js` add this code after entry:
      ```
      module: {
      loaders: [
          {
            loader: 'babel-loader',
            test: /\.js$/,
            exclude: /node_modules/
          }
        ]
      },
      devServer: {
        port: 3000,
        contentBase: './build',
        inline: true
      }
      ```
      * Update `package.json':
      ```
      "script": {
        "build": "webpack",
        "start": "webpack-dev-server"
      },
      "babel": {
        "presets": ["es2015"]
      },
      ```
    * run `npm start` to get a server  
    * change browser to localhost: 3000 to check the automatic update
    
##  Understanding ES6 Essentials Part 1

##  Understanding ES6 Essentials Part 2

##  Classes and Prototypes

##  Data Structures in ES6

##  Closures in ES6

##  ES6 Generators

##  Asynchronous Programming, Promises and APIs

##  ES7 and ES8 Proposals
