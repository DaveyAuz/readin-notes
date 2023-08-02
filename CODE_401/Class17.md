# Reading Notes Class #17
<ol>

><li> In non-technical terms, describe what using OAuth can provide for your application.

In non-technical terms, using OAuth can provide your application with a secure and convenient way to access and use resources or data from other websites or services without needing to ask users for their passwords. It's like having a trusted middleman that helps your application request permission from users to access their information on other platforms.

Imagine you have an app that wants to let users sign in using their Google or Facebook accounts. Instead of asking users to share their passwords directly with your app, which can be risky and make users uncomfortable, you can use OAuth. OAuth allows your app to redirect users to Google or Facebook, where they will be asked to log in and give permission for your app to access certain information. Once permission is granted, Google or Facebook sends back a special code to your app, which can be used to securely access the approved information.

In summary, OAuth provides a secure and user-friendly way for your app to interact with other services and use data from those services, without storing or handling user passwords directly. It ensures that users have control over what information they share with your app, while also allowing your app to integrate seamlessly with popular platforms and services.

</li>


><li> Which authentication providers are covered in the tutorial?

In the tutorial "Securing a Web Application," the authentication providers covered are:

1. **Google**: The tutorial demonstrates how to set up OAuth2 authentication with Google as the identity provider. Users can sign in to the web application using their Google accounts.

2. **GitHub**: The tutorial also covers setting up OAuth2 authentication with GitHub as the identity provider. Users can sign in to the web application using their GitHub accounts.

The tutorial walks you through the process of integrating OAuth2 authentication with these two popular providers in a Spring Boot web application. It shows how to configure the application to handle authentication requests, how to redirect users to the respective authentication providers for login, and how to process the authentication response to gain access to user information.

</li>

<ol>

[HOME](../README.md)