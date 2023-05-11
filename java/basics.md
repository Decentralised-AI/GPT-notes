# Java Basics

## Install the develop environment in Linux

To install the development environment for Java on Linux, you need to follow these general steps:

1. Install the Java Development Kit (JDK):
   - Open a terminal.
   - Update the package lists by running the command:
     ```
     sudo apt update
     ```
   - Install the default JDK package (OpenJDK) by running the command:
     ```
     sudo apt install default-jdk
     ```
   - Alternatively, you can install a specific JDK version by specifying the package name, such as `openjdk-11-jdk` for OpenJDK 11.

2. Verify the JDK installation:
   - After the installation is complete, verify that the JDK is properly installed by running the following command:
     ```
     java -version
     ```
   - This command should display the Java version information, confirming that the JDK is installed and accessible.

3. Set up environment variables:
   - To configure the Java environment variables, open a terminal and run the following command:
     ```
     sudo nano /etc/environment
     ```
   - In the editor, add the following line at the end of the file:
     ```
     JAVA_HOME="/usr/lib/jvm/default-java"
     ```
   - Save the file and exit the editor.
   - Update the environment variables by running the command:
     ```
     source /etc/environment
     ```

4. Install an Integrated Development Environment (IDE) (Optional):
   - While not strictly necessary, using an IDE can greatly enhance your Java development experience.
   - Popular Java IDEs for Linux include Eclipse, IntelliJ IDEA, and NetBeans.
   - You can download the IDE of your choice from the respective website and follow the installation instructions specific to the IDE.

That's it! You should now have a Java development environment set up on your Linux system. You can create Java projects, write code, compile and run Java programs using the installed JDK and your preferred IDE or a text editor.

## IDES

Integrated Development Environments (IDEs) provide a comprehensive set of tools and features to aid in the development of software, including the ability to execute Java programs. Here's an overview of how IDEs can execute Java programs:

1. Creating a Java Project:
   - In your IDE, create a new Java project or import an existing one. This step helps organize your code and manage dependencies.

2. Writing Java Code:
   - Within your Java project, create or open a Java source file (usually with a `.java` extension) in the IDE's code editor.
   - Write your Java code, including classes, methods, and other necessary components, using the IDE's code editing features (e.g., syntax highlighting, code completion, refactoring tools).

3. Building the Project:
   - IDEs automatically handle the build process for you. When you save changes to your Java code, the IDE typically compiles the code in the background or upon request.
   - The IDE may provide visual feedback, such as highlighting compilation errors or displaying build logs, to help you identify and fix any issues.

4. Running Java Programs:
   - IDEs offer various ways to execute Java programs. Here are a few common methods:

   a. Running the Main Class:
      - If your Java program contains a `main` method (the entry point for execution), you can directly run the main class from within the IDE.
      - Right-click on the main class file in the project explorer or code editor.
      - Choose the "Run" or "Run As" option from the context menu and select "Java Application" or a similar option.
      - The IDE will execute the program and display the output in the IDE's console or output window.

   b. Creating Run/Debug Configurations:
      - IDEs allow you to create custom run/debug configurations to execute Java programs with specific settings.
      - Configure the run/debug options, such as program arguments, VM options, classpath, and environment variables.
      - Save the configuration and execute it with the click of a button or a keyboard shortcut.

   c. Running JUnit Tests:
      - If your project includes JUnit tests, IDEs provide integration with the JUnit framework.
      - You can run individual test methods, test suites, or the entire test suite directly from the IDE.
      - The IDE displays the test results, including pass/fail status and any associated log output.

   d. Running External Tools or Plugins:
      - IDEs often offer integration with external tools or plugins for specific purposes, such as application servers, build tools (Maven, Gradle), or other frameworks.
      - You can configure and execute these tools or plugins from within the IDE, leveraging their functionality alongside your Java programs.

5. Debugging Java Programs:
   - IDEs provide powerful debugging capabilities to help identify and fix issues in Java programs.
   - You can set breakpoints in your code, step through the code execution, inspect variables, and analyze the program's state at different points.
   - IDEs offer features like watch expressions, call stack visualization, and interactive debugging tools to assist in troubleshooting.

IDEs streamline the development and execution process by providing an integrated environment where you can write, build, run, and debug your Java programs effectively. The specific steps and options may vary slightly depending on the IDE you are using, but the general workflow remains consistent.

## Compiling and running Java programs

To write and run Java programs, you'll need a text editor or an integrated development environment (IDE) and a Java Development Kit (JDK) installed on your system. Here's an overview of the process:

1. Writing Java Programs:
   - Open a text editor or an IDE (such as Eclipse, IntelliJ IDEA, or NetBeans) to write your Java code.
   - Create a new file with a `.java` extension. This file will contain your Java source code.
   - Start by writing the Java code within a class. A basic Java program must contain a `main` method, which serves as the entry point for execution.

   Here's an example of a simple Java program that prints "Hello, World!" to the console:

   ```java
   public class HelloWorld {
       public static void main(String[] args) {
           System.out.println("Hello, World!");
       }
   }
   ```

