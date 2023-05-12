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



