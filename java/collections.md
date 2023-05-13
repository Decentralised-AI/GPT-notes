# Java Collections Framework

The Java Collections Framework provides a set of classes and interfaces that are designed to handle and manipulate collections of objects in Java. It offers a standardized way to store, retrieve, manipulate, and process groups of objects efficiently. The framework includes various data structures and algorithms to handle different types of collections. Here are the key components of the Java Collections Framework:

1. Interfaces:
   - `Collection`: The root interface of the framework that defines basic operations for working with collections.
   - `List`: An ordered collection that allows duplicate elements and provides methods for positional access.
   - `Set`: A collection that does not allow duplicate elements and does not maintain any specific order.
   - `Queue`: A collection designed for holding elements prior to processing. It follows the FIFO (First-In, First-Out) principle.
   - `Map`: An object that maps keys to values. It does not allow duplicate keys and provides efficient retrieval of values based on keys.

2. Classes:
   - `ArrayList`: Implements the `List` interface using a resizable array. It provides fast element retrieval but slower insertion and deletion.
   - `LinkedList`: Implements the `List` and `Deque` interfaces using a doubly-linked list. It provides fast insertion and deletion but slower element retrieval.
   - `HashSet`: Implements the `Set` interface using a hash table. It provides fast access and does not allow duplicate elements.
   - `TreeSet`: Implements the `SortedSet` interface using a self-balancing binary search tree. It maintains elements in sorted order.
   - `HashMap`: Implements the `Map` interface using a hash table. It provides fast key-value pair retrieval based on keys.
   - `TreeMap`: Implements the `SortedMap` interface using a self-balancing binary search tree. It maintains key-value pairs in sorted order.

3. Algorithms and Utilities:
   - The framework provides various algorithms, such as sorting, searching, shuffling, and reversing collections, through the `Collections` class.
   - The `Arrays` class offers utility methods for working with arrays, including sorting, searching, and converting between arrays and collections.

The Java Collections Framework simplifies the process of working with collections in Java by providing a consistent and efficient way to store and manipulate data. It promotes code reuse, enhances productivity, and improves the performance of data manipulation operations. By utilizing the framework, you can easily choose the appropriate data structure and algorithm based on your requirements, leading to cleaner and more efficient code.

## ArrayList

`ArrayList` is a class in the Java Collections Framework that implements the `List` interface. It is designed to provide a resizable array-like data structure that can dynamically grow or shrink based on the number of elements it contains. It allows you to store and manipulate a collection of objects in a sequential manner.

Here are the key features and characteristics of `ArrayList`:

1. Resizable Array: `ArrayList` internally uses an array to store the elements. The array has a certain initial capacity, but it can automatically resize itself when needed to accommodate more elements. This dynamic resizing makes `ArrayList` suitable for situations where the number of elements is not known in advance.

2. Ordered Collection: `ArrayList` maintains the order of elements based on their insertion order. It allows duplicate elements, and each element is associated with an index starting from 0. This index-based access allows for efficient random access and retrieval of elements.

3. Dynamic Size: As you add or remove elements from an `ArrayList`, it automatically adjusts its size to accommodate the changes. This eliminates the need for manual resizing or handling of array sizes, making it convenient to work with varying numbers of elements.

4. Efficient Random Access: `ArrayList` provides constant-time (O(1)) access to elements by their index. This means retrieving an element by its index is efficient and does not depend on the size of the list.

5. Flexible Modifications: `ArrayList` supports various methods for modifying its content, including adding elements at the end or at specific positions, removing elements, replacing elements, and clearing the entire list. These operations are optimized for efficiency, considering the dynamic resizing and repositioning of elements.

6. Iteration and Traversal: `ArrayList` provides convenient ways to iterate over its elements using enhanced for-loop, iterators, or streams. This allows you to perform operations on each element or process the entire list easily.

7. Not Thread-Safe: By default, `ArrayList` is not synchronized and not thread-safe. If you need to use `ArrayList` in a multi-threaded environment, you should consider synchronizing access to it or use the thread-safe variant, such as `Vector` or `CopyOnWriteArrayList`.

Here's an example of using `ArrayList`:

