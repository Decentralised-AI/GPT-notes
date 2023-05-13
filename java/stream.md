# Java Stream API for processing collections and performing functional-style 

## Overview

Streams in Java are a sequence of elements that can be processed in a declarative and functional style. They provide a powerful and expressive way to perform operations on data collections. Streams are part of the Java Stream API introduced in Java 8 and are designed to work seamlessly with lambda expressions and functional interfaces.

Here are key characteristics of streams:

1. Sequence of Elements: Streams represent a sequence of elements, which can be objects of any type, such as integers, strings, or custom objects.

2. Source: Streams are created from a data source, which can be a collection, an array, an I/O channel, or any other source that can provide an ordered sequence of elements.

3. Functional-Style Operations: Streams provide a set of operations that can be performed on the elements. These operations are inspired by functional programming concepts and include filtering, mapping, reducing, sorting, and more. The operations are applied to the elements in a fluent and declarative manner.

4. Lazy Evaluation: Streams use lazy evaluation, which means that the operations are executed only when necessary. Intermediate operations, such as filtering or mapping, do not trigger the computation immediately. Instead, they build a pipeline of operations that is executed on-demand when a terminal operation is invoked.

5. Pipelining: Streams support pipelining, where multiple operations can be chained together to form a processing pipeline. Each operation in the pipeline transforms the elements in some way, allowing for concise and readable code.

6. Parallel Execution: Streams can be processed sequentially or in parallel. Parallel streams divide the elements into multiple chunks and process them concurrently on multiple threads, taking advantage of multi-core processors and potentially improving performance for large datasets.

By using streams, you can express complex data processing tasks in a more concise and readable manner. Streams promote a functional programming style and help you focus on the logic of data manipulation rather than the details of iteration and looping. They offer benefits such as code readability, expressiveness, laziness, and potential parallelism, making them a powerful tool in Java for working with collections and performing data transformations.


## Benefits of Using Streams

   - Concise and Readable Code: Streams allow you to write code in a more declarative and functional style, making it easier to understand and maintain. This leads to more concise and readable code compared to traditional iterative approaches.

   - Enhanced Productivity: Streams provide a higher level of abstraction, handling the complexity of iteration and providing built-in operations for common data processing tasks. This allows you to focus on the business logic rather than low-level details, resulting in increased productivity.

   - Seamless Parallel Execution: Streams have built-in support for parallel processing, allowing you to take advantage of multi-core processors and achieve better performance. You can parallelize the execution of operations simply by invoking the `parallel()` method on a stream.

   - Lazy Evaluation: Streams use lazy evaluation, which means that operations are only executed when necessary. This improves efficiency by avoiding unnecessary computations. For example, if you have a large collection and apply a filtering operation, only the elements that satisfy the filter condition will be processed.

   - Pipelining: Streams support a pipeline of operations, where multiple operations can be chained together. Each operation in the pipeline transforms the data in some way, enabling a fluent and expressive style of programming. This helps in writing more compact and readable code.

   - Integration with Existing APIs: Streams are designed to seamlessly integrate with existing Java APIs. They can be used with collections, arrays, I/O operations, and other data sources, allowing you to leverage the power of streams in various scenarios.

   - Built-in Operations: Streams provide a rich set of built-in operations such as filtering, mapping, sorting, aggregating, and more. These operations can be combined to express complex data processing requirements easily.

   - Potential for Optimization: The internal implementation of streams optimizes the execution of operations, such as using short-circuiting techniques for certain operations like `findFirst()` and `anyMatch()`. This can lead to improved performance in specific scenarios.

By using streams in Java, you can write code that is more expressive, readable, and efficient. Streams provide a higher level of abstraction, allowing you to focus on the logic of data processing rather than the mechanics of iteration. They also offer seamless parallelism, lazy evaluation, and a wide range of built-in operations, making them a powerful tool for working with collections and performing functional-style operations on data.

## Creating streams from collections or arrays

Creating a Stream from a collection or array is one of the common ways to start working with streams in Java. The Stream API provides convenient methods to convert collections or arrays into streams. Let's see how you can create a stream from a collection or array:

1. Creating a Stream from a Collection:
   To create a stream from a collection, you can use the `stream()` method provided by the `Collection` interface. Here's an example:

   ```java
   List<String> names = List.of("Alice", "Bob", "Charlie", "Dave");
   Stream<String> stream = names.stream();
   ```

   In this example, we have a `List` called `names`, and we call the `stream()` method on it to obtain a `Stream` of `String` elements.

2. Creating a Stream from an Array:
   To create a stream from an array, you can use the static `Stream.of()` method or the `Arrays.stream()` method. Here are examples of both approaches:

   ```java
   String[] names = {"Alice", "Bob", "Charlie", "Dave"};
   Stream<String> stream1 = Stream.of(names);
   
   // or
   
   Stream<String> stream2 = Arrays.stream(names);
   ```

   In the first example, we use the `Stream.of()` method, passing the array as an argument. In the second example, we use the `Arrays.stream()` method specifically designed for creating a stream from an array.

Once you have created a stream from a collection or array, you can perform various operations on the stream, such as filtering, mapping, sorting, and reducing, to process and transform the elements as per your requirements.

It's important to note that creating a stream from a collection or array doesn't modify the original collection or array. Instead, it provides a new stream that allows you to perform operations on the elements.

Creating a stream from a collection or array is the starting point for leveraging the power of streams in Java. It enables you to apply functional-style operations on the elements and perform complex data processing tasks in a more concise and readable way.

## Intermediate and terminal operations

In a Java Stream pipeline, the operations are divided into two types: intermediate operations and terminal operations. The order in which these operations are applied is crucial and can affect the result. Here's the order of operations in a stream pipeline:

1. **Source**: The stream is created from a data source, such as a collection or an array.

2. **Intermediate Operations**: Intermediate operations transform the stream elements and can be chained together. They are executed lazily, meaning they are not evaluated until a terminal operation is invoked. Some common intermediate operations include `filter`, `map`, `flatMap`, `sorted`, `distinct`, `limit`, `skip`, and `peek`. These operations allow you to modify, filter, or transform the elements of the stream.

   - Intermediate operations can be applied in any order as long as the desired outcome is achieved.
   - Intermediate operations are not executed immediately. They are stacked up and executed only when a terminal operation is called.

3. **Terminal Operation**: A terminal operation produces a result or a side effect. It triggers the processing of the stream and produces a final result or performs an action. Examples of terminal operations are `forEach`, `collect`, `reduce`, `count`, `min`, `max`, and `anyMatch`.

   - A stream can have only one terminal operation.
   - Terminal operations are eager, meaning they trigger the processing of the stream and produce a result or a side effect.

It's important to note that the order and combination of intermediate operations can greatly affect the efficiency and correctness of your stream processing. Additionally, the output of the stream pipeline may vary depending on the order in which the operations are applied.

Remember to consider the characteristics and requirements of your data and the desired outcome when chaining intermediate operations in a stream pipeline.

### Intermediate Operations
   Intermediate operations are operations that transform a stream into another stream. These operations are usually chained together to form a processing pipeline. Intermediate operations are lazy, meaning they are not executed immediately when called. Instead, they are executed when a terminal operation is invoked on the stream.

   Some common intermediate operations include:
   - `filter(Predicate)`: Filters the stream based on a condition specified by the predicate.
   - `map(Function)`: Transforms each element in the stream by applying a function to it.
   - `sorted()`: Sorts the elements of the stream in their natural order or using a custom comparator.
   - `distinct()`: Removes duplicate elements from the stream.
   - `limit(long)`: Limits the size of the stream to a specified number of elements.
   - `skip(long)`: Skips a specified number of elements from the stream.

   Here's an example that demonstrates the use of intermediate operations:

   ```java
   List<Integer> numbers = List.of(1, 2, 3, 4, 5);

   List<Integer> doubledNumbers = numbers.stream()
       .filter(n -> n % 2 == 0)
       .map(n -> n * 2)
       .collect(Collectors.toList());
   ```

   In this example, the stream of numbers is filtered to include only even numbers, then each number is doubled using the `map` operation. The resulting stream is collected into a new list.

