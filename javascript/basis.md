# Javascript basis
## Syntax
JavaScript uses a similar syntax to other programming languages, with statements and expressions used to define actions or values. Here's an example of a basic JavaScript statement:

```javascript
console.log("Hello, world!");
```

This statement prints the message "Hello, world!" to the console, which is a tool available in most web browsers for debugging and testing.

## Data types

3. Data types:
JavaScript has several built-in data types, including strings, numbers, booleans, arrays, objects, and more. Here are a few examples:

```javascript
// String data type
let myString = "Hello, world!";

// Number data type
let myNumber = 42;

// Boolean data type
let myBoolean = true;

// Array data type
let myArray = ["apple", "banana", "orange"];

// Object data type
let myObject = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
  email: "john@example.com"
};
```

### typeof operand

`typeof` is a built-in operator in JavaScript that is used to determine the data type of a given value. It takes a single operand (the value whose type is to be determined) and returns a string that indicates the type of the value.

The syntax for the `typeof` operator is as follows:

```
typeof operand
```

Here, `operand` is the value whose type is to be determined.

The `typeof` operator can return any of the following string values:

- `"undefined"`: If the operand is `undefined`.
- `"boolean"`: If the operand is a Boolean value (`true` or `false`).
- `"number"`: If the operand is a number, including integer, floating-point, and NaN values.
- `"string"`: If the operand is a string.
- `"bigint"`: If the operand is a BigInt value.
- `"symbol"`: If the operand is a symbol.
- `"function"`: If the operand is a function.
- `"object"`: If the operand is an object or `null`.

Here are some examples of the `typeof` operator in JavaScript:

```javascript
typeof 42; // "number"
typeof "hello"; // "string"
typeof true; // "boolean"
typeof {}; // "object"
typeof null; // "object"
typeof undefined; // "undefined"
typeof []; // "object"
typeof function() {}; // "function"
typeof NaN; // "number"
```

In the examples above, `typeof` is used to determine the data type of different values in JavaScript. Note that `typeof null` returns "object", which is a known quirk of the language. Also, `typeof []` returns "object", even though arrays are a specialized type of object in JavaScript.

Note that the `typeof` operator does not distinguish between different types of objects. It treats all objects (including arrays and dates) as a single data type, which is `"object"`. To determine the specific type of an object, you can use other techniques, such as the `instanceof` operator or the `Object.prototype.toString` method.

The `typeof` operator is useful for checking the type of a value before performing operations on it, or for debugging purposes. For example, you might use `typeof` to determine whether a variable is defined before accessing its properties, or to verify that a function argument has the expected data type.

### numbers

In JavaScript, the `number` data type represents both integer and floating-point numbers. Numbers in JavaScript are implemented using the IEEE-754 standard, which is the same standard used by most other programming languages.

There are several ways to represent numbers in JavaScript:

- Integer literals: These are whole numbers, expressed in decimal (base 10), binary (base 2), octal (base 8), or hexadecimal (base 16) notation. For example: `42`, `0b101010` (binary for 42), `0o52` (octal for 42), and `0x2a` (hexadecimal for 42).
- Floating-point literals: These are decimal numbers with a fractional part, expressed using a decimal point. For example: `3.14`, `1.0e-6` (scientific notation for 0.000001), and `Infinity` (representing positive infinity).
- Arithmetic expressions: These are combinations of numbers and arithmetic operators (`+`, `-`, `*`, `/`, `%`, and `**`) that evaluate to a numeric value. For example: `2 + 3`, `7 - 5`, `4 * 6`, `10 / 2`, `11 % 3` (remainder of 11 divided by 3), and `2 ** 8` (2 raised to the power of 8).

JavaScript provides several built-in functions for working with numbers, such as `parseInt` (converts a string to an integer), `parseFloat` (converts a string to a floating-point number), `isNaN` (checks if a value is not a number), `isFinite` (checks if a value is a finite number), `Math.abs` (returns the absolute value of a number), `Math.round` (rounds a number to the nearest integer), and many others.

