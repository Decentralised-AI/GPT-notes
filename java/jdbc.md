# JDBC API

## Using database connectivity and interaction 

Database connectivity and interaction using the JDBC (Java Database Connectivity) API allows Java applications to connect to and interact with relational databases. JDBC provides a set of classes and interfaces that facilitate communication between Java applications and databases, enabling tasks such as executing SQL queries, retrieving and updating data, and managing database transactions.

To establish database connectivity and perform database operations using JDBC, you can follow these general steps:

1. **Load the JDBC driver**: Before establishing a connection to a database, you need to load the JDBC driver for the specific database you want to connect to. Each database vendor provides a JDBC driver that you need to include in your project's dependencies and load using the `Class.forName()` method.

```java
Class.forName("com.mysql.cj.jdbc.Driver");
```

2. **Establish a database connection**: Use the `DriverManager.getConnection()` method to establish a connection to the database. You need to provide the appropriate connection URL, username, and password for the database.

```java
String url = "jdbc:mysql://localhost:3306/mydatabase";
String username = "username";
String password = "password";
Connection connection = DriverManager.getConnection(url, username, password);
```

3. **Create a Statement or PreparedStatement**: Once the connection is established, you can create a `Statement` or `PreparedStatement` object to execute SQL statements against the database. `Statement` is used for general-purpose SQL statements, while `PreparedStatement` is used for parameterized queries.

```java
Statement statement = connection.createStatement();
PreparedStatement preparedStatement = connection.prepareStatement("SELECT * FROM mytable WHERE id = ?");
```

4. **Execute SQL queries or updates**: Use the `executeQuery()` method of the `Statement` or `PreparedStatement` object to execute SELECT queries and retrieve result sets. Use the `executeUpdate()` method to execute INSERT, UPDATE, DELETE, and other SQL statements that modify data.

```java
ResultSet resultSet = statement.executeQuery("SELECT * FROM mytable");
int rowsAffected = statement.executeUpdate("INSERT INTO mytable (col1, col2) VALUES (value1, value2)");
```

5. **Process the result set**: If you executed a SELECT query and obtained a result set, you can iterate over the result set to retrieve and process the returned data.

```java
while (resultSet.next()) {
    int id = resultSet.getInt("id");
    String name = resultSet.getString("name");
    // Process the retrieved data
}
```

6. **Close the resources**: After you have finished working with the database, make sure to close the database resources in the reverse order of their creation: result sets, statements, and the database connection.

```java
resultSet.close();
statement.close();
connection.close();
```

Remember to handle any potential exceptions that may occur during database connectivity and interaction, and wrap the JDBC operations within try-catch blocks or use the appropriate exception handling mechanisms.

By following these steps, you can connect to a database, execute SQL queries, retrieve and update data, and manage transactions using the JDBC API in Java.


### Example

Here's an example of data retrieval from a database using JDBC in Java, including exhaustive exception handling:

```java
import java.sql.*;

public class DataRetrievalExample {

    public static void main(String[] args) {
        Connection connection = null;
        Statement statement = null;
        ResultSet resultSet = null;

        try {
            // Load the JDBC driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Establish the database connection
            String url = "jdbc:mysql://localhost:3306/mydatabase";
            String username = "username";
            String password = "password";
            connection = DriverManager.getConnection(url, username, password);

            // Create a statement
            statement = connection.createStatement();

            // Execute the SQL query
            String query = "SELECT * FROM employees";
            resultSet = statement.executeQuery(query);

            // Process the result set
            while (resultSet.next()) {
                int id = resultSet.getInt("id");
                String name = resultSet.getString("name");
                double salary = resultSet.getDouble("salary");
                System.out.println("ID: " + id + ", Name: " + name + ", Salary: " + salary);
            }

        } catch (ClassNotFoundException e) {
            System.out.println("JDBC driver not found!");
            e.printStackTrace();
        } catch (SQLException e) {
            System.out.println("Database connection error!");
            e.printStackTrace();
        } finally {
            // Close the resources
            try {
                if (resultSet != null) {
                    resultSet.close();
                }
                if (statement != null) {
                    statement.close();
                }
                if (connection != null) {
                    connection.close();
                }
            } catch (SQLException e) {
                System.out.println("Error closing database resources!");
                e.printStackTrace();
            }
        }
    }
}
```

