# Object oriented programming

## Introduction to OOP
### What is OOP and why is it important?
OOP stands for Object-Oriented Programming, which is a programming paradigm that focuses on organizing code into objects that contain data and methods. In OOP, objects are instances of classes, which define the properties and behaviors of the objects.

OOP is important because it allows developers to write code that is more modular, reusable, and easier to maintain. By encapsulating data and behavior into objects, OOP makes it possible to create complex systems that are easier to understand and modify. OOP also makes it possible to write code that is more secure, as objects can be designed to only expose certain methods and properties to the outside world, while keeping other data and behavior private. Additionally, OOP can improve code performance, as objects can be designed to be more efficient than procedural code in certain scenarios.

### Key concepts in OOP: encapsulation, inheritance, polymorphism

Object-oriented programming (OOP) is a programming paradigm that revolves around the use of objects that contain data and methods to manipulate that data. The following are the key concepts in OOP:

1. Encapsulation: This is the practice of grouping data and methods that operate on that data within a single unit called a class. The class controls the access to the data, which can only be accessed through the methods defined in the class. Encapsulation helps to keep the code organized, maintainable, and secure by hiding the implementation details from the outside world.

2. Inheritance: This is the concept where a class can inherit properties and methods from another class. The class that inherits the properties and methods is called the child class, while the class from which it inherits is called the parent class or super class. Inheritance promotes code reuse, reduces code duplication, and makes the code more manageable.

3. Polymorphism: This is the ability of objects of different classes to be used interchangeably. In other words, different objects can respond to the same method call in different ways. Polymorphism allows for more flexibility and extensibility in the code.

Overall, these concepts help to make the code more modular, easier to maintain, and more scalable.

### Understanding objects in OOP in Javascript

In traditional object-oriented programming languages like Java or C++, objects are created by defining a class, which acts as a blueprint for the object. The class describes the properties and methods that each instance of the object will have.

However, in JavaScript, there is no built-in support for classes. Instead, objects are created using either object literals or constructor functions. This is because JavaScript was initially designed as a scripting language for web browsers and was not intended for large-scale application development. As a result, it has evolved differently from traditional programming languages.

Despite the lack of built-in class support, JavaScript still supports the key principles of OOP, such as encapsulation, inheritance, and polymorphism. These concepts can be implemented using prototypes, constructor functions, and other language features. In fact, the lack of strict class definitions in JavaScript can make it a more flexible and dynamic language for OOP. 

In recent years, the ES6 specification introduced a new syntax for defining classes in JavaScript, which is syntactic sugar on top of the existing prototype-based system. While it may look like traditional class-based OOP, it is still fundamentally based on prototypes and constructor functions.

In JavaScript, objects are a fundamental data type, and they can be created using object literals, constructor functions, or ES6 classes.

## Creating objects

### Creating objects using object literals

In JavaScript, you can create objects using object literals, which is a way of defining an object using a comma-separated list of key-value pairs enclosed in curly braces. Here's an example:

```javascript
const person = {
  name: 'John',
  age: 30,
  address: {
    street: '123 Main St',
    city: 'Anytown',
    state: 'CA',
    zip: '12345'
  },
  sayHello: function() {
    console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
  }
};
```

In this example, we've defined an object called `person` with four properties: `name`, `age`, `address`, and `sayHello`. The `address` property is itself an object with four properties, and the `sayHello` property is a function.

You can access the properties and methods of an object using dot notation, like this:

```javascript
console.log(person.name); // 'John'
person.sayHello(); // logs 'Hello, my name is John and I'm 30 years old.'
```

Object literals are a convenient way to create objects in JavaScript, especially if you only need to create a few instances of an object. However, if you need to create many instances of an object with the same properties and methods, it may be more efficient to use a constructor function or a class to create the object.

### Creating objects using constructor functions

In JavaScript, objects can also be created using constructor functions. A constructor function is a special function that is used to create objects. The convention is to start the name of a constructor function with a capital letter to distinguish it from regular functions.

To create an object using a constructor function, you first define the constructor function and then create a new instance of the object using the `new` keyword. Here's an example:

```javascript
function Person(name, age, occupation) {
  this.name = name;
  this.age = age;
  this.occupation = occupation;
}

let person1 = new Person('John', 30, 'Software Engineer');
let person2 = new Person('Jane', 25, 'Designer');
```

In this example, we define a `Person` constructor function that takes three arguments: `name`, `age`, and `occupation`. The `this` keyword is used to assign the values of these arguments to properties of the object that is being created.

To create a new `Person` object, we use the `new` keyword followed by the name of the constructor function and the arguments that it takes. In this example, we create two `Person` objects: `person1` and `person2`.

Constructor functions can also have methods that are shared by all instances of the object. These methods can be added to the constructor function's prototype object. Here's an example:

