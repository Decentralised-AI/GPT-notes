# Object-Oriented Programming (OOP)

## Classes

In Java, a class is a blueprint or template that defines the structure and behavior of objects. It serves as a blueprint for creating individual objects of that class type. Here's an explanation of classes in Java:

1. Class Declaration:
   - To declare a class, you use the `class` keyword followed by the class name.
   - Example:
     ```java
     public class MyClass {
         // Class body
     }
     ```

2. Class Members:
   - A class can contain various members, including fields (variables), methods, constructors, and nested classes.
   - Fields: Fields represent the state or data of an object. They define the characteristics or attributes that objects of the class will have.
   - Methods: Methods define the behavior or actions that objects of the class can perform. They encapsulate the logic and operations associated with the class.
   - Constructors: Constructors are special methods used for initializing objects of the class. They are called when an object is created and help set up its initial state.
   - Nested Classes: Java allows you to define classes within other classes. These nested classes can be static or non-static and provide additional encapsulation and organization.

3. Object Creation:
   - Once a class is defined, you can create objects (instances) of that class using the `new` keyword.
   - Example:
     ```java
     MyClass obj = new MyClass(); // Creating an object of MyClass
     ```

4. Access Modifiers:
   - Java provides access modifiers to control the visibility and accessibility of class members.
   - `public`: Public members are accessible from any other class.
   - `private`: Private members are only accessible within the same class.
   - `protected`: Protected members are accessible within the same class, subclasses, and classes in the same package.
   - Default (no modifier): Members with no explicit access modifier are accessible within the same package.

5. Class Inheritance:
   - Java supports class inheritance, allowing you to create a new class based on an existing class. The new class, called a subclass or derived class, inherits the properties and methods of the parent class, called the superclass or base class.
   - Inheritance promotes code reusability and allows for the creation of more specialized classes.
   - Example:
     ```java
     public class SubClass extends SuperClass {
         // Additional members and overrides
     }
     ```

6. Method Overriding:
   - Inheritance also allows you to override methods defined in the superclass within the subclass. Method overriding enables the subclass to provide its own implementation of a method inherited from the superclass.
   - Example:
     ```java
     public class SubClass extends SuperClass {
         @Override
         public void someMethod() {
             // Custom implementation in the subclass
         }
     }
     ```

7. Accessing Class Members:
   - Class members are accessed using the dot (`.`) operator on an object or class reference.
   - Example:
     ```java
     MyClass obj = new MyClass();
     int value = obj.someField; // Accessing a field
     obj.someMethod(); // Invoking a method
     ```

Classes are a fundamental concept in object-oriented programming (OOP) and provide a way to define and organize code into reusable components. They encapsulate data and behavior, enable code reuse through inheritance, and allow for the creation of objects based on the defined class structure.


## Objects 


In Java, an object is an instance of a class that represents a real-world entity or concept. Objects are created from classes and have their own state (data) and behavior (methods). Here's an explanation of objects in Java:

1. Object Creation:
   - To create an object, you use the `new` keyword followed by the class name and parentheses.
   - Example:
     ```java
     MyClass obj = new MyClass(); // Creating an object of MyClass
     ```

2. Object State (Data):
   - Objects have their own state, which is defined by the fields (variables) of the class. Each object of a class has its own copy of instance variables.
   - Example:
     ```java
     public class Person {
         String name; // Instance variable
         int age; // Instance variable
     }

     Person person1 = new Person(); // Creating an object of Person
     person1.name = "John"; // Setting the name field of person1
     person1.age = 25; // Setting the age field of person1

     Person person2 = new Person(); // Creating another object of Person
     person2.name = "Mary"; // Setting the name field of person2
     person2.age = 30; // Setting the age field of person2
     ```

3. Object Behavior (Methods):
   - Objects can perform actions or exhibit behavior through methods defined in the class. Methods encapsulate the logic and operations associated with the object's behavior.
   - Example:
     ```java
     public class Person {
         String name; // Instance variable
         int age; // Instance variable

         public void sayHello() {
             System.out.println("Hello, my name is " + name);
         }

         public void celebrateBirthday() {
             age++;
             System.out.println("Happy birthday! I am now " + age + " years old.");
         }
     }

     Person person = new Person();
     person.name = "John";
     person.age = 25;
     person.sayHello(); // Output: Hello, my name is John
     person.celebrateBirthday(); // Output: Happy birthday! I am now 26 years old.
     ```

4. Object Interactions:
   - Objects can interact with each other by invoking methods or accessing fields of other objects.
   - Example:
     ```java
     public class Person {
         String name;
         int age;

         public void sayHelloTo(Person otherPerson) {
             System.out.println("Hello, " + otherPerson.name + "! My name is " + name + ".");
         }
     }

     Person person1 = new Person();
     person1.name = "John";

     Person person2 = new Person();
     person2.name = "Mary";

     person1.sayHelloTo(person2); // Output: Hello, Mary! My name is John.
     ```

Objects in Java represent the instances of classes and allow you to model and work with real-world entities or concepts in your programs. They encapsulate state (data) and behavior (methods) and can interact with each other to perform tasks and achieve desired functionality.



## Class contructors, properties and methods

In Java, classes are used to define objects that have properties (fields) and behavior (methods). Let's explore class constructors, properties, and methods in detail:

1. Class Constructors:
   - A constructor is a special method used to create and initialize objects of a class.
   - It has the same name as the class and is invoked using the `new` keyword when creating an object.
   - Constructors do not have a return type, not even `void`.
   - Constructors can take parameters to initialize the object's properties.
   - Example:
     ```java
     public class Person {
         String name;
         int age;

         // Constructor with parameters
         public Person(String name, int age) {
             this.name = name;
             this.age = age;
         }
     }
     ```