In this example, we first load the JDBC driver using `Class.forName()`, then establish a connection to the database using `DriverManager.getConnection()`. We create a `Statement` object to execute the SQL query and obtain a `ResultSet` with the returned data. We then iterate over the result set using `resultSet.next()` and retrieve the values of each column using the appropriate data types. Finally, we close the database resources in the `finally` block to ensure proper resource cleanup.

The example includes exhaustive exception handling to catch and handle any potential exceptions that may occur during database connectivity, query execution, and resource management. The exceptions are printed to the console for demonstration purposes, but in a production environment, you might want to handle them more gracefully, such as logging the errors or displaying appropriate error messages to the user.

Remember to replace the database URL, username, and password with the appropriate values for your database configuration.

By following this example, you can retrieve data from a database using JDBC in Java while handling potential exceptions that may arise during the process.

## Transactions

In Java, transactions are used to group a set of database operations into a single logical unit of work that should be executed atomically. Transactions ensure that either all the operations within the transaction are successfully committed to the database or none of them are, maintaining data consistency and integrity. If an error occurs or an exception is thrown during the transaction, it can be rolled back, undoing any changes made so far.

Here's how you can use transactions in Java:

1. **Establish a database connection**: Connect to the database using JDBC as described earlier using the `DriverManager.getConnection()` method.

```java
Connection connection = DriverManager.getConnection(url, username, password);
```

2. **Disable auto-commit mode**: By default, JDBC operates in auto-commit mode, where each SQL statement is treated as a separate transaction and is automatically committed to the database. To enable transactions, you need to disable auto-commit mode.

```java
connection.setAutoCommit(false);
```

3. **Perform database operations**: Execute your desired database operations within the transaction using `Statement` or `PreparedStatement` objects.

```java
Statement statement = connection.createStatement();
statement.executeUpdate("INSERT INTO employees (name, salary) VALUES ('John', 50000)");
statement.executeUpdate("UPDATE employees SET salary = 55000 WHERE id = 1");
```

4. **Commit the transaction**: If all the operations within the transaction have been successfully executed, commit the transaction to make the changes permanent in the database.

```java
connection.commit();
```

5. **Rollback the transaction**: If an error occurs during the transaction or if you decide to cancel the transaction, you can roll back the changes made so far, undoing them.

```java
connection.rollback();
```

6. **Close the database connection**: Once you have finished working with the database, close the connection as usual.

```java
connection.close();
```

It's important to note that not all databases support transactions, so you should ensure that your database system supports them before using transactions. Additionally, exceptions and error handling are crucial when working with transactions. If an exception occurs, you should catch it and roll back the transaction to maintain data integrity.

By using transactions, you can ensure that a set of related database operations are executed atomically and consistently, providing data integrity and recoverability in case of failures or errors.

### Example

Here's an example of using transactions in Java with JDBC, including exception handling:

```java
import java.sql.*;

public class TransactionExample {

    public static void main(String[] args) {
        Connection connection = null;
        Statement statement = null;

        try {
            // Load the JDBC driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Establish the database connection
            String url = "jdbc:mysql://localhost:3306/mydatabase";
            String username = "username";
            String password = "password";
            connection = DriverManager.getConnection(url, username, password);

            // Disable auto-commit mode to enable transactions
            connection.setAutoCommit(false);

            // Create a statement
            statement = connection.createStatement();

            // Perform database operations within the transaction
            statement.executeUpdate("INSERT INTO employees (name, salary) VALUES ('John', 50000)");
            statement.executeUpdate("UPDATE employees SET salary = 55000 WHERE id = 1");

            // Commit the transaction if all operations are successful
            connection.commit();

            System.out.println("Transaction committed successfully.");

        } catch (ClassNotFoundException e) {
            System.out.println("JDBC driver not found!");
            e.printStackTrace();
        } catch (SQLException e) {
            System.out.println("Database connection or transaction error!");
            e.printStackTrace();

            // Rollback the transaction if an exception occurs
            try {
                if (connection != null) {
                    connection.rollback();
                    System.out.println("Transaction rolled back.");
                }
            } catch (SQLException ex) {
                System.out.println("Error rolling back transaction!");
                ex.printStackTrace();
            }
        } finally {
            // Close the resources
            try {
                if (statement != null) {
                    statement.close();
                }
                if (connection != null) {
                    connection.close();
                }
            } catch (SQLException e) {
                System.out.println("Error closing database resources!");
                e.printStackTrace();
            }
        }
    }
}
```

