# Reading Notes Class #3

<ol>

><li>Explain the difference between an “int” and an “Integer” in Java.
  In Java, an "int" and an "Integer" are both used to represent whole numbers, but they have some important differences.

* Type:
"int" is a primitive data type in Java, while "Integer" is a class from the Java standard library.

* Object-oriented features:
As a primitive type, "int" doesn't have any methods or other object-oriented features. On the other hand, "Integer" is a class and has many useful methods such as parseInt() and compareTo().

* Null value:
"int" cannot be null, whereas "Integer" can be null. This means that "Integer" can be used in situations where nullability is required, such as in collections or as method parameters.

* Boxing/unboxing:
Java has the concept of boxing and unboxing to convert between primitives and their corresponding wrapper classes. When an "int" is boxed to an "Integer", a new object is created on the heap to wrap the value of the "int". This can be a performance hit in certain situations.

* Memory allocation:
"int" is a primitive type and is stored directly on the stack, whereas "Integer" is a class and is stored on the heap, requiring more memory allocation.

* In summary, "int" is a primitive data type used to represent whole numbers in Java, while "Integer" is a class that provides object-oriented features and the ability to be null. Depending on the situation, it may be more appropriate to use one over the other.

</li>

><li> What is the default value for ints? Integers?
In Java, the default value for an int primitive type is 0. This means that if an int variable is declared but not initialized, it will have a value of 0.

On the other hand, the default value for an Integer object (which is a wrapper class for the int primitive type) is null. This means that if an Integer variable is declared but not initialized, it will have a value of null.

It's important to note that the default values for other primitive types in Java are as follows:

* boolean: false
* char: '\u0000'
* byte: 0
* short: 0
* long: 0L
* float: 0.0f
* double: 0.0d

It's always a good practice to initialize variables to their intended values to avoid unexpected results in your code.

</li>

><li> What is autoboxing? Unboxing?
In Java, autoboxing and unboxing are features that allow automatic conversion between primitive types and their corresponding wrapper classes.

Autoboxing is the automatic conversion of a primitive type to its corresponding wrapper class. For example, when an int primitive is assigned to an Integer object, the Java compiler automatically converts the int to an Integer using autoboxing.

Here's an example of autoboxing in Java:

```java
int x = 10;
Integer y = x; // autoboxing int to Integer
```
Unboxing is the opposite of autoboxing - it's the automatic conversion of a wrapper class to its corresponding primitive type. For example, when an Integer object is assigned to an int primitive, the Java compiler automatically unboxes the Integer to an int.

Here's an example of unboxing in Java:

```java
Integer x = 10;
int y = x; // unboxing Integer to int
```
Autoboxing and unboxing can make code more concise and easier to read by allowing the programmer to use primitive types and their corresponding wrapper classes interchangeably, without having to explicitly convert between them. However, it's important to be aware of the performance impact of autoboxing and unboxing, especially in performance-critical code, as these operations can be slower than working with primitive types directly.

</li>

><li> List the three basic categories of exceptions.
In Java, exceptions are divided into three basic categories:

* Checked exceptions:
Checked exceptions are exceptions that must be either caught and handled, or declared in the method signature using the throws keyword. Examples of checked exceptions include 'IOException' and 'SQLException'. These exceptions are checked at compile time to ensure that they are properly handled.

* Unchecked exceptions (also called Runtime Exceptions):
Unchecked exceptions are exceptions that do not have to be caught or declared. They are typically caused by programming errors such as null pointer exceptions or array index out of bounds exceptions. Examples of unchecked exceptions include NullPointerException and 'ArrayIndexOutOfBoundsException'.

* Errors:
Errors are exceptional conditions that are not recoverable, such as 'OutOfMemoryError' or 'StackOverflowError'. Errors should not be caught or handled by application code, as they typically indicate a serious problem with the JVM or system environment.

It's important to note that exceptions in Java form a hierarchy, with the base class Throwable at the top, and the two main subclasses Exception and Error below it. All exceptions in Java are subclasses of Throwable, so catching a Throwable will catch both exceptions and errors. However, it's generally not recommended to catch Throwable unless absolutely necessary, as it can mask serious problems and make debugging more difficult.

</li>

><li> What type of statement can you use to handle an exception?
* In Java, there are two types of statements that can be used to handle exceptions:

try-catch statement:
The try-catch statement is used to catch and handle exceptions. The try block contains the code that may throw an exception, and the catch block contains the code that handles the exception if it is thrown. Multiple catch blocks can be used to handle different types of exceptions. Here's an example of a try-catch statement:

```java
try {
   // code that may throw an exception
} catch (ExceptionType1 e1) {
   // code to handle exception of type ExceptionType1
} catch (ExceptionType2 e2) {
   // code to handle exception of type ExceptionType2
} finally {
   // optional code that is always executed, regardless of whether an exception was thrown or caught
}
```

* Throws clause:
The throws clause is used to declare that a method may throw a checked exception, without actually handling the exception. The throws clause is added to the method signature, and specifies the types of exceptions that the method may throw. Here's an example of a method signature with a throws clause:

```java
public void myMethod() throws MyCheckedException {
   // code that may throw MyCheckedException
}
```
It's important to note that the throws clause is only used for checked exceptions, and not for unchecked exceptions or errors.
</li>

><li> In Java Describe a situation where you think it would be useful to have a program that scans text.
In Java, there are many situations where it would be useful to have a program that can scan and analyze text. Here are a few examples:

* Text mining and analysis:
Java text scanning programs can be used to extract meaningful information from large volumes of unstructured text, such as social media posts, news articles, and customer reviews. By analyzing the content of these texts, businesses and organizations can gain insights into customer sentiment, market trends, and brand perception.

* Search engine optimization:
Java text scanning programs can be used to analyze website content and optimize it for search engines. These programs can scan web pages for keywords and phrases that are relevant to a particular search query, and provide suggestions for how to improve the content to rank higher in search results.

* Spell checking and grammar checking:
Java text scanning programs can be used to detect and correct spelling and grammar errors in written text. These programs can scan a piece of text and identify any misspelled words or grammatical errors, and suggest corrections to improve the overall quality and readability of the text.

* Fraud detection:
Java text scanning programs can be used to detect fraudulent activity, such as phishing scams, by scanning emails and other text-based communications for suspicious keywords and patterns. By analyzing the content of these communications, these programs can identify potential fraud and alert users to take appropriate action.

Overall, Java text scanning programs can help businesses and organizations improve efficiency, accuracy, and productivity by automating the process of analyzing and understanding written language.
</li>

></li> What is input from a Scanner broken down into?
In Java, input from a Scanner object is broken down into tokens. A token is a sequence of characters that represents a single element of input. By default, the Scanner class breaks input into tokens by whitespace, which includes spaces, tabs, and line breaks.

For example, if the input "Hello World" is passed to a Scanner object, it will be broken down into two tokens: "Hello" and "World". These tokens can then be processed or manipulated as needed by the Java program.

The Scanner class provides methods for reading different types of input, such as strings, integers, and floating-point numbers, as tokens. The next() method reads the next token as a string, while the nextInt() and nextDouble() methods read the next token as an integer or double, respectively.

It's also possible to use the useDelimiter() method of the Scanner class to specify a different delimiter for breaking input into tokens, such as a comma or semicolon. This can be useful when processing input from a file or a user input stream that has a specific format.

</li>




</ol>

[HOME](../README.md)