2. Class Properties (Fields):
   - Properties represent the state or data associated with objects of the class.
   - They are declared within the class and hold values specific to each object.
   - Properties can have different data types, such as `int`, `String`, `boolean`, or even other class types.
   - Example:
     ```java
     public class Person {
         String name;
         int age;
     }
     ```

3. Class Methods:
   - Methods define the behavior or actions that objects of the class can perform.
   - They encapsulate the logic and operations associated with the class.
   - Methods are declared within the class and can be invoked on objects of that class.
   - They can have parameters, perform computations, access properties, and return values.
   - Example:
     ```java
     public class Person {
         String name;
         int age;

         // Constructor
         public Person(String name, int age) {
             this.name = name;
             this.age = age;
         }

         // Method to display information about the person
         public void displayInfo() {
             System.out.println("Name: " + name);
             System.out.println("Age: " + age);
         }
     }
     ```

In the above example, the `Person` class has a constructor that takes parameters to initialize the `name` and `age` properties of the object. It also has a `displayInfo()` method that displays the object's information.

To use the class, you can create objects of the class and access their properties or invoke their methods. Here's an example:

```java
Person person = new Person("John", 25); // Creating an object of Person

System.out.println(person.name); // Accessing the name property
// Output: John

person.displayInfo(); // Invoking the displayInfo() method
// Output:
// Name: John
// Age: 25
```

Constructors, properties, and methods work together to define the behavior and state of objects created from a class. Constructors ensure proper initialization of object properties, properties hold the object's data, and methods provide the functionality or actions that can be performed on those objects.

## Encapsulation

Encapsulation is one of the fundamental principles of object-oriented programming (OOP) and is a mechanism for bundling data (properties) and methods (behavior) within a class. It involves the concept of hiding internal implementation details and providing controlled access to the data.

In Java, encapsulation is achieved by using access modifiers (such as `private`, `public`, `protected`) to control the visibility and accessibility of class members (fields and methods). Here are some key aspects of encapsulation in Java:

1. Data Hiding:
   - Encapsulation allows you to hide the internal state (data) of an object from direct external access.
   - By declaring fields as `private`, you restrict direct access to those fields from outside the class.
   - Example:
     ```java
     public class Person {
         private String name; // Private field

         // Getter method to access the private field
         public String getName() {
             return name;
         }

         // Setter method to modify the private field
         public void setName(String newName) {
             name = newName;
         }
     }
     ```

2. Accessor and Mutator Methods:
   - Encapsulation promotes the use of getter and setter methods to access and modify the private fields of a class.
   - Getter methods provide read-only access to the properties, while setter methods allow modification.
   - This way, you can maintain control over how the fields are accessed and updated, enabling data validation or applying additional logic if needed.
   - Example:
     ```java
     public class Person {
         private int age; // Private field

         // Getter method
         public int getAge() {
             return age;
         }

         // Setter method with data validation
         public void setAge(int newAge) {
             if (newAge >= 0) {
                 age = newAge;
             }
         }
     }
     ```

3. Encapsulation Benefits:
   - Encapsulation enhances the maintainability, reusability, and flexibility of code by providing a clear separation between the internal implementation and external access.
   - It protects the integrity of data by controlling access to fields and enforcing validation rules through setter methods.
   - It allows for easier modification of internal implementation details without affecting the code using the class.
   - Encapsulation also helps in achieving code organization and reducing dependencies.

By encapsulating the internal state of objects and providing controlled access through methods, you can ensure that data integrity is maintained and changes to the implementation can be made without impacting the code using the class. Encapsulation is a key principle in Java and helps in building robust and maintainable code.

## Inheritance

Inheritance is a fundamental concept in object-oriented programming (OOP) that allows you to create new classes (derived or child classes) based on existing classes (base or parent classes). It enables the reuse of code and promotes the concept of "is-a" relationship between classes. In Java, inheritance is implemented using the `extends` keyword. Here's an explanation of inheritance in Java:

1. Base Class (Parent Class):
   - The base class is the existing class from which other classes will inherit.
   - It contains common properties and methods that are shared among the derived classes.
   - Example:
     ```java
     public class Animal {
         protected String name;

         public Animal(String name) {
             this.name = name;
         }

         public void eat() {
             System.out.println(name + " is eating.");
         }
     }
     ```

2. Derived Class (Child Class):
   - The derived class is the new class created by inheriting from the base class.
   - It inherits the properties and methods of the base class and can add its own specific properties and methods.
   - The derived class can also override the inherited methods to provide its own implementation.
   - Example:
     ```java
     public class Dog extends Animal {
         public Dog(String name) {
             super(name); // Invoke the base class constructor
         }

         public void bark() {
             System.out.println(name + " is barking.");
         }

         // Override the eat() method of the base class
         @Override
         public void eat() {
             System.out.println(name + " is eating bones.");
         }
     }
     ```

3. Inheritance Syntax:
   - To create a derived class, use the `extends` keyword followed by the name of the base class.
   - The derived class can access the inherited properties and methods using the `super` keyword.
   - Example:
     ```java
     public class Main {
         public static void main(String[] args) {
             Dog dog = new Dog("Buddy"); // Creating an object of the derived class

             dog.eat(); // Inherited method from Animal class
             // Output: Buddy is eating bones.

             dog.bark(); // Method specific to Dog class
             // Output: Buddy is barking.
         }
     }
     ```

In the above example, the `Animal` class is the base class, and the `Dog` class is derived from it using the `extends` keyword. The `Dog` class inherits the `name` property and `eat()` method from the `Animal` class and adds its own `bark()` method. The `eat()` method is overridden in the `Dog` class to provide a specific implementation.

Inheritance allows you to create a hierarchy of classes, with more specialized classes inheriting common behavior and properties from more general classes. It promotes code reuse, extensibility, and modularity in object-oriented programming.

## Visibility modifiers