```java
import java.util.ArrayList;

public class ArrayListExample {
    public static void main(String[] args) {
        // Creating an ArrayList
        ArrayList<String> fruits = new ArrayList<>();

        // Adding elements
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");

        // Accessing elements
        System.out.println(fruits.get(1)); // Output: Banana

        // Modifying elements
        fruits.set(2, "Grapes");

        // Removing an element
        fruits.remove(0);

        // Iterating over elements
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

In the example above, we create an `ArrayList` named `fruits` to store strings. We add elements using the `add` method, access elements using the `get` method, modify an element using the `set` method, and remove an element using the `remove` method. Finally, we iterate over the elements using an enhanced for-loop to print each fruit.

`ArrayList` is a versatile and commonly used data structure in Java. It provides the flexibility of dynamically resizing arrays while maintaining an ordered collection.

Certainly! Here's an example demonstrating different ways to iterate over an `ArrayList`:

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.ListIterator;

public class ArrayListIterationExample {
    public static void main(String[] args) {
        // Creating an ArrayList
        ArrayList<String> colors = new ArrayList<>();

        // Adding elements
        colors.add("Red");
        colors.add("Green");
        colors.add("Blue");

        // 1. Enhanced for-loop
        System.out.println("Using enhanced for-loop:");
        for (String color : colors) {
            System.out.println(color);
        }

        // 2. Iterator
        System.out.println("\nUsing Iterator:");
        Iterator<String> iterator = colors.iterator();
        while (iterator.hasNext()) {
            String color = iterator.next();
            System.out.println(color);
        }

        // 3. ListIterator (allows bidirectional traversal)
        System.out.println("\nUsing ListIterator (forward):");
        ListIterator<String> listIterator = colors.listIterator();
        while (listIterator.hasNext()) {
            String color = listIterator.next();
            System.out.println(color);
        }

        System.out.println("\nUsing ListIterator (backward):");
        while (listIterator.hasPrevious()) {
            String color = listIterator.previous();
            System.out.println(color);
        }

        // 4. Stream API (Java 8+)
        System.out.println("\nUsing Stream API:");
        colors.stream().forEach(System.out::println);
      
        // 5. Classic for loop
        System.out.println("\nUsing classic for loop:");
        for (int i = 0; i < colors.size(); i++) {
            String color = colors.get(i);
            System.out.println(color);
        }
    }
}
```

In this example, we create an `ArrayList` named `colors` and add some elements. Then we demonstrate the following ways to iterate over the elements:

1. Enhanced for-loop: This loop simplifies the iteration process and allows you to directly access each element in the `ArrayList` without using an explicit iterator.

2. Iterator: We obtain an iterator from the `ArrayList` using the `iterator()` method and iterate over the elements using the `hasNext()` and `next()` methods.

3. ListIterator: This iterator provides additional capabilities like bidirectional traversal. We obtain a `ListIterator` using the `listIterator()` method and use `hasNext()`, `next()`, `hasPrevious()`, and `previous()` methods to traverse the `ArrayList`.

4. Stream API: Starting from Java 8, you can use the Stream API to perform operations on collections. In this case, we convert the `ArrayList` to a stream and use the `forEach` method to print each element.

5.  Classic for loop to iterate over the elements of the ArrayList. We use the size() method to determine the length of the list and access each element using the get() method with the corresponding index.

These different approaches to iteration provide flexibility and convenience based on your specific requirements.


## HashMap


`HashMap` is a class in the Java Collections Framework that implements the `Map` interface. It provides an efficient way to store and retrieve key-value pairs, where each key is unique within the map. `HashMap` uses hashing techniques to store and locate elements based on their keys, allowing for fast access and retrieval.

Here are the key features and characteristics of `HashMap`:

1. Key-Value Pairing: `HashMap` stores data in the form of key-value pairs. Each key is associated with a corresponding value. Keys are unique within the map, meaning that duplicate keys are not allowed, but different keys can be associated with the same value.

2. Efficient Retrieval: `HashMap` provides fast retrieval of values based on their associated keys. It uses the concept of hashing, which involves mapping keys to unique indices in an underlying array. This allows for constant-time (O(1)) retrieval of values when the key is known.

3. Dynamic Size: `HashMap` can dynamically resize itself based on the number of elements it contains. It starts with an initial capacity and automatically grows or shrinks as elements are added or removed. This makes `HashMap` suitable for scenarios where the number of elements is not known in advance.

4. Ordering: By default, `HashMap` does not guarantee any specific order of the elements. The order in which elements are stored and retrieved may vary. If you need to maintain a specific order, you can use `LinkedHashMap`, which maintains the insertion order, or `TreeMap`, which orders elements based on their natural ordering or a custom comparator.