#### map()

In Java, the `map` operation is an intermediate operation provided by the Stream API. It allows you to transform each element of a stream into another form by applying a function to it. The `map` operation takes a `Function` as its argument, which is a functional interface representing the transformation function.

Here's the syntax of the `map` operation:

```java
<R> Stream<R> map(Function<? super T, ? extends R> mapper)
```

- `T` represents the type of elements in the input stream.
- `R` represents the type of elements in the resulting stream.
- `mapper` is the transformation function that takes an element of type `T` as input and returns an element of type `R`.

The `map` operation applies the mapper function to each element of the stream and returns a new stream consisting of the transformed elements.

Here's an example that demonstrates the usage of the `map` operation:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class MapExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie");

        // Map names to their lengths
        List<Integer> nameLengths = names.stream()
                .map(name -> name.length())
                .collect(Collectors.toList());

        System.out.println(nameLengths); // Output: [5, 3, 7]
    }
}
```

In this example, we have a list of names. We use the `stream()` method to obtain a stream of elements from the list. Then, we chain the `map` operation, specifying a function that transforms each name into its length using the `length()` method. The `map` operation applies the function to each name and returns a new stream of name lengths.

Finally, we collect the name lengths into a new list using the `collect` terminal operation with the `Collectors.toList()` collector. The resulting list contains the lengths of the names.

The output of the program will be `[5, 3, 7]`, as it maps each name to its length using the `map` operation and collects the transformed values into a new list.



#### filter()

In Java, the `filter` operation is an intermediate operation provided by the Stream API. It allows you to select elements from a stream based on a given condition. The `filter` operation takes a predicate as its argument, which is a functional interface representing a condition that each element of the stream should satisfy.

Here's the syntax of the `filter` operation:

```java
Stream<T> filter(Predicate<? super T> predicate)
```

- `T` represents the type of elements in the stream.
- `predicate` is the condition that elements must satisfy. It takes an element of type `T` as input and returns a boolean value indicating whether the element should be included in the filtered stream.

The `filter` operation applies the predicate to each element of the stream. If the predicate returns `true` for an element, it is included in the resulting stream. If the predicate returns `false`, the element is filtered out.

Here's an example that demonstrates the usage of the `filter` operation:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class FilterExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Filter even numbers
        List<Integer> evenNumbers = numbers.stream()
                .filter(number -> number % 2 == 0)
                .collect(Collectors.toList());

        System.out.println(evenNumbers); // Output: [2, 4, 6, 8, 10]
    }
}
```

In this example, we have a list of numbers. We use the `stream()` method to obtain a stream of elements from the list. Then, we chain the `filter` operation, specifying a predicate that checks if each number is even (`number % 2 == 0`). The `filter` operation retains only the even numbers in the resulting stream.

Finally, we collect the filtered numbers into a new list using the `collect` terminal operation with the `Collectors.toList()` collector. The resulting list contains only the even numbers.

The output of the program will be `[2, 4, 6, 8, 10]`, as it filters out all the odd numbers from the original list based on the condition provided in the `filter` operation.

Here's an example of using the `filter` intermediate operation with Java streams:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class FilterExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "Dave", "Eve");

        // Filter names starting with "A"
        List<String> filteredNames = names.stream()
                .filter(name -> name.startsWith("A"))
                .collect(Collectors.toList());

        System.out.println(filteredNames); // Output: [Alice]
    }
}
```

In this example, we have a list of names. We use the `stream()` method to obtain a stream of elements from the list. Then, we chain the `filter` intermediate operation, specifying a predicate that checks if each name starts with the letter "A". The `filter` operation retains only the elements that satisfy the predicate.

Finally, we collect the filtered names into a new list using the `collect` terminal operation with the `Collectors.toList()` collector. The resulting list contains only the names that start with "A".

The output of the program will be `[Alice]`, as it filters out all the names except "Alice" based on the condition provided in the `filter` operation.

#### reduce()

In Java, the `reduce` operation is a terminal operation provided by the Stream API. It allows you to combine the elements of a stream into a single result by applying a binary operation repeatedly. The `reduce` operation takes two forms: one that accepts an identity value and another that does not.

Here are the two variations of the `reduce` operation:

1. `reduce(BinaryOperator<T> accumulator)`: This variation of the `reduce` operation does not require an initial value. It takes a `BinaryOperator` as an argument, which specifies the binary operation to be applied to the elements of the stream. The operation is applied successively to the elements from left to right, producing a single result.

2. `reduce(T identity, BinaryOperator<T> accumulator)`: This variation of the `reduce` operation accepts an initial value (identity). It takes an initial value and a `BinaryOperator` as arguments. The identity value is used as the initial accumulated value, and the binary operation is applied to combine the elements of the stream with the accumulated value.

Here's an example that demonstrates the usage of the `reduce` operation:

```java
import java.util.Arrays;
import java.util.List;
import java.util.Optional;

