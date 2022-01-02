## Week 1

An **Information Model** is an abstract, formal representation of entities that includes their properties, relationships and the operations that can be performed on them. The entities being modeled can be from the real world, such as a library. Information Models and Data Models are different and serve different purposes.

An **Information Model** is at the conceptual level and defines relationships between objects. Data Models are defined at a more concrete level, are specific and include details. A **data model** is the blueprint of any database system. There are several types of Information Models. The most familiar is the **Hierarchical**, typically used to show organization charts. As shown is in this figure, the hierarchical model organizes its data using a tree structure. The root of the tree is the parent node followed by child nodes. A child node cannot have more than one parent; however, a parent can have many child nodes. The first hierarchical database management system was the **Information Management System** released by IBM in 1968 and was originally built as the database for the Apollo space program. The Relational Model is the most used data model for databases because this model allows for data independence. **Data** is stored in a simple data structure, tables. This provides logical data independence, physical data independence, and physical storage independence. An **Entity-Relationship Data Model, or ER Data Model**, is an alternative to a relational data model. Using a simplified library database as an example, this figure shows an Entity-Relationship Diagram, or ERD, that represents entities (called tables) and their relationships. There are authors who write books, borrowers who take books out on loan, various copies of each book, etc. This is the final ER diagram. But how do you get there? An Entity-Relationship Model proposes thinking of a database as a collection of entities. Rather than being used as a model on its own, the ER Model is used as a tool to design relational databases. In the ER Model, **entities are objects that exist independently of any other entities in the database**. It is simple to convert an ER Diagram into a collection of tables. The building blocks of an ER Diagram are entities and attributes. **Entities have attributes**, which are the data elements that characterize the entity. Attributes tell us more about the entity. In an ER Diagram, an entity is drawn as a rectangle, and attributes are drawn as ovals. Entities can be a noun (person, place, or thing). Using a simplified library as an example, a book is an example of an entity. Attributes are certain properties or characteristics of an entity and tell us more about the entity. The entity Book has attributes such as book title, the edition of the book, the year the book was written, etc. Attributes are connected to exactly one entity. The entity Book becomes a table in the database, and the attributes become the columns in a table. Continuing the simplified library example, books are written by authors. Book is an entity, and Author is an entity. For the entity Author, the ER Diagram would look like this. The entity Author has attributes such as the author’s last name, first name, email, city, country and an author ID (to uniquely identify the author). The entity Author becomes a table in the database, and the attributes become the columns in the table. In the simplified library database, you progress through the process of identifying entities, such as borrowers who take books out on loan, various copies of each book, and copies of books out on loan. This is the final ER Diagram. Each entity becomes a table in the database. In this video, you learned that: Information Models are abstract, formal representations of entities that include their properties, relationships and the operations that can be performed on them. Data Models are defined at a more concrete level, are specific and include details. The Relational Model is the most used data model for databases because this model allows for logical data independence, physical data independence, and physical storage independence. Entities are objects that exist independently of any other entities in the database. Entities can be a noun (person, place, or thing), such as a book or an author. Attributes are the data elements that characterize the entity. For example, the book entity will have attributes like author and title.
---
- entity become tables
- attributes become columns

**Data Types**
1. Character string
  - fixed length
    - CHAR(n)
  - variable length
    - VARCHAR(n)
    - LONGCHAR
2. Numeric
  - Integer
    - INT, SMALLINT, BIGINT
  - Decimal
    - DECIMAL, NUMERIC, FLOAT, SINGLE, DOUBLE
3. Datetime
  - Date, Time, Datetime
4. Boolean
5. Large object
6. Binary string
7. XML
8. User defined types (UDTs)
---
**Concept for Relational Table**
1. Relation is mathematical term for table.
  - Relation Schema, specifies the name of a relation, and the name and type of attributes
  - Relation Instance: a table made up of rows (tuple) and columns (attributes, field)