```javascript
function Person(name, age, occupation) {
  this.name = name;
  this.age = age;
  this.occupation = occupation;
}

Person.prototype.greet = function() {
  console.log('Hello, my name is ' + this.name + '.');
}

let person1 = new Person('John', 30, 'Software Engineer');
let person2 = new Person('Jane', 25, 'Designer');

person1.greet(); // Output: Hello, my name is John.
person2.greet(); // Output: Hello, my name is Jane.
```

In this example, we add a `greet` method to the `Person` constructor function's prototype object. This method can be called on any instance of the `Person` object. When called, it will output a message to the console that includes the object's `name` property.

In JavaScript, the `new` operator is used to create an instance of an object from a constructor function. When you use the `new` operator, it creates a new object and sets its internal `[[Prototype]]` property to the `prototype` property of the constructor function.

Here is an example of how to use the `new` operator to create an instance of an object from a constructor function:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

const person = new Person('John', 30);
```

In the example above, we define a `Person` constructor function that takes two parameters: `name` and `age`. When we create a new instance of the `Person` object using the `new` operator, the `this` keyword refers to the new object being created. We set the `name` and `age` properties of the new object using the values passed as arguments to the constructor function.

Note that the `new` operator also implicitly returns the newly created object, so there is no need to use the `return` keyword in the constructor function.

When creating an object from a constructor function in JavaScript, if you forget to use the `new` keyword, the function will be called as a regular function, and its return value will be `undefined` by default. 

This can cause unexpected behavior and errors, as the properties and methods that are supposed to be added to the new object will instead be added to the global object or the object that the function was called on.

For example, consider the following constructor function:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
  this.sayHello = function() {
    console.log("Hello, my name is " + this.name + " and I am " + this.age + " years old.");
  }
}
```

If you create a new object using the `new` keyword, the function will be called as a constructor:

```javascript
let person1 = new Person("Alice", 30);
person1.sayHello(); // "Hello, my name is Alice and I am 30 years old."
```

However, if you forget to use `new`, the function will be called as a regular function and the properties and methods will not be added to a new object:

```javascript
let person2 = Person("Bob", 35);
console.log(person2); // undefined
console.log(name); // "Bob"
console.log(age); // 35
```

In this example, `person2` is `undefined`, and the `name` and `age` variables are added to the global object instead of the new object. This can lead to unintended side effects and errors in your code.

In JavaScript, the `new` keyword is used to create a new instance of an object that is defined by a constructor function. When the `new` keyword is used, a new object is created with its internal `[[Prototype]]` property set to the constructor function's `prototype` property. Then, the constructor function is called with `this` referring to the newly created object.

The `this` keyword refers to the current instance of the object when a function is called as a method of that object. In the case of constructor functions, `this` is used to refer to the new instance of the object that is being created when the function is called with the `new` keyword. 

If the `new` keyword is not used when calling the constructor function, `this` will refer to the global object (`window` in a browser or `global` in Node.js), which is not what is intended. This can cause unintended consequences and errors in your code.

Here is an example to illustrate the relationship between `new` and `this` in JavaScript:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

const john = new Person('John', 30);
console.log(john.name); // "John"
console.log(john.age); // 30

const mary = Person('Mary', 25);
console.log(mary.name); // TypeError: Cannot read property 'name' of undefined
console.log(mary.age); // TypeError: Cannot read property 'age' of undefined
console.log(name); // "Mary"
console.log(age); // 25
```

In the first example, the `new` keyword is used to create a new instance of the `Person` object with the `name` and `age` properties set. In the second example, the `Person` function is called without the `new` keyword, so `this` refers to the global object. As a result, the properties are not set on a new object, and instead, the global `name` and `age` variables are created and set to the provided values.


### Creating objects using the new operator and classes

In ES6, JavaScript introduced the class syntax, which provides a more concise and familiar way to create objects with the new operator.

To create an object using the new operator and classes, you first define a class using the class keyword, and then create an instance of that class using the new operator.

In JavaScript, the `new` operator is used to create new instances of an object. This can be done using a constructor function or a class. Here's an example of how to create an object using the `new` operator with a class:

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

let john = new Person('John', 30);
john.greet(); // Output: Hello, my name is John and I am 30 years old.
```

In the above example, we define a `Person` class with a constructor function that takes two arguments: `name` and `age`. When we call `new Person('John', 30)`, a new instance of the `Person` class is created with `name` set to `'John'` and `age` set to `30`. We then call the `greet` method on this instance, which logs a message to the console.

When using the `new` operator with a class, the `this` keyword refers to the new instance of the class being created. The constructor function sets properties on this new instance using `this.propertyName = value`.

Under the hood, the new operator creates a new object and sets its internal [[Prototype]] property to the prototype property of the class. It then calls the constructor function with this set to the new object, and returns the object.

Using classes with the new operator is a more concise and familiar way to create objects in JavaScript, especially for developers coming from other object-oriented languages. However, it's important to note that classes in JavaScript are still based on the underlying prototype-based model, and that the class syntax is just syntactic sugar on top of existing language features.

