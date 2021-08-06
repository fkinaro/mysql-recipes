# Database Structures

- What is a relational database: A collection of logically ordered data.
- Relational Database Management System: The software used to manage databases.
- Table: Represents an entity type. 
- Row: Represents an entity.
- Column: Represents attributes/characteristics.


## Data Types
- Define how data is stored.
### Major types:
1. String
2. Date
3. Datetime
4. TEXT
5. BLOB

## Working with databases
### Constraints
- Used to limit the type of data that can go into a table.
- Some examples:
  - UNIQUE
  - NOT NULL
  - PRIMARY KEY
  - CHECK
  - FOREIGN KEY
  - DEFAULT


- SQL statements are terminated with **semicolon (;)**. 
- Keywords are case-insensitive.


## Some basic operatins
- Create a database:
```shell
CREATE DATABASE registration IF NOT EXISTS;
```
This creates a new database called _registration_ only if there is no such database already.

- Delete a database
```shell
DROP DATABASE registration IF EXISTS;
```
This deletes the _registration_ database if there is such database already.

- Use a specific database:
```shell
USE registration;
```
Try running this immediately after dropping the database and see what happens.


## working with tables
- Create a table: 
  ```shell 
  CREATE TABLE user(
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(40) NOT NULL,
    last_name VARCHAR(40) NOT NULL,
    username VARCHAR(35) NOT NULL UNIQUE,
    email VARCHAR(80) NOT NULL UNIQUE
  );
  ```
  - This creates a table to store user details. The SQL keywords are in uppercase; they define requirements that the data must meet.

  - **`user_id`** is set as the primary key and increases by one every time a new user is registered.
- Delete a table:
  ```shell
  DROP TABLE user IF EXISTS;
  ```

- Add a new column:
  ```shell
  ALTER TABLE user
  ADD password VARCHAR(80) NOT NULL;
  ```
  - Adds a new column at the end
- Change data type
  ```shell
  ALTER TABLE user
  ALTER COLUMN password TEXT;
  ```
- Delete a column
  ```shell
  ALTER TABLE user
  DROP COLUMN password;
  ```
