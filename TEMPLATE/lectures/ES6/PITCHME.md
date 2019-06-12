---?color=black
@title[Title]

@snap[west headline text-white span-70]
ECMAScript 6 (ES6)
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend


---
@title[Contents]
### Contents

@ol[](false)
- What is ECMAScript 6 (ES6)?
- Babel.js Transpiler
- ES6 Syntax
- ES6 Functions
- ES6 Classes
- Modules & import & export


---
@title[Contents]
### Contents

@ol[](false)
- **What is ECMAScript 6 (ES6)?**
- Babel.js Transpiler
- ES6 Syntax
- ES6 Functions
- ES6 Classes
- Modules & import & export


---
@title[What is jQuery?]
### What is ECMAScript 6 (ES6)?

@ul[list-bullets-black](true)
- It's a _version_ of JavaScript
- 1995 - JavaScript begins
- ECMA in charge of new JavaScript specifications
- European Computer Manufacturer Association (ECMA)
- In 2015 ECMA release ECMAScript 6 (ES6) (ECMAScript2015)
- What's new...

@ulend

---
@title[What is ES6?]
### What's new in ES6?

@ul[list-bullets-black](true)
- Declare variables using keywords:
  - ``let``
  - ``const``
- Functions:
  - arrow functions ``=>``
  - with default parameters
- Classes
- These are features you might want to start using, but...

@ulend

---
@title[ES6 Browser Support]
### ES6 Browser Support

@ul[list-bullets-black](true)
- Browsers **DO NOT** automatically support new JavaScript features
- New features will not work on most existing browsers
- Features may work on new browser versions
- For example...
@ulend

---
@title[ES6 Browser Support]
### ES6 Browser Support

*Function Default Parameter* feature doesn't work in IE11

```javascript
<html>  
<head>
    <script type="text/javascript">    
        // supported in Chrome71 but not IE11
        function hello(name="Joe Bloggs") {
            console.log(`hello ${name}`);
        }
        hello();
        hello('tomo');
    </script>
</head>
</html>
```