2. Degree: the number of attributes in a relation
3. Cardinality: the number of tuples
---
The relational model is the most used data model for databases because this model allows for logical data independence, physical data independence, and physical storage independence.

Entities are objects that exist independently of any other entities in the database, while attributes are the data elements that characterize the entity.

The building blocks of a relationship are entities, relationship sets, and crows foot notations.

Relationships can be one-to-one, one-to-many, or many-to-many.

When translating an Entity-Relationship Diagram to a relational database table, the entity becomes the table and the attributes become columns in the table.

Data types define the type of data that can be stored in a column and can include character strings, numeric values, dates/times, Boolean values and more.

The advantages of using the correct data type for a column are data integrity, data sorting, range selection, data calculations, and the of standard functions.

In a relational model, a relation is made up of two parts: A relation schema specifying the name of a relation and the attributes and a relation instance, which is a table made up of the attributes, or columns, and the tuples, or rows.

Degree refers to the number of attributes, or columns, in a relation.

Cardinality refers to the number of tuples, or rows in a relation.
---
A **single-tier topology** is one where the database is installed on a user’s local desktop. It is useful for small databases that only require single user access.
In **2-tier database** topologies the database resides on a remote server and users access it from client systems.
In **3-tier database** topologies the database resides on a remote server and users access it through an application server or a middle-tier.
In **Cloud deployments** the database resides in the cloud, and users access it through an application server layer or another interface that also resides in the cloud.
---
**Distributed Architecture**
1. Shared disk architecture (shared common storage)
2. Shared nothing architecture
  - replication
  - partitioning (each partition containing a subset of the overall data, when these partitions are placed on separate nodes in a cluster, it is called Sharding)
---
Three main classes of users are: Data Engineers Data Scientists and Business Analysts Application Developers.
Databases can be accessed through: Graphical and Web Interfaces which make it easy to interact with the database visually. Command line tools and scripts can be cumbersome to use but are powerful in the hands of an experienced Data Engineer and help with automating repetitive tasks. APIs and ORMs which help application developers create applications that access a database on behalf of a user or client application.
Major categories of database applications include: Database Management tools like phpMyAdmin or pgAdmin. Data Science and BI tools like Microsoft Excel, IBM Congos, and MicroStrategy, which enable Data Scientists and Data Analysts to analyze data and produce targeted reports. Purpose built or off the shelf business applications for tasks such as e-commerce, supply chain, etc.
---
**Summary**
There are four types of database topology:
1. Single tier. The database is installed on a user’s local desktop.
2. 2-tier. The database resides on a remote server and users access it from client systems.
3. 3-tier. The database resides on a remote server and users access it through an application server or a middle tier.
4. Cloud deployments. The database resides in the cloud, and users access it through an application server layer or another interface that also resides in the cloud.

In **shared disk distributed database architectures**, multiple database servers process the workload in parallel, allowing the workload to be processed faster. There are three shared nothing distributed database architectures:

**Replication**. Changes taking place on a database server are replicated to one or more database replicas. In a single location, database replication provides high availability. When database replica is stored in a separate location, it provides a copy of the data for disaster recovery.

**Partitioning**. Very large tables are split across multiple logical partitions.

**Sharding**. Each partition has its own compute resources.

There are different classes of database users, who use databases in different ways:
Three main classes of users are Data Engineers, Data Scientists and Business Analysts, and Application Developers.

Database users can access databases through Graphical and Web interfaces, command line tools and scripts, and APIs and ORMs.

Major categories of database applications include Database Management tools, Data Science and BI tools, and purpose built or off the shelf business applications.

Relational databases are available with commercial licenses or open source.

**MySQL** is an object-relational database that supports many operating systems, a range of languages for client application development, relational and JSON data, multiple storage engines, and high availability and scalability options.

**PostgreSQL** is an open source, object-relational database that supports a range of languages for client application development, relational, structured, and non-structured data, and replication and partitioning for high availability and scalability.
