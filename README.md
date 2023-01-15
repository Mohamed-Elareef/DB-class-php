# PHP Database Class

This is a basic PHP class for interacting with a database. It provides methods for connecting to a database, executing SQL queries, and handling errors. 

## Requirements

- PHP 5.3 or later
- PDO extension for PHP
- MySQL or another supported PDO database

## Features

- Connection handling
- CRUD (Create, Read, Update, Delete) operations
- Query building
- Error handling
- Prepared statements

## Documentation
- __construct(): This method is used to create a new PDO instance and set the connection parameters for the database. It also sets the error mode to throw exceptions, so that any errors that occur can be caught and handled.

- query($query): This method is used to prepare a SQL query for execution. It takes a single argument, which is the query string.

- bind($param, $value, $type = null): This method is used to bind values to parameters in a prepared statement. It takes three arguments: $param is the name of the parameter, $value is the value to be bound, and $type is the data type of the value (if not provided, the method will try to determine the data type automatically).

- execute(): This method is used to execute a prepared statement. It returns a boolean value indicating whether the execution was successful or not.

- resultset(): This method is used to retrieve all rows from the result set of a SELECT query. It returns an array of associative arrays, where each inner array represents a row of the result set.

- single(): This method is used to retrieve a single row from the result set of a SELECT query. It returns an associative array representing the row.

- rowCount(): This method is used to get the number of rows affected by the last executed statement.

- lastInsertId(): This method is used to get the ID of the last inserted row.

## Usage

To use the class, simply include it in your PHP script and create a new instance of the class. The class uses PDO to connect to the database, so you'll need to provide your database connection details (hostname, username, password, and database name) in the class constructor.

```php
$db = new DB();
```

You can then use the class methods to interact with the database. For example, to insert data into a table:
```php
$db->query('INSERT INTO table_name (column1, column2, column3) VALUES (:value1, :value2, :value3)');
$db->bind(':value1', 'some value');
$db->bind(':value2', 'another value');
$db->bind(':value3', 'third value');
$db->execute();
```


To retrieve data from the database:
```php
$db->query('SELECT * FROM table_name WHERE id = :id');
$db->bind(':id', $id);
$rows = $db->resultset();
```

Please refer to the class documentation for more information on the available methods and their usage.

## Note

This is a basic implementation, to be used as a starting point for your implementation, and it should be customized to meet the specific needs of your project.



