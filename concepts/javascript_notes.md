# JavaScript

**Objects in JavaScript are just bags of properties. Properties are inherited from the prototype the object belongs to.**

In a nutshell, Object in JavaScript is just key-value pairs stored in a Hash. The difference between property and a method is that -- a property is a **value** stored in the hash key, whereas method is a **function** stored in hash key.
```
var person = {
  name: "John Doe",
  sayHello: function() {
        console.log("hello");
  }
}
```
In this code sample.

```name``` is the property of object ```person```, it stored String "John Doe", you can access it via dot notation ```person.name```.
```sayHello``` is the method of object, and it is a function. You can also access it using dot notation ```person.sayHello()```. Notice that sayHello is just a function, and function invocation requires you to use () here.

### ```function``` 

```function``` is a keyword.

```function``` creates an object that can be **called/invoked**. This object is a new Function object. A function is an object that can be invoked. The case of function names in JavaScript has no effect on how they run.

Example of JavaScript function object:
```
var bark = function() {
  return 'Woof';
}
bark(); //invoking the function will return 'Woof'

var barkWithName = function(name) {
  return name + 'says Woof';
}
barkWithName('Frank'); //invoking the function with argument will return 'Frank says Woof'
```
Parantheses must be included for function invocations even if there are no arguments.
```return``` must be explicitly stated..

**Anonymous functions** can be used in JavaScript. Similar to blocks in Ruby.
```
['one', 'two', 'three'].forEach(function(number) {
  console.log(number);
}); // prints each number one after another
```
Anonymous functions passed to a named function are referred to as a **callback**.
```
var callback = function(arg) {
  console.log(arg);
};
['one', 'two', 'three'].forEach(callback); // prints each number one after another
```

### ```class``

```classs ``` is a keyword introduced in ES6.

```class``` defines and instantiates a object factory, which in turn can instantiate objects of said ```class```.

To define and instantiate a class in JavaScript:
```
class Dog {

}

var dog = new Dog();
```

JavaScript classes are a type of ```function```.

#### Constructor

Use a ```constructor``` method to 'initialize' an object with an instance variable:
```
class Dog {
  constructor(breed) {
    this.breed = breed;
  }
}

var frank = new Dog('Sausage')
```
Inside the function, ```this``` is the newly created object.

##### Example from [Skill Workshop](https://github.com/rjkviegas/skills-workshops/blob/master/week-5/encapsulation_with_constructor_and_prototype_pattern/exemplar_dont_read_until_after_workshop/questions.md)
```
function Thing() {
  // these three lines are run automatically by JS because the `new`
  // keyword was used, even though they don't appear in your code:
  // var thing = {};
  // thing.__proto__ = Thing.prototype;
  // return thing;
};

Thing.prototype.setName = function(name) {
  this._name = name;
}

var thing = new Thing();
thing.setName("Isla");
```

What's cool is all three lines inside the constructor above happen automatically.

When thing.setName("Isla") is run, JavaScript finds out which setName to run. It looks first on thing itself and finds nothing. Then it looks on the object at thing.__proto__. thing.__proto__ points at the Thing.prototype object. So JavaScript finds the setName function and runs it. This is the essence of prototypal inheritance.

Imagine we change the code to this:
```
function Thing() {
  // these three lines are run automatically by JS because the `new`
  // keyword was used, even though they don't appear in your code:
  // var thing = {};
  // thing.__proto__ = Thing.prototype;
  // return thing;
};

Thing.prototype.setName = function(name) {
  this._name = name;
}

var thing = new Thing();

// we've added these three lines of code:
thing.setName = function(name) {
  return "WHATEVER you're not the boss of me";
};

thing.setName("Isla");
```
When the prototypal lookup happens, it first checks thing itself and immediately finds a setName() function. This is the one it calls, so it never sees the one on Thing.prototype.

#### Method

**JSC**
Cannot use ? at the end of the method, instead put 'is' at the beginning.

To define a method:
```
class Dog {
  bark(name) {
    console.log(name + ' says Woof!');
  }
}
```
The ```bark``` method is now stored in ```Dog.prototype```. 

This can be displayed by:
```
var fido = new Dog();
console.log(fido); //=> Dog {}
                        > __proto__: Object
```

Prefixing a method with an underscore denotes it to be a ```private``` method.
```
class Banana {
  _myPrivsteMethod() {
    // ...
  }
}
```

### ```var```

Within a function ```var``` creates a local variable, "no var" will look up the scope chain until it finds the invariable or hits the global scope (at which point it will create it, and global variables are not usually a good idea):

```
// These are both globals
var foo = 1;
bar = 2;

function()
{
    var foo = 1; // Local
    bar = 2;     // Global

    // Execute an anonymous function
    (function()
    {
        var wibble = 1; // Local
        foo = 2; // Inherits from scope above (creating a closure)
        moo = 3; // Global
    }())
}
```

**JSC**

thisIsCamelCase not underscores
``` var theMeaningOfLife = 42```

### Constants

ES6 introduced ```const``` keyword for "immutable variables". This means the variable cannot be reassigned new content BUT the assigned content can be altered.

In older versions, constants naming convention would be ALL CAPS.

```Dog.prototype.NUMBER_OF_LEGS = 4;````

### Arrays
```
var animals = ['cat', 'dog' 'horse']

//JS version of Ruby's each
animals.forEach(function(animal) {
  alert('Old McDonald has a ' + animal);
})

animals[0]; //=> 'cat'
animals[2]; //=> 'horse'

//JSC
animals.push('snake');
animals; //=> ['cat', 'dog' 'horse', 'snake']

//JS version of Ruby's include?
if(animals.indexOf('cow') > -1 {
  alert('Mooo');
})
```
### Falsy

There are only six falsey values in JavaScript:
1. ```undefined```
2. ```null``` 
3. ```NaN```
4. ```0```
5. ```""``` (empty string)
6. ```false```

**Good Practice**
- close your brackets once they are opened
- parentheses around conditionals are not necessary but recommended

### Debugging Tips
- use ```console.log()``` to print stuff, also use the Console tab of the Chrome developer tools

### Miscellaneous

```"use strict";``` Defines that JavaScript code should be executed in "strict mode". ***It helps you to write cleaner code.***

#### Not Allowed In ```'use strict';``` mode:
- Using a variable, without declaring it
- Using an object, without declaring it
- Deleting a variable (or object)
- Deleting a function
- Duplicating a parameter name
- The ```this``` keyword in functions refers to the object that called the function. If the object is not specified, functions in ```strict``` mode will return ```undefined``` and functions in normal mode will return the global object (window)

### Jasmine

#### Examples
```
expect(airport.planes()).toContain(plane);
expect(airport.planes()).toEqual([]);
expect(airport.clearForLanding).toHaveBeenCalledWith(plane);
expect(airport.isStormy()).toBeFalsy();

expect(function() { plane.takeOff(); }).toThrowError('cannot take off during storm');
```

##### Spies

Jasmine has test double functions called spies. 
A spy can stub any function and tracks calls to it and all arguments. 
A spy only exists in the describe or it block in which it is defined, and will be removed after each spec.

```
airport = jasmine.createSpyObj('airport'); // bare spy
airport = jasmine.createSpyObj('airport', ['clearForLanding', 'clearForTakeOff']); // mocking using object with multiple properties
spyOn(airport, 'isStormy').and.returnValue(true); // 
```
