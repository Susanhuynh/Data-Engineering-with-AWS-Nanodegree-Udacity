### Relational Database
- Relational Database is a digital databse based on the relational model of data. A software system used to maintain relational databases is a relational database management system RDBMS.

    Relational Database is not distributed database. Therefore, you only can scale them vertically by adding more storage on the machine.

    SQL is used to interact with database.

    + Database/Schema: a collection of tables
    + Tables/Relation: A group of rows sharing the same labeled elements.
    + Columns/Attribute: A labeled element
    + Row/Tuple: A Single Item

- Advantages of using a Relational Database:
    + Ease of us -- SQL
    + Ability to JOINS
    + Ability to do aggregations and analytics
    + Smaller data volumes
    + Easier to change business requirements
    + Flexibility for queries
    + Modeling the data not modeling queries
    + Second Index Availability
    + ACID Transactions - strong data integrity:
        + Atomic: whole transaction is processed or nothing happened.
        + Consistency: only transactions that follow constraints and rules are written into database otherwise database keeps previous state.
        + Isolation: transactions are processed independently and securely, order does not matter.
        + Durability: completed transactions are saved to database even if cases of system failure.

- When not to use Relational Database:
    + Large amount of data
    + Need to be able to store different data type formats
    + Need high throughput - fast reads
    + Need a flexible schema
    + Need high availability: describe a database  where there is very little downtime of the system, it is always on and functioning.
    + Need horizontal scalability: add more machines or nodes to a system to increase performance and add space. 

### What is PostgreSQL?
- It is RDBMS and uses SQL. It provides various features that reliably store and scale complicated data workloads.
- PostgresSQL SQL syntax is different than other relational database SQL syntax.

### What is NoSQL Database? 
- NoSQL Database has a simpler design, simpler horizontal scaling, and finer control of availability. Data structures used are different than those in Relational Database are make some operations faster.

- The basics of Apache Cassandra:
    + Keyspace: Collection of tables
    + Table: A group of partitions
    + Rows: A single item
    + Partition:
        + A fundamental of access
        + Collection of rows
        + How data is distributed
    + Primary Key: is made up of a partition key and clustering columns
    + Columns: 
        + Clustering and Data
        + Labeled element

- When to use a NoSQL Database:
    + Large amounts of data
    + Need horizotal scalability
    + Need high throughput -- fast reads
    + Need flexible schema
    + Need high availability
    + Need to be store different data type formats
    + Users are distributed - low latency

- When not to use NoSQL Database?
    + Need ACID transactions
    + Need ability to do JOINS
    + Ability to do aggregations and analytics
    + Have changing business requirements
    + Queries are not available and need to have flexibility
    + Have a small dataset
    
**NoSQL Database and Relational Database does not replace each other for all tasks. Both do different tasks extremely well, and should be utilized for the use cases they fit best.**
 
### Relational Data Models
- The importance of Relational Database:
    + Standardize of data model
    + Flexibility in adding and altering tables
    + Data Integrity
    + SQL
    + Simplicity
    + Intuitive Organization

- **OLAP vs OLTP**
    + Online Analytical Processing (OLAP): Databases optimized for these workloads allow for complext analytical and ad hoc queries. These type of databases are optimized for reads.
    + Online Transactional Processing (OLTP): Databases optimized for these workloads allow for les complex queries in large volumne. These types of queries for these databases are read, insert, update and delete.
 
- **Normalization**
    + The process of structuring a relational database in accordance with a series of normal forms in order to reduce data redundancy and increase data integrity.
    + We dont want or need extra copies of our data, this is data redundancy. We want to be able to update data in on place and have that be the source of truth, that is data integrity.
    + Objectives of Normal Form:
        + To free the databse from unwanted insertions, updates and delete dependencies.
        + To reduce the need for refactoring the database as new types of data are introduced
        + To make the relational model more informative to users.
        + To make the database neutral to the query statistics.
    + The proces of normalization is a step by step process:
        + First Normal Form (1NF): 
            + Atomic values: each cell contains unique and single values
            + Be able to add data without altering tables
            + Seperate different relations into different tables
            + Keep relationships between tables together with foreign keys
        + Second Normal Form (2NF):
            + Reach 1NF
            + All columns in the table must rely on the Primary Key
        + Third Normal Form (3NF):
            + Reach 2NF
            + No transitive dependencies

- **Denormalization**
    + The process of trying to improve the read performance of a database at the expense of losing some write performance by adding redundant copies of data. 
    + Logical Design Change:
        + The Desinger is incharge of keeping data consistent
        + Reads will be faster (select)
        + Writes will be slower (insert, update, delete)