One important thing to keep in mind when working with numbers in JavaScript is that they are subject to floating-point rounding errors. This means that some calculations may not yield exact results, especially when dealing with very large or very small numbers. To minimize rounding errors, you can use integer arithmetic (e.g., by multiplying and dividing by powers of 10) or a third-party library that provides arbitrary-precision arithmetic.

Here are some examples of using the `number` type in JavaScript:

```javascript
// Integer literals
let a = 42;
let b = 0b101010; // binary for 42
let c = 0o52; // octal for 42
let d = 0x2a; // hexadecimal for 42

console.log(a); // output: 42
console.log(b); // output: 42
console.log(c); // output: 42
console.log(d); // output: 42

// Floating-point literals
let e = 3.14;
let f = 1.0e-6; // scientific notation for 0.000001
let g = Infinity;

console.log(e); // output: 3.14
console.log(f); // output: 1e-6
console.log(g); // output: Infinity

// Arithmetic expressions
let x = 2 + 3;
let y = 7 - 5;
let z = 4 * 6;
let w = 10 / 2;
let r = 11 % 3;
let s = 2 ** 8;

console.log(x); // output: 5
console.log(y); // output: 2
console.log(z); // output: 24
console.log(w); // output: 5
console.log(r); // output: 2
console.log(s); // output: 256
```

In the examples above, we create variables of type `number` using integer literals, floating-point literals, and arithmetic expressions. We also use some arithmetic operators (`+`, `-`, `*`, `/`, `%`, and `**`) to perform calculations with these numbers. Finally, we use the `console.log` function to output the results to the console.

### string

In JavaScript, the `string` data type is used to represent text. A string is a sequence of characters enclosed in single or double quotes. Here are some examples:

```javascript
let message1 = 'Hello, world!';
let message2 = "This is a string.";
let message3 = 'It\'s a beautiful day.';

console.log(message1); // output: Hello, world!
console.log(message2); // output: This is a string.
console.log(message3); // output: It's a beautiful day.
```

