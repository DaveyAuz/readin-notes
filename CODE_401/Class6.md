# Reading Notes Class #6

<ol>

><li> What is the difference between an Object and a Class in Java?

In Java, a class is a blueprint or template for creating objects, while an object is an instance of a class.

A class defines the properties and behaviors of a particular type of object. It includes information such as the object's data fields (also called instance variables) and the methods that can be called on the object. For example, a class can define a "Car" object with data fields such as make, model, and year, and methods such as start, stop, and accelerate.

An object, on the other hand, is a specific instance of a class that has been created in memory. It has its own set of values for the data fields defined in the class and can call the methods defined in the class. For example, if we create an object of the "Car" class, we can set its make to "Toyota", its model to "Corolla", and its year to "2018". We can also call its methods such as start() and stop().

To summarize, a class defines the blueprint for an object, while an object is a specific instance of a class that has been created in memory with its own values for the data fields and can call the methods defined in the class.
</li>

><li>Explain to a non-technical friend the concept of inheritance in Java.
Think of inheritance like a family tree. Just like how children inherit certain traits and characteristics from their parents, in Java, one class can inherit the properties and methods of another class.

So let's say we have a class called "Animal". This class defines certain properties and behaviors that are common to all animals, like having a name, age, and the ability to move. Now, let's say we want to create a new class called "Dog". Since a dog is a type of animal, we can use inheritance to have the "Dog" class inherit all the properties and behaviors of the "Animal" class.

This means that the "Dog" class will automatically have all the properties and behaviors of the "Animal" class, like a name, age, and the ability to move. However, we can also add additional properties and behaviors that are specific to dogs, like the ability to bark or fetch.

Inheritance is useful because it allows us to reuse code and avoid duplicating efforts. Instead of creating a brand new class from scratch every time, we can build on top of existing classes and inherit their properties and behaviors. This saves time and makes our code more organized and modular.

So that's inheritance in a nutshell! Just like how children inherit certain traits and characteristics from their parents, in Java, classes can inherit properties and behaviors from other classes.

</li>

><li> Static methods are also called what? Why?

In Java, static methods are also called class methods because they belong to the class as a whole rather than to any specific instance of the class.

When we declare a method as static, it means that the method is associated with the class rather than with any particular object of that class. This means that we can call the static method on the class itself, rather than on an instance of the class.

For example, let's say we have a class called "MathUtils" with a static method called "add". We can call this method on the class itself, like this:

```java
int sum = MathUtils.add(2, 3);
```
Notice that we didn't have to create an instance of the "MathUtils" class before calling the "add" method. We were able to call it directly on the class.

Static methods are useful when we want to define a utility method that doesn't rely on any state or data specific to an instance of the class. By making the method static, we can call it without having to create an object of the class first, which can save memory and improve performance.

</li>

><li> How can you access a variable of a class without instantiating an object from that class?

In Java, you can access a variable of a class without instantiating an object from that class by declaring the variable as static.

When we declare a variable as static, it means that the variable belongs to the class as a whole, rather than to any specific instance of the class. This means that we can access the variable directly on the class itself, rather than on an instance of the class.

Here's an example to illustrate this:

```java
public class MyClass {
    public static int myVariable = 42;
}
```

In this example, we've declared a class called "MyClass" with a static variable called "myVariable". To access this variable without instantiating an object from the class, we can simply use the class name and the dot operator:

```java
int x = MyClass.myVariable;
```
Notice that we didn't have to create an instance of the "MyClass" class before accessing the "myVariable" variable. We were able to access it directly on the class.

Static variables are useful when we want to define a variable that's shared across all instances of the class, or when we want to define a constant value that shouldn't change throughout the lifetime of the program. By making the variable static, we can access it without having to create an object of the class first, which can save memory and improve performance.

</li>


><li> What is a Design Pattern? Describe one or two with analogies from your previous work experience.
In Java, a design pattern is a reusable solution to a commonly occurring problem in software design. It is a proven way of solving problems that developers face when designing and implementing software systems.

In the City Explorer project at Codefellows, we used several design patterns to integrate various APIs and databases.

We used the Adapter design pattern to integrate the LocationIQ API, Weatherbit API, and MovieDB API with our application. The Adapter pattern is used to convert the interface of one class into another interface that clients expect. In our case, we created an adapter class for each API that converted the API's interface into a format that our application could work with.

We also used the Singleton design pattern to manage our connection to the MongoDB database. The Singleton pattern is used to ensure that only one instance of a class is created and to provide a global point of access to that instance. In our case, we created a singleton class called MongoDBConnection that managed our connection to the MongoDB database.

To make HTTP requests to our APIs, we used the Axios library, which is a popular JavaScript library for making HTTP requests. We used Axios to send GET requests to the Weatherbit API, MovieDB API, and LocationIQ API, and to receive responses in JSON format.

Finally, we used Render, a cloud platform for deploying and scaling web applications, to host our application. Render provided us with a reliable and scalable infrastructure for deploying our application.

By using these design patterns and libraries, we were able to integrate multiple APIs and databases into our application and provide a seamless user experience for our users.
</li>

><li> What is a Singleton?
In Java, a Singleton is a design pattern that restricts the instantiation of a class to one object. This means that there can only be one instance of a Singleton class in the entire application.

To implement the Singleton pattern, you need to make the class's constructor private so that it cannot be instantiated from outside the class. Then, you create a static method in the class that provides access to the single instance of the class. This static method creates an instance of the class if one does not exist and returns the existing instance if it does.

Here is an example of a Singleton class in Java:

```java
public class Singleton {
    private static Singleton instance;

    private Singleton() {
        // private constructor to prevent instantiation from outside the class
    }

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

In this example, the Singleton class has a private constructor and a getInstance() method that returns the single instance of the class. The getInstance() method creates a new instance of the Singleton class if one does not already exist and returns the existing instance if it does.

The Singleton pattern is useful when you need to ensure that there is only one instance of a particular class in your application, such as a configuration object or a connection to a database.



</li>

</ol>

[HOME](../README.md)