In Java, visibility modifiers (public, private, and protected) are used to control the accessibility of methods and properties (also known as fields or variables) in classes. These modifiers define the scope within which a method or property can be accessed. Here's an overview of each visibility modifier:

1. Public:
   - The `public` modifier makes a method or property accessible to all classes, regardless of their location or relationship with the declaring class.
   - Public members can be accessed from any other class, within the same package or from different packages.
   - Example:
     ```java
     public class MyClass {
         public int publicVariable;
         public void publicMethod() {
             // Method implementation
         }
     }
     ```

2. Private:
   - The `private` modifier restricts the accessibility of a method or property to the class in which it is declared.
   - Private members cannot be accessed or modified from outside the class.
   - This modifier is useful for encapsulation, as it hides the internal implementation details of a class.
   - Example:
     ```java
     public class MyClass {
         private int privateVariable;
         private void privateMethod() {
             // Method implementation
         }
     }
     ```

3. Protected:
   - The `protected` modifier allows access to a method or property within the same package and in subclasses, even if they are in a different package.
   - Protected members are not accessible from classes that are outside the package and are not subclasses of the declaring class.
   - This modifier is useful for providing controlled access to inherited members.
   - Example:
     ```java
     package com.example;

     public class MyBaseClass {
         protected int protectedVariable;
         protected void protectedMethod() {
             // Method implementation
         }
     }

     package com.example.subpackage;

     public class MySubClass extends MyBaseClass {
         public void someMethod() {
             protectedVariable = 10; // Accessing protected variable from subclass
             protectedMethod(); // Accessing protected method from subclass
         }
     }
     ```

By using these visibility modifiers, you can control the accessibility of methods and properties in your classes, providing encapsulation, data hiding, and controlled access to class members. This helps in building well-structured and maintainable code by enforcing proper encapsulation and preventing unwanted access or modification of internal implementation details.

## Interfaces and Abstract Classes 

Interfaces and abstract classes are key features of Java that facilitate abstraction, code organization, and implementation of common behavior in object-oriented programming. While they share some similarities, there are also distinct differences between them. Let's explore interfaces and abstract classes in Java:

Interfaces:
- An interface in Java is a contract or a blueprint for a class. It defines a set of abstract methods (methods without implementation) and constants (public static final variables) that a class implementing the interface must adhere to.
- Interfaces can also include default methods (methods with default implementation) starting from Java 8 and static methods starting from Java 8.
- Multiple interfaces can be implemented by a single class, allowing for multiple inheritance of behavior.
- Interfaces are declared using the `interface` keyword.
- Example:
```java
public interface Drawable {
    void draw(); // Abstract method

    default void display() {
        System.out.println("Displaying the drawable object.");
    }
}
```

Abstract Classes:
- An abstract class in Java is a class that cannot be instantiated and serves as a base for other classes. It can contain both abstract and non-abstract methods.
- Abstract methods are declared without implementation and must be overridden by concrete (non-abstract) subclasses.
- Abstract classes can also include regular methods with implementation.
- A class can extend only one abstract class.
- Abstract classes are declared using the `abstract` keyword.
- Example:
```java
public abstract class Shape {
    private String color;

    public Shape(String color) {
        this.color = color;
    }

    public abstract double area(); // Abstract method

    public void displayColor() {
        System.out.println("The shape color is: " + color);
    }
}
```

Differences between Interfaces and Abstract Classes:
1. Implementation: Interfaces provide a way to define only method signatures, while abstract classes can have both abstract and non-abstract methods with implementation.
2. Multiple Inheritance: A class can implement multiple interfaces, but it can extend only one abstract class.
3. Accessibility: Interface methods are implicitly public, while abstract class methods can have different access modifiers.
4. Constructor: Interfaces cannot have constructors, while abstract classes can have constructors that are invoked when a subclass is instantiated.
5. Fields: Interfaces can only have constants (public static final variables), while abstract classes can have fields with any access modifier.
6. Version: Default methods and static methods were introduced in interfaces starting from Java 8, whereas abstract classes existed prior to Java 8.

In general, use interfaces when you want to define a contract that specifies behavior without providing implementation details. Use abstract classes when you want to define a common base class for related classes that share common behavior and provide some default implementation.

It's worth noting that since Java 8, with the introduction of default methods in interfaces, the distinction between interfaces and abstract classes has become more flexible. You can now include default method implementations in interfaces, allowing them to provide some level of implementation while still enforcing a contract.


## Polymorphism

Polymorphism is a fundamental concept in object-oriented programming that allows objects of different classes to be treated as objects of a common superclass or interface. It enables code to be written that can work with objects of multiple types, providing flexibility and reusability. In Java, polymorphism is achieved through method overriding and method overloading. Here's an explanation of polymorphism in Java:

1. Method Overriding:
   - Method overriding occurs when a subclass provides its own implementation of a method that is already defined in its superclass.
   - The overridden method in the subclass has the same name, return type, and parameter list as the method in the superclass.
   - The overridden method is invoked based on the actual type of the object at runtime.
   - Example:
     ```java
     public class Animal {
         public void makeSound() {
             System.out.println("Animal makes a sound.");
         }
     }

     public class Dog extends Animal {
         @Override
         public void makeSound() {
             System.out.println("Dog barks.");
         }
     }
     ```

2. Method Overloading:
   - Method overloading occurs when multiple methods in the same class have the same name but different parameter lists (number, order, or type of parameters).
   - The methods can have different return types or access modifiers, but that alone does not determine overloading.
   - The appropriate method is selected based on the number and type of arguments passed during the method invocation.
   - Example:
     ```java
     public class Calculator {
         public int add(int num1, int num2) {
             return num1 + num2;
         }

         public double add(double num1, double num2) {
             return num1 + num2;
         }
     }
     ```