In the first two examples, we create strings by enclosing the text in single and double quotes, respectively. In the third example, we need to use the backslash (`\`) to escape the single quote within the string.

Strings are important data types in JavaScript, and they support many operations and methods. Here are some examples of common string operations:

```javascript
// Concatenation
let firstName = 'John';
let lastName = 'Doe';
let fullName = firstName + ' ' + lastName;

console.log(fullName); // output: John Doe

// String length
let message = 'JavaScript is awesome!';
let length = message.length;

console.log(length); // output: 22

// Accessing characters by index
let str = 'Hello, world!';
let firstChar = str[0];
let lastChar = str[str.length - 1];

console.log(firstChar); // output: H
console.log(lastChar); // output: !

// Substrings
let email = 'user@example.com';
let username = email.substring(0, email.indexOf('@'));

console.log(username); // output: user
```

In the first example, we concatenate two strings using the `+` operator. In the second example, we use the `length` property of the string to get its length. In the third example, we access individual characters of the string using their index. In the fourth example, we extract a substring from a string using the `substring` method and the `indexOf` method to find the index of the "@" character.

### boolean

In JavaScript, the `boolean` data type is used to represent logical values. A boolean value can be either `true` or `false`. For example:

```javascript
let isRaining = true;
let hasSunshine = false;

console.log(isRaining);    // output: true
console.log(hasSunshine);  // output: false
```

Boolean values are often used in conditional statements to control the flow of a program. For example:

```javascript
let age = 25;

if (age >= 18) {
  console.log('You are an adult.');
} else {
  console.log('You are a minor.');
}
```

In this example, we use a conditional statement (`if...else`) to check if the `age` variable is greater than or equal to 18. If the condition is true, the first block of code will execute and display the message "You are an adult." Otherwise, the second block of code will execute and display the message "You are a minor."

Boolean values can also be created by using comparison operators, such as `==`, `!=`, `>`, `<`, `>=`, and `<=`. For example:

```javascript
let x = 5;
let y = 10;

console.log(x < y);   // output: true
console.log(x == y);  // output: false
```

In this example, we use the `<` operator to compare the values of `x` and `y`. The first expression returns `true` because `x` is less than `y`. We also use the `==` operator to check if `x` is equal to `y`. The second expression returns `false` because `x` is not equal to `y`.

### null and undefined

In JavaScript, both `null` and `undefined` represent the absence of a value, but they are used in different contexts.

`null` is an assignment value that represents the intentional absence of any object value. It can be assigned to a variable to explicitly indicate that it has no value or that a value is yet to be assigned. For example:

```javascript
let foo = null; // foo is explicitly assigned to null to indicate it has no value
```

`undefined`, on the other hand, indicates the absence of any assigned value. It is used when a variable has been declared but has not yet been assigned a value, or when a function is expected to return a value but doesn't. For example:

```javascript
let bar; // bar is declared but not assigned a value, so it is undefined
function baz() {
  // this function does not return a value, so it returns undefined
}
```

It's important to understand the difference between `null` and `undefined` because they can have different effects in your code. For example, trying to access a property of an object that is `undefined` will throw a `TypeError`, whereas accessing a property of an object that is `null` will not throw an error but will simply return `null`. 

In general, it's a good practice to initialize variables with a value to avoid confusion between `null` and `undefined`.

In JavaScript, there are several values that are considered falsy, meaning they are treated as if they are `false` in conditional statements. These values include `null`, `undefined`, `NaN`, an empty string `""`, the number `0`, and the boolean value `false`. Here's a closer look at each of these values:

- `null`: Represents a deliberate non-value or absence of any object value. For example, if a variable has been declared but has not been assigned a value, its value will be `null`.
```javascript
let a = null;
console.log(a); // output: null
```

- `undefined`: Indicates that a variable has been declared but not initialized, or that a function is expected to return a value but doesn't. It is also the default return value of functions that don't have an explicit return statement.
```javascript
let b;
console.log(b); // output: undefined
```

- `NaN`: Stands for "Not a Number" and is returned when a mathematical operation doesn't make sense or when the result is undefined.
```javascript
let c = "hello" / 2;
console.log(c); // output: NaN
```

- Empty string `""`: Represents an empty or blank string. It is also falsy, meaning it is treated as if it is `false` in conditional statements.
```javascript
let d = "";
if (d) {
  console.log("This will not be executed");
}
```

- Number `0`: Represents the number zero, which is also falsy.
```javascript
let e = 0;
if (!e) {
  console.log("This will be executed");
}
```

- Boolean `false`: Represents the boolean value false, which is also falsy.
```javascript
let f = false;
if (!f) {
  console.log("This will be executed");
}
```

It's important to understand these values because they can cause unexpected behavior in your code if not handled correctly in conditional statements or when performing operations.

## Literals

In JavaScript, a "literal" is a value that is directly specified in the source code, without the need for any additional computation or evaluation. For example, the following are all examples of literals in JavaScript:

- 42
- "hello world"
- true
- null

## Variables

In contrast, a "variable" is a named storage location in memory that can hold a value. Variables are used to store data that may change over time, or that is computed as part of a program's execution. In JavaScript, variables can be declared using the `var`, `let`, or `const` keywords.

The `var` keyword was the original way to declare variables in JavaScript, but it has since been largely replaced by `let` and `const`. Variables declared with `var` are function-scoped, which means that they are accessible within the function in which they are defined, as well as any nested functions. For example:

```javascript
function example() {
  var x = 42;
  console.log(x); // prints 42
}
```

In contrast, variables declared with `let` and `const` are block-scoped, which means that they are accessible only within the block in which they are defined. For example:

```javascript
function example() {
  let x = 42;
  if (true) {
    let x = 99;
    console.log(x); // prints 99
  }
  console.log(x); // prints 42
}
```

In addition to literals and variables, JavaScript also provides a range of operators and expressions that can be used to manipulate and combine values. These include arithmetic operators (such as `+`, `-`, `*`, and `/`), comparison operators (such as `==`, `!=`, `<`, and `>`), and logical operators (such as `&&`, `||`, and `!`).

## Castings and conversions

JavaScript provides various ways to convert one data type to another. These are known as type conversions or type castings. Type conversions are important because they allow us to use values of one type as another type, which can be useful in various programming scenarios.

Here are some common ways to convert between data types in JavaScript:

1. **String conversion:** You can convert any data type to a string using the `toString()` method. For example:

   ```javascript
   const num = 123;
   const str = num.toString(); // str is "123"
   ```

2. **Number conversion:** You can convert a string to a number using the `Number()` or `parseInt()` methods. For example:

   ```javascript
   const str = "123";
   const num1 = Number(str); // num1 is 123
   const num2 = parseInt(str); // num2 is 123
   ```

   You can also use the `parseFloat()` method to convert a string to a floating-point number.

3. **Boolean conversion:** You can convert any data type to a boolean using the `Boolean()` method. In general, any value that is considered "truthy" in JavaScript will be converted to `true`, and any value that is considered "falsy" will be converted to `false`. For example:

   ```javascript
   const num1 = 123;
   const bool1 = Boolean(num1); // bool1 is true

   const str = "";
   const bool2 = Boolean(str); // bool2 is false
   ```

4. **Explicit conversion:** You can also use explicit type conversions to convert values between types using the `String()`, `Number()`, and `Boolean()` functions. For example:

   ```javascript
   const num = 123;
   const str = String(num); // str is "123"

   const bool = true;
   const num1 = Number(bool); // num1 is 1
   const num2 = Number(false); // num2 is 0
   ```

It's important to understand the different ways to convert between data types in JavaScript to avoid unexpected results and errors in your code.



### valueOf() and toString()

`valueOf()` and `toString()` are methods available for JavaScript's `String` object.

The `valueOf()` method returns the primitive value of a `String` object. It's similar to the `toString()` method, but instead of returning a string, it returns the primitive value of the object.

For example, consider the following code:

```javascript
const str = "hello world";
const primitive = str.valueOf();
console.log(primitive);
```

The `valueOf()` method returns the primitive value of the `str` object, which is the string "hello world". The `console.log()` statement will output "hello world" to the console.

On the other hand, the `toString()` method returns a string representing the object. If the object is already a string, it simply returns the string itself.

For example, consider the following code:

```javascript
const str = "hello world";
const strObj = new String(str);
const strRepresentation = strObj.toString();
console.log(strRepresentation);
```

The `toString()` method returns a string representation of the `strObj` object, which is the string "hello world". The `console.log()` statement will output "hello world" to the console.

In general, you should use `valueOf()` when you want to retrieve the primitive value of a `String` object, and `toString()` when you want to convert the object to a string representation.

### Conversion table

Here's a table of conversion types in JavaScript:

| From Type | To Type | Conversion Method |
| --- | --- | --- |
| Number | String | `.toString()` or `String()` |
| String | Number | `parseInt()` or `parseFloat()` |
| Boolean | Number | `Number()` |
| Number | Boolean | `Boolean()` |
| String | Boolean | `Boolean()` |

Note that there are other ways to perform type conversions in JavaScript, but these are the most common methods. Also, keep in mind that some conversions may not be possible, and will result in a `NaN` or `undefined` value.

## Operators

In JavaScript, operators are special symbols or keywords that are used to perform operations on values. They can be used to perform arithmetic, comparison, assignment, logical, and other types of operations.

Here are some of the most common types of operators in JavaScript:

1. Arithmetic Operators: These operators are used to perform mathematical calculations on values, such as addition, subtraction, multiplication, and division. For example, `+` is the addition operator, `-` is the subtraction operator, `*` is the multiplication operator, and `/` is the division operator.

2. Comparison Operators: These operators are used to compare two values and return a Boolean value (`true` or `false`) indicating whether the comparison is true or false. For example, `==` is the equality operator, `!=` is the inequality operator, `<` is the less-than operator, and `>` is the greater-than operator.

3. Assignment Operators: These operators are used to assign values to variables. For example, `=` is the assignment operator, which assigns the value on the right-hand side of the operator to the variable on the left-hand side.

4. Logical Operators: These operators are used to perform logical operations on Boolean values. For example, `&&` is the logical AND operator, which returns `true` if both of its operands are `true`, and `||` is the logical OR operator, which returns `true` if at least one of its operands is `true`.

5. Bitwise Operators: These operators are used to perform bitwise operations on values, which involve manipulating the individual bits of a value. For example, `&` is the bitwise AND operator, `|` is the bitwise OR operator, and `^` is the bitwise XOR operator.

6. String Operators: These operators are used to concatenate or compare strings. For example, `+` is the concatenation operator, which combines two or more strings into a single string, and `==` and `!=` are comparison operators that can be used to compare strings.


Here are a few examples:

```javascript
// Arithmetic operators
let x = 10;
let y = 5;
console.log(x + y); // Output: 15
console.log(x - y); // Output: 5
console.log(x * y); // Output: 50
console.log(x / y); // Output: 2

// Comparison operators
let a = 10;
let b = 5;
console.log(a > b); // Output: true
console.log(a < b); // Output: false
console.log(a == b); // Output: false
console.log(a != b); // Output: true

// Logical operators
let p = true;
let q = false;
console.log(p && q); // Output: false
console.log(p || q); // Output: true
console.log(!p); // Output: false

// Assignment operators
let c = 10;
c += 5; // Equivalent to c = c + 5
console.log(c); // Output: 15
``` 

## Control flow

Control flow in JavaScript refers to the way that a program executes different statements or blocks of code depending on certain conditions. JavaScript provides several control flow statements, including conditionals and loops, which can be used to create more complex programs.

Control flow statements are essential for creating more complex programs in JavaScript. By combining conditionals and loops, you can create programs that can respond to user input, manipulate data, and interact with other web technologies.

### Conditionals:
In JavaScript, conditional statements are used to execute different pieces of code based on a particular condition. There are several types of conditional statements in JavaScript, including the `if` statement, the `if...else` statement, the `switch` statement, and the ternary operator.

1. The `if` statement:
The `if` statement is used to execute a block of code if a particular condition is true. Here's the basic syntax:

```javascript
if (condition) {
  // Code to execute if the condition is true
}
```

Here's an example:

```javascript
let age = 18;
if (age >= 18) {
  console.log("You are old enough to vote!");
}
```

In this example, the code inside the `if` block will be executed because the condition (`age >= 18`) is true.

2. The `if...else` statement:
The `if...else` statement is used to execute one block of code if a condition is true, and another block of code if the condition is false. Here's the basic syntax:

```javascript
if (condition) {
  // Code to execute if the condition is true
} else {
  // Code to execute if the condition is false
}
```

Here's an example:

```javascript
let age = 16;
if (age >= 18) {
  console.log("You are old enough to vote!");
} else {
  console.log("You are not old enough to vote yet.");
}
```

In this example, the code inside the `else` block will be executed because the condition (`age >= 18`) is false.

3. The `switch` statement:
The `switch` statement is used to execute different blocks of code based on different possible values of a variable. Here's the basic syntax:

```javascript
switch (expression) {
  case value1:
    // Code to execute if expression === value1
    break;
  case value2:
    // Code to execute if expression === value2
    break;
  default:
    // Code to execute if none of the cases match
    break;
}
```

Here's an example:

```javascript
let dayOfWeek = "Monday";
switch (dayOfWeek) {
  case "Monday":
  case "Tuesday":
  case "Wednesday":
  case "Thursday":
  case "Friday":
    console.log("It's a weekday.");
    break;
  case "Saturday":
  case "Sunday":
    console.log("It's the weekend!");
    break;
  default:
    console.log("Not a valid day of the week.");
    break;
}
```

In this example, the code inside the first `case` block will be executed because `dayOfWeek` is equal to `"Monday"`.

4. The ternary operator:
The ternary operator is a shorthand way to write an `if...else` statement in a single line of code. Here's the basic syntax:

```javascript
condition ? valueIfTrue : valueIfFalse;
```

Here's an example:

```javascript
let age = 16;
let message = age >= 18 ? "You are old enough to vote!" : "You are not old enough to vote yet.";
console.log(message);
```

In this example, the value of the `message` variable will be `"You are not old enough to vote yet."` because the condition (`age >= 18`) is false.

Conditional statements are an essential part of any programming language, and understanding them is crucial for creating complex programs in JavaScript.


## Loops:
In JavaScript, loops are used to repeat a block of code multiple times. There are several types of loops in JavaScript, including the `for` loop, the `while` loop, and the `do...while` loop.

1. The `for` loop:
The `for` loop is used to repeat a block of code a specific number of times. Here's the basic syntax:

```javascript
for (initialization; condition; increment/decrement) {
  // Code to repeat
}
```

Here's an example:

```javascript
for (let i = 1; i <= 10; i++) {
  console.log(i);
}
```

In this example, the loop will repeat 10 times, and the value of `i` will be printed to the console on each iteration.

2. The `while` loop:
The `while` loop is used to repeat a block of code while a particular condition is true. Here's the basic syntax:

```javascript
while (condition) {
  // Code to repeat
}
```

Here's an example:

```javascript
let i = 1;
while (i <= 10) {
  console.log(i);
  i++;
}
```

In this example, the loop will repeat 10 times, and the value of `i` will be printed to the console on each iteration.

3. The `do...while` loop:
The `do...while` loop is similar to the `while` loop, except that the code inside the loop will always execute at least once, even if the condition is initially false. Here's the basic syntax:

```javascript
do {
  // Code to repeat
} while (condition);
```

Here's an example:

```javascript
let i = 1;
do {
  console.log(i);
  i++;
} while (i <= 10);
```

In this example, the loop will repeat 10 times, and the value of `i` will be printed to the console on each iteration.

Loops are an essential part of any programming language, and understanding how they work is crucial for creating complex programs in JavaScript. It's also important to be aware of the potential pitfalls of loops, such as infinite loops, which can cause a program to crash or become unresponsive.

## Debugging

Debugging is a crucial skill for developers, and there are several techniques that can help in the process of debugging functions in JavaScript. Here are some common techniques:

1. Console.log(): This is the most basic and widely used technique for debugging in JavaScript. It allows you to print out the value of a variable or the result of an expression at a specific point in the code to check if it's what you expect. You can also use console.group() and console.groupEnd() to group console.log() outputs and make them more organized.

2. Breakpoints: This technique allows you to stop the execution of the code at a specific point and inspect the state of the code. You can set breakpoints in the browser developer tools or in an IDE like Visual Studio Code. Once the breakpoint is hit, you can inspect the value of variables, step through the code, and more.

3. Debugging tools: There are many tools available for debugging JavaScript code. These tools allow you to set breakpoints, inspect variables, and step through the code. Some of the most popular tools include Chrome DevTools, Firefox Developer Tools, and Visual Studio Code.

4. Stack trace: When an error occurs in your code, you can use the stack trace to see the sequence of function calls that led up to the error. This can help you identify the source of the problem and fix it.

5. Unit tests: Writing unit tests can help you catch errors and bugs in your code early on. By testing individual functions or code modules in isolation, you can ensure that they are working as expected and catch any errors before they propagate to other parts of the code.

Overall, the key to effective debugging is to be systematic and methodical. Take a structured approach to debugging, use the right tools, and be persistent in your efforts to find and fix the problem.