5. Null Values and Keys: `HashMap` allows null values and a single null key. This means you can store null values and retrieve them using the associated null key. However, keep in mind that excessive use of null keys or values can make the code less readable and increase the chances of NullPointerExceptions.

6. Not Thread-Safe: `HashMap` is not synchronized and is not thread-safe by default. If you need to use `HashMap` in a multi-threaded environment, you should consider using `ConcurrentHashMap` or synchronizing access to the map manually using synchronization constructs.

7. Iteration: `HashMap` provides several methods to iterate over its elements, including key-based iteration, value-based iteration, and entry-based iteration. You can use iterators or enhanced for-loops to traverse the keys, values, or key-value pairs stored in the map.

Here's an example demonstrating the basic usage of `HashMap`:

```java
import java.util.HashMap;

public class HashMapExample {
    public static void main(String[] args) {
        // Creating a HashMap
        HashMap<String, Integer> studentScores = new HashMap<>();

        // Adding key-value pairs
        studentScores.put("John", 85);
        studentScores.put("Emily", 92);
        studentScores.put("Daniel", 78);

        // Accessing values
        int johnScore = studentScores.get("John");
        System.out.println("John's score: " + johnScore);

        // Modifying values
        studentScores.put("Emily", 95);

        // Removing a key-value pair
        studentScores.remove("Daniel");

        // Checking if a key exists
        boolean hasEmily = studentScores.containsKey("Emily");
        System.out.println("Has Emily: " + hasEmily);

        // Iterating over the keys
        for (String name : studentScores.keySet()) {
            System.out.println("Name: " + name + ", Score: " + studentScores.get(name));
        }
    }
}
```

In this example, we create a `HashMap` named `studentScores` to store the scores of students. We add key-value pairs using the `put` method, retrieve values using the `

## Stack

In Java, the `Stack` class is a part of the Java Collections Framework and represents a Last-In-First-Out (LIFO) data structure. It is an implementation of a stack, which is a data structure that allows elements to be added and removed from one end only, called the top of the stack.

Here are the key features and characteristics of the `Stack` class:

1. LIFO Order: The `Stack` follows the LIFO order, meaning that the last element added is the first one to be removed. New elements are added to the top of the stack, and removal operations also happen at the top.

2. Extends Vector Class: In Java, the `Stack` class is implemented as a subclass of the `Vector` class. Therefore, it inherits the methods and behaviors of `Vector` while providing additional stack-specific operations.

3. Push and Pop Operations: The `Stack` class provides two main operations for manipulating the stack:

   - `push(element)`: This method adds an element to the top of the stack.
   - `pop()`: This method removes and returns the element at the top of the stack.

4. Peeking: The `Stack` class also allows you to inspect the element at the top of the stack without removing it using the `peek()` method. It returns the top element without modifying the stack.

5. Empty Check: You can check if the stack is empty using the `empty()` method, which returns `true` if the stack is empty and `false` otherwise.

6. Search Operation: The `Stack` class provides a `search(element)` method to check the position of an element within the stack. It returns the 1-based position of the element from the top of the stack. If the element is not found, it returns -1.

7. Thread Safety: The `Stack` class is not synchronized by default, meaning that it is not thread-safe for concurrent access. If you need to use a synchronized version of the stack in a multi-threaded environment, you can use the `java.util.concurrent` package, such as `java.util.concurrent.ConcurrentLinkedDeque` or synchronize access to the stack manually using synchronization constructs.

Here's an example demonstrating the basic usage of the `Stack` class:

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        // Creating a Stack
        Stack<String> stack = new Stack<>();

        // Pushing elements onto the stack
        stack.push("Java");
        stack.push("Python");
        stack.push("C++");

        // Peeking the top element
        String topElement = stack.peek();
        System.out.println("Top element: " + topElement);

        // Popping elements from the stack
        String poppedElement = stack.pop();
        System.out.println("Popped element: " + poppedElement);

        // Checking if the stack is empty
        boolean isEmpty = stack.empty();
        System.out.println("Is stack empty? " + isEmpty);

        // Searching for an element in the stack
        int position = stack.search("Java");
        System.out.println("Position of 'Java': " + position);
    }
}
```