3. Polymorphic Usage:
   - Polymorphism allows objects of different subclasses to be treated as objects of a common superclass or interface.
   - You can assign an object of a subclass to a variable of the superclass or interface type.
   - The appropriate method implementation is invoked based on the actual type of the object.
   - Example:
     ```java
     Animal animal = new Dog(); // Polymorphic assignment

     animal.makeSound(); // Output: Dog barks.
     ```

In the above example, the `Animal` class has a method called `makeSound()`, which is overridden in the `Dog` class. By creating an object of the `Dog` class and assigning it to a variable of type `Animal`, polymorphism is achieved. When invoking the `makeSound()` method on the `animal` object, the overridden method in the `Dog` class is called.

Polymorphism allows you to write more flexible and reusable code by working with objects of different types through a common interface. It promotes code extensibility and simplifies code maintenance, as new classes can be added without modifying existing code that depends on the superclass or interface.

### Abstraction and polymorphism

Polymorphism with interfaces is closely related to the concept of abstraction in Java. Interfaces provide a way to define a contract for classes that implement them, allowing for a high level of abstraction and polymorphic behavior. Let's explore how polymorphism and interfaces work together in the context of abstraction:

1. Abstraction:
   - Abstraction is a fundamental principle of object-oriented programming that focuses on capturing the essential characteristics and behavior of an object while hiding unnecessary implementation details.
   - It allows you to create abstract concepts or models that represent real-world entities or systems.
   - Abstraction is achieved in Java through interfaces and abstract classes.

2. Interfaces and Polymorphism:
   - An interface in Java defines a contract or a set of methods that a class implementing the interface must adhere to.
   - Interfaces provide a way to achieve abstraction by defining the behavior without specifying the implementation details.
   - Interfaces can be used as types to create variables, method parameters, and return types.
   - Polymorphism with interfaces allows objects of different classes to be treated as objects of the interface type.
   - By programming to the interface, you can work with objects at a higher level of abstraction, enabling flexibility and code reuse.

3. Polymorphic Behavior with Interfaces:
   - When a class implements an interface, it must provide an implementation for all the methods declared in the interface.
   - You can create objects of different classes that implement the same interface and treat them interchangeably.
   - You can assign an object of an implementing class to a variable of the interface type, achieving polymorphism.
   - At runtime, the appropriate implementation of the method is invoked based on the actual type of the object.
   - This allows you to write code that is not dependent on specific class implementations but rather on the contract defined by the interface.

4. Example:
   ```java
   public interface Vehicle {
       void start();
       void stop();
   }

   public class Car implements Vehicle {
       @Override
       public void start() {
           System.out.println("Car started.");
       }

       @Override
       public void stop() {
           System.out.println("Car stopped.");
       }
   }

   public class Bike implements Vehicle {
       @Override
       public void start() {
           System.out.println("Bike started.");
       }

       @Override
       public void stop() {
           System.out.println("Bike stopped.");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Vehicle car = new Car();
           Vehicle bike = new Bike();

           car.start();  // Output: Car started.
           bike.start(); // Output: Bike started.
       }
   }
   ```

In the example above, the `Vehicle` interface defines the contract for classes representing vehicles. The `Car` and `Bike` classes implement the `Vehicle` interface and provide their own implementations for the `start()` and `stop()` methods.

By creating objects of the `Car` and `Bike` classes and assigning them to variables of the `Vehicle` interface type, polymorphism is achieved. The `start()` method is invoked on the `car` and `bike` objects, and the appropriate implementation is called based on the actual type of the objects.

This polymorphic behavior allows you to write code that is generic and works with any class implementing the `Vehicle` interface. It enables code reuse, flexibility, and the ability to work with objects at a higher level of abstraction.

###  Polymorphic array of objects based on inheritance

Certainly! Here's an example of a polymorphic array of objects:

```java
public class Shape {
    public void draw() {
        System.out.println("Drawing a shape");
    }
}

public class Circle extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

public class Square extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a square");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape[] shapes = new Shape[3];
        shapes[0] = new Circle();
        shapes[1] = new Square();
        shapes[2] = new Circle();

        for (Shape shape : shapes) {
            shape.draw();
        }
    }
}
```

In this example, we have a class hierarchy consisting of a base class `Shape` and two derived classes `Circle` and `Square`, both of which inherit from `Shape` and override the `draw()` method.

In the `Main` class, we create an array `shapes` of type `Shape` and initialize it with instances of `Circle`, `Square`, and `Circle`. Since both `Circle` and `Square` are subclasses of `Shape`, they can be stored in the array of type `Shape`. This is an example of polymorphism, where objects of different classes are treated as objects of a common superclass.

We then iterate over the `shapes` array using a foreach loop, calling the `draw()` method on each object. Since the `draw()` method is overridden in the subclasses, the appropriate implementation is executed based on the actual type of each object.

When you run the program, it will output:

```
Drawing a circle
Drawing a square
Drawing a circle
```

This demonstrates how polymorphism allows you to treat objects of different classes as if they belong to a common type, enabling you to write code that operates on them uniformly.


### Polymorphic array of objects based on interface implementation


Here's an updated example that demonstrates a polymorphic array of objects based on interface implementation:

```java
interface Drawable {
    void draw();
}

class Circle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Square implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a square");
    }
}

public class Main {
    public static void main(String[] args) {
        Drawable[] drawables = new Drawable[3];
        drawables[0] = new Circle();
        drawables[1] = new Square();
        drawables[2] = new Circle();

        for (Drawable drawable : drawables) {
            drawable.draw();
        }
    }
}
```

In this example, we have an interface `Drawable` that declares the `draw()` method. Both the `Circle` and `Square` classes implement this interface and provide their own implementations for the `draw()` method.

In the `Main` class, we create an array `drawables` of type `Drawable` and initialize it with instances of `Circle`, `Square`, and `Circle`. Since both `Circle` and `Square` implement the `Drawable` interface, they can be stored in the array of type `Drawable`. This is an example of polymorphism based on interface implementation.