### Setting properties and methods in objects

In JavaScript, properties and methods can be added to objects using dot notation or bracket notation. Dot notation is used to access or set properties and methods of an object directly, while bracket notation is used to access or set properties and methods of an object using a string value.

To set a property in an object, use the dot notation or bracket notation and assign a value to it. For example:

```javascript
let myObj = {};
myObj.myProperty = "Hello World"; // Using dot notation to set the property
myObj["myMethod"] = function() { console.log("Method called"); }; // Using bracket notation to set the method
```

To set a method in an object, you can assign a function to a property or use the function keyword to create a method. For example:

```javascript
let myObj = {
  myMethod: function() {
    console.log("Method called");
  }
};

myObj.myMethod(); // Output: "Method called"
```

You can also set properties and methods when creating an object using object literals or constructor functions. For example:

```javascript
// Object literal
let myObj = {
  myProperty: "Hello World",
  myMethod: function() {
    console.log("Method called");
  }
};

// Constructor function
function MyObject() {
  this.myProperty = "Hello World";
  this.myMethod = function() {
    console.log("Method called");
  }
}

let newObj = new MyObject();
newObj.myMethod(); // Output: "Method called"
```

In ES6, you can use class syntax to define properties and methods of an object. For example:

```javascript
class MyClass {
  constructor() {
    this.myProperty = "Hello World";
  }

  myMethod() {
    console.log("Method called");
  }
}

let myObj = new MyClass();
myObj.myMethod(); // Output: "Method called"
```

## Inheritance

### Protoypes

In JavaScript, every object has a prototype. A prototype is an object from which the object inherits its properties and methods. 

When a property or method is accessed on an object, JavaScript looks for the property or method on the object first. If the property or method is not found on the object, JavaScript looks for it on the object's prototype. If the property or method is still not found, JavaScript looks for it on the prototype's prototype, and so on, until it reaches the end of the prototype chain.

In JavaScript, prototypes are implemented using the `prototype` property of constructor functions. When an object is created using a constructor function, its prototype is set to the `prototype` property of the constructor function.

For example, consider the following constructor function:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.sayHello = function() {
  console.log("Hello, my name is " + this.name);
};
```

In this example, the `Person` constructor function defines a `sayHello` method on its prototype. When an object is created using the `Person` constructor function, it will inherit the `sayHello` method from the `Person.prototype` object:

```javascript
var person = new Person("John", 30);
person.sayHello(); // logs "Hello, my name is John"
```

The `person` object does not have a `sayHello` method defined on it directly, but it inherits the method from its prototype, which is the `Person.prototype` object.

### Object Properties and Methods inheritance

In JavaScript, objects are collections of properties, which can be either data properties or accessor properties, and methods. Properties are values that are associated with an object, while methods are functions that are associated with an object and can perform some action or return a value.

Object properties can be defined using either dot notation or bracket notation. For example:

```javascript
const myObject = {};
myObject.property1 = 'value1'; // dot notation
myObject['property2'] = 'value2'; // bracket notation
```

Object methods are functions that are defined as properties of an object. For example:

```javascript
const myObject = {
  myMethod: function() {
    console.log('Hello, world!');
  }
};

myObject.myMethod(); // prints "Hello, world!"
```

Methods can also be defined using shorthand notation:

```javascript
const myObject = {
  myMethod() {
    console.log('Hello, world!');
  }
};

myObject.myMethod(); // prints "Hello, world!"
```

In addition to properties and methods that are defined directly on an object, objects can also inherit properties and methods from their prototype object using the prototype chain. The prototype object is essentially a template object that is used to create new objects that share its properties and methods. When a property or method is accessed on an object, if the object does not have a property or method with that name, JavaScript will look up the prototype chain to find the property or method on the object's prototype or its prototype's prototype, and so on.


When a method is defined on an object, it is created anew for each instance of the object. This can be inefficient in terms of memory usage. Defining a method on the prototype, on the other hand, means that the method is shared by all instances of the object and is only created once. This can be more memory-efficient.

Additionally, defining a method on the prototype allows for dynamic changes to the method that are reflected in all instances of the object. If a method is defined on an object itself, changes to that method will only affect that specific object and not others that may inherit from its prototype.

In general, it is recommended to define methods on the prototype rather than on the object itself, as this can help with memory usage and allow for more dynamic changes to the object's behavior.

Understanding object properties and methods is important in object-oriented programming because it allows developers to create complex and flexible data structures that can be used to model real-world entities and behaviors.

### classic inheritance

Inheritance in JavaScript is implemented using prototypes. A prototype is an object from which other objects inherit properties and methods. In classic JavaScript, objects do not have classes, but they have prototypes. Each object has a prototype, and the prototype can have its own prototype, creating a chain of inheritance.

Inheritance in classic JavaScript is accomplished by setting the prototype of an object to be another object. This can be done using the `Object.create()` method or by setting the `prototype` property of a constructor function.

Here's an example of inheritance in classic JavaScript using prototypes:

```javascript
// Define the parent object
var Animal = function(name) {
  this.name = name;
};

