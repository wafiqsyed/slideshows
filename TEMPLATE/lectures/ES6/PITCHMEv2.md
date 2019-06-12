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


---

- JSX



---
@title[Exercise 1]
#### Exercise 1

[@fa[external-link]](https://github.com/noucampdotorgRESTAPI2019/ES6/blob/master/exercises/ES6Ex1.md)