We then iterate over the `drawables` array using a foreach loop, calling the `draw()` method on each object. Since each object in the array implements the `draw()` method from the `Drawable` interface, the appropriate implementation is executed based on the actual type of each object.

When you run the program, it will output:

```
Drawing a circle
Drawing a square
Drawing a circle
```

This demonstrates how polymorphism, based on interface implementation, allows you to treat objects of different classes as if they implement a common interface and provides a way to write code that operates on them uniformly.

### Factories

Here's an example of a factory pattern using interfaces and a polymorphic array of objects in Java:

```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Square implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a square");
    }
}

class ShapeFactory {
    public Shape createShape(String type) {
        if (type.equalsIgnoreCase("circle")) {
            return new Circle();
        } else if (type.equalsIgnoreCase("square")) {
            return new Square();
        } else {
            throw new IllegalArgumentException("Invalid shape type");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        ShapeFactory factory = new ShapeFactory();
        Shape[] shapes = new Shape[2];
        shapes[0] = factory.createShape("circle");
        shapes[1] = factory.createShape("square");

        for (Shape shape : shapes) {
            shape.draw();
        }
    }
}
```

In this example, we have an interface `Shape` that declares the `draw()` method. The `Circle` and `Square` classes implement the `Shape` interface and provide their own implementations for the `draw()` method.

The `ShapeFactory` class acts as a factory for creating different shapes based on a given type. The `createShape()` method takes a `String` argument representing the type of shape to create. If the type is "circle," it creates and returns a `Circle` object. If the type is "square," it creates and returns a `Square` object. Otherwise, it throws an `IllegalArgumentException`.

In the `Main` class, we create an instance of `ShapeFactory` and use it to create two shapes: a circle and a square. We store these shapes in a polymorphic array of type `Shape`. This means that we can store objects of different classes that implement the `Shape` interface in the same array.

We then iterate over the `shapes` array using a foreach loop and call the `draw()` method on each object. Since the `draw()` method is overridden in the `Circle` and `Square` classes, the appropriate implementation is executed based on the actual type of each object.

When you run the program, it will output:

```
Drawing a circle
Drawing a square
```

This demonstrates how the factory pattern, combined with interfaces and a polymorphic array of objects, allows for the creation and manipulation of different objects based on a common interface, providing flexibility and code reusability.

Here's an updated example that includes a `Shape` abstract class with a base implementation of the `draw()` method:

```java
abstract class Shape {
    public abstract void draw();

    public void commonMethod() {
        System.out.println("This is a common method in the Shape class");
    }
}

class Circle extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Square extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a square");
    }
}

class ShapeFactory {
    public Shape createShape(String type) {
        if (type.equalsIgnoreCase("circle")) {
            return new Circle();
        } else if (type.equalsIgnoreCase("square")) {
            return new Square();
        } else {
            throw new IllegalArgumentException("Invalid shape type");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        ShapeFactory factory = new ShapeFactory();
        Shape[] shapes = new Shape[2];
        shapes[0] = factory.createShape("circle");
        shapes[1] = factory.createShape("square");

        for (Shape shape : shapes) {
            shape.draw();
            shape.commonMethod();
        }
    }
}
```

In this updated example, we have introduced an abstract class `Shape` that provides a base implementation for the `draw()` method. The `draw()` method is declared as abstract in the `Shape` class, making it mandatory for subclasses to provide their own implementation. Additionally, the `Shape` class includes a non-abstract method called `commonMethod()` which has a base implementation.

The `Circle` and `Square` classes extend the `Shape` class and provide their own implementations for the `draw()` method.

In the `Main` class, we create an instance of `ShapeFactory` and use it to create a circle and a square. We store these shapes in a polymorphic array of type `Shape`. The `draw()` method is called on each object, and since `Circle` and `Square` are subclasses of `Shape`, they inherit the `commonMethod()` implementation as well.

When you run the program, it will output:

```
Drawing a circle
This is a common method in the Shape class
Drawing a square
This is a common method in the Shape class
```

This example demonstrates how the abstract class `Shape` can provide a common base implementation for the `draw()` method, while still allowing subclasses to override it. The use of interfaces, abstract classes, and polymorphism provides a flexible and extensible approach to working with different shapes in a factory pattern.

## Generics

Java generics provide a way to create reusable and type-safe code by allowing classes and methods to be parameterized with types. Generics enable you to define classes, interfaces, and methods that can work with different types without sacrificing type safety at compile time. 

Generics provide several benefits, including type safety, code reusability, and improved code readability. They allow you to write generic algorithms and data structures that can work with different types, providing flexibility and reducing the need for type casting. Generics are widely used in Java collections, such as ArrayList, HashSet, and HashMap, to ensure type safety and to enable generic programming paradigms.

Here are the key concepts and usage of generics in Java:

### Type Parameters

Type parameters in Java generics are placeholders for actual types that will be supplied when using generic classes, interfaces, or methods. They allow you to create reusable and type-safe code by making the code generic and independent of specific types.

Here are the key points about type parameters in Java generics:

1. Syntax:
   - Type parameters are defined using angle brackets `< >` after the class, interface, or method name.
   - Type parameter names are typically single uppercase letters, but any valid identifier can be used.
   - Example:
     ```java
     class MyClass<T> {
         // Class implementation using type parameter T
     }
     
     interface MyInterface<U> {
         // Interface methods using type parameter U
     }
     
     <V> void myMethod(V param) {
         // Method implementation using type parameter V
     }
     ```

2. Naming Conventions:
   - By convention, single uppercase letters (such as T, U, V) are used as type parameter names to represent arbitrary types.
   - However, you can use any valid identifier as the type parameter name.
   - Choose a type parameter name that is meaningful and reflects the purpose of the parameter in your code.

