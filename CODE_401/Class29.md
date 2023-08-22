# Reading Notes Class #29

<ol>

><li> What database engine is Room wrapped around? Do you think this is a good choice? Why or why not?

Room is an Android library provided by the Android Jetpack suite for working with SQLite, which is a relational database management system. Room is essentially a layer of abstraction built on top of SQLite, which makes it easier for developers to work with databases in Android applications.

SQLite is a self-contained, serverless, and zero-configuration database engine that is embedded within the application itself. It's designed to be lightweight, fast, and reliable, making it a popular choice for mobile applications, including Android.

Using SQLite as the underlying database engine for Room is a good choice for several reasons:

1. **Performance:** SQLite is highly optimized and designed to provide efficient and fast database operations, which is crucial for mobile applications where resources like CPU and memory are limited.

2. **Reliability:** SQLite databases are ACID-compliant, ensuring data integrity and reliability. This is essential for applications that require consistent and accurate data storage.

3. **Lightweight:** SQLite databases are compact and require minimal system resources. This is important for mobile devices, where storage space can be limited.

4. **Cross-Platform:** SQLite is a widely used database engine that is available on various platforms, making it a portable choice for applications that might need to run on different operating systems.

5. **Integration:** Since Android already comes with built-in support for SQLite, using it as the underlying database engine for Room simplifies integration and ensures compatibility.

6. **Maturity:** SQLite has been around for a long time and has proven to be a stable and reliable database engine for a wide range of applications.

7. **Developer Familiarity:** Many developers are already familiar with SQL, the query language used with SQLite, which makes it easier to work with Room and create complex queries.

While SQLite is a good choice for many Android applications, there are cases where other database engines might be more suitable, such as when dealing with massive amounts of data, complex data relationships, or the need for more advanced features like full-text search or geospatial queries. In such cases, developers might consider using other databases like Realm or Firebase Firestore, which offer different trade-offs in terms of features and performance.

Overall, the choice of using SQLite as the underlying database engine for Room is generally a solid and appropriate choice for most Android applications due to its performance, reliability, and integration with the Android platform.

</li>

><li> Do Rooms have any similarities to JPA?

Yes, Room and Java Persistence API (JPA) share some similarities, as they both provide object-relational mapping (ORM) frameworks for working with databases in Android (Room) and Java (JPA) applications. Here are some of the key similarities between Room and JPA:

1. **Object-Relational Mapping (ORM)**: Both Room and JPA aim to simplify the process of mapping Java/Kotlin objects to database tables and vice versa. They allow developers to work with objects in their code while abstracting the complexities of database interactions.

2. **Entity Annotations**: Both frameworks use annotations to mark Java/Kotlin classes as entities that represent database tables. In JPA, the `@Entity` annotation is used to mark classes as entities, and in Room, the `@Entity` annotation is used for the same purpose.

3. **Relationship Annotations**: Both Room and JPA provide annotations to define relationships between entities, such as `@ManyToOne`, `@OneToMany`, `@OneToOne`, and more. These annotations help establish the relationships between different entity classes and the corresponding database tables.

4. **Primary Key Annotations**: Both frameworks allow developers to specify primary key fields using annotations. In JPA, the `@Id` annotation is used to mark primary key fields, and in Room, the `@PrimaryKey` annotation serves the same purpose.

5. **Query Annotations**: Both Room and JPA provide annotations to define custom database queries directly in the entity classes or in dedicated DAO (Data Access Object) interfaces. For example, Room uses the `@Query` annotation, and JPA uses the `@NamedQuery` and `@NamedNativeQuery` annotations.

6. **Generated SQL**: Both frameworks generate SQL queries based on annotations and provided information. Developers can define queries using high-level constructs, and the frameworks handle the translation of these queries into actual SQL statements.

7. **Data Access Objects (DAOs)**: Both Room and JPA emphasize the use of DAOs to abstract database operations. DAOs provide methods for performing CRUD (Create, Read, Update, Delete) operations on entities without directly writing SQL statements.

8. **Relationship Handling**: Both frameworks support various types of relationships between entities, such as one-to-one, one-to-many, and many-to-many, using annotations to specify how entities are related.

However, there are also some differences between Room and JPA:

1. **Platform**: Room is specifically designed for Android applications, while JPA is a standard ORM framework for Java applications. JPA can be used in various Java environments, including Java EE, Java SE, and Java ME.

2. **Annotations**: While there are similarities in the types of annotations used, the actual annotation names and packages differ between Room and JPA due to their different platforms and implementations.

3. **Database Management**: Room provides additional features tailored for mobile devices and local data management, such as handling SQLite databases efficiently and supporting asynchronous queries with LiveData or RxJava.

4. **Integration**: JPA integrates with various Java EE technologies and application servers, while Room is tightly integrated with the Android ecosystem, offering features like LiveData for reactive programming.

In summary, while Room and JPA share some common concepts and annotations due to their nature as ORM frameworks, they are designed for different platforms and have specific features that cater to the needs of Android development and Java applications, respectively.

</li>

><li> Describe a DAO in your own words

A DAO (Data Access Object) is an essential component when using the Room persistence library to manage your app's data storage. It acts as an intermediary layer between your app's code and the database, providing an abstract way to perform database operations without directly dealing with SQL queries. DAOs define methods that allow you to interact with the database by performing CRUD (Create, Read, Update, Delete) operations and executing custom queries.

In Room, you define DAOs as either interfaces or abstract classes and annotate them with `@Dao`. DAO methods are then annotated with specific annotations that indicate the type of database operation they perform, such as `@Insert`, `@Update`, `@Delete`, or `@Query`. Here's an overview of the key points related to DAOs:

**1. Defining Methods:**

- **Insert Methods:** Annotated with `@Insert`, these methods allow you to add data to the database.
- **Update Methods:** Annotated with `@Update`, these methods let you modify existing data in the database.
- **Delete Methods:** Annotated with `@Delete`, these methods enable you to remove data from the database.
- **Query Methods:** Annotated with `@Query`, these methods allow you to execute custom SQL queries and retrieve data from the database.

**2. Convenience Annotations:**

- Room provides convenience annotations (`@Insert`, `@Update`, `@Delete`) that simplify common database operations. You only need to define the method signature, and Room generates the necessary SQL code.

**3. Query Methods:**

- `@Query` annotation lets you define and execute complex SQL queries. Room validates these queries at compile time, reducing the chances of runtime errors.

**4. Parameters:**

- DAO methods can accept parameters, which can be used in SQL queries. Parameters can be primitive types, objects, or collections.

**5. Return Types:**

- Depending on the type of operation, DAO methods can return various types, such as `void`, `long`, `int`, `List`, custom data classes, or even special types like `Cursor` for direct cursor access.

**6. Separation of Concerns:**

- DAOs help maintain a separation of concerns in your app's architecture. They encapsulate database operations, making it easier to manage and test your data storage logic independently from other components.

**7. Mocking and Testing:**

- DAOs facilitate unit testing by providing a clear and abstract interface to interact with the database. You can mock DAOs during testing to simulate database interactions.

Overall, DAOs in Room offer a clean and organized way to manage database interactions in your app. They abstract away the low-level details of database management, allowing you to focus on your app's logic and functionality.

</li>

<ol>

[HOME](../README.md)