In this example, we establish a database connection, disable auto-commit mode to enable transactions, and create a `Statement` object to execute the database operations within the transaction. We perform the desired database operations (an INSERT and an UPDATE) and commit the transaction if all operations are successful.

If an exception occurs during the transaction or the commit fails, we catch the `ClassNotFoundException` and `SQLException` exceptions and handle them appropriately. In the catch block, we roll back the transaction using `connection.rollback()` and print an error message.

Finally, we close the database resources in the `finally` block to ensure proper resource cleanup. The example demonstrates the use of exception handling to handle potential errors during database connectivity, transaction execution, and resource management.

Remember to replace the database URL, username, and password with the appropriate values for your database configuration.

By following this example, you can perform database operations within transactions using JDBC in Java, ensuring data integrity and providing appropriate exception handling.

## Statements and PreparedStatements

Statements and PreparedStatements are both used for executing SQL queries and updates in Java JDBC, but they have some differences in terms of their functionality and usage:

1. **Compilation**: Statements are compiled and executed directly by the database each time they are executed. PreparedStatements, on the other hand, are precompiled by the database and stored as prepared statements. This compilation step happens only once, regardless of how many times the PreparedStatement is executed. This makes PreparedStatements more efficient when executing the same SQL statement multiple times with different parameter values.

2. **SQL Injection Prevention**: PreparedStatements provide built-in protection against SQL injection attacks. With PreparedStatements, you can parameterize the SQL queries and set the parameter values separately, preventing malicious SQL code injection. Statements, on the other hand, require you to manually escape or sanitize the input values to avoid SQL injection vulnerabilities.

3. **Performance**: PreparedStatements can offer better performance compared to Statements, especially when executing the same SQL statement multiple times with different parameter values. The precompilation and caching of PreparedStatements can reduce the overhead of parsing and optimizing the SQL query each time it is executed.

4. **Flexibility**: Statements are suitable for executing static SQL queries that do not have any input parameters. PreparedStatements, on the other hand, are more flexible and can handle dynamic SQL queries with parameters. You can easily set parameter values in PreparedStatements using the `setXXX()` methods, where `XXX` represents the data type of the parameter.

5. **Batch Execution**: PreparedStatements support batch execution, where you can add multiple sets of parameter values and execute them as a batch. This can be useful when you need to perform bulk inserts or updates. Statements do not directly support batch execution.

In general, it is recommended to use PreparedStatements over Statements due to their advantages in terms of performance, security, and flexibility. They provide better protection against SQL injection attacks and offer potential performance improvements through query optimization and caching. However, there may be scenarios where Statements are still appropriate, such as for executing static SQL queries or in cases where the same SQL statement is executed only once.

Consider your specific requirements and choose the appropriate option accordingly.

## Example of PreparedStatements

Here's an example that demonstrates the usage of PreparedStatements in Java JDBC:

```java
import java.sql.*;

public class PreparedStatementExample {

    public static void main(String[] args) {
        Connection connection = null;
        PreparedStatement preparedStatement = null;

        try {
            // Load the JDBC driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Establish the database connection
            String url = "jdbc:mysql://localhost:3306/mydatabase";
            String username = "username";
            String password = "password";
            connection = DriverManager.getConnection(url, username, password);

            // Prepare the SQL statement with parameters
            String sql = "INSERT INTO employees (name, salary) VALUES (?, ?)";
            preparedStatement = connection.prepareStatement(sql);

            // Set the parameter values
            preparedStatement.setString(1, "John");
            preparedStatement.setDouble(2, 50000.0);

            // Execute the SQL statement
            int rowsAffected = preparedStatement.executeUpdate();

            if (rowsAffected > 0) {
                System.out.println("Record inserted successfully.");
            } else {
                System.out.println("Record insertion failed.");
            }

        } catch (ClassNotFoundException e) {
            System.out.println("JDBC driver not found!");
            e.printStackTrace();
        } catch (SQLException e) {
            System.out.println("Database connection or query execution error!");
            e.printStackTrace();
        } finally {
            // Close the resources
            try {
                if (preparedStatement != null) {
                    preparedStatement.close();
                }
                if (connection != null) {
                    connection.close();
                }
            } catch (SQLException e) {
                System.out.println("Error closing database resources!");
                e.printStackTrace();
            }
        }
    }
}
```