3. Parameterizing Classes and Interfaces:
   - Type parameters are specified when creating instances of generic classes or implementing generic interfaces.
   - Actual types are provided as type arguments when instantiating the class or implementing the interface.
   - Example:
     ```java
     MyClass<Integer> myInt = new MyClass<>();
     MyInterface<String> myStr = new MyInterfaceImpl<>();
     ```

4. Multiple Type Parameters:
   - You can define multiple type parameters for a class, interface, or method, separated by commas.
   - Example:
     ```java
     class Pair<K, V> {
         private K key;
         private V value;
         
         // Class implementation using type parameters K and V
     }
     
     <T, U> void processPair(Pair<T, U> pair) {
         // Method implementation using type parameters T and U
     }
     ```

5. Type Parameter Constraints:
   - Type parameters can be constrained to specific types or interfaces using upper bounds or lower bounds.
   - Upper bounds restrict the type parameter to a specific class or interface or its subtypes.
   - Lower bounds restrict the type parameter to a specific class or interface or its supertypes.
   - Example:
     ```java
     class MyClass<T extends Number> {
         // Class implementation using type parameter T, which must be a subtype of Number
     }
     
     <T extends Comparable<T>> void compare(T obj1, T obj2) {
         // Method implementation with a type parameter T that must implement Comparable
     }
     ```

Type parameters in Java generics provide flexibility and enable the creation of generic code that can work with different types. They allow you to write reusable and type-safe code, avoiding the need for explicit type casting and improving code readability. Type parameters are widely used in Java collections, algorithms, and APIs to create generic classes, interfaces, and methods that can operate on various types while maintaining type safety.

Here's an example of using type parameters in a simple generic class called `Box`. The `Box` class allows you to store and retrieve an object of any type:

```java
public class Box<T> {
    private T item;

    public void addItem(T item) {
        this.item = item;
    }

    public T getItem() {
        return item;
    }

    public static void main(String[] args) {
        // Create a Box for Integer
        Box<Integer> integerBox = new Box<>();
        integerBox.addItem(42);
        int number = integerBox.getItem(); // No casting needed
        System.out.println("Number: " + number);

        // Create a Box for String
        Box<String> stringBox = new Box<>();
        stringBox.addItem("Hello, World!");
        String message = stringBox.getItem(); // No casting needed
        System.out.println("Message: " + message);
    }
}
```

In the example above, the `Box` class is defined with a type parameter `T`. This allows the class to work with any type specified during instantiation. The `addItem` method accepts an item of type `T` and stores it in the `item` field. The `getItem` method retrieves the item of type `T` from the `item` field.

In the `main` method, two instances of the `Box` class are created: one for `Integer` and one for `String`. The type parameter `T` is replaced with the actual types `Integer` and `String` when creating the instances. This ensures that the `Box` objects are restricted to storing and retrieving only the specified types.

With this approach, you can create instances of `Box` for any type you need, and the type safety is maintained throughout the usage of the class. The compiler ensures that only compatible types are used, and you don't need to explicitly cast the retrieved items to their original types.

### Parameterized Types

Parameterized types in Java generics refer to the use of actual type arguments to specify the specific types that a generic class, interface, or method will work with. They allow you to create instances of generic classes or invoke generic methods with specific types, providing type safety and enabling the creation of reusable code.

Here are the key points about parameterized types in Java generics:

1. Type Arguments:
   - Type arguments are actual types that are provided as arguments when using a generic class, interface, or method.
   - Type arguments replace the type parameters defined in the generic declaration.
   - Example:
     ```java
     List<String> stringList = new ArrayList<>(); // Parameterized type: List<String>
     Map<Integer, String> map = new HashMap<>(); // Parameterized type: Map<Integer, String>
     ```

2. Creating Instances:
   - Parameterized types are used when creating instances of generic classes.
   - Type arguments are supplied within the angle brackets after the class name.
   - Example:
     ```java
     List<Integer> numbers = new ArrayList<>();
     Set<String> stringSet = new HashSet<>();
     ```

3. Invoking Generic Methods:
   - Parameterized types are also used when invoking generic methods.
   - Type arguments are provided when calling the generic method.
   - Example:
     ```java
     Collections.<Integer>sort(numbers); // Type argument <Integer> for the sort() method
     MyClass.<String>myGenericMethod("Hello"); // Type argument <String> for the myGenericMethod() method
     ```

4. Type Safety:
   - Parameterized types ensure type safety by specifying the specific types that a generic class, interface, or method will work with.
   - Type arguments allow the compiler to perform type checking at compile-time, preventing type-related errors.
   - The compiler can detect incompatible types or issues with type conversions.
   - Example:
     ```java
     List<String> stringList = new ArrayList<>();
     stringList.add("Hello");
     stringList.add(42); // Error: Incompatible types, expects String
     ```

5. Raw Types:
   - It is possible to use a generic class without providing type arguments, which results in a raw type.
   - Raw types do not perform type checking and are less type-safe.
   - However, raw types are still allowed for backward compatibility with pre-Java 5 code.
   - Example:
     ```java
     List list = new ArrayList(); // Raw type: List (without type argument)
     list.add("Hello");
     list.add(42); // No compile-time error, but less type-safe
     ```

Parameterized types in Java generics allow you to create type-safe and reusable code by providing actual types for generic classes, interfaces, or methods. They improve code readability, reduce the need for explicit type casting, and help catch type-related errors at compile-time. By using parameterized types, you can write more generic and flexible code that can work with various types while maintaining type safety.

Here's last with key points about parameterized types in Java generics:

```java
public class Box<T> {
    private T item;

    public void addItem(T item) {
        this.item = item;
    }

    public T getItem() {
        return item;
    }

    public static void main(String[] args) {
        // Create a Box for Integer
        Box<Integer> integerBox = new Box<>(); // Parameterized type: Box<Integer>
        integerBox.addItem(42);
        int number = integerBox.getItem(); // No casting needed
        System.out.println("Number: " + number);

        // Create a Box for String
        Box<String> stringBox = new Box<>(); // Parameterized type: Box<String>
        stringBox.addItem("Hello, World!");
        String message = stringBox.getItem(); // No casting needed
        System.out.println("Message: " + message);
    }
}
```

