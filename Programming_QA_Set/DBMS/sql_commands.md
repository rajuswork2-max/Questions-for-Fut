# SQL Commands Cheat Sheet

This document contains a comprehensive list of commonly used SQL commands categorized by their functionality.

## 1. Data Definition Language (DDL)
DDL commands are used to define the database schema and structure.

### `CREATE`
Creates a new database, table, index, or view.
```sql
-- Create a database
CREATE DATABASE database_name;

-- Create a table
CREATE TABLE table_name (
    column1 datatype constraints,
    column2 datatype constraints,
    ...
);
```

### `ALTER`
Modifies an existing database object (e.g., adding or dropping a column).
```sql
-- Add a new column
ALTER TABLE table_name ADD column_name datatype;

-- Drop a column
ALTER TABLE table_name DROP COLUMN column_name;

-- Modify a column's datatype
ALTER TABLE table_name MODIFY COLUMN column_name new_datatype;
```

### `DROP`
Deletes an entire database, table, index, or view.
```sql
-- Drop a table
DROP TABLE table_name;

-- Drop a database
DROP DATABASE database_name;
```

### `TRUNCATE`
Removes all records from a table, but keeps the table structure intact.
```sql
TRUNCATE TABLE table_name;
```

---

## 2. Data Manipulation Language (DML)
DML commands are used for managing data within schema objects.

### `INSERT`
Inserts new records into a table.
```sql
-- Insert into specific columns
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);

-- Insert into all columns
INSERT INTO table_name
VALUES (value1, value2, value3);
```

### `UPDATE`
Modifies existing records in a table.
```sql
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE condition;
```

### `DELETE`
Deletes existing records from a table.
```sql
DELETE FROM table_name
WHERE condition;
```

---

## 3. Data Query Language (DQL)
DQL commands are used to query and retrieve data from the database.

### `SELECT`
Retrieves data from one or more tables.
```sql
-- Select specific columns
SELECT column1, column2 FROM table_name;

-- Select all columns
SELECT * FROM table_name;

-- Select with distinct values (removes duplicates)
SELECT DISTINCT column_name FROM table_name;
```

### Clauses and Operators used with `SELECT`
```sql
-- WHERE (Filter records)
SELECT * FROM table_name WHERE condition;

-- ORDER BY (Sort records)
SELECT * FROM table_name ORDER BY column_name ASC|DESC;

-- GROUP BY (Group records that have the same values)
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name;

-- HAVING (Filter grouped records)
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name HAVING COUNT(*) > condition;

-- LIMIT / TOP (Limit the number of returned records)
SELECT * FROM table_name LIMIT number;
```

### `JOIN` Operations
Used to combine rows from two or more tables based on a related column between them.
```sql
-- INNER JOIN (Returns records that have matching values in both tables)
SELECT * FROM table1
INNER JOIN table2 ON table1.column_name = table2.column_name;

-- LEFT JOIN (Returns all records from the left table, and matched records from the right table)
SELECT * FROM table1
LEFT JOIN table2 ON table1.column_name = table2.column_name;

-- RIGHT JOIN (Returns all records from the right table, and matched records from the left table)
SELECT * FROM table1
RIGHT JOIN table2 ON table1.column_name = table2.column_name;

-- FULL OUTER JOIN (Returns all records when there is a match in either left or right table)
SELECT * FROM table1
FULL OUTER JOIN table2 ON table1.column_name = table2.column_name;
```

---

## 4. Data Control Language (DCL)
DCL commands are used to manage access rights and permissions to the database system.

### `GRANT`
Gives user access privileges to the database.
```sql
GRANT SELECT, INSERT ON table_name TO user_name;
```

### `REVOKE`
Withdraws user access privileges given by the `GRANT` command.
```sql
REVOKE SELECT, INSERT ON table_name FROM user_name;
```

---

## 5. Transaction Control Language (TCL)
TCL commands are used to manage changes made by DML commands and ensure data integrity.

### `COMMIT`
Saves all transactions to the database since the last COMMIT or ROLLBACK.
```sql
COMMIT;
```

### `ROLLBACK`
Undoes transactions that have not yet been saved to the database.
```sql
ROLLBACK;
```

### `SAVEPOINT`
Sets a point within a transaction to which you can later roll back.
```sql
SAVEPOINT savepoint_name;

-- Rollback to the specific savepoint
ROLLBACK TO savepoint_name;
```