Animal.prototype = {
  speak: function() {
    console.log(this.name + ' makes a noise.');
  }
};

// Define the child object
var Dog = function(name) {
  Animal.call(this, name);
};

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.speak = function() {
  console.log(this.name + ' barks.');
};

// Instantiate the objects
var animal = new Animal('animal');
var dog = new Dog('dog');

// Call the methods
animal.speak(); // Output: animal makes a noise.
dog.speak(); // Output: dog barks.
```

In this example, we define a parent object `Animal` with a `speak` method. We then define a child object `Dog` that inherits from `Animal` using `Object.create()`. We then add a new `speak` method to `Dog`. We then instantiate the objects and call their respective methods.

Note that we also use the `call()` method to call the parent constructor function and set the `name` property of the child object. We also reset the `constructor` property of the `Dog` prototype to point to the `Dog` constructor function.


### extends

In ES6 (ECMAScript 2015) and later versions of JavaScript, the `class` keyword was introduced to create classes, which can be used for object-oriented programming. `class` makes it easier to create inheritance relationships between classes and objects.

To create a subclass in ES6, you use the `extends` keyword. The subclass inherits properties and methods from the superclass, and can also add its own properties and methods. Here's an example:

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(this.name + ' makes a noise.');
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name); // call the super class constructor and pass in the name parameter
  }

  speak() {
    console.log(this.name + ' barks.');
  }
}

let d = new Dog('Rex');
d.speak(); // output: "Rex barks."
```

In this example, the `Animal` class has a constructor that takes a `name` parameter, and a `speak` method that logs a message to the console. The `Dog` class extends the `Animal` class using the `extends` keyword. It also has a constructor that calls the `super` constructor of the `Animal` class, and a `speak` method that logs a different message to the console.

When the `speak` method is called on the `Dog` instance `d`, it calls the `speak` method of the `Dog` class, because it overrides the `speak` method of the `Animal` class. This results in the message "Rex barks." being logged to the console.

In addition to inheriting properties and methods from the parent class, the child class can also define its own properties and methods. This allows for customization and specialization of the child class while still maintaining the basic functionality of the parent class.


### Constructor functions vs ES6 classes

Defining parent and child classes is a fundamental concept in Object-Oriented Programming. In JavaScript, parent and child classes can be defined using constructor functions or ES6 classes. 

With constructor functions, the child class is defined using the `prototype` property of the parent class. The `Object.create()` method is used to create a new object that has the parent object as its prototype. The `call()` method is then used to call the parent constructor in the context of the child object, which initializes the child object with the properties and methods of the parent object.

Here's an example of defining parent and child classes using constructor functions:

```javascript
// Parent class
function Animal(name, age) {
  this.name = name;
  this.age = age;
}

Animal.prototype.makeSound = function() {
  console.log("Animal makes a sound");
};

// Child class
function Dog(name, age, breed) {
  Animal.call(this, name, age);
  this.breed = breed;
}

Dog.prototype = Object.create(Animal.prototype);

Dog.prototype.bark = function() {
  console.log("Dog barks");
};

// Creating objects from classes
const animal1 = new Animal("Lion", 5);
const dog1 = new Dog("Max", 3, "Labrador");

animal1.makeSound(); // Output: Animal makes a sound
dog1.makeSound(); // Output: Animal makes a sound
dog1.bark(); // Output: Dog barks
```

With ES6 classes, the `extends` keyword is used to create a child class that inherits from a parent class. The child class has its own constructor method, which calls the parent constructor using the `super()` method. This initializes the child object with the properties and methods of the parent object.

Here's an example of defining parent and child classes using ES6 classes:

```javascript
// Parent class
class Animal {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  makeSound() {
    console.log("Animal makes a sound");
  }
}

// Child class
class Dog extends Animal {
  constructor(name, age, breed) {
    super(name, age);
    this.breed = breed;
  }

  bark() {
    console.log("Dog barks");
  }
}

// Creating objects from classes
const animal1 = new Animal("Lion", 5);
const dog1 = new Dog("Max", 3, "Labrador");

animal1.makeSound(); // Output: Animal makes a sound
dog1.makeSound(); // Output: Animal makes a sound
dog1.bark(); // Output: Dog barks
```

In both examples, the child class inherits from the parent class and has its own properties and methods.

### Overriding methods in child classes

In JavaScript, when creating child classes that inherit from a parent class, it is possible to override methods from the parent class. This means that the child class can provide its own implementation of a method that was defined in the parent class.

To override a method in a child class, you simply define a method with the same name as the parent method. When the child object calls that method, it will use the implementation provided by the child class instead of the one in the parent class.

Here's an example:

