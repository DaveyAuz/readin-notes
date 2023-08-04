# Reading Notes Class #19
<ol>

><li> Can you change the state of a data structure using functional programming?

In functional programming, the main principle is immutability, which means that data structures, once created, should not be changed. Instead of modifying the existing data, functional programming encourages creating new data structures with the desired changes.

In Java, you can follow functional programming principles to create new data structures and apply transformations to them without modifying the original data. Java provides various functional programming features that facilitate this approach:

1. Immutable Classes: You can define your data structures as immutable classes, where the state of the object cannot be changed after it is constructed. All instance variables are declared as final, and any methods that would modify the object's state return a new object instead.

2. Collections: Java provides immutable versions of collections through the `Collections` class, such as `Collections.unmodifiableList`, `Collections.unmodifiableSet`, and `Collections.unmodifiableMap`. These methods create read-only versions of the original collections, preventing modifications to the underlying data.

3. Streams: Java 8 introduced the `Stream` API, which allows you to perform functional-style operations on collections. Streams are designed to be used with immutable data structures and provide various methods like `map`, `filter`, `reduce`, etc., to process data without changing the original collection.

4. Functional Interfaces and Lambdas: Java's functional interfaces, like `Function`, `Consumer`, and `Predicate`, along with lambda expressions, allow you to pass behavior as an argument to methods. This approach enables you to perform transformations on data without modifying it directly.

By following these functional programming practices, you can effectively change the state of a data structure in Java by creating new instances that represent the desired changes. This immutability helps in writing more predictable, thread-safe, and functional code.

</li>

><li> Define purely functional programming.

Purely functional programming in Java refers to the practice of writing programs using functional programming principles without relying on mutable state or side effects. In a purely functional approach, functions are the primary building blocks of the program, and they operate on immutable data structures, producing new data as output rather than modifying existing data.

The key characteristics of purely functional programming in Java include:

1. Immutability: Data structures are declared as immutable, meaning their state cannot be changed after creation. Instead of modifying data in place, new data structures are created with the desired changes.

2. Functions as First-Class Citizens: In purely functional programming, functions are treated as first-class citizens, meaning they can be assigned to variables, passed as arguments to other functions, and returned as values from functions.

3. No Side Effects: Functions in purely functional programming do not have side effects, such as modifying global variables or performing I/O operations. They only produce output based on their inputs and have no impact on the external environment.

4. Recursion: Purely functional programming often relies heavily on recursion to perform repetitive tasks, as looping constructs like `for` and `while` loops are typically avoided due to their mutable nature.

5. Higher-Order Functions: Higher-order functions, which are functions that take other functions as arguments or return functions, are commonly used in purely functional programming to achieve composability and abstraction.

6. Lazy Evaluation: Lazy evaluation is a technique where computations are deferred until the result is needed. This allows for more efficient use of resources and can be beneficial in functional programming.

While Java is not a purely functional language by design, it does support functional programming features, such as lambda expressions, functional interfaces, and the Stream API introduced in Java 8. Developers can follow functional programming principles in Java to achieve some of the benefits of purely functional programming, such as improved readability, testability, and modularity. However, writing purely functional code in Java may require additional discipline and attention to avoid using mutable data structures and side effects.

</li>

><li> How do you think purely functional programming will differ from the programs you’ve written so far in this course?

Purely functional programming in Java and the JavaScript programs written in this course would differ in several ways due to the nature of the languages and their support for functional programming features. Here are some key differences:

1. **Immutability and Data Structures:** In JavaScript, you can use libraries like Immutable.js to work with immutable data structures, but it's not a built-in feature. In contrast, Java has more support for immutability through the `final` keyword and the Java Collections Framework, which includes immutable collections like `Collections.unmodifiableList`. Purely functional programming in Java may leverage these features more extensively to ensure immutability of data structures.

2. **Type System:** Java is a statically-typed language with a strong type system, whereas JavaScript is dynamically-typed. The static typing in Java allows for better compile-time checks and can help catch errors earlier. However, this may also lead to more explicit type annotations in functional Java code compared to JavaScript.

3. **Higher-Order Functions:** Both Java and JavaScript support higher-order functions (functions that can take other functions as arguments or return functions as results), but JavaScript's functional programming capabilities are more prominent and idiomatic. In JavaScript, you can easily use anonymous functions, arrow functions, and closures for functional programming. Java, on the other hand, requires more verbosity for functional-style programming, especially before Java 8 introduced lambda expressions and the `Stream` API.

4. **Functional Libraries:** JavaScript has several popular functional programming libraries like Ramda and Lodash, which provide numerous utility functions for functional programming. While Java also has libraries that support functional programming, such as Vavr and Javaslang, they may not be as widely used as their JavaScript counterparts.

5. **Async Programming:** JavaScript's asynchronous nature with the event loop makes it well-suited for handling asynchronous operations using callbacks, promises, or async/await. Java also supports asynchronous programming, but the approach and syntax (e.g., using CompletableFuture or RxJava) are different.

6. **Functional Composition:** JavaScript's flexibility and dynamic nature allow for more concise and expressive functional compositions. In Java, functional composition is possible, but it may involve more verbose code due to the nature of the language.

7. **Functional Pipeline:** The functional pipeline concept, popularized by libraries like Lodash and Ramda in JavaScript, allows for cleaner and more readable code by chaining functions together. Java's Stream API introduced in Java 8 provides similar capabilities, but the syntax and usage might be slightly different.

Overall, while both Java and JavaScript can support functional programming, JavaScript's more lightweight and dynamic nature often makes it a more natural fit for functional programming paradigms. Java, being a statically-typed language, may require more explicit type annotations and boilerplate code for functional programming constructs. However, with the introduction of lambdas and the Stream API in Java 8 and the ongoing evolution of the language, Java has become more functional-friendly over time.

</li>

<ol>

[HOME](../README.md)