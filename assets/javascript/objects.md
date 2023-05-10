
# Javascript standard built-in objects

JavaScript has several standard built-in objects that provide useful functionality for working with data and manipulating the environment. Here are some of the most commonly used standard built-in objects in JavaScript:

1. `Array`: Represents an ordered list of values that can be of any data type.
2. `Object`: Represents a collection of properties, where each property has a name and a value.
3. `String`: Represents a sequence of characters, which can be manipulated in various ways.
4. `Number`: Represents a numeric value, which can be used for mathematical calculations.
5. `Boolean`: Represents a logical value that can be either `true` or `false`.
6. `Date`: Represents a specific moment in time, and can be used for time-based calculations.
7. `Math`: Provides a set of mathematical functions, such as `Math.sin()`, `Math.cos()`, and `Math.sqrt()`.
8. `RegExp`: Represents a regular expression, which is used to match patterns in strings.

Each of these standard built-in objects has its own set of properties and methods that can be used to perform various operations. Additionally, developers can create their own custom objects using the built-in `Object` constructor or by defining classes using the `class` keyword in modern versions of JavaScript.

## Array

In JavaScript, an array is a special type of object that stores a collection of values, which can be of any data type. Arrays are often used to store lists of data that need to be manipulated or iterated over in a specific order.

Here are some key features of arrays in JavaScript:

1. Declaration: Arrays can be declared using either array literals or the `Array` constructor. For example:

```javascript
let myArray = [1, 2, 3];
let myArray2 = new Array(1, 2, 3);
```

2. Accessing elements: You can access individual elements of an array using square brackets notation and the zero-based index of the element. For example:

```javascript
let myArray = ['apple', 'banana', 'orange'];
console.log(myArray[0]); // Output: 'apple'
```

3. Modifying elements: You can modify individual elements of an array using square brackets notation and the zero-based index of the element. For example:

```javascript
let myArray = ['apple', 'banana', 'orange'];
myArray[0] = 'pear';
console.log(myArray); // Output: ['pear', 'banana', 'orange']
```

4. Array length: You can determine the length of an array using the `length` property. For example:

```javascript
let myArray = [1, 2, 3];
console.log(myArray.length); // Output: 3
```

5. Adding and removing elements: You can add or remove elements from an array using various methods such as `push()`, `pop()`, `shift()`, `unshift()`, `splice()`, etc. For example:

```javascript
let myArray = ['apple', 'banana', 'orange'];
myArray.push('pear');
console.log(myArray); // Output: ['apple', 'banana', 'orange', 'pear']

myArray.pop();
console.log(myArray); // Output: ['apple', 'banana', 'orange']
```

6. Iteration: You can iterate over the elements of an array using various methods such as `for` loop, `forEach()`, `map()`, `filter()`, `reduce()`, etc. For example:

```javascript
let myArray = [1, 2, 3];
for (let i = 0; i < myArray.length; i++) {
  console.log(myArray[i]);
}

myArray.forEach(function(element) {
  console.log(element);
});
```

Arrays are a fundamental data structure in JavaScript, and are used extensively in web development for tasks such as storing and manipulating user input, data from APIs, and more.

## Object

The Object is a standard built-in object in JavaScript that serves as a basic building block for creating more complex data structures. It is the base constructor for all objects in JavaScript and provides methods and properties for working with objects.

One of the key features of the Object in JavaScript is its ability to store properties and methods as key-value pairs. This makes it a flexible and powerful tool for creating complex data structures, as well as for implementing object-oriented programming concepts.

Some of the most commonly used methods of the Object include:

- Object.create() - Creates a new object with the specified prototype object and properties.
- Object.keys() - Returns an array of a given object's own enumerable properties, in the same order as that provided by a for...in loop.
- Object.values() - Returns an array of a given object's own enumerable property values, in the same order as that provided by a for...in loop.
- Object.entries() - Returns an array of a given object's own enumerable property pairs [key, value], in the same order as that provided by a for...in loop.

Here is an example of creating an object using the Object constructor:

```javascript
const person = new Object();
person.name = 'John';
person.age = 30;
person.sayHello = function() {
  console.log('Hello, my name is ' + this.name);
};
```

In this example, we create a new object called `person` using the Object constructor. We then add some properties to the object (`name` and `age`) and a method called `sayHello` that logs a message to the console.

Overall, the Object in JavaScript is a fundamental and versatile building block for creating complex data structures and implementing object-oriented programming concepts.


## String

The String is a standard built-in object in JavaScript that represents a sequence of characters. It provides a wide range of methods for working with strings, such as finding substrings, replacing text, and converting case.

Here are some of the most commonly used methods of the String object:

- `charAt()` - Returns the character at the specified index.
- `concat()` - Concatenates two or more strings and returns a new string.
- `indexOf()` - Returns the index of the first occurrence of a specified substring.
- `replace()` - Replaces a specified substring with another string.
- `split()` - Splits a string into an array of substrings based on a specified delimiter.
- `substr()` - Returns a specified number of characters from a string, starting at a specified index.
- `toLowerCase()` - Converts a string to lowercase.
- `toUpperCase()` - Converts a string to uppercase.
- `trim()` - Removes whitespace from both ends of a string.