```javascript
class Animal {
  makeSound() {
    console.log('Generic animal sound');
  }
}

class Cat extends Animal {
  makeSound() {
    console.log('Meow!');
  }
}

let animal = new Animal();
let cat = new Cat();

animal.makeSound(); // Outputs "Generic animal sound"
cat.makeSound(); // Outputs "Meow!"
```

In this example, we define an `Animal` class with a `makeSound()` method that outputs a generic animal sound. We then define a `Cat` class that extends the `Animal` class and overrides the `makeSound()` method with its own implementation that outputs "Meow!".

When we create an instance of the `Animal` class and call `makeSound()`, we get the generic animal sound output. But when we create an instance of the `Cat` class and call `makeSound()`, we get the "Meow!" output, which is the implementation provided by the child class.

### Accessing parent class methods from child classes

In classic JavaScript, you can access parent class methods from child classes by using the prototype chain. When a child object is created, its internal prototype property is set to the parent object's prototype, which allows the child object to inherit properties and methods from its parent.

To access a parent method from a child object, you can use the `call()` or `apply()` method to call the parent method in the context of the child object. Here's an example:

```javascript
function Parent(name) {
  this.name = name;
}

Parent.prototype.sayHello = function() {
  console.log('Hello, ' + this.name);
}

function Child(name) {
  Parent.call(this, name);
}

Child.prototype = Object.create(Parent.prototype);
Child.prototype.constructor = Child;

Child.prototype.sayHello = function() {
  console.log('Hi, ' + this.name);
  Parent.prototype.sayHello.call(this);
}

var child = new Child('Alice');
child.sayHello(); // outputs "Hi, Alice" and "Hello, Alice"
```

In this example, the `Parent` class defines a `sayHello()` method on its prototype. The `Child` class inherits from `Parent` by setting its prototype to an instance of `Parent.prototype`. When the `sayHello()` method is called on a `Child` object, it first logs "Hi, Alice" and then calls the parent method in the context of the child object using `Parent.prototype.sayHello.call(this)`. This logs "Hello, Alice".

### Using super keyword

In ES6, accessing parent class methods from child classes is done using the `super` keyword. The `super` keyword refers to the parent class and can be used to call the parent class's constructor or methods.

To call a method from the parent class in a child class, we use the `super` keyword followed by a dot and the name of the method. For example, consider the following `Person` class and its `Student` child class:

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }
  
  sayHello() {
    console.log(`Hello, my name is ${this.name}.`);
  }
}

class Student extends Person {
  constructor(name, major) {
    super(name);
    this.major = major;
  }
  
  sayHello() {
    super.sayHello();
    console.log(`I'm studying ${this.major}.`);
  }
}

const student1 = new Student('John', 'Computer Science');
student1.sayHello();
```

In this example, `Student` extends `Person`, and its constructor calls the `Person` constructor using `super`. The `Student` class also overrides the `sayHello` method of the `Person` class but still wants to call the `Person` class's implementation of `sayHello`. This is accomplished using `super.sayHello()`. The output of the `sayHello` method call on `student1` would be:

```
Hello, my name is John.
I'm studying Computer Science.
```

## Encapsulation

Encapsulation is a fundamental concept in object-oriented programming that refers to the practice of bundling data and methods that operate on that data within a single unit. This can help prevent external code from accessing or modifying the internal state of an object, providing better control over how an object is used and maintained.

### Classic encapsulation

In classic JavaScript, encapsulation can be achieved through the use of constructor functions and the `this` keyword. Constructor functions can be used to define a blueprint for creating new objects that have the same properties and methods. Properties can be added to the object by assigning them to `this` within the constructor function, and methods can be defined by adding them to the object's prototype.

For example, consider the following constructor function:

```javascript
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;

  this.getMake = function() {
    return this.make;
  }

  this.getModel = function() {
    return this.model;
  }

  this.getYear = function() {
    return this.year;
  }
}
```

This constructor function defines a `Car` object with three properties (`make`, `model`, and `year`) and three methods (`getMake`, `getModel`, and `getYear`). Each of these methods uses `this` to access the object's properties, and is thus encapsulated within the object.

To create a new `Car` object, you can use the `new` keyword:

```javascript
var myCar = new Car("Toyota", "Camry", 2021);
```

This creates a new `Car` object with the specified `make`, `model`, and `year` properties.

### ES6 encapsulation

In ES6, encapsulation can be achieved through the use of classes and access modifiers. ES6 provides three access modifiers for class members: public, private, and protected. The public modifier indicates that a member can be accessed from outside the class, while the private modifier indicates that a member can only be accessed from within the class. The protected modifier is similar to the private modifier, but it also allows access from within derived classes.

To create a private member in an ES6 class, you can use the `#` symbol before the member name, like so:

```javascript
class MyClass {
  #privateMember;

  constructor() {
    this.#privateMember = 'private';
  }

  publicMethod() {
    console.log(this.#privateMember);
  }
}
```

