# SQLite CRUD Operations

This project demonstrates CRUD (Create, Read, Update, Delete) operations using SQLite. The code provides examples of how to interact with an SQLite database in a typical application.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## Introduction

SQLite is a C-language library that implements a small, fast, self-contained, high-reliability, full-featured SQL database engine. This project provides a simple implementation of basic CRUD operations to demonstrate how to work with SQLite databases.

## Features

- Create a database and table.
- Insert records into the table.
- Read records from the table.
- Update records in the table.
- Delete records from the table.

## Requirements

- Java Gradle 8.9
- SQLite3

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/thimathi/SqLite_CRUD_Operations.git
    cd SqLite_CRUD_Operations
    ```

2. Ensure you have SQLite installed. If not, you can install it using:
    ```bash
    sudo apt-get install sqlite3
    ```

## Usage

1. Run the Java to perform CRUD operations:
    ```bash
    ./gradlew run

    ```

2. Follow the on-screen instructions to perform different operations.

## Examples

Here are some examples of how to use the CRUD operations:

1. **Create a table**:
    String createTableQuery = "CREATE TABLE IF NOT EXISTS users ("
                          + "id INTEGER PRIMARY KEY,"
                          + "name TEXT NOT NULL,"
                          + "age INTEGER"
                          + ");";
statement.execute(createTableQuery);


2. **Insert a record**:
   String insertQuery = "INSERT INTO users (name, age) VALUES (?, ?);";
PreparedStatement preparedStatement = connection.prepareStatement(insertQuery);
preparedStatement.setString(1, "John Doe");
preparedStatement.setInt(2, 30);
preparedStatement.executeUpdate();


3. **Read records**:
    String selectQuery = "SELECT * FROM users;";
ResultSet resultSet = statement.executeQuery(selectQuery);
while (resultSet.next()) {
    System.out.println(resultSet.getInt("id") + " " + resultSet.getString("name") + " " + resultSet.getInt("age"));
}


4. **Update a record**:
    String updateQuery = "UPDATE users SET age = ? WHERE name = ?;";
PreparedStatement preparedStatement = connection.prepareStatement(updateQuery);
preparedStatement.setInt(1, 35);
preparedStatement.setString(2, "John Doe");
preparedStatement.executeUpdate();


5. **Delete a record**:
    String deleteQuery = "DELETE FROM users WHERE name = ?;";
PreparedStatement preparedStatement = connection.prepareStatement(deleteQuery);
preparedStatement.setString(1, "John Doe");
preparedStatement.executeUpdate();


## Contributing

Contributions are welcome! Please fork this repository and submit pull requests with your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
