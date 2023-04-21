# Reading Notes Class #4

<ol>

><li> Explain the difference between an object and a class.
In Java, a class is a blueprint or template for creating objects, while an object is an instance of a class.

A class in Java defines the properties and behaviors of a group of objects. It defines the data members, which are the variables that store the state of the objects, and the methods, which are the functions that manipulate the state of the objects. A class can also define constructors, which are special methods used to initialize the state of an object when it is created.

On the other hand, an object is an instance of a class. When a class is instantiated, it creates an object in memory that has its own set of values for the class's data members. This object can be manipulated using the class's methods. Each object has its own unique state, which is determined by the values of its data members.

For example, consider a class called "Person" that has data members such as name, age, and address, and methods such as eat(), sleep(), and work(). When we create an object of the Person class, we are creating a new instance of that class with specific values for its data members. We can then call the methods on the object to manipulate its state. So, we may create an object called "person1" with a name of "John", an age of 25, and an address of "123 Main St", and then call the eat() method on that object to simulate the person eating a meal.

</li>

><li>Name two types of state that a Student object might have.

In Java, a Student object might have two types of state:

* Instance variables: These are variables that hold the state of an object. For a Student object, instance variables might include attributes such as name, age, grade, and student ID. Instance variables are declared within the class definition, and each instance of the class (i.e. each Student object) has its own copy of these variables.
For example, the following code defines a Student class with instance variables for name, age, and grade:

```java
public class Student {
   String name;
   int age;
   int grade;
}
```

* Current state or status: This is a more dynamic type of state that can change over time. For a Student object, current state might include whether the student is currently enrolled in a course or not, whether they have completed a particular assignment, or whether they have passed or failed a test. Current state can be represented using instance variables, but it can also be calculated on the fly based on other variables or external factors.
For example, the following code adds a boolean instance variable called "enrolled" to the Student class, which represents the current enrollment status of the student:

```java
public class Student {
   String name;
   int age;
   int grade;
   boolean enrolled;
}
```
Note that the enrolled variable can be set to true or false depending on whether the student is currently enrolled in a course or not.
</li>

><li> Name two types of behaviors that a student object might have.
In Java, a Student object might have two types of behaviors:

Instance methods: These are methods that define the behaviors or actions that a Student object can perform. For example, a Student object might have a method called "study" that updates the student's current state (e.g. by increasing their knowledge level) or a method called "submitAssignment" that updates their grade.
Here is an example of a Student class with two instance methods:

```java
public class Student {
   String name;
   int age;
   int grade;
   
   public void study() {
      // Update student's state (e.g. increase knowledge level)
   }
   
   public void submitAssignment() {
      // Update student's grade
   }
}
```

* Static methods: These are methods that are associated with the class itself rather than with individual instances of the class. Static methods can be called directly on the class without creating an instance of the class. For example, a Student class might have a static method called "getAverageGrade" that calculates the average grade for all students.
Here is an example of a Student class with a static method:

```java
public class Student {
   String name;
   int age;
   int grade;
   
   public static double getAverageGrade(Student[] students) {
      // Calculate average grade for all students in array
   }
}
```

Note that the getAverageGrade method takes an array of Student objects as a parameter and returns the average grade for all students in the array. Since this method is associated with the class itself, we can call it without creating an instance of the class.
</li>

><li> Explain the significance of a constructor for a class.

In Java, a constructor is a special method that is used to initialize objects of a class. The constructor is called automatically when a new object is created using the "new" keyword.

The significance of a constructor for a class in Java is that it performs the following tasks:

* Initializing instance variables: A constructor initializes the instance variables of an object when it is created. This ensures that the object is in a valid state and ready to use.

* Setting default values: If no values are provided to the constructor, it can set default values for the instance variables. This simplifies object creation by providing a default state for the object.

* Providing arguments to set initial values: A constructor can take arguments to set the initial values of the instance variables. This simplifies object creation by allowing the caller to specify the initial state of the object.

* Enforcing encapsulation: A constructor can be used to set private instance variables, enforcing encapsulation and preventing other classes from accessing or modifying the state of the object directly.

* Enabling inheritance: Constructors can be used to initialize the state of a subclass by calling the constructor of the superclass. This allows subclasses to inherit the state of the superclass and add their own additional state as needed.

In summary, a constructor is a key part of a class in Java, as it initializes objects and sets their initial state. It also enables encapsulation and inheritance and provides a simple interface for creating objects.
</li>

></li> Write the declaration statement for a class named “Student” (do not fill it with fields and methods).

```java
public class Student {
    // Fields and methods go here
}
```
This declaration statement includes the keyword "public" to indicate that the class can be accessed from other classes in the same package or from other packages, if the class is imported. The class name "Student" follows the keyword "class", and the curly braces {} enclose the class body, which includes the fields and methods that define the behavior of the class.

Note that this declaration statement only defines the structure of the class, without including any fields or methods. Fields and methods are added within the curly braces of the class body, as needed to implement the desired functionality of the class.

</li>

><li> What is the value of the binary number 1101?

According to google, The binary number 1101 is equivalent to the decimal number:

>* 1 x 2^3 + 1 x 2^2 + 0 x 2^1 + 1 x 2^0 = 8 + 4 + 0 + 1 = 13

Therefore, the value of the binary number 1101 is 13 in decimal. The Hexidecimal value of the binary number 1101 is d as well.
</li>

><li> Write the number 52 in binary. Write it in hexidecimal.

What is 52 in Binary? - (Base 2)	(110100)₂
What is 52 in Hexadecimal? - (Base 16)	(34)₁₆

</li>

</ol>

[HOME](../README.md)