## 1. Inserting records
```shell
INSERT INTO user (username, email, password) 
VALUES ("kinaro", "kinaro@outlook.com", "CrappyPass");
```
## 2. Selecting only unique values
```shell
SELECT DISTINCT email FROM user;
```
- This query takes only one column name as the operand.

## 3. Showing only a limited number of records
### (a) Grouping by a column name
```shell
SELECT email
FROM user
WHERE id < 5
LIMIT 2;
```
- This only takes one column name as the operand to the SELECT statement.
- Try running with multiple column names to see that:
```shell
SELECT (username, email)
FROM user
WHERE id < 5
LIMIT 2;
```

## 4. Change a value
- Select the value you want to change by using the `WHERE` clause.
```shell
# General Syntax:
UPDATE user
SET username="FKinaro"
WHERE id=1;
```

**If you omit the `WHERE` clause, _ALL_ records will be updated to the values you have specified**


## 5. Delete a value
- Remove a row from the database;
```shell
DELETE FROM user WHERE id=4;
```
```shell
DELETE FROM user WHERE username LIKE 'kina%';
```

## 6. Working with joins and subqueries.
