# JavaScript

**Objects in JavaScript are just bags of properties. Properties are inherited from the prototype the object belongs to.**

### ```function``` 

```function``` is a keyword.

```function``` creates an object that can be **called/invoked**. This object is a new Function object. A function is an object that can be invoked.

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

#### Initialization

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

**Good Practice**
- close your brackets once they are opened
- parentheses around conditionals are not necessary but recommended

### Debugging Tips
- use ```console.log()``` to print stuff, also use the Console tab of the Chrome developer tools