In this example, `#privateMember` is a private member of the `MyClass` class, which can only be accessed from within the class itself. The `publicMethod()` method, which is a public member, can access the private member.

ES6 also provides getter and setter methods, which can be used to control access to class properties. Getters and setters can be used to expose private members in a controlled way, by allowing read and write access to those members through public methods.

```javascript
class MyClass {
  #privateMember;

  constructor() {
    this.#privateMember = 'private';
  }

  get privateMember() {
    return this.#privateMember;
  }

  set privateMember(value) {
    this.#privateMember = value;
  }

  publicMethod() {
    console.log(this.#privateMember);
  }
}
```

In this example, the `privateMember` property is a private member of the `MyClass` class. The `get` and `set` methods allow read and write access to the property, respectively, while the `publicMethod()` method can access the private member directly.

Overall, encapsulation is an important concept in object-oriented programming, and ES6 provides powerful tools for achieving it in JavaScript.


### Using closures to achieve encapsulation

In JavaScript, closures are often used to achieve encapsulation. Closures are functions that have access to the outer (enclosing) function's variables and parameters, even after the outer function has returned. This allows you to create private variables and functions in JavaScript, which can only be accessed by the closure function.

Here's an example of how you can use closures to achieve encapsulation in JavaScript:

```javascript
function createCounter() {
  let count = 0;

  return {
    increment() {
      count++;
    },
    decrement() {
      count--;
    },
    getCount() {
      return count;
    }
  };
}

const counter = createCounter();
console.log(counter.getCount()); // 0
counter.increment();
console.log(counter.getCount()); // 1
counter.decrement();
console.log(counter.getCount()); // 0
```

In this example, we're creating a closure function `createCounter` that has a private variable `count`. The closure function returns an object with three methods: `increment`, `decrement`, and `getCount`. These methods have access to the private `count` variable because of the closure created by the `createCounter` function.

By returning an object with only the necessary methods, we can prevent external code from accessing or modifying the `count` variable directly. This creates a level of encapsulation in our code, making it more modular and easier to maintain.






## Polymorphism


Polymorphism refers to the ability of objects to take on different forms depending on the context in which they are used. In JavaScript, we can implement polymorphism using prototype inheritance and method overriding.

### Classic Javascript

To implement polymorphism in classic JS, we can create a parent class with a method, and then create multiple child classes that inherit from the parent class and override the method with their own implementation.

For example, consider a Shape parent class with a draw() method:

```javascript
function Shape() {}

Shape.prototype.draw = function() {
  console.log('Drawing a shape');
}
```

We can then create child classes, such as Circle and Rectangle, that inherit from the Shape class and override the draw() method with their own implementation:

```javascript
function Circle() {}

Circle.prototype = Object.create(Shape.prototype);
Circle.prototype.constructor = Circle;

Circle.prototype.draw = function() {
  console.log('Drawing a circle');
}

function Rectangle() {}

Rectangle.prototype = Object.create(Shape.prototype);
Rectangle.prototype.constructor = Rectangle;

Rectangle.prototype.draw = function() {
  console.log('Drawing a rectangle');
}
```

Now we can create objects of the Circle and Rectangle classes and call their draw() methods, and each object will use its own implementation of the method:

```javascript
var circle = new Circle();
circle.draw(); // Output: "Drawing a circle"

var rectangle = new Rectangle();
rectangle.draw(); // Output: "Drawing a rectangle"
```

This shows how we can achieve polymorphism in classic JS by using prototype inheritance and method overriding. However, it can be more complex and error-prone than using classes and inheritance in modern JS.

### ES6

In ES6, polymorphism can be implemented using classes and method overriding. Polymorphism is the ability of objects of different classes to be used interchangeably. In ES6, you can define a base class with some common methods and properties, and then define derived classes that inherit from the base class.

To implement polymorphism in ES6, you can define a base class with some common methods and properties, and then define derived classes that inherit from the base class. The derived classes can override the base class methods with their own implementations, providing different behavior for different objects.

Here is an example:

```javascript
class Shape {
  constructor(name) {
    this.name = name;
  }
  draw() {
    console.log(`Drawing ${this.name}`);
  }
}

class Circle extends Shape {
  constructor(radius) {
    super("circle");
    this.radius = radius;
  }
  draw() {
    console.log(`Drawing a ${this.name} with radius ${this.radius}`);
  }
}

class Square extends Shape {
  constructor(side) {
    super("square");
    this.side = side;
  }
  draw() {
    console.log(`Drawing a ${this.name} with side ${this.side}`);
  }
}

const shapes = [new Circle(5), new Square(10)];
shapes.forEach(shape => shape.draw());
```

In this example, we define a base class `Shape` with a `draw` method, and two derived classes `Circle` and `Square` that inherit from the `Shape` class. Each derived class has its own implementation of the `draw` method. Finally, we create an array of shapes and call the `draw` method for each shape, and each shape draws itself differently depending on its type.

