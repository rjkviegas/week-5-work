# JavaScript

Objects in JavaScript are just bags of properties. Properties are inherited from the prototype the object belongs to.

### ```function``` 

```function``` is a keyword.

```function``` creates an object that can be **called** (invoke may be a better word to use). This object is a new Function object.

Example of JavaScript function object:
```
var bark = function() {
  return 'Woof';
}

bark();
```
Parantheses must be included even if there are no arguments.
```return``` must be used explicitly.

Anonymous (no name) functions can be used in JavaScript. Like blocks in Ruby.
Anonymous functions passed to a named function are referred to as a **callback**.

### ```class``

```classs ``` is a keyword introduced in ES6.

```class``` defines and instantiates a object factory, which in turn can instantiate objects of said ```class```.

To define and instantiate a class in JavaScript:
```
class Dog {

}

var = dog = new Dog();
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

var barney = new Dog('Pug')
```
Inside the function, ```this``` is the newly created object.

#### Method

To define a method in JS:
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
console.log(fido);

### JavaBuzz

Notes:

- close your brackets once they are opened.


