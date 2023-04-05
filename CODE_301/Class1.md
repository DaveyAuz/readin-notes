# Reading-Notes Class 1

<ol>
> <li> What Is a "Component?"
 
 Component-based architecture focuses on the decomposition of the design into individual functional or logical components that represent well-defined communication interfaces containing methods, events, and properties. It provides a higher level of abstraction and divides the problem into sub-problems, each associated with component partitions.
</li>

    ><li> What are the characteristics of a component?
    
    * Reusability − Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a specific task.

    * Replaceable − Components may be freely substituted with other similar components.

    * Not context specific − Components are designed to operate in different environments and contexts.

    * Extensible − A component can be extended from existing components to provide new behavior.

    * Encapsulated − A A component depicts the interfaces, which allow the caller to use its functionality, and do not expose details of the internal processes or any internal variables or state.

    * Independent − Components are designed to have minimal dependencies on other components.
</li>

><li> What are the advantages of using component-based architecture?
    Component-based architecture (CBA) is a software engineering approach that emphasizes the creation of complex systems by breaking them down into smaller, modular, and reusable components. Some advantages of using CBA include:

    * Reusability: Components can be easily reused across multiple applications or systems, saving time and effort in development.

    * Scalability: CBA allows for easy scaling of systems, as new components can be added or removed as needed.

    * Maintenance: CBA makes it easier to maintain complex systems, as each component can be updated or replaced independently of the others.

    * Faster development: CBA speeds up development by allowing developers to focus on developing individual components without worrying about the larger system.

    * Flexibility: CBA provides greater flexibility in software development, as components can be easily swapped out or modified as needed.

    * Lower costs: Reusing existing components and reducing development time can lead to lower development costs.

    * Improved quality: CBA allows for greater consistency and quality control, as components are tested and verified independently of the larger system.

Overall, CBA promotes modular design and development, which can lead to more efficient and effective software development.
</li>


><li> What is “props” short for?
    In React, "props" is short for "properties". Props are a mechanism for passing data from a parent component to a child component in a React application.
</li>


><li> How are props used in React?
    Props are passed as an object of key-value pairs and are read-only, meaning that they cannot be modified by the child component. The child component can access the props passed down from the parent component and use them to render its output.
    Using props allows for a more modular and reusable component-based architecture in React, as components can be composed and reused with different props to create different output. Props can also be used to customize the behavior of a component, allowing for greater flexibility in the application.
</li>


><li> What is the flow of props?
    In React, props flow in a unidirectional manner, from parent components to child components.

Here is the typical flow of props in a React application:

    * The parent component defines and sets the props data, usually as an object with key-value pairs.

    * The parent component passes the props down to the child component(s) through its JSX markup, using the props as attributes.

    * The child component(s) receive the props as a read-only object and use them to render their output.

    * If the parent component updates the props data, it will trigger a re-render of the parent component and all its child components that use the updated props.

Note that while props are passed from parent to child, child components cannot directly modify or pass props back up to the parent component. Instead, they can trigger events that the parent component can listen for, and the parent component can modify the props data and pass it back down to the child component(s). This unidirectional flow of data ensures a clear and predictable data flow in a React application.
</li>
</ul>

[HOME](../README.md)