By using polymorphism, we can write code that can work with different types of objects without knowing their specific types in advance, which makes our code more flexible and easier to maintain.


### Implementing polymorphism emulating interfaces in ES6

In JavaScript, there are no built-in interfaces like in some other object-oriented programming languages. However, you can implement polymorphism using a concept similar to interfaces. 

An interface defines a contract that classes must adhere to, specifying the properties and methods that a class must implement. In JavaScript, we can use an object to define an interface. To implement this interface, a class must have methods that match the methods specified in the interface.

Here's an example of implementing polymorphism using an interface in JavaScript:

```javascript
// Define the interface
const Shape = {
  calculateArea() {}
};

// Implement the interface in a class
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  calculateArea() {
    return this.width * this.height;
  }
}

class Circle {
  constructor(radius) {
    this.radius = radius;
  }

  calculateArea() {
    return Math.PI * this.radius ** 2;
  }
}

// Use the classes polymorphically
function printArea(shape) {
  console.log(`The area is ${shape.calculateArea()}`);
}

const rectangle = new Rectangle(5, 10);
const circle = new Circle(7);

printArea(rectangle); // The area is 50
printArea(circle); // The area is 153.93804002589985
```

In this example, we define an interface `Shape` with a method `calculateArea`. We then implement this interface in two classes, `Rectangle` and `Circle`. Both classes have a `calculateArea` method that calculates the area of the shape, but they do it differently depending on their shape. Finally, we use the `printArea` function to print the area of the different shapes, polymorphically using the `calculateArea` method from the interface.

## Design Patterns

Patterns are reusable solutions to commonly occurring problems in software development. They are a way to provide structure and organization to code, making it more modular, flexible, and easy to maintain. In JavaScript, there are several design patterns that can be used to solve different types of problems, such as the singleton pattern, factory pattern, observer pattern, and decorator pattern, to name a few.

Learning and using design patterns in JavaScript can be very beneficial as they help developers to write better, cleaner, and more efficient code. By using patterns, developers can avoid common pitfalls, improve the performance and scalability of their code, and create more reusable and maintainable codebases.

Additionally, design patterns can provide a common language and structure for developers to communicate with each other and share solutions to common problems. This makes it easier to collaborate on projects and reduces the likelihood of errors or misunderstandings.

Overall, while it's not necessary to use design patterns in every situation, understanding and utilizing them can greatly improve the quality and maintainability of your code.

### Singleton

The Singleton pattern is a design pattern that restricts the instantiation of a class to a single instance and provides a global point of access to that instance. In other words, it ensures that a class has only one instance and provides a way to access it globally.

In ES6, we can implement the Singleton pattern using a combination of the `class` syntax and the `static` keyword. Here's an example:

```javascript
class Singleton {
  static instance = null;

  constructor() {
    if (Singleton.instance) {
      return Singleton.instance;
    }
    Singleton.instance = this;
    this.name = 'Singleton';
  }

  sayName() {
    console.log(`My name is ${this.name}.`);
  }
}

const s1 = new Singleton(); // creates a new instance
const s2 = new Singleton(); // returns the existing instance

console.log(s1 === s2); // true

s1.sayName(); // "My name is Singleton."
s2.sayName(); // "My name is Singleton."
```

In this example, the `instance` property is defined as a `static` property of the `Singleton` class, which means it belongs to the class itself, not its instances. When a new instance of `Singleton` is created, the constructor checks if `instance` already exists, and if so, it returns the existing instance instead of creating a new one. If `instance` does not exist, it creates a new instance and sets `instance` to the new instance.

The `sayName` method is a regular instance method that can be called on the Singleton instance. In this example, calling `sayName` on `s1` and `s2` will both output "My name is Singleton."

The Singleton pattern is useful when we want to limit the number of instances of a class and ensure that all code accesses the same instance. It is commonly used for things like database connections, logging services, and configuration objects. However, it can also make testing more difficult and introduce global state, which can lead to potential issues if not managed carefully.

### Factory

The factory pattern is a creational design pattern that provides a way to create objects without specifying the exact class or constructor function that should be used to create them. Instead of creating objects directly, a factory function is used to create and return new instances of objects based on some input or configuration.

In ES6, we can use a class as a factory to create objects. The class can have a factory method that takes some parameters and returns a new instance of an object with some initial configuration. Here's an example:

```javascript
class ShapeFactory {
  static createShape(type, options) {
    switch(type) {
      case 'circle':
        return new Circle(options);
      case 'rectangle':
        return new Rectangle(options);
      case 'triangle':
        return new Triangle(options);
      default:
        throw new Error(`Invalid shape type: ${type}`);
    }
  }
}

class Circle {
  constructor(options) {
    // initialize circle object
  }
}

class Rectangle {
  constructor(options) {
    // initialize rectangle object
  }
}

class Triangle {
  constructor(options) {
    // initialize triangle object
  }
}

// usage
const circle = ShapeFactory.createShape('circle', { radius: 10 });
const rectangle = ShapeFactory.createShape('rectangle', { width: 20, height: 30 });
const triangle = ShapeFactory.createShape('triangle', { base: 20, height: 30 });
```