public class ReduceExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

        // Example 1: Reduce without identity
        Optional<Integer> sum1 = numbers.stream()
                .reduce((a, b) -> a + b);

        sum1.ifPresent(System.out::println); // Output: 15

        // Example 2: Reduce with identity
        Integer sum2 = numbers.stream()
                .reduce(0, (a, b) -> a + b);

        System.out.println(sum2); // Output: 15
    }
}
```

In this example, we have a list of numbers. We use the `stream()` method to obtain a stream of elements from the list. Then, we use the `reduce` operation to calculate the sum of the numbers.

In the first example, we don't provide an initial value (identity) to the `reduce` operation. The binary operation `(a, b) -> a + b` is used to add the numbers together. The result is wrapped in an `Optional` because the stream may be empty. We use the `ifPresent` method to print the sum if it exists.

In the second example, we provide an initial value of `0` to the `reduce` operation. The binary operation `(a, b) -> a + b` is used to add the numbers to the initial value. The result is an `Integer` representing the sum of the numbers.

Both examples produce the same output: `15`, which is the sum of the numbers in the list.

#### flatMap()

In Java, the `flatMap` operation is an intermediate operation provided by the Stream API. It allows you to transform each element of a stream into multiple elements and then flatten the resulting elements into a single stream. The `flatMap` operation takes a function as its argument, which returns a stream for each input element.

Here's the syntax of the `flatMap` operation:

```java
<R> Stream<R> flatMap(Function<? super T, ? extends Stream<? extends R>> mapper)
```

- `T` represents the type of elements in the input stream.
- `R` represents the type of elements in the resulting stream.
- `mapper` is the function that takes an element of type `T` as input and returns a stream of elements of type `R`.

The `flatMap` operation applies the mapper function to each element of the stream and flattens the resulting streams into a single stream.

Here's an example that demonstrates the usage of the `flatMap` operation:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class FlatMapExample {
    public static void main(String[] args) {
        List<List<Integer>> numbers = Arrays.asList(
                Arrays.asList(1, 2, 3),
                Arrays.asList(4, 5, 6),
                Arrays.asList(7, 8, 9)
        );

        // Flatten the nested lists into a single stream
        List<Integer> flattenedNumbers = numbers.stream()
                .flatMap(list -> list.stream())
                .collect(Collectors.toList());

        System.out.println(flattenedNumbers); // Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
    }
}
```

In this example, we have a list of nested lists of numbers. We use the `stream()` method to obtain a stream of elements from the outer list. Then, we chain the `flatMap` operation, specifying a function that returns a stream for each inner list using `list.stream()`. The `flatMap` operation applies this function to each inner list and flattens the resulting streams into a single stream.

Finally, we collect the flattened numbers into a new list using the `collect` terminal operation with the `Collectors.toList()` collector. The resulting list contains all the numbers from the nested lists in a flattened form.

The output of the program will be `[1, 2, 3, 4, 5, 6, 7, 8, 9]`, as the `flatMap` operation flattens the nested lists and combines all the numbers into a single stream.

#### sorted()

In Java, the `sorted` operation is an intermediate operation provided by the Stream API. It allows you to sort the elements of a stream in a specified order. The `sorted` operation can be used with both natural ordering (using the `Comparable` interface) or a custom ordering (using a `Comparator`).

