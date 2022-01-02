## Week 2

**SQL Statement**
1. DDL (Data Definition Language)
  - define, change, drop data
  - CREATE, ALTER, TRUNCATE, DROP
2. DML (Data Manipulation Language)
  - read and modify data
  - CRUD operation (Create, Read, Update, and Delete)
  - INSERT, SELECT, UPDATE, DELETE
---
**Create Table Consideration**
1. Schema
2. Table name
3. Column name
4. Data type
5. Duplicates
6. Null values
**Syntax**
```
CREATE TABLE table_name
  (
  column_name_1 datatype optional_parameters,
  column_name_2 datatype,
  ...
  column_name_n datatype

  *PRIMARY KEY NOT NULL*

  )
```
PRIMARY KEY is the unique identifier for a row / an observation.
---
**ALTER Table**
```
ALTER TABLE table_name
  ADD COLUMN column_name datatype
  ...
  ADD COLUMN column_name_n datatype;

ALTER TABLE table_name
  ALTER COLUMN column_name SET DATA TYPE
CHAR(20);

ALTER TABLE table_name
  DROP COLUMN column_name
```
---
**DROP Statement**
``DROP TABLE table_name``
---
**TRUNCATE Statement** to delete all the records in table
```
TRUNCATE TABLE table_name
  IMMEDIATE;
```
---
**Data Movement Tools and Utilities**
Three main categories of Data Movement Tools:
1. Backup and Restore
2. Import and Export
  - uses the file format of DEL, ASC, PC/IXF, JSON
  ```
  db2 import from filename of fileformat messagesfile into table

  df2 export to filename of fileformat messages messagesfile select * from table
  ```
3. Load
  1. Source
  2. Target
  3. Define
  4. Finalize
```
db2 load from filename of fileformat messages messagesfile import_mode

into table copy yes/no use tsm data buffer pages
```
---
**INSERT Statement**
```
INSERT INTO table_name(column_name_1, column_name_2) VALUES
  (observation, observation),
  (observation, observation);
```
---
**Summary and Highlights**
DDL statements, including CREATE, ALTER, TRUNCATE, and DROP, are used for defining objects like tables in a database.

DML statements, including INSERT, SELECT, UPDATE, and DELETE, are used for manipulating data in tables.

Many Relational Database Management Systems (RDBMS) have schemas that contain tables, views, functions, and other database objects.

Most RDBMS provide a GUI through which you can create and alter the structure of tables.

You can also create and alter tables by using DDL SQL statements:

CREATE TABLE. Creates entities (tables) in a relational database and sets the attributes (columns) in a table, including the names of columns, the data types of columns, and constraints (for example, the Primary Key.)

ALTER TABLE. Changes the structure of a table by adding or removing columns, modifying the data type of columns, and adding or removing keys and constraints.

DROP TABLE. Deletes a table from a database.

TRUNCATE TABLE. Removes all rows in a table.

There are utilities that help you to manage the movement of data:

You use the BACKUP and RESTORE utilities to create and recover copies of entire databases, including all objects like tables, views, constraints, and data.

You use the IMPORT utility to insert data into a specific table from different formats, such as DEL/CSV, ASC and IXF, and the EXPORT utility to save data from a specific table into various formats, such as CSV.

You can use the LOAD utilities, instead of INSERT statements, to quickly insert large amounts of data a variety of different data sources into tables.

The Load Data utility is a simple to use interface in the Db2 Web Console.
---
**Creating Primary Key**
```
CREATE TABLE table_name(
  column_name_1 INT NOT NULL,
  ...
  column_name_n INT NULL,

  PRIMARY KEY(column_name_1)
);

ALTER TABLE table_name
  ADD PRIMAY KEY(column_name_1, ISBN);
```

---
**Creating Foreign Key**
```
CREATE TABLE copy(
  copy_id INT NOT NULL,
  book_id INT NULL,
)
...
CONSTRAINT fk_copy_book FOREIGN KEY(book_id)
  REFERENCES book(book_id)
  ON UPDATE NO ACTION
);
```
---
**INDEX Creation** to improve *select* queries
```
CREATE TABLE table_name(
  ...
  PRIMARY KEY(column_name)
);

CREATE UNIQUE INDEX index_column_name
  ON table_name(column_name);
```
---
**Normalization** reduces data duplication
1. First Normal Form (1NF): each row must be unique, each cell contain only a single value
2. Second Normal Form (2NF): create separate tables for sets of values that apply to multiple rows
3. Third Normal Form (3NF): eliminate columns that do not depend on the key

**Normalization in OLTP and OLAP**
1. OLTP
  - data is read and written frequently
  - data is normalized to 3NF or BCNF
2. OLAP
  - data is mostly read only
  - data is de-normalized
---
**Constraints**
1. Entity Integrity Constraint
2. Referential Integrity Constraint
3. Semantic Integrity Constraint
4. Domain Constraint
5. Null Constraint
6. Check Constraint
---
**Summary and Highlight**
The objects in a Relational Database Management System (RDBMS) object hierarchy include:

Instances. This is a logical boundary for a database or set of databases where you organize and isolate database objects and set configuration parameters.

Relational databases. This is a set of objects used to store, manage, and access data.

Schemas. A user or system schema is a logical grouping of tables, views, nicknames, triggers, functions, packages, and other database objects. Schemas provide naming contexts so that you can distinguish between objects with the same name.

Database partitions. You can split very large tables across multiple partitions to improve performance.

Database objects. Database objects are the items that exist within the database, such as tables, constraints, indexes, views, and aliases.

Primary key and Foreign Keys have several uses:

Primary keys enforce uniqueness of rows in a table, whereas Foreign keys are columns in a table that contain the same information as the primary key in another table.

You can use primary and foreign keys to create relationships between tables. Relationships between tables reduce redundant data and improve data integrity.

Indexes provide ordered pointers to rows in tables and can improve the performance of SELECT queries, but can decrease the performance of INSERT, UPDATE, and DELETE queries.

Normalization reduces redundancy and increases consistency of data. There are two forms of normalization:

First normal form (1NF). In this form, the table contains only single values and has no repeating groups.

Second normal form (2NF). This form splits data into multiple tables to reduce redundancy.

You can define six relational model constraints:

Entity integrity constraint. Ensures that the primary key is a unique value that identifies each tuple (or row.)

Referential integrity constraint. Defines relationships between tables.

Semantic integrity constraint. Refers to the correctness of the meaning of the data.

Domain constraint. Specifies the permissible values for a given attribute.

Null constraint. Specifies that attribute values cannot be null.

Check constraint. Limits the values that are accepted by an attribute.