In this example, we define a ShapeFactory class that has a static method `createShape` that takes a `type` parameter and an `options` parameter. The `createShape` method then creates and returns an object based on the `type` parameter.

The `Circle`, `Rectangle`, and `Triangle` classes are the objects that can be created by the factory. Each of these classes has its own constructor that takes an `options` parameter, which is used to initialize the object.

Using a factory pattern has several benefits. It provides a way to create objects without having to specify the exact class or constructor function. It also centralizes the object creation logic, making it easier to modify or extend in the future. However, the factory pattern can also lead to complex code and reduce the flexibility of the object creation process.

### Observer

The Observer pattern is a behavioral design pattern that allows an object (known as the subject) to maintain a list of its dependents (known as observers) and notify them automatically of any state changes, usually by calling one of their methods. 

In ES6, the Observer pattern can be implemented using the built-in `Proxy` object. The `Proxy` object allows you to define custom behavior for fundamental operations (e.g. property lookup, assignment, invocation) on an object. 

To implement the Observer pattern using `Proxy`, you would create an object that represents the subject, and define a list of observers as an array property on that object. You would then create a `Proxy` object for the subject, and define a `set` trap on the `Proxy` object. Whenever a property of the subject is set, the `set` trap would be invoked and would notify each observer in the list of the change.

Here is an example implementation of the Observer pattern using `Proxy` in ES6:

```javascript
const subject = {
  observers: [],

  subscribe(observer) {
    this.observers.push(observer);
  },

  unsubscribe(observer) {
    this.observers = this.observers.filter(obs => obs !== observer);
  },

  notify(data) {
    this.observers.forEach(observer => observer.update(data));
  }
};

const observer1 = {
  update(data) {
    console.log(`Observer 1 received data: ${data}`);
  }
};

const observer2 = {
  update(data) {
    console.log(`Observer 2 received data: ${data}`);
  }
};

subject.subscribe(observer1);
subject.subscribe(observer2);

const subjectProxy = new Proxy(subject, {
  set(target, key, value) {
    target[key] = value;
    target.notify(value);
    return true;
  }
});

subjectProxy.data = "Some data"; // Output: "Observer 1 received data: Some data", "Observer 2 received data: Some data"
```

In this example, `subject` is the object that represents the subject. It has an `observers` array property, and methods to subscribe, unsubscribe, and notify observers. 

`observer1` and `observer2` are objects that represent observers. They each have an `update` method that is called when the subject notifies them of a change. 

`subjectProxy` is a `Proxy` object that wraps the `subject` object. It has a `set` trap that is invoked whenever a property of the subject is set. When the `set` trap is invoked, it updates the property on the subject, and then calls the `notify` method to notify all observers of the change. 

When `subjectProxy.data` is set to "Some data", both `observer1` and `observer2` are notified of the change and their `update` methods are called with the data.

### Decorator

The decorator pattern is a design pattern that allows behavior to be added to an individual object dynamically without affecting the behavior of other objects from the same class. It is a structural pattern that is used to add functionality to an object at runtime.

In ES6, the decorator pattern can be implemented using decorators. Decorators are functions that can modify the behavior of a class or a class property. They can be used to add functionality such as logging, caching, validation, or access control to an object.

Here's an example of implementing the decorator pattern in ES6:

```javascript
// Decorator function that logs method calls
function log(target, name, descriptor) {
  const original = descriptor.value;
  descriptor.value = function (...args) {
    console.log(`Calling ${name} with args: ${args}`);
    return original.apply(this, args);
  };
  return descriptor;
}

// Class that uses the log decorator
class Calculator {
  @log
  add(a, b) {
    return a + b;
  }
}

const calculator = new Calculator();
console.log(calculator.add(2, 3)); // Calling add with args: 2,3
                                   // 5
```

In this example, the `log` function is a decorator that logs the method calls of a class. The `@log` syntax is used to apply the `log` decorator to the `add` method of the `Calculator` class. When the `add` method is called, the `log` decorator is executed first, and it logs the method call before calling the original `add` method.


## Best Practices:
- Writing reusable and maintainable code
- Avoiding anti-patterns
- Writing efficient code
- Documenting code using JSDoc comments
- Writing unit tests

## Advanced Topics:
- Asynchronous programming in OOP
- Error handling in OOP
- Functional programming in OOP
- Implementing data structures using OOP

## Frameworks and Libraries:
- Popular JavaScript frameworks and libraries for OOP: React, Angular, Vue.js
- Benefits and drawbacks of using frameworks and libraries
- Understanding how frameworks and libraries implement OOP