Here are the two variations of the `sorted` operation:

1. `sorted()`: This variation uses the natural ordering of the elements. The elements in the stream must implement the `Comparable` interface to determine their natural order. The sorted stream will be in ascending order.

2. `sorted(Comparator<? super T> comparator)`: This variation uses a custom comparator to determine the order of the elements. The provided `Comparator` object specifies the comparison logic for sorting. The sorted stream will be in the order defined by the comparator.

Here's an example that demonstrates the usage of the `sorted` operation:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class SortedExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(5, 2, 7, 1, 9);

        // Sort the numbers in ascending order
        List<Integer> sortedNumbers = numbers.stream()
                .sorted()
                .collect(Collectors.toList());

        System.out.println(sortedNumbers); // Output: [1, 2, 5, 7, 9]
    }
}
```

In this example, we have a list of numbers. We use the `stream()` method to obtain a stream of elements from the list. Then, we chain the `sorted` operation without any arguments, which uses the natural ordering of the elements. The `sorted` operation sorts the numbers in ascending order.

Finally, we collect the sorted numbers into a new list using the `collect` terminal operation with the `Collectors.toList()` collector. The resulting list contains the numbers sorted in ascending order.

The output of the program will be `[1, 2, 5, 7, 9]`, as the `sorted` operation arranges the numbers in ascending order.

#### peek()

In Java, the `peek` operation is an intermediate operation provided by the Stream API. It allows you to perform a non-destructive operation on each element of the stream while still preserving the stream's original elements.

The `peek` operation takes a `Consumer` functional interface as a parameter. This `Consumer` is applied to each element of the stream, allowing you to perform some side effect or intermediate operation on the element. The `peek` operation does not modify the elements or the stream itself.

Here's an example that demonstrates the usage of the `peek` operation:

```java
import java.util.stream.Stream;

public class StreamPeekExample {
    public static void main(String[] args) {
        Stream<Integer> numbers = Stream.of(1, 2, 3, 4, 5);

        Stream<Integer> peekedStream = numbers.peek(System.out::println);

        peekedStream.forEach(System.out::println);
    }
}
```

In this example, we have a stream of integers created using the `of` method from `Stream`. We then apply the `peek` operation, which uses `System.out.println` as the `Consumer` to print each element of the stream. The `peek` operation does not modify the elements, it simply outputs them to the console.

The `forEach` terminal operation is used to print each element of the peeked stream, again using `System.out.println`.

The output of the program will be:

```
1
2
3
4
5
1
2
3
4
5
```

As you can see, the `peek` operation allows us to perform an action on each element without modifying the original stream. In this example, the peeked stream prints each element twice, once during the `peek` operation and again during the `forEach` operation.

The `peek` operation is useful when you want to perform intermediate operations for debugging or logging purposes while still maintaining the original stream elements. It is commonly used to gain insights into the data flowing through the stream without modifying it.

### Short-circuiting operations

Short-circuiting operations in Java Stream API are a special type of intermediate operation that can optimize the processing of a stream by avoiding unnecessary computations. These operations have the ability to terminate the stream traversal early, without processing all the elements in the stream. This behavior can provide performance improvements and efficiency in certain scenarios. Here are some common short-circuiting operations and their effects:

1. **findFirst()**: This operation returns an `Optional` containing the first element of the stream, or an empty `Optional` if the stream is empty. It stops the stream traversal as soon as it finds the first element.

2. **findAny()**: Similar to `findFirst()`, this operation returns an `Optional` containing any element of the stream, or an empty `Optional` if the stream is empty. It does not guarantee a specific element and can provide better performance in parallel streams.

3. **anyMatch(predicate)**: This operation tests whether any element in the stream matches the given predicate. It terminates the stream traversal as soon as it finds a matching element and returns `true`. If no matching element is found, it returns `false`.

4. **allMatch(predicate)**: This operation tests whether all elements in the stream match the given predicate. It stops the stream traversal and returns `false` as soon as it encounters a non-matching element. If all elements match the predicate, it returns `true`.

5. **noneMatch(predicate)**: This operation tests whether no element in the stream matches the given predicate. It terminates the stream traversal as soon as it finds a matching element and returns `false`. If no matching element is found, it returns `true`.

6. **limit(maxSize)**: This operation restricts the stream to a maximum number of elements specified by `maxSize`. Once the specified number of elements is reached, it stops processing further elements in the stream.

7. **skip(n)**: This operation skips the first `n` elements in the stream and returns a new stream that starts from the `n+1` element onwards. It allows you to bypass a certain number of elements in the stream.

The use of short-circuiting operations can significantly optimize the execution of stream operations, especially when dealing with large datasets or expensive computations. They allow you to process only the elements needed to fulfill a certain condition or retrieve a result, saving unnecessary computation time and resources.


#### limit()

In Java, the `limit` operation is an intermediate operation provided by the Stream API. It allows you to limit the size of a stream by specifying the maximum number of elements to be processed.

The `limit` operation takes a single parameter, which represents the maximum number of elements to be included in the stream. If the stream has fewer elements than the specified limit, all the elements are included.

Here's an example that demonstrates the usage of the `limit` operation:

```java
import java.util.stream.Stream;