In this example, we create a `Stack` named `stack` and perform various operations on it. We push elements onto the stack using the `push` method, peek at the top element using `peek`, pop an element from the stack using `pop`, check if the stack is empty using `empty`, and search for an element within the stack using `search`. The example demonstrates the basic functionalities of the `Stack` class in Java.

## PriorityQueue

In Java, the `PriorityQueue` class is a part of the Java Collections Framework and implements the `Queue` interface. It represents a queue where elements are ordered based on their natural ordering or a custom comparator. Elements with higher priority are dequeued first.

Here are the key features and characteristics of the `PriorityQueue` class:

1. Priority Ordering: The `PriorityQueue` orders elements based on their priority. The priority can be determined by the natural ordering of elements (if they implement the `Comparable` interface) or a custom comparator provided during the queue's instantiation.

2. Element Insertion: Elements can be inserted into the `PriorityQueue` using the `add(element)` or `offer(element)` methods. The element is inserted at an appropriate position in the queue based on its priority.

3. Element Removal: The `PriorityQueue` provides methods to remove elements from the queue. The `remove()` and `poll()` methods remove and return the highest-priority element from the queue. If multiple elements have the same highest priority, the order of removal is determined based on their position in the queue.

4. Peek: The `PriorityQueue` allows you to inspect the highest-priority element without removing it using the `peek()` method. It returns the highest-priority element or `null` if the queue is empty.

5. Size and Empty Check: You can check the size of the `PriorityQueue` using the `size()` method and determine if it is empty using the `isEmpty()` method.

6. Not Thread-Safe: By default, `PriorityQueue` is not synchronized and is not thread-safe. If you need to use it in a multi-threaded environment, you should consider using synchronization constructs or using the `java.util.concurrent` package's synchronized versions, such as `PriorityBlockingQueue`.

7. Implementation: Internally, `PriorityQueue` is implemented as a binary heap, which allows for efficient insertion, removal, and retrieval of elements based on their priority. The binary heap ensures that the highest-priority element is always at the front of the queue.

Here's an example demonstrating the basic usage of the `PriorityQueue` class:

```java
import java.util.PriorityQueue;

public class PriorityQueueExample {
    public static void main(String[] args) {
        // Creating a PriorityQueue
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        // Adding elements
        pq.offer(10);
        pq.offer(30);
        pq.offer(20);

        // Retrieving and removing elements
        int firstElement = pq.poll();
        System.out.println("First element: " + firstElement);

        // Retrieving, but not removing, the highest-priority element
        int highestPriorityElement = pq.peek();
        System.out.println("Highest priority element: " + highestPriorityElement);

        // Checking if the queue is empty
        boolean isEmpty = pq.isEmpty();
        System.out.println("Is queue empty? " + isEmpty);
    }
}
```

In this example, we create a `PriorityQueue` named `pq` and add elements to it using the `offer` method. We then retrieve and remove the highest-priority element using `poll` and peek at the highest-priority element without removing it using `peek`. Finally, we check if the queue is empty using `isEmpty`. The example demonstrates the basic functionalities of the `PriorityQueue` class in Java.

## HashSet

In Java, the `HashSet` class is a part of the Java Collections Framework and implements the `Set` interface. It represents an unordered collection of unique elements, where each element is stored using its hash code for efficient retrieval.

Here are the key features and characteristics of the `HashSet` class:

1. Uniqueness: The `HashSet` ensures that each element in the set is unique. It does not allow duplicate elements. If you attempt to add a duplicate element, it will be ignored, and the set will remain unchanged.

2. No Order: The `HashSet` does not maintain any specific order of elements. Elements are stored based on their hash code, and their positions in the set may change as elements are added or removed.

3. Efficient Retrieval: The `HashSet` provides constant-time performance for basic operations such as `add(element)`, `contains(element)`, and `remove(element)`. These operations rely on the hash code of the elements, which allows for efficient retrieval.

4. Null Elements: The `HashSet` allows the inclusion of a single `null` element. If you attempt to add multiple `null` elements, only one will be added, and subsequent additions will be ignored.

5. Iteration: You can iterate over the elements of a `HashSet` using an enhanced for loop or an iterator. However, keep in mind that the iteration order is not guaranteed and may vary between different runs of the application.

6. No Indexing: Unlike some other collection types, such as `ArrayList`, the `HashSet` does not provide direct indexing access to its elements. Elements can only be accessed by iterating over the set or using the `contains` method to check for their presence.