In this example, we establish a database connection, prepare an SQL statement with placeholders (`?`) for parameters, and create a `PreparedStatement` object using the `connection.prepareStatement()` method.

We set the parameter values using the appropriate setter methods (`setXXX()`) on the `PreparedStatement` object, where `XXX` represents the data type of the parameter. In this case, we set the name as a string (`setString()`) and the salary as a double (`setDouble()`).

Finally, we execute the SQL statement using `preparedStatement.executeUpdate()` to insert the record into the database. The method returns the number of rows affected by the statement. Based on the result, we print a success or failure message.

Remember to replace the database URL, username, and password with the appropriate values for your database configuration.

By using PreparedStatements, you can dynamically set parameter values and execute parameterized SQL statements, which helps prevent SQL injection attacks and provides better performance through statement caching and optimization.

## Connection pools

In Java, a connection pool is a mechanism that manages and maintains a pool of database connections, allowing multiple clients to efficiently share and reuse these connections. It helps optimize the performance and scalability of database operations in applications that require frequent database access.

Here's a brief explanation of how connection pools work in Java:

1. **Creating the Connection Pool**: At application startup, a connection pool is initialized by creating a fixed number of database connections based on the configuration settings. These connections are added to the pool.

2. **Acquiring a Connection**: When a client requests a database connection, it borrows a connection from the pool. The connection pool keeps track of available connections and assigns one to the client.

3. **Using the Connection**: The client can perform database operations using the borrowed connection. Once the client is done, it releases the connection back to the pool.

4. **Reusing Connections**: When a connection is released, it is not immediately closed. Instead, it is returned to the pool and marked as available for reuse. This allows subsequent client requests to reuse the existing connections rather than creating new ones.

5. **Managing Connection Lifecycle**: The connection pool is responsible for managing the lifecycle of connections, including opening and closing them. It ensures that connections are properly closed and released, even if the client forgets to do so explicitly.

6. **Connection Pool Monitoring**: Connection pools often provide monitoring and management features. This includes tracking the number of active and idle connections, setting connection timeout limits, and adjusting pool size dynamically based on the application's demand.

The advantages of using connection pools include:

- **Improved Performance**: Reusing existing connections eliminates the overhead of establishing a new connection for each database operation, resulting in improved performance and reduced latency.

- **Resource Management**: Connection pools manage the limited resources (connections) efficiently, preventing resource exhaustion and ensuring optimal utilization.

- **Scalability**: Connection pooling enables handling multiple concurrent requests by providing a shared pool of connections, allowing for better scalability of database operations.

Java provides several libraries and frameworks for implementing connection pools, such as Apache Commons DBCP, HikariCP, and Tomcat Connection Pool. These libraries typically provide configurable settings to control pool size, connection timeouts, and other parameters.

When using connection pools, it is important to configure and tune the pool size appropriately based on your application's needs and the database server's capacity. Too few connections may result in performance issues due to contention, while too many connections may consume excessive resources.

Overall, connection pools are a valuable tool for managing and optimizing database connections in Java applications, enabling efficient and scalable interaction with databases.

### HikariCP

HikariCP is a high-performance, lightweight connection pool library for Java applications. It is widely used and highly regarded for its excellent performance and scalability. HikariCP is designed to be fast, reliable, and easy to use, making it a popular choice for managing database connections in Java applications.

Here are some key features and benefits of HikariCP:

1. **High Performance**: HikariCP is known for its exceptional performance. It achieves this through various optimizations, such as minimizing lock contention, using a low-level connection pooling algorithm, and leveraging asynchronous I/O operations.

2. **Lightweight**: HikariCP has a small footprint and minimal dependencies, making it lightweight and efficient. This is important for applications that require high performance and have limited resources.

3. **Connection Management**: HikariCP handles connection pooling and management automatically. It provides a configurable pool of database connections that can be efficiently shared across multiple threads or clients.

4. **Connection Pool Configuration**: HikariCP offers a wide range of configuration options to customize the connection pool behavior. You can specify parameters such as pool size, connection timeout, maximum lifetime, and connection validation settings.

5. **Connection Pool Monitoring**: HikariCP provides built-in monitoring and management features. It exposes various metrics and statistics related to connection pool usage, allowing you to monitor the performance and health of the connection pool.