2. Compiling Java Programs:
   - Once you have written your Java program, you need to compile it to bytecode, which can be executed by the Java Virtual Machine (JVM).
   - Open a command prompt or terminal and navigate to the directory containing your Java source file (`HelloWorld.java` in the example above).
   - Use the `javac` command followed by the filename to compile the Java source file. For example:
     ```
     javac HelloWorld.java
     ```
   - If there are no compilation errors, this will generate a compiled bytecode file with a `.class` extension.

3. Running Java Programs:
   - After successful compilation, you can run the Java program.
   - In the same command prompt or terminal, use the `java` command followed by the class name (excluding the `.java` or `.class` extension) to execute the program. For example:
     ```
     java HelloWorld
     ```
   - The program output will be displayed in the console:
     ```
     Hello, World!
     ```

4. Managing Dependencies:
   - If your Java program depends on external libraries or frameworks, you'll need to manage those dependencies.
   - Build tools like Apache Maven or Gradle can help you handle dependencies by specifying them in a configuration file (e.g., `pom.xml` for Maven).
   - These build tools will automatically download the required dependencies and include them in the compilation and execution process.

It's important to note that more complex Java projects typically involve multiple classes and packages. In such cases, you'll need to organize your code into appropriate directory structures and import necessary classes in your source files.

By following these steps, you can write and run Java programs on your local machine. As your projects grow, using an IDE with features like code completion, debugging, and project management can greatly enhance your development experience.

## Hello World

To create and execute a Java "Hello, World!" program, follow these steps:

1. Set up the Java Development Environment:
   - Install the Java Development Kit (JDK) on your system. Ensure that the `java` and `javac` commands are accessible from the command line or terminal.

2. Create a new Java source file:
   - Open a text editor or an Integrated Development Environment (IDE) of your choice.
   - Create a new file and give it a `.java` extension. For example, `HelloWorld.java`.

3. Write the "Hello, World!" program:
   - Open the Java source file (`HelloWorld.java`) in your text editor or IDE.
   - Inside the file, write the following code:

   ```java
   public class HelloWorld {
       public static void main(String[] args) {
           System.out.println("Hello, World!");
       }
   }
   ```

   This program defines a class named `HelloWorld` with a `main` method. The `main` method is the entry point for Java programs, where the execution starts. It prints "Hello, World!" to the console using the `System.out.println` statement.

4. Save the Java source file:
   - Save the Java source file (`HelloWorld.java`) in an appropriate directory on your system.

5. Compile the Java program:
   - Open a command prompt or terminal.
   - Navigate to the directory where the Java source file is located.
   - Compile the Java source file using the `javac` command followed by the filename:

   ```
   javac HelloWorld.java
   ```

   This command compiles the Java source file into bytecode and generates a corresponding `.class` file.

6. Run the Java program:
   - After successful compilation, execute the Java program using the `java` command followed by the class name:

   ```
   java HelloWorld
   ```

   The program will be executed, and you should see the output in the console:

   ```
   Hello, World!
   ```

Congratulations! You have created and executed a Java "Hello, World!" program. This basic program serves as a starting point for learning Java and verifying that your Java development environment is properly set up.

## Data types

Java has several built-in data types that allow you to store and manipulate different kinds of values. Here are the main data types in Java:

1. Primitive Data Types:
   - byte: Represents a signed 8-bit integer. Range: -128 to 127.
   - short: Represents a signed 16-bit integer. Range: -32,768 to 32,767.
   - int: Represents a signed 32-bit integer. Range: -2,147,483,648 to 2,147,483,647.
   - long: Represents a signed 64-bit integer. Range: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.
   - float: Represents a single-precision 32-bit floating-point number.
   - double: Represents a double-precision 64-bit floating-point number.
   - boolean: Represents a boolean value (either true or false).
   - char: Represents a single Unicode character.

2. Reference Data Types:
   - Classes: You can define your own classes to represent complex objects.
   - Arrays: Allows you to store multiple values of the same type in a single variable.
   - Strings: Represents a sequence of characters.

3. Wrapper Classes:
   - Java also provides wrapper classes for each primitive data type. These classes allow you to treat the primitive types as objects.
   - For example, `Integer` is the wrapper class for `int`, `Double` for `double`, and so on.
   - Wrapper classes provide additional methods and functionality for working with primitive types.

4. Other Data Types:
   - Enumerations: Represents a fixed set of constants. Enumerations provide type safety and can be used in switch statements.
   - BigInteger: Represents an arbitrary-precision integer.
   - BigDecimal: Represents an arbitrary-precision decimal number.
   - Date and Time types: Java provides various classes for working with dates and times, such as `LocalDate`, `LocalTime`, `LocalDateTime`, `ZonedDateTime`, and more.

It's important to note that Java is a statically typed language, which means that you must declare the data type of a variable before using it. For example:

```java
int age = 25;
double salary = 50000.50;
boolean isStudent = true;
char grade = 'A';
String name = "John Doe";
```

Additionally, Java supports type inference with the introduction of the `var` keyword in Java 10. It allows the compiler to infer the type of a variable based on the value assigned to it.