public class StreamLimitExample {
    public static void main(String[] args) {
        Stream<Integer> numbers = Stream.of(1, 2, 3, 4, 5);

        Stream<Integer> limitedStream = numbers.limit(3);

        limitedStream.forEach(System.out::println);
    }
}
```

In this example, we have a stream of integers created using the `of` method from `Stream`. We then apply the `limit` operation with a limit of `3`, which means we want to include only the first three elements of the stream.

The `forEach` terminal operation is used to print each element of the limited stream.

The output of the program will be:

```
1
2
3
```

As you can see, only the first three elements of the stream are processed and printed, while the remaining elements are ignored due to the limit.

The `limit` operation is useful when you want to process a subset of elements from a larger stream, or when you want to avoid processing unnecessary elements when dealing with large data sets.

#### skip()

In Java, the `skip` operation is an intermediate operation provided by the Stream API. It allows you to skip a specified number of elements from the beginning of a stream and continue processing the remaining elements.

The `skip` operation takes a single parameter, which represents the number of elements to be skipped. If the stream has fewer elements than the specified number, an empty stream is returned.

Here's an example that demonstrates the usage of the `skip` operation:

```java
import java.util.stream.Stream;

public class StreamSkipExample {
    public static void main(String[] args) {
        Stream<Integer> numbers = Stream.of(1, 2, 3, 4, 5);

        Stream<Integer> skippedStream = numbers.skip(2);

        skippedStream.forEach(System.out::println);
    }
}
```

In this example, we have a stream of integers created using the `of` method from `Stream`. We then apply the `skip` operation with a value of `2`, which means we want to skip the first two elements of the stream.

The `forEach` terminal operation is used to print each element of the skipped stream.

The output of the program will be:

```
3
4
5
```

As you can see, the first two elements (1 and 2) are skipped, and the remaining elements (3, 4, and 5) are processed and printed.

The `skip` operation is useful when you want to exclude a certain number of elements from the beginning of a stream, allowing you to focus on a specific subset of the data.



#### Example

Here's an example that demonstrates the use of various intermediate operations in the Java Stream API:

```java
import java.util.Arrays;
import java.util.List;

