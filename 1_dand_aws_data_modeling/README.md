### Relational Database
- Relational Database is a digital databse based on the relational model of data. A software system used to maintain relational databases is a relational database management system RDBMS.

Relational Database is not distributed database. Therefore, you only can scale them vertically by adding more storage on the machine.

SQL is used to interact with database.

Database/Schema: a collection of tables
Tables/Relation: A group of rows sharing the same labeled elements.
Columns/Attribute: A labeled element
Row/Tuple: A Single Item

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
        ++ Atomic: whole transaction is processed or nothing happened.
        ++ Consistency: only transactions that follow constraints and rules are written into database otherwise database keeps previous state.
        ++ Isolation: transactions are processed independently and securely, order does not matter.
        ++ Durability: completed transactions are saved to database even if cases of system failure.

- When not to use Relational Database:
    + Large amount of data
    + Need to be able to store different data type formats
    + Need high throughput - fast reads
    + Need a flexible schema
    + Need high availability: describe a database  where there is very little downtime of the system, it is always on and functioning.
    + Need horizontal scalability: add more machines or nodes to a system to increase performance and add space. 

    ### What is PostgreSQL?
    - It is RDBMS and uses SQL. 