```java
var count = 10; // Compiler infers count as int
var pi = 3.1415; // Compiler infers pi as double
var message = "Hello"; // Compiler infers message as String
```

Understanding and utilizing the different data types in Java is essential for effectively managing and manipulating data in your programs.

## Constants and variables

In Java, variables are used to store and manipulate data. They serve as named containers that hold values of a particular data type. Here's an overview of variables in Java:

1. Variable Declaration and Initialization:
   - To declare a variable, you need to specify its data type followed by the variable name. For example:
     ```java
     int age;
     double salary;
     String name;
     ```
   - Variables can be initialized at the time of declaration or later in the code. For example:
     ```java
     int age = 25;
     double salary = 50000.50;
     String name = "John Doe";
     ```

2. Variable Naming Rules:
   - Variable names must start with a letter, underscore (_), or dollar sign ($).
   - After the first character, variable names can include letters, digits, underscores, and dollar signs.
   - Variable names are case-sensitive. For example, `count` and `Count` are considered different variables.
   - It's good practice to use descriptive names that reflect the purpose of the variable.

3. Variable Types:
   - Local Variables: Variables declared within a method, constructor, or block are called local variables. They have a limited scope and are accessible only within the enclosing block.
   - Instance Variables: Variables declared within a class but outside any method are called instance variables. They are associated with an instance of the class and are accessible by any method within the class.
   - Class Variables (Static Variables): Variables declared with the `static` keyword within a class are called class variables. They are shared among all instances of the class and can be accessed using the class name.

4. Variable Assignments and Operations:
   - You can assign new values to variables using the assignment operator (=). For example:
     ```java
     age = 30;
     salary = salary + 1000.50;
     ```
   - Java supports various operators for performing arithmetic, assignment, comparison, logical, and other operations on variables.

5. Variable Scope:
   - The scope of a variable determines where it can be accessed within the program.
   - Local variables have a limited scope and are only accessible within the block where they are declared.
   - Instance variables are accessible throughout the class, within any method or constructor.
   - Class variables are accessible throughout the class and can also be accessed using the class name from other classes.

6. Constants:
   - In Java, you can declare constants using the `final` keyword. Constants are variables whose value cannot be changed once assigned.
   - By convention, constant names are written in uppercase with underscores separating words. For example:
     ```java
     final double PI = 3.1415;
     final int MAX_SIZE = 100;
     ```

Variables play a vital role in Java programming as they allow you to store and manipulate data dynamically. By understanding the different types of variables, their scope, and the rules for naming and initialization, you can effectively work with data in your Java programs.

## Operators, expressions and precedence

In Java, operators and expressions are fundamental components of the language that allow you to perform computations, manipulate data, and make decisions. Here's an explanation of operators and expressions in Java:

1. Operators:
   - Operators are symbols that perform specific operations on one or more operands (variables, constants, or expressions).
   - Java supports various types of operators, including:
     - Arithmetic Operators: Perform basic mathematical operations like addition (+), subtraction (-), multiplication (*), division (/), and modulus (%).
     - Assignment Operators: Assign values to variables, such as the equals sign (=), combined with arithmetic operators (+=, -=, *=, /=, %=).
     - Comparison Operators: Compare two values and return a boolean result, such as equal to (==), not equal to (!=), greater than (>), less than (<), etc.
     - Logical Operators: Perform logical operations on boolean values, such as logical AND (&&), logical OR (||), and logical NOT (!).
     - Bitwise Operators: Perform operations on individual bits of integer values, such as bitwise AND (&), bitwise OR (|), bitwise XOR (^), bitwise complement (~), etc.
     - Increment/Decrement Operators: Increase or decrease the value of a variable by one, such as increment (++), decrement (--).
     - Conditional Operator (Ternary Operator): Allows you to write compact conditional expressions, such as condition ? expression1 : expression2.
     - And more, including bitwise shift operators, instance of operator, etc.

2. Expressions:
   - Expressions are combinations of operators, operands, and method invocations that evaluate to a single value.
   - Java expressions can be as simple as a single variable or a constant, or they can be more complex, involving multiple operators and operands.
   - Examples of expressions:
     ```java
     int sum = 5 + 3; // Expression: 5 + 3
     boolean result = (age >= 18) && (salary > 50000); // Expression: (age >= 18) && (salary > 50000)
     int max = (a > b) ? a : b; // Expression: (a > b) ? a : b
     ```

3. Precedence and Associativity:
   - Operators in Java have different precedence levels, which determine the order of evaluation when multiple operators are present in an expression.
   - Parentheses can be used to override the default precedence and specify the desired order of evaluation.
   - Operators with higher precedence are evaluated before operators with lower precedence.
   - In cases where multiple operators have the same precedence, the associativity of the operators determines the evaluation order (left-to-right or right-to-left).

4. Side Effects:
   - Some operators, such as assignment operators and increment/decrement operators, can have side effects by modifying the values of variables.
   - It's important to understand the behavior of these operators and their potential impact on your program's logic.

Understanding operators and expressions is crucial for performing computations and making decisions in Java programs. By using the appropriate operators and constructing meaningful expressions, you can manipulate data and control the flow of your program effectively.