Here is an example of using some of these methods:

```javascript
const str = 'Hello, World!';

console.log(str.charAt(0)); // 'H'
console.log(str.concat(' How are you?')); // 'Hello, World! How are you?'
console.log(str.indexOf('o')); // 4
console.log(str.replace('World', 'John')); // 'Hello, John!'
console.log(str.split(', ')); // ['Hello', 'World!']
console.log(str.substr(7, 5)); // 'World'
console.log(str.toLowerCase()); // 'hello, world!'
console.log(str.toUpperCase()); // 'HELLO, WORLD!'
console.log('   hello   '.trim()); // 'hello'
```

Overall, the String object in JavaScript is a powerful tool for working with text-based data, providing a wide range of methods for manipulating and transforming strings.

## Number

The `Number` object is a built-in object in JavaScript that represents numeric values. It provides a range of methods and properties for working with numbers.

Some of the commonly used methods and properties of the `Number` object include:

1. `Number.MAX_VALUE`: This property returns the maximum representable numeric value in JavaScript (1.7976931348623157e+308).
2. `Number.MIN_VALUE`: This property returns the smallest representable positive numeric value in JavaScript (5e-324).
3. `Number.isNaN()`: This method determines whether a value is NaN (not a number).
4. `Number.parseInt()`: This method parses a string argument and returns an integer of the specified radix (the base in mathematical numeral systems).
5. `Number.toFixed()`: This method formats a number using fixed-point notation (the number of digits to appear after the decimal point is specified).
6. `Number.toString()`: This method returns a string representation of a number in the specified radix.

Here are some examples of using `Number` object methods:

```javascript
console.log(Number.MAX_VALUE); // Output: 1.7976931348623157e+308
console.log(Number.isNaN("hello")); // Output: true
console.log(Number.parseInt("1010", 2)); // Output: 10
console.log((123.456).toFixed(2)); // Output: "123.46"
console.log((16).toString(2)); // Output: "10000"
```

In addition to these methods and properties, the `Number` object also provides several other useful methods for working with numbers in JavaScript.

## Boolean

The Boolean object in JavaScript is a standard built-in object that represents a boolean value, which can be either true or false. It is one of the primitive types in JavaScript, along with numbers, strings, null, and undefined.

The Boolean object can be created using the Boolean() constructor or by using a boolean literal (true or false).

Example of creating a Boolean object:

```javascript
const boolObj = new Boolean(true);
```

Example of using a boolean literal:

```javascript
const bool = true;
```

The Boolean object has a few properties and methods, such as:

- `constructor`: Returns the function that created the Boolean object's prototype.
- `prototype`: Allows you to add properties and methods to a Boolean object.
- `toString()`: Converts the boolean value to a string and returns it.
- `valueOf()`: Returns the primitive value of the Boolean object.

Example usage:

```javascript
const boolObj = new Boolean(true);
console.log(boolObj.toString()); // "true"
console.log(boolObj.valueOf()); // true
```

It's important to note that while the Boolean object is a wrapper around a boolean value, it's generally recommended to use the boolean literals directly instead of creating Boolean objects, as it can lead to unexpected behavior when doing comparisons or type coercion.

## Date

The `Date` object is a standard built-in object in JavaScript that represents a date and time. It is used for working with dates and times in JavaScript, and provides methods for creating, manipulating, and formatting dates.

To create a `Date` object, you can use the `new Date()` constructor, which takes several arguments to set the date and time. If no arguments are provided, the current date and time will be used.

Here's an example of creating a `Date` object:

```javascript
const now = new Date(); // current date and time
```

The `Date` object has many properties and methods for working with dates and times, such as:

- `getFullYear()`: Returns the year of the date.
- `getMonth()`: Returns the month of the date (0-11).
- `getDate()`: Returns the day of the month (1-31).
- `getHours()`: Returns the hour of the date (0-23).
- `getMinutes()`: Returns the minutes of the date (0-59).
- `getSeconds()`: Returns the seconds of the date (0-59).
- `getTime()`: Returns the number of milliseconds since January 1, 1970.
- `setFullYear()`: Sets the year of the date.
- `setMonth()`: Sets the month of the date (0-11).
- `setDate()`: Sets the day of the month (1-31).
- `setHours()`: Sets the hour of the date (0-23).
- `setMinutes()`: Sets the minutes of the date (0-59).
- `setSeconds()`: Sets the seconds of the date (0-59).

Here's an example of using some of these methods:

```javascript
const now = new Date();
const year = now.getFullYear();
const month = now.getMonth();
const day = now.getDate();

console.log(year); // current year
console.log(month); // current month (0-11)
console.log(day); // current day of the month
```

The `Date` object also provides methods for formatting dates and times, such as `toLocaleString()`, `toDateString()`, and `toTimeString()`. These methods return a string representation of the date and time in the specified format.

Here's an example of using `toLocaleString()`:

```javascript
const now = new Date();
const dateString = now.toLocaleString('en-US', {
  weekday: 'long',
  year: 'numeric',
  month: 'long',
  day: 'numeric',
  hour: 'numeric',
  minute: 'numeric',
  second: 'numeric',
});

console.log(dateString); // e.g. "Friday, May 7, 2023, 2:34:56 PM"
```

Overall, the `Date` object provides a powerful and flexible way to work with dates and times in JavaScript.

To format a date in JavaScript for the Spanish standard, you can use the `toLocaleDateString()` method with the `options` parameter. Here's an example:

```javascript
const date = new Date();
const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric', hour: 'numeric', minute: 'numeric', second: 'numeric', timeZone: 'Europe/Madrid' };
const formattedDate = date.toLocaleDateString('es-ES', options);

console.log(formattedDate);
```

In this example, we create a new `Date` object, then define an `options` object with the desired formatting options. The `toLocaleDateString()` method is then called with the `es-ES` locale and the `options` parameter to format the date according to the Spanish standard. The resulting formatted date is stored in the `formattedDate` variable and printed to the console.

Note that the `timeZone` option is included to ensure that the date is formatted in the correct time zone.

## Math

The `Math` object in JavaScript is a standard built-in object that provides mathematical constants and functions. Some of the commonly used methods provided by the `Math` object are:

- `Math.abs(x)`: Returns the absolute value of a number.
- `Math.ceil(x)`: Returns the smallest integer greater than or equal to a number.
- `Math.floor(x)`: Returns the largest integer less than or equal to a number.
- `Math.max([x[, y[, ...]]])`: Returns the largest of zero or more numbers.
- `Math.min([x[, y[, ...]]])`: Returns the smallest of zero or more numbers.
- `Math.pow(x, y)`: Returns the value of a number raised to the power of another number.
- `Math.round(x)`: Returns the value of a number rounded to the nearest integer.
- `Math.sqrt(x)`: Returns the square root of a number.

Here are some examples of using the `Math` object:

```javascript
// Absolute value
Math.abs(-10); // returns 10

// Ceiling
Math.ceil(4.2); // returns 5

// Floor
Math.floor(4.8); // returns 4

// Maximum
Math.max(1, 5, 3); // returns 5

// Minimum
Math.min(1, 5, 3); // returns 1

// Power
Math.pow(2, 3); // returns 8

// Round
Math.round(4.4); // returns 4

// Square root
Math.sqrt(16); // returns 4
```

The `Math` object also provides constants such as `Math.PI` and `Math.E` for the mathematical constants pi and e, respectively.

## RegExp


In JavaScript, regular expressions are defined using the `RegExp` object or by using forward slashes (`/`) to delimit the regular expression pattern.

Here's an example of using the `RegExp` constructor to create a regular expression pattern that matches any string containing the word "apple":

```javascript
const pattern = new RegExp('apple');
```

Alternatively, you can use the forward slash notation to define the same regular expression pattern:

```javascript
const pattern = /apple/;
```

Regular expressions are a powerful and flexible tool for searching and manipulating text. They allow you to search for patterns in a string and replace those patterns with other text. Regular expressions are commonly used in text processing, search engines, and data validation.

Here's an example of how to use the `RegExp` object to search for a pattern in a string:

```javascript
const pattern = /hello/i;
const str = 'Hello World';
const result = pattern.test(str); // true
```

In this example, we create a regular expression pattern `/hello/i`, which matches the string "hello" in a case-insensitive manner. We then use the `test()` method of the `RegExp` object to test whether the pattern matches the string "Hello World".

Regular expressions can also be used to extract substrings from a string:

```javascript
const str = 'The quick brown fox';
const pattern = /quick\s(.*)\sfox/;
const result = str.match(pattern); // ["quick brown fox", "brown"]
```

In this example, we create a regular expression pattern `/quick\s(.*)\sfox/`, which matches the word "quick" followed by any number of characters followed by the word "fox". We use the `match()` method of the string object to find the first substring that matches the pattern. The method returns an array that contains the matched substring and any captured groups.

Regular expressions in JavaScript support a wide variety of patterns and options, including character classes, quantifiers, alternation, and lookaround. The `RegExp` object also provides methods for replacing text, splitting strings, and more.

Regular expression patterns can include a variety of special characters and syntax to match specific patterns in text. Here are some common examples:

- `.` : Matches any single character except for a newline character.
- `*` : Matches the preceding expression zero or more times.
- `+` : Matches the preceding expression one or more times.
- `?` : Makes the preceding expression optional (matches zero or one times).
- `^` : Matches the beginning of the string.
- `$` : Matches the end of the string.
- `[]` : Defines a character set, matching any one of the characters within the brackets.
- `()` : Defines a group of characters, which can be treated as a single unit and modified with quantifiers such as `*`, `+`, or `?`.

For example, the following regular expression pattern matches any string that starts with a capital letter and is followed by one or more lowercase letters:

```javascript
const pattern = /^[A-Z][a-z]+$/;
```

This pattern uses the `^` character to match the beginning of the string, followed by a character range `[A-Z]` to match a single capital letter, and `[a-z]+` to match one or more lowercase letters. The `$` character is not used in this example, but could be added to the end of the pattern to ensure that the string ends with the matched pattern.