Key points about parameterized types in the example:

1. Parameterized Type:
   - The class `Box` is declared with a type parameter `T` using angle brackets `<T>`.
   - This makes `Box` a generic class that can work with any type specified during instantiation.
   - Example: `Box<Integer>` and `Box<String>` create parameterized types of `Box` for `Integer` and `String` respectively.

2. Type Argument:
   - When creating an instance of `Box`, the type parameter `T` is replaced with an actual type called the type argument.
   - The type argument is specified within the angle brackets during object creation.
   - Example: `new Box<Integer>()` creates an instance of `Box` with `Integer` as the type argument.

3. Type Safety:
   - Parameterized types provide type safety by allowing the compiler to enforce type constraints at compile time.
   - The compiler ensures that only compatible types are used with the parameterized types.
   - Example: `integerBox.addItem(42)` adds an `Integer` value, and `int number = integerBox.getItem()` retrieves it without casting.

4. No Casting Required:
   - With parameterized types, there is no need to explicitly cast the retrieved items to their original types.
   - The compiler automatically infers the correct type based on the type argument.
   - Example: `int number = integerBox.getItem()` retrieves the `Integer` value without requiring casting.

Using parameterized types in Java generics allows you to create generic classes, interfaces, or methods that can work with a range of types while ensuring type safety. By specifying the type argument when creating instances, you can create specialized versions of generic classes that are restricted to specific types. This improves code reusability and readability while preventing type-related errors.

### Generic Methods

Generic methods in Java generics are methods that are parameterized with type parameters, allowing them to work with multiple types. They provide a way to write methods that can operate on different types while maintaining type safety and code reusability.

Here are the key points about generic methods in Java generics:

1. Syntax:
   - Generic methods are declared by specifying the type parameters before the return type of the method.
   - Type parameters are enclosed in angle brackets `< >`.
   - Example:
     ```java
     public <T> void myGenericMethod(T item) {
         // Method implementation using type parameter T
     }
     ```

2. Type Parameters:
   - Type parameters in generic methods are independent of the type parameters of the enclosing class or interface.
   - Type parameters can have any valid identifier name, but by convention, a single uppercase letter is used (e.g., T, U, V).
   - Multiple type parameters can be declared, separated by commas.
   - Example:
     ```java
     public <T, U> void myGenericMethod(T item1, U item2) {
         // Method implementation using type parameters T and U
     }
     ```

3. Type Inference:
   - In many cases, the type arguments for generic methods can be inferred by the compiler based on the method arguments.
   - This allows you to invoke the generic method without explicitly specifying the type arguments.
   - Example:
     ```java
     myGenericMethod("Hello"); // Inferred type argument: String
     myGenericMethod(42); // Inferred type argument: Integer
     ```

4. Using Type Parameters:
   - Type parameters in generic methods can be used as the method parameter types, return type, or within the method implementation.
   - They allow you to perform operations or apply logic that is generic and independent of specific types.
   - Example:
     ```java
     public <T> T processItem(T item) {
         // Method implementation using type parameter T
         return item;
     }
     ```

5. Bounds for Type Parameters:
   - Type parameters in generic methods can have bounds, similar to type parameters in generic classes or interfaces.
   - Bounds restrict the types that can be used as type arguments.
   - Example:
     ```java
     public <T extends Number> double sumNumbers(T[] numbers) {
         // Method implementation using type parameter T, which must be a subtype of Number
         double sum = 0;
         for (T number : numbers) {
             sum += number.doubleValue();
         }
         return sum;
     }
     ```

Generic methods in Java generics provide flexibility and enable you to write reusable code that can work with different types. They are useful when you need to create methods that are not tied to a specific class but can operate on various types. Generic methods are commonly used in utility classes, algorithms, and APIs to provide generic behavior while maintaining type safety and code reusability.

### Wildcards

Wildcards in Java generics provide a way to create flexible and reusable code that can work with different types. They allow you to define generic classes, interfaces, or methods that operate on a range of unknown types or specific subtypes.

There are two types of wildcards in Java generics: the upper bounded wildcard (`<?>`) and the lower bounded wildcard (`<? super T>`). Let's explore each one:

1. Upper Bounded Wildcard (`<?>`):
   - The `<?>` wildcard represents an unknown type that is a subtype of a specified upper bound.
   - It allows the generic code to accept any type that is a subtype of the specified upper bound.
   - It provides flexibility and allows the code to work with a range of different types.
   - Example:
     ```java
     public void processList(List<? extends Number> numbers) {
         // Process a list of numbers or its subtypes
         // Can read from the list but cannot write into it
     }
     ```
   - In the example above, the `processList` method accepts a `List` that contains elements of an unknown type, which is a subtype of `Number`. It can work with lists of `Integer`, `Double`, or any other subtype of `Number`. The method can read elements from the list but cannot add or modify elements.

2. Lower Bounded Wildcard (`<? super T>`):
   - The `<? super T>` wildcard represents an unknown type that is a supertype of a specified lower bound.
   - It allows the generic code to accept any type that is a supertype of the specified lower bound.
   - It provides flexibility and allows the code to work with a range of different types.
   - Example:
     ```java
     public void addNumbers(List<? super Integer> numbers) {
         // Add integers or any supertype of Integer to the list
         // Can add elements but cannot safely read from the list
     }
     ```
   - In the example above, the `addNumbers` method accepts a `List` that can contain elements of an unknown type, which is a supertype of `Integer`. It can add integers or any supertype of `Integer` to the list. The method can add elements to the list, but it cannot safely read elements as the exact type is unknown.

