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

## Usage

To use the class, simply include it in your PHP script and create a new instance of the class. The class uses PDO to connect to the database, so you'll need to provide your database connection details (hostname, username, password, and database name) in the class constructor.

```php
$db = new DB();
```

You can then use the class methods to interact with the database. For example, to insert data into a table:

$db->query('INSERT INTO table_name (column1, column2, column3) VALUES (:value1, :value2, :value3)');
$db->bind(':value1', 'some value');
$db->bind(':value2', 'another value');
$db->bind(':value3', 'third value');
$db->execute();

