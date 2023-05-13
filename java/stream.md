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

In the Java Stream API, operations can be classified into two categories: terminal operations and intermediate operations. Understanding the distinction between these two types of operations is crucial for effectively working with streams.

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



### Terminal Operations:
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