[@fa[external-link]](http://localhost/ES6/helloES6_1.html)

---
@title[ES6 Browser Support]
### ES6 Browser Support

@ul[list-bullets-black](true)
- Check [here](http://kangax.github.io/compat-table/es6/) for compatibility
- The solution is to always use a *transpiler*
- You can _transpile_ new code to previous code versions
- ES6 code can be transpiled into ES5
- [Babel.js](https://babeljs.io/) is a transpiler_
@ulend

---
@title[Contents]
### Contents

@ol[](false)
- What is ECMAScript 6 (ES6)?
- **Babel.js Transpiler**
- ES6 Syntax
- ES6 Functions
- ES6 Classes
- Modules & import & export



---
@title[Babel.js]
### Babel.js Transpiler

@ul[list-bullets-black](true)
- ES6 code -> ES5 code
- Babel.js used with React.js
- For simplicity we'll use a [in browser version](https://cdnjs.com/libraries/babel-standalone)
- _Webpack_ is another better solution_

@ulend

---
@title[ES6 Browser Support]
### ES6 Browser Support

_Function Default Parameter_ feature doesn't work in IE11

```html
<html>  
<head>
<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
  <script type="text/babel">    
    function hello(name="Joe Bloggs") {
      console.log(`hello ${name}`);
    }
    hello();
    hello('tomo');
  </script>
</head>
</html>
```

[@fa[external-link]](http://localhost/ES6/helloES6_2.html)

---
@title[Contents]
### Contents

@ol[](false)
- What is ECMAScript 6 (ES6)?
- Babel.js Transpiler
- **ES6 Syntax**
- ES6 Functions
- ES6 Classes
- Modules & import & export



---
@title[Contents]
### ES6 Syntax

@ul[](false)
- ``let`` keyword
- ``const`` keyword
- Template Strings
@ulend

---
@title[ES6 Syntax]
### let keyword

@ul[list-bullets-black](true)
- ``var`` declares variables with a global scope
- ``let`` declares variables with _block scope_

@ulend

---
@title[ES6 Syntax]
### var keyword

```html
<html>  
<head>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
  <script type="text/babel">   
    var age=20;     
    if(age) {
      var age=30;
      console.log(age); // what is printed?
    }    
    console.log(age); // what is printed?
  </script>
</head>
</html>
```

[@fa[external-link]](http://localhost/ES6/let1.html)


---
@title[ES6 Syntax]
### let keyword

```html
<html>  
<head>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
  <script type="text/babel">   
    var age=20; 
    if(age){
      let age=30;
      console.log(age); // what is printed?
    }
    console.log(age); // what is printed?
  </script>
</head>
</html>
```

[@fa[external-link]](http://localhost/ES6/let2.html)

..
  ---
  @title[Hoisting]
  ### Hoisting

  ```html
  <html>  
  <head>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
      <script type="text/babel">          
          if(age){
              console.log(age); // what is printed?
          }        
          console.log(age); // what is printed?

          var age=20; 
      </script>
  </head>
  </html>
  ```

  [@fa[external-link]](http://localhost/ES6/let3.html)


---
@title[ES6 Syntax]
### const keyword

@ul[list-bullets-black](true)
- The ``const`` keyword creates a read-only reference to a value
- ``const`` references can not be reassigned...
@ulend

---
@title[ES6 Syntax]
### const keyword

```html
<html>  
<head>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
  <script type="text/babel">   
    const PI = 3.141592653589793;
    // PI = 3.14;    // This will give an error
    // PI = PI + 10;   // This will also give an error
    console.log(`PI = ${PI}`);
  </script>
</head>
</html>
```

@ul[list-bullets-black](true)
- But, you can change the value of constant objects and arrays...
@ulend

[@fa[external-link]](http://localhost/ES6/const1.html)

---
@title[ES6 Syntax]
### const keyword

```html
<html>  
<head>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
  <script type="text/babel">   
    const club={"name":"FCB", "sponsor":"Rakuten"};
    //const club={"name":"FCB","sponsor":"Nike"}; // ERROR
    club.sponsor="Nike";  // OK
    console.log(club);

    const cars = {"Audi", "BMW", "Skoda"};
    cars[2]="VW";  // OK
    console.log(cars);
  </script>
</head>
</html>
```

[@fa[external-link]](http://localhost/ES6/const2.html)



---
@title[Template Strings]
### Template Strings

@ul[list-bullets-black](false)

- We've already seen *Tempate Strings*
- Convenient for printing variables
@ulend

```javascript
var age = 20;
console.log(`age = ${age}`); //template string & expression

console.log("age = " + age); //concatenation
```


---
@title[Contents]
### Contents

@ol[](false)
- What is ECMAScript 6 (ES6)?
- Babel.js Transpiler
- ES6 Syntax
- **ES6 Functions**
- ES6 Classes
- Modules & import & export


---
@title[Contents]
### ES6 Functions

@ul[](false)
- Default Function Parameters
- Function Declarations
- Function Expressions
- Arrow Functions
@ulend


---
@title[Contents]
### ES6 Functions

@ul[](false)
- **Default Function Parameters**
- Function Declarations
- Function Expressions
- Arrow Functions
@ulend

---
@title[Default Function Parameters]
### Default Function Parameters


```javascript
<html>  
<head>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
  <script type="text/babel">   
    function add(x,y) {
        return x+y;
    }
    console.log(add(1,2)); // prints?
  </script>
</head>
</html>
```

[@fa[external-link]](http://localhost/ES6/default1.html)

---
@title[Default Function Parameters]
### Default Function Parameters


```javascript
<html>  
<head>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
  <script type="text/babel">   
    function add(x,y) {
        return x+y;
    }
    console.log(add()); // prints?
  </script>
</head>
</html>
```

[@fa[external-link]](http://localhost/ES6/default2.html)

---
@title[Default Function Parameters]
### Default Function Parameters

@ul[](false)
- You can give function parameters default values
@ulend

```javascript
<html>  
<head>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.js"></script>
  <script type="text/babel">   
    function add(x=0,y=0) {
        return x+y;
    }
    console.log(add());    // prints?
    console.log(add(1,2)); // prints?
    console.log(add(2)); // prints?
  </script>
</head>
</html>
```
[@fa[external-link]](http://localhost/ES6/default3.html)


---
@title[JavaScript Functions]
### JavaScript Functions

@ul[](true)
- JavaScript functions are defined with the ``function`` keyword
- You can use a function @size[1.5em](declaration) or a function @size[1.5em](expression)
- For example...


---
@title[Contents]
### ES6 Functions

@ul[](false)
- Default Function Parameters
- **Function Declarations**
- **Function Expressions**
- Arrow Functions
@ulend


---
@title[Functions Declarations]
### Function Declarations

@ul[](false)
- Declared functions have the following syntax:
@ulend

```javascript
function add(x,y)
{
  return x+y;
}

var ans = add(1,2); // ans=3
```


---
@title[Function Expressions]
### Function Expressions

@ul[](false)
- Function expressions have the following syntax:
@ulend

```javascript
var add = function(x,y)
{
  return x+y;
};

var ans = add(1,2); // ans=3
```

@ul[](true)
- The function above is actually an anonymous function assigned to variable ``add``
@ulend


---
@title[Function Declaration v Expression]
### Function Declaration v Expression

@ul[](true)
- They are more @size[1.5em](similar) than different
- You call them the same way
- They are just different @size[1.5em](styles) of writing functions
- But, you'll see function expression style more frequently from here
- Which one you chose is almost entirely a matter of personal taste
- But there are some differences...
@ulend


---
@title[Function Declaration v Expression]
### Function Declaration v Expression

@ul[](false)
- Function declarations execute @size[1.5em](before) function calls
- This works..
@ulend

```javascript
console.log(add(1,2)); // OK! add was HOISTED

function add(x,y) { 
  return x+y;
}
```
@[3-5](1st)
@[1](2nd)
@[3-5,1]()


@ul[](true)
- This is known as **hoisting**
@ulend

[@fa[external-link]](http://localhost/ES6/function2.html)


---
@title[Hoisting]
### Hoisting
@ul[](true)
- JavaScript by default moves all @size[1.5em](declarations) to the top of the current scope
- This includes variable and function declarations
- Because of this, JavaScript @size[1.5em](functions) can be called before they are declared
- and JavaScript @size[1.5em](variables) can be assigned values before they are declared
- Declarations made with ``let`` or ``const`` are not hoisted!
 
@ulend


---
@title[Function Declaration v Expression]
### Function Declaration v Expression

@ul[](true)
- Function expressions execute only when the interpreter reaches them
- Function expressions have no name - anonymous
- For example...
@ulend

```javascript
console.log(add(1,2)); // ERROR! add not loaded yet
        
var add = function (x,y) { 
  return x+y;
}

console.log(add(1,2)); // OK! add loaded
```
@[1](1st)
@[1,3-5](2nd)
@[1,3-5,7](3rd)

@ul[](true)
- Functions expressions are not hoisted
@ulend


---
@title[Contents]
### ES6 Functions

@ul[](false)
- Default Function Parameters
- Function Declarations
- Function Expressions
- **Arrow Functions**
@ulend


---
@title[Arrow Functions]
### Arrow Functions

@ul[](true)
- Arrow functions are an @size[1.5em](abbreviated) syntax for function expressions
- You don't need:
  - the ``function`` keyword
  - the ``return`` keyword
  - the curly brackets
- It's a new token **=>** 
- For example, let's look at the ``add()`` function again...
@ulend


---
@title[Arrow Functions]
### Arrow Functions

@ul[](false)
- Regular ``add()`` function expression
@ulend

```javascript     
var add = function (x,y) { 
  return x+y;
}

console.log(add(1,2));
```

---
@title[Arrow Functions]
### Arrow Functions

@ul[](false)
- Abbreviated arrow function
@ulend

```javascript     
var add = (x,y) => { 
  return x+y;
}

console.log(add(1,2));
```
@ul[](true)
- Because this is a single statement function you could further abbreviate to...
@ulend

[@fa[external-link]](http://localhost/ES6/arrow1.html)

---
@title[Arrow Functions]
### Arrow Functions

@ul[](false)
- Abbreviated arrow function
@ulend

```javascript     
var add = (x,y) => x+y;

console.log(add(1,2));
```
@ul[](true)
- I'll continue to use ``return`` and curly braces for clarity
@ulend

[@fa[external-link]](http://localhost/ES6/arrow2.html)


---
@title[Map Function]
### map Function

@ul[](true)
- ``map()`` is used with arrays
- ``map()`` it creates a new array from an existing array using a function
- Let's see an example...
@ulend

---
@title[Map Function]
### map Function

```javascript     
var numbers = [1,2,3,4,5];

var sqr = function(num) {
  return num*num;
}

var values = numbers.map(sqr);
console.log(values);
```
@[1](numbers array)
@[1,3-5](function to apply to numbers array)
@[1,3-5,7](map each numbers value to sqr function)
@[*]


@ul[](true)
- Often you'll see arrow function syntax used...
@ulend

[@fa[external-link]](http://localhost/ES6/map1.html)




---
@title[Map Function]
### map Function

```javascript     
var numbers = [1,2,3,4,5];

var values = numbers.map((num) => { return num*num; });
console.log(values);
```
@ul[](true)
- We could abbreviate more with this...
@ulend

[@fa[external-link]](http://localhost/ES6/map2.html)

---
@title[Map Function]
### map Function

```javascript     
var numbers = [1,2,3,4,5];

var values = numbers.map(num => num*num);
console.log(values);
```
@ul[](true)
- This works because it is a single statement function
- But, I'll use ``return`` and curly braces from here on
@ulend

[@fa[external-link]](http://localhost/ES6/map3.html)




---
@title[Contents]
### Contents

@ol[](false)
- What is ECMAScript 6 (ES6)?
- Babel.js Transpiler
- ES6 Syntax
- ES6 Functions
- **ES6 Classes**
- Modules & import & export
@olend


---
@title[ES6 Classes]
### ES6 Classes

@ol[](false)
- Create a Class
- Constructor & Properties
- Methods
- Inheritance
- Getters & Setters
@olend


---
@title[Classes]
### Create a Class

```javascript     
class Person {    
}

var person = new Person();    
```
@[1-2](Declare class)
@[1-2,4](Create an instance of class)
@[*]()

@ul[](true)
- Class declarations are not hoisted
- So, declare first and then use it
@ulend


---
@title[Classes]
### Class Constructor & Properties 

```javascript     
class Person {    
  constructor(name,age) {
    this.name=name;
    this.age=age;
  }
}
var person = new Person("Joe",21);    
console.log(person);
```
@[1-6](Use constructor to initialise properties)
@[1-6,7,8](Create an instance of Person)
@[*]()

@ul[](true)
- The ``constructor`` method creates and initialises class properties
@ulend

[@fa[external-link]](http://localhost/ES6/class2.html)

---
@title[Classes]
### Class Methods

```javascript     
class Person {    
  constructor(name,age) {
    this.name=name;
    this.age=age;
  }
  info(){
    console.log(`[name=${this.name}, age=${this.age}]`); 
  }
}
var person = new Person("Joe",21);    
person.info();    
```
@[6-8](an info method)
@[6-8,10-11](call it)
@[*]()

[@fa[external-link]](http://localhost/ES6/class3.html)

---
@title[Classes]
### Class Inheritance

@ul[](false)
- Let's extend from `Person`
@ulend

```javascript     
class Student extends Person{
  constructor(name, age){
    super(name,age);
  }
}
var student = new Student("Mary",21);    
student.info();  // info() inherited from Person
```
@[1,5](Student extends Person)
@[1,5,2-4](Student constructor)
@[1,5,2-4,6-7](Create student object and call method info)
@[*]()

[@fa[external-link]](http://localhost/ES6/class4.html)

---
@title[Classes]
### Class Getters & Setters

```javascript     
class Person {    
    constructor(name,age) {
        this.name=name;this.age=age;
    }
    info(){console.log(`[name=${this.name}, age=${this.age}]`);}
    get getAge(){
        return this.age; 
    }
    set setAge(age){
        this.age=age;
    }
}
var person = new Person("Joe",21);    
console.log(person.getAge);  // no parentheses
person.setAge=22;            // no parentheses
person.info(); 
```
@[6-8](getter)
@[9-11](setter)
@[*]()

[@fa[external-link]](http://localhost/ES6/class5.html)


---
@title[Contents]
### Contents

@ol[](false)
- What is ECMAScript 6 (ES6)?
- Babel.js Transpiler
- ES6 Syntax
- ES6 Functions
- ES6 Classes
- **Modules & import & export**
@olend

---
@title[import]
### import & export

@ul[](true)
- ES6 supports the `import` keyword
- import is used to import @size[em](functions), @size[em](classes), etc. exported by another module
- For example, let's put our `Person` class in a module of it's own...
@ulend

---
@title[import]
### import & export

```javascript     
// Person.js
class Person {    
  constructor(name,age) {
    this.name=name;
    this.age=age;
  }
  info(){
    console.log(`Person: [name=${this.name}, age=${this.age}]`);
  }
}
```


@ul[](true)
- We must `export` the class to outside modules...
- We can `export` in 2 ways:
  - **default**
  - **named**
@ulend

---
@title[import]
### export default

```javascript     
// Person.js
export default class Person {    
  constructor(name,age) {
    this.name=name;
    this.age=age;
  }
  info(){
    console.log(`Person: [name=${this.name}, age=${this.age}]`);
  }
}
```
@[2,10](Person is default export)
@[*]()

@ul[](true)
- So we import like this...
@ulend

---
@title[import]
### import default

```javascript     
// testPerson.js
import Person from './Person.js';

var person = new Person("Joe",21);    
person.info();    
```
@[2](import Person class to Person reference)
@[*]()

@ul[](true)
- Only one class/function in a module can be the `default`
- We can export things as **named** too...
@ulend

---
@title[import]
### export named

```javascript     
// Person.js
export default class Person {    
  ...
}
class Student extends Person {
    constructor(name, age, studentNumber){
        super(name,age);
        this.studentNumber=studentNumber;
    }
}
export { Student };
```
@[2-4](Person is the default export)
@[11](Student is a named export)
@[*]()

@ul[](true)
- Export as many named classes/functions as you like
- We import like this...
@ulend

---
@title[import]
### import named

```javascript     
// testPerson.js
import Person from './Person.js';
import {Student} from './Person.js';

var person = new Person("Joe",21);    
person.info();  

var student = new Student("Joey",21,"00909693");    
```
@[3](import Student class)
@[3,8](use Student class)


@ul[](true)
- You can export @size[1.5em](functions) too...
@ulend

---
@title[import]
### export named functions

```javascript     
// Person.js
export default class Person {    
  ...
}
class Student extends Person {
  ...
}
function sqr(num){
  return num*num;
}
export { Student , sqr };
```
@[8,9,10](sqr function)
@[8,9,10,11](export it as a named function)
@[*]()

@ul[](true)
- import like this...
@ulend

---
@title[import]
### import function

```javascript     
// testPerson.js
import Person from './Person.js';
import {Student} from './Person.js';
import {sqr} from './Person.js';

var person = new Person("Joe",21);    
person.info();  

var student = new Student("Joey",21,"00909693");    
student.info();    

console.log(sqr(3));
```
@[4](import sqr function)
@[4,12](use sqr function)

---
@title[import]
### import v require() function

@ul[](false)
- Previously, we did this:
@ulend
```javascript
var express = require('express');
```

@ul[](false)
- now we can do this:
@ulend
```javascript
import express from 'express';
```



---?color=black
@title[Title]

@snap[west headline text-white span-70]
ES6
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
