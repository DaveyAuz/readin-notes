# Reading-Notes Class 5

<ol>

><li>What is the single responsibility principle and how does it apply to components?

The Single Responsibility Principle (SRP) is a software design principle that states that a class or component should have only one reason to change. In other words, a component should have a single responsibility or job to perform, and it should do it well.

In practical terms, this means that each component in a software system should have a clear and specific purpose, and should not be responsible for doing too many things at once. When a component has too many responsibilities, it can become harder to understand, maintain, and modify, which can lead to bugs and other issues.

For example, let's consider a web application that allows users to create and manage tasks. One component in the application might be responsible for managing the user interface, while another component might be responsible for managing the database. If the user interface component also had to manage the database, it would violate the SRP, since it would have multiple responsibilities.

Applying the SRP to components involves identifying the specific responsibilities of each component in a software system and ensuring that each component is responsible for only one thing. This can help to make the system more modular, easier to understand, and more maintainable over time.

</li>

><li>What does it mean to build a ‘static’ version of your application?

When you build a "static" version of a React application, you are essentially creating a bundle of optimized HTML, CSS, and JavaScript files that can be served directly to users without the need for dynamic server-side processing.

To build a static version of a React application, you typically use a tool such as React's built-in create-react-app or a third-party tool like Gatsby. These tools generate a collection of optimized files that represent the entire application, including all of the necessary HTML, CSS, and JavaScript.

Once the static files are generated, they can be uploaded to a static file hosting service or a Content Delivery Network (CDN) for fast and reliable delivery to users. This approach has several benefits, including faster load times, improved performance, and better scalability, as static files can be served from multiple locations around the world to minimize latency.

However, building a static version of a React application also has some limitations. For example, since the application is pre-built and cannot execute any server-side logic, it cannot fetch or update data in real-time without the need for additional services or frameworks. Additionally, certain dynamic features, such as user authentication or server-side rendering, may not be possible in a static version of the application.

</li>

><li>Once you have a static application, what do you need to add?

If you already have a static application, the next step would be to add dynamic functionality to make it more interactive and engaging for users. Here are a few things you can consider adding:

* Backend functionality: Add server-side scripting and database integration to create dynamic functionality, such as user authentication, data storage and retrieval, and content management.

*	Client-side scripting: Use client-side scripting languages like JavaScript to add dynamic functionality to the user interface, such as real-time updates, interactive forms, and animations.

*	APIs: Integrate third-party APIs to enable your application to communicate with other services and fetch data from external sources.

*	Content Management System (CMS): Add a CMS to enable users to create, edit, and publish content on the application without requiring technical skills.

*	Responsive design: Make sure your application is responsive and can adapt to different screen sizes, ensuring a consistent user experience across different devices.
*	Accessibility: Ensure your application is accessible to users with disabilities by adding features such as keyboard navigation, screen reader compatibility, and alternative text for images.

By adding these dynamic features, you can enhance the functionality and user experience of your static application.

</li>

><li>What are the three questions you can ask to determine if something is state?

In computer science, "state" refers to the current condition or information held by a system or component at a given point in time. Here are three questions you can ask to determine if something is state:

*	Does it change over time? If the answer is yes, then it's likely state. For example, if you have a variable that stores a user's name and that name can change, then the variable is holding state.

*	Is it needed to resume a process? If the answer is yes, then it's likely state. For example, if you have an e-commerce application and you need to save the items in a user's shopping cart, that information is considered state because it's needed to resume the shopping process when the user returns to the application.

*	Does it affect behavior or output? If the answer is yes, then it's likely state. For example, if you have a button on a webpage that changes color when clicked, the color of the button is considered state because it affects the visual output of the page.

By asking these questions, you can determine whether something is state or not. Understanding state is important for programming and software development because it can affect how data is stored, processed, and managed in a system.

</li> 

><li> How can you identify where state needs to live?
In software development, it's important to identify where state needs to live in order to manage it effectively. Here are some steps you can follow to identify where state needs to live:

* Identify the components: Identify the different components in your application and the relationships between them. This will help you understand the flow of data and where state might be needed.

* Determine the responsibilities: For each component, determine what responsibilities it has and what data it needs to manage. This will help you identify which components need to hold state.

* Analyze the data flow: Analyze the flow of data between components and determine which components need to share state. For example, if one component needs to access data from another component, they may need to share state.

* Consider the scope: Consider the scope of the state and where it needs to be accessed. For example, if the state needs to be accessed by multiple components, it may need to be stored in a higher-level component such as the application state.

* Prioritize simplicity: Prioritize simplicity and avoid over-complicating the state management. Keep in mind that too many components holding state can lead to complex data flows and make the application difficult to maintain.

By following these steps, you can identify where state needs to live and manage it effectively in your application. It's important to keep in mind that the best approach may vary depending on the specific requirements of your application and the programming language or framework you are using.



></li>What is a “higher-order function”?

A higher-order function is a function that takes one or more functions as arguments, or returns a function as its result. In other words, a higher-order function is a function that operates on other functions, either by accepting them as arguments or by returning them as results.

Higher-order functions are an important concept in functional programming, and they allow for more abstract and reusable code. For example, a higher-order function could take a function that performs a specific calculation, and use it to perform that calculation on a range of different inputs.

Some common examples of higher-order functions include map, filter, and reduce in JavaScript, which take a function as an argument and apply it to an array of values. Another example is the compose function, which takes two or more functions and returns a new function that applies them in sequence.

</li>

><li>Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?
The greaterThan function, as defined in the reading, takes a single argument n and returns a new function that tests whether a given number is greater than n.

Line 2 of the greaterThan function defines a new function using a function expression. This new function, which is returned by the greaterThan function, takes a single argument m and tests whether m is greater than n.

In other words, line 2 creates a closure, where the inner function has access to the n variable defined in the outer function. This means that when the returned function is later called, it remembers the value of n from when it was originally created.

So, in summary, line 2 of the greaterThan function is creating a new function that has access to the n variable in the outer scope and can use it to compare with the argument passed to the function.
</li>

><li>Explain how either map or reduce operates, with regards to higher-order functions.

Both map and reduce are higher-order functions in JavaScript that operate on arrays and take a function as an argument.

map is used to transform an array by applying a function to each of its elements and returning a new array with the transformed values. The function that is passed as an argument to map is applied to each element of the array, and the transformed values are collected into a new array. The original array is not modified by the map function. 'Reduce' is used to combine the elements of an array into a single value by applying a function to each element of the array and accumulating the results. The function that is passed as an argument to reduce takes two arguments: an accumulator value and the current value of the array. The function returns a new accumulator value that is used in the next iteration of the reduce function. The final value of the accumulator is returned as the result of the reduce function.

</li>

</ol?>
[HOME](../README.md)