Wildcards in Java generics provide a way to write more flexible and reusable code that can work with a range of types. They allow you to create generic classes, interfaces, or methods that can operate on unknown types or specific subtypes, providing flexibility and type safety. Wildcards are commonly used when defining generic collections, utility methods, or APIs that need to accommodate a variety of types.

Here's an example using wildcards in Java generics:

```java
import java.util.ArrayList;
import java.util.List;

public class WildcardExample {
    public static void printList(List<?> list) {
        for (Object item : list) {
            System.out.println(item);
        }
    }

    public static void main(String[] args) {
        List<Integer> integerList = new ArrayList<>();
        integerList.add(10);
        integerList.add(20);
        integerList.add(30);

        List<String> stringList = new ArrayList<>();
        stringList.add("Hello");
        stringList.add("World");

        System.out.println("Printing integerList:");
        printList(integerList);

        System.out.println("Printing stringList:");
        printList(stringList);
    }
}
```

In this example, we have a method `printList` that takes a `List` with a wildcard `?` as the type parameter. The `printList` method can accept a `List` of any type because the wildcard allows for flexibility.

In the `main` method, we create two lists: `integerList` of type `List<Integer>` and `stringList` of type `List<String>`. We then call the `printList` method and pass these lists as arguments.

The `printList` method iterates over the given list using a for-each loop and prints each item. Since the `list` parameter has a wildcard, we can't know the exact type of the items, so we use the `Object` type to iterate over them.

When we run the program, it prints the elements of both `integerList` and `stringList` without any issues, even though they are of different types. The wildcard allows us to create a single method that can work with different types of lists.

Using wildcards in Java generics provides flexibility when working with generic types. It allows us to create generic methods or classes that can accept different types without being tightly bound to a specific type.

### Bounded Type Parameters

Bounded type parameters in Java generics allow you to restrict the types that can be used as type arguments in a generic class, interface, or method. By using bounded type parameters, you can define generic code that operates on a specific range of types or their subtypes.

There are two types of bounded type parameters: upper bounded type parameters and lower bounded type parameters. Let's explore each one:

1. Upper Bounded Type Parameters:
   - An upper bounded type parameter restricts the type argument to be a specific type or any of its subtypes.
   - It is denoted by the `extends` keyword, followed by the upper bound type.
   - Example:
     ```java
     public class Box<T extends Number> {
         // Code for the generic class Box
     }
     ```
   - In the example above, the type parameter `T` is bounded by the `Number` class. It means that when creating an instance of the `Box` class, the type argument for `T` must be either `Number` or one of its subtypes, such as `Integer`, `Double`, etc. This ensures that the generic class `Box` can only work with numeric types.

2. Lower Bounded Type Parameters:
   - A lower bounded type parameter restricts the type argument to be a specific type or any of its supertypes.
   - It is denoted by the `super` keyword, followed by the lower bound type.
   - Example:
     ```java
     public void processList(List<? super Integer> numbers) {
         // Code for the method that processes a list
     }
     ```
   - In the example above, the type parameter for the `numbers` list is bounded by `Integer` or any of its supertypes. It means that the method `processList` can accept a `List` of `Integer` or a supertype of `Integer`, such as `Number` or `Object`. This allows the method to work with a broader range of types.

Bounded type parameters in Java generics provide a way to restrict the types that can be used in generic code, ensuring type safety and allowing for more specific operations. They allow you to define generic classes, interfaces, or methods that work with a specific range of types or their subtypes. By bounding the type parameters, you can create more specialized and reusable code that operates on a restricted set of types, enabling better code organization and preventing potential type-related errors.






## Packages and Modules

Packages and modules in Java are mechanisms for organizing and structuring code into logical units, providing encapsulation, and managing dependencies. They help in maintaining code organization, improving code reusability, and managing the visibility and accessibility of classes and resources. Let's explore each concept in more detail:

1. Packages:
   - A package in Java is a namespace that groups related classes and interfaces together.
   - Packages are used to avoid naming conflicts between classes and provide a hierarchical organization of code.
   - Packages are declared at the top of Java source files using the `package` keyword.
   - Packages can contain sub-packages, allowing for further organization and categorization of classes.
   - Packages facilitate access control through the use of access modifiers (`public`, `protected`, `private`, and default visibility) to restrict the visibility of classes and members within a package.
   - Example:
     ```java
     package com.example.myapp;
     
     public class MyClass {
         // Class implementation
     }
     ```

2. Modules:
   - Modules are a feature introduced in Java 9 to provide a higher level of encapsulation and modularity in the codebase.
   - A module is a collection of packages and resources that are designed to be cohesive and reusable.
   - Modules define dependencies between each other, specifying which packages are accessible to other modules.
   - Modules are declared in a module-info.java file, which is a descriptor file at the root of the module.
   - Modules enable explicit control over what is exported (made accessible) to other modules and what is encapsulated (hidden) within the module.
   - Modules provide a higher level of encapsulation than packages by enforcing stricter access control and encapsulation boundaries.
   - Example module-info.java:
     ```java
     module com.example.myapp {
         requires other.module;
         exports com.example.myapp;
     }
     ```

3. Benefits of Packages and Modules:
   - Code organization: Packages and modules allow for logical grouping and organization of code, making it easier to navigate and understand.
   - Code reusability: Packages and modules promote code reuse by providing a clear structure and separation of concerns, allowing modules to be shared across projects.
   - Encapsulation and access control: Packages and modules enforce access control rules, allowing developers to control the visibility and accessibility of classes and members.
   - Dependency management: Modules explicitly declare their dependencies, making it easier to manage and understand the dependencies between different parts of the codebase.

Packages and modules are essential concepts in Java that help in creating well-structured and modular codebases, enabling better code organization, reusability, and encapsulation. They are used to manage visibility, control access, and manage dependencies between different parts of a Java application.
