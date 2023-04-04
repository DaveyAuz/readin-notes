# Reading-Notes Class 2
1) What types of things can you pass in the props?
Props can be used to pass various types of data between components, such as:

    * Strings: simple text data, such as names, titles, or descriptions
    * Numbers: numeric data, such as prices, quantities, or ages
    * Booleans: true/false values, such as "is_active" or "is_checked"
    * Objects: complex data structures that can contain multiple values, such as user profiles or product listings
    * Functions: blocks of code that can be executed by the component receiving the props, such as event handlers or utility functions
    * Arrays: collections of data, such as lists of items or sets of options
    * The specific types of props you can pass will depend on the programming language or framework you are using, as well as the specific needs of your application.

2) What is the big difference between props and state?
In programming, both "props" and "state" are used to manage data in a software system, but they serve different purposes and have different characteristics.

Props are short for properties, and they are used to pass data from one component to another in a software system. Props are passed down from a parent component to a child component and are read-only, meaning that they cannot be modified by the child component that receives them. Props are typically used to provide data that a child component needs to render or to trigger events that a parent component needs to respond to.

On the other hand, state is used to manage data within a component itself. State is mutable, meaning that it can be modified by the component that owns it. When the state of a component changes, the component will re-render to reflect the new state. State is typically used to keep track of information that is specific to a component and that may change over time, such as the current user input, the state of a toggle switch, or the items in a shopping cart.

So, the big difference between props and state is that props are used to pass data down from a parent component to a child component, while state is used to manage data within a component itself. Props are read-only and cannot be modified by the child component, while state is mutable and can be updated by the component that owns it.

3) When do we re-render our application?
In programming, a re-render happens when a component in a software system updates its output to reflect changes in its data or in the data of its child components. Re-rendering is a process that involves updating the component's virtual representation and then rendering the updated output on the screen.

    * Components in a software system can be re-rendered in response to various events, such as:

    * Changes in the component's state: If the data stored in the component's state changes, the component will re-render to reflect the new state.

    * Changes in the component's props: If the data passed to the component through its props changes, the component will re-render to reflect the new props.

    * Changes in the data of child components: If the data of a child component changes, the parent component will re-render to reflect the changes in its child components.

    * Changes in the application's global state: If the application's global state changes, all components that depend on that state will re-render to reflect the new state.

Re-rendering can be an expensive operation in terms of performance, so it's important to avoid unnecessary re-renders whenever possible. To optimize performance, developers can use techniques such as memoization, shouldComponentUpdate method, PureComponent, and React.memo to reduce the number of re-renders and improve the overall performance of the application.

4) What are some examples of things that we could store in state?
In programming, the state is used to manage data within a component in a software system. The specific data that is stored in the state of a component depends on the needs of the component and the requirements of the application. Here are some examples of things that could be stored in state:

* User input: If a component receives user input, such as text entered into a form field or a selection made from a dropdown menu, that input can be stored in the component's state.

* Component state: If a component has internal state that affects its behavior, such as a toggle switch that can be turned on and off, that state can be stored in the component's state.

* Data fetched from a server: If a component needs to fetch data from a server, such as a list of products or a user's profile information, that data can be stored in the component's state.

* Error messages: If a component needs to display error messages to the user, such as when a form is submitted with invalid data, those messages can be stored in the component's state.

* Authentication status: If a component needs to know whether the user is logged in or not, that information can be stored in the component's state.

* Progress status: If a component needs to display progress information to the user, such as the percentage of a file upload that has been completed, that information can be stored in the component's state.

These are just a few examples of the types of data that can be stored in the state of a component. The specific data that is stored in the state will depend on the needs of the component and the requirements of the application.

[HOME](./README.md)