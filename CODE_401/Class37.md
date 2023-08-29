# Reading Notes Class #37

<ol>

><li> What is Amazon S3?

Amazon Simple Storage Service (Amazon S3) is a storage service provided by Amazon Web Services (AWS) that allows you to store and retrieve data, such as files and objects, in a secure and scalable manner. It offers features like high scalability, data availability, security, and performance. You can use Amazon S3 to store various types of data, such as data lakes, websites, mobile app content, backup and restore data, archive data, and more. It provides different storage classes to suit different use cases, allowing you to manage costs effectively based on the access patterns of your data. Amazon S3 also offers features for managing data access, security, and monitoring, making it a versatile solution for storing and managing your data in the cloud.

</li>


><li> List at least 3 features that it offers to its users.

Certainly, here are three features that Amazon S3 offers to its users:

1. **Storage Classes:** Amazon S3 provides different storage classes to match the access patterns and cost requirements of your data. These include options like S3 Standard for frequently accessed data, S3 Intelligent-Tiering for data with changing access patterns, and S3 Glacier for archiving data at lower costs.

2. **Data Management:** Amazon S3 offers features such as lifecycle policies, object locking, and replication. With lifecycle policies, you can automatically transition objects between storage classes or expire them after a certain period. Object locking helps prevent data from being deleted or modified for regulatory compliance. Replication allows you to replicate objects across different AWS regions for redundancy and disaster recovery.

3. **Access Control and Security:** Amazon S3 provides robust access control mechanisms. You can use bucket policies, AWS Identity and Access Management (IAM) policies, and access control lists (ACLs) to define who can access your data and what they can do with it. It also offers features like Block Public Access to prevent public access to your buckets and objects, and S3 Object Ownership to manage object ownership and access control at scale.

These features, among others, make Amazon S3 a versatile and reliable solution for storing, managing, and securing your data in the cloud.

</li>

><li> What is an object key?

An object key, often referred to as a key name, is a unique identifier assigned to each object stored within an Amazon S3 bucket. It functions like a file name in a traditional file system, allowing you to locate and retrieve specific objects within a bucket. The combination of the bucket name, object key, and optionally a version ID (if versioning is enabled) provides a precise way to address and access individual objects stored in Amazon S3.

For example, in the URL `https://my-bucket.s3.amazonaws.com/images/pic.jpg`, "images/pic.jpg" is the object key. The object key helps organize and categorize objects within a bucket and enables you to easily retrieve or manipulate the desired objects based on their unique identifiers.

</li>

><li> Which dependencies are needed to install Amplify AWS S3 to your android application?

To install Amplify AWS S3 to your Android application, you need to add the following dependencies to your app's `build.gradle` file:

```gradle
dependencies {
    implementation 'com.amplifyframework:aws-storage-s3:2.12.0'
    implementation 'com.amplifyframework:aws-auth-cognito:2.12.0'
}
```

These dependencies are required to use Amplify AWS S3 functionality in your Android app. The `aws-storage-s3` dependency provides the necessary classes and methods to interact with Amazon S3 storage, while the `aws-auth-cognito` dependency provides authentication support using Amazon Cognito for accessing S3 resources securely.

After adding these dependencies, don't forget to sync your project to ensure that the libraries are downloaded and integrated into your Android application.

</li>


><li> What is needed in order to upload data to your bucket?

To upload data to your Amazon S3 bucket using the Amplify Storage category, you need to follow these steps:

1. **Initialize Amplify:** You need to initialize the Amplify Storage category by adding the necessary plugins and configuring Amplify. This is typically done in your application's `onCreate()` method.

```java
import com.amplifyframework.auth.cognito.AWSCognitoAuthPlugin;
import com.amplifyframework.core.Amplify;
import com.amplifyframework.storage.s3.AWSS3StoragePlugin;

public class MyAmplifyApp extends Application {
    @Override
    public void onCreate() {
        super.onCreate();

        try {
            Amplify.addPlugin(new AWSCognitoAuthPlugin());
            Amplify.addPlugin(new AWSS3StoragePlugin());
            Amplify.configure(getApplicationContext());
        } catch (AmplifyException error) {
            Log.e("MyAmplifyApp", "Could not initialize Amplify", error);
        }
    }
}
```

2. **Upload the Data:** Once Amplify is initialized, you can use the `Amplify.Storage.uploadFile()` method to upload your data to the S3 bucket. Provide a key (path) for the object, the data to be uploaded (in the form of a file), and callbacks to handle the upload result.

```java
import com.amplifyframework.core.Amplify;

private void uploadFile() {
    File exampleFile = new File(getApplicationContext().getFilesDir(), "ExampleKey");

    try {
        BufferedWriter writer = new BufferedWriter(new FileWriter(exampleFile));
        writer.append("Example file contents");
        writer.close();
    } catch (Exception exception) {
        Log.e("MyAmplifyApp", "Upload failed", exception);
    }

    Amplify.Storage.uploadFile(
        "ExampleKey",
        exampleFile,
        result -> Log.i("MyAmplifyApp", "Successfully uploaded: " + result.getKey()),
        storageFailure -> Log.e("MyAmplifyApp", "Upload failed", storageFailure)
    );
}
```

In this code snippet, `ExampleKey` is the key (path) of the object you want to upload, and `exampleFile` is the file containing the data you want to upload. The `uploadFile()` method provides both success and failure callbacks to handle the upload result.

After successfully executing this code, your data will be uploaded to the specified path in your S3 bucket.

Remember that you also need to handle user authentication before using the Amplify Storage category, as it requires authenticated access to Amazon S3 resources.

</li>


><li> What method(s) initialize(s) the Amplify Auth and Storage categories?

To initialize the Amplify Auth and Storage categories, you need to call the `Amplify.addPlugin()` method for each category and then call the `Amplify.configure()` method to complete the initialization. In your Android application's code, you would typically do this in the `onCreate()` method of your Application class or in the entry point of your app.

Here's how you can initialize the Amplify Auth and Storage categories:

```java
import com.amplifyframework.auth.cognito.AWSCognitoAuthPlugin;
import com.amplifyframework.core.Amplify;
import com.amplifyframework.storage.s3.AWSS3StoragePlugin;

public class MyAmplifyApp extends Application {
    @Override
    public void onCreate() {
        super.onCreate();

        try {
            // Add these lines to add the AWSCognitoAuthPlugin and AWSS3StoragePlugin plugins
            Amplify.addPlugin(new AWSCognitoAuthPlugin());
            Amplify.addPlugin(new AWSS3StoragePlugin());
            Amplify.configure(getApplicationContext());
        } catch (AmplifyException error) {
            Log.e("MyAmplifyApp", "Could not initialize Amplify", error);
        }
    }
}
```

In this code snippet:
- `Amplify.addPlugin(new AWSCognitoAuthPlugin());` adds the Amplify Auth plugin that provides authentication using Amazon Cognito.
- `Amplify.addPlugin(new AWSS3StoragePlugin());` adds the Amplify Storage plugin that provides storage management using Amazon S3.
- `Amplify.configure(getApplicationContext());` completes the configuration of the plugins and initializes Amplify.

By adding these lines in the `onCreate()` method of your `Application` class, you ensure that the Amplify Auth and Storage categories are properly initialized and ready to be used throughout your app.

</li>

<ol>
[HOME](../README.md)