public class StreamIntermediateOperationsExample {
    public static void main(String[] args) {
        List<String> words = Arrays.asList("hello", "world", "java", "stream", "example");

        List<String> mappedWords = words.stream()
                .map(String::toUpperCase)                // map operation to convert each word to uppercase
                .filter(word -> word.length() > 4)       // filter operation to keep words with length greater than 4
                .sorted()                               // sorted operation to sort the words in natural order
                .limit(3)                               // limit operation to keep only the first 3 words
                .collect(Collectors.toList());          // collect the words into a list

        System.out.println("Mapped, filtered, sorted, limited words: " + mappedWords);

        int sumOfLengths = words.stream()
                .flatMapToInt(word -> word.chars())      // flatMap operation to flatten the characters of each word
                .peek(System.out::println)              // peek operation to print each character
                .skip(5)                                // skip operation to skip the first 5 characters
                .reduce(0, (sum, ch) -> sum + 1);        // reduce operation to count the remaining characters

        System.out.println("Sum of lengths: " + sumOfLengths);
    }
}
```

In this example, we have a list of words, and we perform the following operations:

- `map`: Converts each word to uppercase.
- `filter`: Keeps only the words with a length greater than 4.
- `sorted`: Sorts the words in natural order.
- `limit`: Keeps only the first 3 words.
- `flatMapToInt`: Flattens the characters of each word into an `IntStream`.
- `peek`: Prints each character in the stream.
- `skip`: Skips the first 5 characters.
- `reduce`: Counts the remaining characters by accumulating a sum.

The results are stored in the `mappedWords` list and the `sumOfLengths` variable, respectively.

Feel free to modify the example or use your own data to explore the behavior of these intermediate operations.

### Terminal Operations

Terminal operations are operations that produce a final result or a side effect. When a terminal operation is invoked on a stream, the stream is consumed and cannot be reused. Terminal operations trigger the execution of the intermediate operations and produce a result.

   Some common terminal operations include:
   - `forEach(Consumer)`: Performs an action on each element of the stream.
   - `collect(Collector)`: Collects the elements of the stream into a collection or other data structure.
   - `count()`: Returns the count of elements in the stream.
   - `anyMatch(Predicate)`: Returns true if any element matches the given predicate.
   - `allMatch(Predicate)`: Returns true if all elements match the given predicate.
   - `noneMatch(Predicate)`: Returns true if no element matches the given predicate.

   Here's an example that demonstrates the use of terminal operations:

   ```java
   List<String> names = List.of("Alice", "Bob", "Charlie");

   boolean anyMatch = names.stream().anyMatch(name -> name.startsWith("B"));
   long count = names.stream().count();
   List<String> collectedNames = names.stream().collect(Collectors.toList());
   ```

   In this example, the `anyMatch` terminal operation checks if any name starts with "B". The `count` operation counts the number of names in the stream, and the `collect` operation collects the names into a list.

By combining intermediate and terminal operations, you can create powerful data processing pipelines with streams. Intermediate operations allow you to transform and manipulate the data, while terminal operations produce the final result or side effect.

#### Example

Certainly! Here's an example that demonstrates every terminal operation available in the Java Stream API:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamTerminalOperationsExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

        // forEach - prints each element of the stream
        numbers.stream()
                .forEach(System.out::println);

        // count - counts the number of elements in the stream
        long count = numbers.stream()
                .count();
        System.out.println("Count: " + count);

        // collect - collects the elements of the stream into a collection
        List<Integer> squaredNumbers = numbers.stream()
                .map(n -> n * n)
                .collect(Collectors.toList());
        System.out.println("Squared Numbers: " + squaredNumbers);

        // min - finds the minimum element in the stream
        int min = numbers.stream()
                .min(Integer::compareTo)
                .orElseThrow();
        System.out.println("Min: " + min);

        // max - finds the maximum element in the stream
        int max = numbers.stream()
                .max(Integer::compareTo)
                .orElseThrow();
        System.out.println("Max: " + max);

        // findFirst - finds the first element in the stream
        int first = numbers.stream()
                .findFirst()
                .orElseThrow();
        System.out.println("First: " + first);

        // findAny - finds any element in the stream
        int any = numbers.stream()
                .findAny()
                .orElseThrow();
        System.out.println("Any: " + any);

        // allMatch - checks if all elements satisfy a condition
        boolean allMatch = numbers.stream()
                .allMatch(n -> n > 0);
        System.out.println("All Match: " + allMatch);

        // anyMatch - checks if any element satisfies a condition
        boolean anyMatch = numbers.stream()
                .anyMatch(n -> n > 3);
        System.out.println("Any Match: " + anyMatch);

        // noneMatch - checks if no element satisfies a condition
        boolean noneMatch = numbers.stream()
                .noneMatch(n -> n < 0);
        System.out.println("None Match: " + noneMatch);

        // toArray - converts the stream into an array
        Integer[] array = numbers.stream()
                .toArray(Integer[]::new);
        System.out.println("Array: " + Arrays.toString(array));
    }
}
```

