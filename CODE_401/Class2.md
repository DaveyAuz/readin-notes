# Reading Notes Class #2\

<ol>

><li> Use an analogy to explain Built-In packages. Give examples.
Built-In packages in Java can be thought of as pre-built toolboxes that contain a variety of useful tools and resources that programmers can use to create their programs more efficiently. Just like how a carpenter has a toolbox filled with different tools for different tasks, a Java programmer has access to a variety of built-in packages with different functions.

For example, the "java.util" package contains a set of utility classes that provide functionality such as data structures (e.g., ArrayList, HashMap), date and time manipulation (e.g., Calendar, Date), and input/output (e.g., Scanner, Random). This package can be thought of as a toolbox that a programmer can use to handle common tasks related to data manipulation and input/output.

Similarly, the "java.io" package contains classes that provide functionality related to input and output streams, file handling, and serialization. This package can be thought of as a toolbox that a programmer can use to handle tasks related to reading and writing data to and from files or other sources.

Overall, built-in packages in Java are like toolboxes that provide pre-built tools and resources for programmers to use, allowing them to write code more efficiently and effectively.

</li>


><li> Explain the steps for creating a new package in IntelliJ.
To create a new Java package in IntelliJ, follow these steps:

* Open your IntelliJ IDEA and create a new Java project. If you already have a project open, you can skip this step.

* Right-click on the project folder in the Project tool window and select "New" > "Package". Alternatively, you can go to "File" > "New" > "Package".

* In the "New Package" dialog box, enter the name of the new package. The name should be in lowercase and should be a valid Java identifier. For example, if you want to create a package for your project's GUI classes, you might name it "gui".

* Choose the location where you want to create the new package. By default, IntelliJ will suggest a location within your project directory.

* Click "OK" to create the new package.

* Once the package is created, you can start adding classes to it. Right-click on the package name in the Project tool window and select "New" > "Java Class". Enter a name for the new class and click "OK".

* IntelliJ will create a new Java class file within the package. You can start adding code to the class and use it in your project.

That's it! You've successfully created a new Java package in IntelliJ.

</li>

><li> Which loop types use a loop counter?
In Java, two loop types use a loop counter - the for loop and the while loop.
In a for loop, a loop counter is declared as part of the loop syntax. The counter is initialized to a starting value, and the loop continues until the counter reaches a specified end value. The counter is incremented or decremented at the end of each iteration of the loop.
In a while loop, a loop counter is typically declared outside the loop, before the loop begins. The counter is used as the condition for the loop, and it is updated within the loop to control the number of iterations.
</li>


></li> Explain the difference between While and Do-While loops.
In Java, both while and do-while loops are used to execute a block of code repeatedly until a certain condition is met. The main difference between them is when the condition is checked.

The while loop first checks the condition before executing the block of code. If the condition is true, the block of code is executed, and the loop continues. If the condition is false, the loop is terminated. The do-while loop, on the other hand, first executes the block of code, and then checks the condition. If the condition is true, the loop continues, and if it's false, the loop is terminated. 

</li>

  ><li> Describe 3 built-in methods for Arrays.
  
  In Java, the Arrays class provides several built-in methods for working with arrays. Here are three commonly used methods:

>* sort(): This method is used to sort the elements of an array in ascending order. It can be used with any primitive or object type array. The syntax is as follows:

```java
    Arrays.sort(arrayName);
```

>For example, to sort an integer array called myArray, you would use the following code:

```java
int[] myArray = {3, 1, 4, 1, 5, 9, 2, 6, 5};
Arrays.sort(myArray);
```

>* binarySearch(): This method is used to search for a specified element in a sorted array. It returns the index of the element if it is found, or a negative value if it is not found. The syntax is as follows:

```java
Arrays.binarySearch(arrayName, element);
```
>For example, to search for the integer value 4 in the previously sorted myArray, you would use the following code:

```java
int index = Arrays.binarySearch(myArray, 4);
```

>If the element is found, index will be set to the index of the element in the array (in this case, index would be 5). 

>* toString(): This method is used to convert an array to a string. It returns a string representation of the contents of the array. The syntax is as follows:

```java 
Arrays.toString(arrayName);

```
>For example, to convert the myArray to a string, you would use the following code:

```java 
String arrayString = Arrays.toString(myArray);
```
>This would set arrayString to the string "[1, 1, 2, 3, 4, 5, 5, 6, 9]" (assuming myArray was previously sorted).

</li>

><li> How is the size of an array determined in Java?
In Java, the size of an array is determined at the time of its creation, and it cannot be changed later. The size of the array is specified in the declaration of the array, using the square brackets notation.
For example, to create an array of 10 integers, you would write:

```java
int[] myArray = new int[10];
```

In this example, the size of the array is specified as 10, which means that the array can hold 10 integers. To access the elements of the array, you would use the index notation, starting at 0 and ending at the size of the array minus 1. For example:

```java
myArray[0] = 42;
myArray[1] = 23;
int x = myArray[0] + myArray[1];
```

In this example, the first element of the array is set to 42, the second element is set to 23, and the third element is the sum of the first two elements, which is 65.

</li>

</ol>

[HOME](../README.md)