7. Hashing and Equality: The `HashSet` relies on the `hashCode()` and `equals()` methods of the elements to determine uniqueness and perform operations such as insertion and removal. It is important to properly implement these methods when using custom objects as elements in a `HashSet`.

Here's an example demonstrating the basic usage of the `HashSet` class:

```java
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        // Creating a HashSet
        HashSet<String> set = new HashSet<>();

        // Adding elements
        set.add("Apple");
        set.add("Banana");
        set.add("Orange");
        set.add("Mango");

        // Printing the HashSet
        System.out.println("HashSet: " + set);

        // Checking if an element exists
        boolean containsApple = set.contains("Apple");
        System.out.println("Contains 'Apple'? " + containsApple);

        // Removing an element
        boolean removedBanana = set.remove("Banana");
        System.out.println("Removed 'Banana'? " + removedBanana);

        // Size of the HashSet
        int size = set.size();
        System.out.println("Size of the HashSet: " + size);
    }
}
```

In this example, we create a `HashSet` named `set` and add elements to it using the `add` method. We then print the contents of the `HashSet` using the `toString` method. Next, we check if an element exists in the set using `contains` and remove an element using `remove`. Finally, we retrieve the size of the `HashSet` using `size`. The example demonstrates the basic functionalities of the `HashSet` class in Java.


## TreeMap

In Java, the `TreeMap` class is a part of the Java Collections Framework and implements the `NavigableMap` interface. It represents a sorted map based on a binary search tree data structure. The elements in a `TreeMap` are ordered based on their natural ordering or a custom comparator.

Here are the key features and characteristics of the `TreeMap` class:

1. Sorted Ordering: The `TreeMap` maintains the elements in sorted order based on their keys. The natural ordering of the keys is used if they implement the `Comparable` interface, or a custom comparator can be provided during the map's instantiation.

2. Key-Value Pairs: Each element in a `TreeMap` is a key-value pair. The keys must be unique within the map, but the values can be duplicated. The elements are stored based on their keys, and the sorting is performed on the keys.

3. Balanced Binary Search Tree: Internally, the `TreeMap` uses a balanced binary search tree, specifically a Red-Black tree, to store the elements. This ensures efficient insertion, deletion, and retrieval operations with a time complexity of O(log N), where N is the number of elements in the map.

4. Navigable Operations: The `TreeMap` provides additional navigation operations beyond the basic `Map` operations. These include methods like `firstKey()`, `lastKey()`, `lowerKey()`, `higherKey()`, etc., which allow you to find keys that are lower or higher than a given key.

5. Null Keys: Unlike some other map implementations, such as `HashMap`, `TreeMap` does not allow null keys. If you attempt to insert a null key, a `NullPointerException` will be thrown.

6. Iteration Order: When iterating over a `TreeMap`, the elements are returned in ascending order based on the keys. This allows you to easily iterate through the map in a sorted manner.

7. Submap Views: The `TreeMap` provides methods to obtain submap views of the map, allowing you to work with a specific range of keys. These methods include `subMap()`, `headMap()`, and `tailMap()`, which return a view of the map containing keys falling within the specified range.

Here's an example demonstrating the basic usage of the `TreeMap` class:

```java
import java.util.TreeMap;

public class TreeMapExample {
    public static void main(String[] args) {
        // Creating a TreeMap
        TreeMap<String, Integer> treeMap = new TreeMap<>();

        // Adding elements
        treeMap.put("Apple", 10);
        treeMap.put("Banana", 5);
        treeMap.put("Orange", 8);
        treeMap.put("Mango", 12);

        // Printing the TreeMap
        System.out.println("TreeMap: " + treeMap);

        // Getting the value for a key
        int appleValue = treeMap.get("Apple");
        System.out.println("Value for 'Apple': " + appleValue);

        // Removing an element
        int removedValue = treeMap.remove("Banana");
        System.out.println("Removed value for 'Banana': " + removedValue);

        // Size of the TreeMap
        int size = treeMap.size();
        System.out.println("Size of the TreeMap: " + size);
    }
}
```

In this example, we create a `TreeMap` named `treeMap` and add elements to it using the `put` method. We then print the contents of the `TreeMap` using the `toString` method. Next, we retrieve the value associated with a specific key using `get` and remove an element using `remove`. Finally, we retrieve the size of the TreeMap.


