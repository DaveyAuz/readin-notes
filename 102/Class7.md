# Reading-Notes Programming with JavaScript

A function is a subprogram designed to perform a particular task.
Functions are executed when they are called. This is known as invoking a function.
Values can be passed into functions and used within the function.
Functions always return a value. In JavaScript, if no return value is specified, the function will return undefined.
Functions are objects. 
Define a Function.
There are a few different ways to define a function in JavaScript:

A Function Declaration defines a named function. To create a function declaration you use the function keyword followed by the name of the function. When using function declarations, the function definition is hoisted, thus allowing the function to be used before it is defined.

Here is an example from my code function

function confirmLoud(){

 let ans = confirm("THIS IS ABOUT TO GET LOUD... DO YOU HAVE PROPER HEARING PROTECTION??!!");

 if (ans == true) {
 alert("Most Excellent!");

 }else{

 alert("Bogus!");  
    }

[HOME](../README.md)