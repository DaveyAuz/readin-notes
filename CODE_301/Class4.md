# Reading-Notes Class 4

<ol>

><li> What is a ‘Controlled Component’?

In the context of React, a "controlled component" refers to an input form element (like a text input or a checkbox) whose value is controlled by React state. This means that the value of the input is not determined by the user's typing or clicking, but rather by the state of the React component that renders the input.

In a controlled component, the value of the input is passed in as a prop, and the onChange event is used to update the value of the component state, which in turn updates the value of the input. This allows the React component to have complete control over the state of the input, which can be useful for validating user input, providing default values, or performing other complex behaviors.

Controlled components are often used in forms where the input values need to be validated before submission, or where the values of multiple inputs need to be coordinated. They are also helpful in making sure that the state of the input is always in sync with the state of the React component, which can simplify the code and prevent bugs.

</li>

><li>Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why?

It depends on the specific use case and requirements of the form.

If the form is simple and does not require complex validation or coordination between multiple inputs, updating the state with the user's responses as they enter them might be a good approach. This allows the user to see their responses immediately and can provide a better user experience.

On the other hand, if the form requires complex validation, such as verifying that certain fields are filled out correctly or checking that the responses are consistent across multiple inputs, it might be better to wait until the user submits the form before updating the state. This allows the form to be validated as a whole, and any errors can be displayed to the user before submitting.

Another consideration is the impact of updating the state on performance. If the form is very large or complex, updating the state with every change could cause performance issues, especially on slower devices. In this case, it might be better to wait until the user submits the form before updating the state to reduce the frequency of state updates.

Ultimately, the decision of whether to update the state with user responses as they enter them or wait until the form is submitted depends on the specific requirements and constraints of the form, as well as considerations such as user experience and performance.

</li>

><li> How do we target what the user is entering if we have an event handler on an input field?
In a React component, you can use the onChange event handler to detect when the user enters or modifies text in an input field. When the onChange event is triggered, you can access the current value of the input field using the event.target.value property.

</li>

><li>Why would we use a ternary operator?
We use the ternary operator as a shorthand way to write a conditional expression in JavaScript. It's a way to write an if...else statement in a single line of code. The ternary operator takes three operands: a condition, a value to be returned if the condition is true, and a value to be returned if the condition is false. The ternary operator can be useful for writing concise and readable code, especially in cases where the condition is simple and the values to be returned are short. However, if the condition or the values to be returned are complex, it might be better to use an if...else statement instead for readability and maintainability reasons.

</li>

><li>Rewrite the following statement using a ternary statement:

> if(x===y){
> console.log(true);
> } else {
> console.log(false);
> }

><ul> Ternary operator:

> x === y ? console.log(true) : console.log(false);
</ul>
></li>

</ol>

[HOME](../README.md)