6. **Ease of Use**: HikariCP is designed to be easy to use and integrate into Java applications. It provides a simple and intuitive API for acquiring and releasing connections, and it can be seamlessly integrated with popular Java frameworks like Spring and Hibernate.

To use HikariCP in your Java application, you need to include the HikariCP dependency in your project. You can typically do this by adding the corresponding Maven or Gradle dependency to your build configuration.

Once HikariCP is included, you can create an instance of the `HikariDataSource` class, which represents the connection pool. You can configure various properties of the connection pool, such as the database URL, username, password, and pool size, using the available setter methods. Then, you can use the `getConnection()` method to acquire a connection from the pool, perform database operations, and release the connection back to the pool when you're done.

Here's a simple example that demonstrates the basic usage of HikariCP:

```java
import com.zaxxer.hikari.HikariConfig;
import com.zaxxer.hikari.HikariDataSource;
import java.sql.Connection;
import java.sql.SQLException;

public class HikariCPExample {

    public static void main(String[] args) throws SQLException {
        // Create HikariCP configuration
        HikariConfig config = new HikariConfig();
        config.setJdbcUrl("jdbc:mysql://localhost:3306/mydatabase");
        config.setUsername("username");
        config.setPassword("password");

        // Create the HikariCP data source
        HikariDataSource dataSource = new HikariDataSource(config);

        // Acquire a connection from the pool
        Connection connection = dataSource.getConnection();

        // Use the connection for database operations
        // ...

        // Release the connection back to the pool
        connection.close();

        // Shutdown the connection pool
        dataSource.close();
    }
}
```

In this example, we configure the HikariCP connection pool by setting the JDBC URL, username, and password. Then, we create an instance of `HikariDataSource` using the configuration. We can use the `getConnection()` method to acquire a connection from the pool and perform database operations. Finally, we release the connection back to the pool by closing it, and we close the connection pool itself.

### Example

Here's an example of a connection factory:

```java
import com.zaxxer.hikari.HikariConfig;
import com.zaxxer.hikari.HikariDataSource;
import org.apache.commons.dbcp2.BasicDataSource;

import java.sql.Connection;
import java.sql.SQLException;

public class ConnectionFactory {

    private static final String HIKARI = "hikari";
    private static final String DBCP = "dbcp";

    public static Connection getConnection(String poolType) throws SQLException {
        if (HIKARI.equals(poolType)) {
            return getHikariConnection();
        } else if (DBCP.equals(poolType)) {
            return getDbcpConnection();
        } else {
            throw new IllegalArgumentException("Invalid pool type specified");
        }
    }

    private static Connection getHikariConnection() throws SQLException {
        HikariConfig config = new HikariConfig();
        config.setJdbcUrl("jdbc:mysql://localhost:3306/mydatabase");
        config.setUsername("username");
        config.setPassword("password");

        HikariDataSource dataSource = new HikariDataSource(config);
        return dataSource.getConnection();
    }

    private static Connection getDbcpConnection() throws SQLException {
        BasicDataSource dataSource = new BasicDataSource();
        dataSource.setUrl("jdbc:mysql://localhost:3306/mydatabase");
        dataSource.setUsername("username");
        dataSource.setPassword("password");

        return dataSource.getConnection();
    }
}
```

In this example, we have a `ConnectionFactory` class that provides a static method `getConnection()` which takes a `poolType` parameter specifying the type of connection pool to use. If the value is `"hikari"`, it creates and returns a connection from the HikariCP pool. If the value is `"dbcp"`, it creates and returns a connection from the Apache DBCP pool. If an invalid value is provided, an `IllegalArgumentException` is thrown.

To use this connection factory, you can call the `getConnection()` method and pass the desired pool type:

```java
try {
    Connection connection = ConnectionFactory.getConnection("hikari");
    // Use the connection for database operations with HikariCP

    // Release the connection
    connection.close();
} catch (SQLException e) {
    // Handle any SQL exceptions
}

try {
    Connection connection = ConnectionFactory.getConnection("dbcp");
    // Use the connection for database operations with Apache DBCP

    // Release the connection
    connection.close();
} catch (SQLException e) {
    // Handle any SQL exceptions
}
```

In this example, we first call `getConnection("hikari")` to get a connection from the HikariCP pool and perform database operations. Then, we call `getConnection("dbcp")` to get a connection from the Apache DBCP pool and perform database operations. Finally, we release the connections by calling `connection.close()`.