This example demonstrates various terminal operations such as `forEach`, `count`, `collect`, `min`, `max`, `findFirst`, `findAny`, `allMatch`, `anyMatch`, `noneMatch`, `toArray`, and prints their respective results.

Please note that the example assumes you have a list of integers named `numbers` for demonstration purposes. Feel free to modify it as needed or use your own data.

## Stream Pipeline

Here's a larger example that demonstrates the use of a streams pipeline in Java:

```java
import java.util.Arrays;
import java.util.List;

public class StreamPipelineExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("apple", "banana", "orange", "kiwi", "mango");

        long count = fruits.stream()                       // Step 1: Create a stream from the list
                .filter(fruit -> fruit.length() > 5)       // Step 2: Filter fruits with length greater than 5
                .map(String::toUpperCase)                  // Step 3: Convert filtered fruits to uppercase
                .sorted()                                  // Step 4: Sort the fruits in natural order
                .peek(System.out::println)                 // Step 5: Print each fruit
                .count();                                  // Step 6: Count the number of fruits

        System.out.println("Total fruits: " + count);       // Output: Total fruits: 3
    }
}
```

In this example, we have a list of fruits. We use a streams pipeline to perform various operations on the stream of fruits:

1. `stream()`: We create a stream from the list of fruits.
2. `filter()`: We filter the fruits based on a condition - in this case, we filter fruits with a length greater than 5.
3. `map()`: We transform each filtered fruit to uppercase using the `toUpperCase` method reference.
4. `sorted()`: We sort the fruits in their natural order (lexicographical order).
5. `peek()`: We print each fruit using the `peek` method, which allows us to perform a side effect operation without affecting the stream.
6. `count()`: We count the number of fruits in the stream.

Finally, we print the total number of fruits using the `count` variable.

The output of the program will be:

```
APPLE
BANANA
ORANGE
Total fruits: 3
```

This example demonstrates how a streams pipeline can be used to filter, transform, sort, and perform other operations on a stream of data in a concise and readable manner.

## Lazy evaluation

Lazy evaluation and processing of stream elements is a fundamental concept in Java Stream API. It enables efficient and on-demand computation of stream operations, allowing for optimized performance and resource utilization. Here's how lazy evaluation works in Java streams:

1. **Intermediate Operations**: Intermediate operations, such as `filter`, `map`, `flatMap`, `sorted`, and `distinct`, are lazily evaluated. When an intermediate operation is invoked on a stream, it doesn't immediately perform the operation on all elements. Instead, it creates a new stream that represents the pipeline of operations to be applied.

2. **Chaining Operations**: Intermediate operations can be chained together to form a pipeline of operations. Each operation modifies the stream, but the actual processing is deferred until a terminal operation is called. This chaining mechanism allows for the creation of complex and efficient computation patterns without explicitly iterating over the elements.

3. **Short-Circuiting Operations**: Short-circuiting operations, such as `findFirst`, `findAny`, `anyMatch`, `allMatch`, and `noneMatch`, further leverage lazy evaluation. They terminate the stream as soon as the desired condition is met, without processing all the remaining elements. This early termination saves unnecessary computation and improves performance.

4. **Terminal Operations**: Terminal operations, like `forEach`, `collect`, `reduce`, `count`, and `min/max`, trigger the actual processing of the stream. When a terminal operation is invoked, the stream pipeline is executed, and the elements are processed sequentially or in parallel, depending on the stream characteristics.

Lazy evaluation allows for more efficient resource usage, as it avoids unnecessary computations on elements that are not required for the final result. It also enables parallel execution of stream operations, where multiple elements can be processed concurrently, further enhancing performance.

It's important to note that lazy evaluation in streams doesn't mean that the operations are deferred indefinitely. Once a terminal operation is called, the stream operations are executed, and the result is produced. Lazy evaluation simply delays the computation until it is necessary, optimizing the processing of stream elements.

