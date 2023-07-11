# Reading Notes Class #1

<ol>

><li> What does “strong typed” mean?
In Java, "strongly typed" means that every variable in the program must have a specific data type that is explicitly declared, and that the compiler enforces this type system to ensure that variables are used only in appropriate ways.

This means that Java is a statically typed language, where the data types of variables are checked at compile-time rather than at runtime. For example, if you declare a variable to be an integer type, you cannot assign it a string value, and the compiler will catch this error before the program is executed.

The advantage of strong typing is that it helps catch errors early in the development process, before the program is executed. It also makes code more readable and maintainable, since it makes it clear what type of data each variable holds.
</li>


><li> What are the primitive data types? 
  In Java, there are eight primitive data types:

* boolean: represents a true/false value.

* byte: represents an 8-bit signed two's complement integer.

* short: represents a 16-bit signed two's complement integer.

* int: represents a 32-bit signed two's complement integer.

* long: represents a 64-bit signed two's complement integer.

* float: represents a single-precision 32-bit IEEE 754 floating point.

* double: represents a double-precision 64-bit IEEE 754 floating point.

* char: represents a single 16-bit Unicode character.

These data types are used to represent simple values and are often used as building blocks for more complex data types, such as arrays, objects, and classes.
</li>

><li> Explain to a non-technical friend the difference in how compilation works in Java and JavaScript.
Java and JavaScript are two programming languages that are used to create software applications, but they have some differences in how their code is compiled and executed.

In Java, the code is compiled into bytecode, which is a platform-independent code that can be executed on any machine that has a Java Virtual Machine (JVM) installed. The JVM interprets the bytecode and executes the program. This means that the code is compiled only once and can be executed on any platform that supports a JVM.

On the other hand, JavaScript is an interpreted language. This means that the code is not compiled into machine code like Java. Instead, the JavaScript code is executed directly by the browser or the JavaScript engine that runs on the server. The JavaScript code is loaded and executed line by line, without going through a compilation process.

So, in summary, Java code is compiled into bytecode and executed on a JVM, while JavaScript code is interpreted and executed directly by the browser or the JavaScript engine.

But Essentially, they both are ways to use human language, symbols and numbers to translate data into binary format so that the computer or server can read and interpret it.

><li> Does code compiling mean that it works correctly?
Not necessarily. Code compiling is the process of translating human-readable source code into machine-readable code that can be executed by a computer. The compiler checks the syntax and structure of the code to ensure it meets the requirements of the programming language, and generates an executable binary file.

However, even if the code compiles without errors, it does not guarantee that it will work correctly. There may still be logical errors or bugs in the code that can cause the program to behave unexpectedly or produce incorrect results.

To ensure that code works correctly, it needs to be thoroughly tested, and any errors or bugs need to be identified and fixed. This process is known as debugging and is an essential part of the software development process.
</li>

  ><li> How many keywords does Java have?
Java has 51 keywords as of Java 16:
abstract,    continue,    for,        new,         switch,
assert,      default,     if,         package,     synchronized,
boolean,     do,          goto,       private,     this,
break,       double,      implements, protected,   throw,
byte,        else,        import,     public,     throws,
case,        enum,        instanceof, return,      transient,
catch,       extends,     int,        short,       try,
char,        final,       interface,  static,     void,
class,       finally,     long,       strictfp,    volatile,
const,      float,       native,     super,       while.

</li>

><li> How do you print words to the console in Java?

  To print words to the console in Java, you can use the System.out.println() statement.

```java
    public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```

When you run this program, it will print the string "Hello, world!" to the console. The println() method adds a newline character at the end of the output, so each new output will be printed on a new line.

</li>

</ol>

[HOME](../README.md)
