## Week 3
**MySQL** creation using command line
```
CREATE DATABASE database_name;
USE database_name;
CREATE TABLE table_name (
  column_name_1 datatype,
  column_name_2 datatype,
  ...
  column_name_n datatype
);
```
---
**Import data files**
```
load data infile 'filename.csv' into table table_name

mysqlimport table_name filename.csv
```
---
**PostgreSQL** creation using command line
```
CREATE DATABASE database_name;
\connect database_name;
CREATE TABLE table_name (column_name_1 datatype, column_name_2 datatype, column_name_n datatype);
```
---
**Views**
A view is an alternative way of representing data from one or more tables or other views. It is used to limit access to sensitive data, simplify data retrieval, reduce access to underlying tables. Whereas, **Materialized views** behave differently to regular views. The result set is materialized, or saved, for future use. It cannot insert, update, or delete rows. However, it can improve performance. 
