### LESSON 1: INTRODUCTION TO DATAWAREHOUSE
**1. What is Data Warehouse? A business Perspective**
- Data Warehouse is a system (including process, technologies and data representations) the enables us to support analytical process.

**2. OLTP (Onine transactional processing)**
 - Scale and maintain level of performance
 - Store in 3RD Normal Form or NoSQL databases
 - Be recent, updated and available in real-time
 - Be stored in normalized relational databases


**3. OLAP (Online Analytical Processing)**
- Flexibity (may not be very clear but it will evolve)
- Organize in an understandable way
- Be historical, aggregated and accurate
- Work with dimensinal data

**4. Data Warehouse in Technical Perspective**
- It is a copy of transaction data specifically structured fro query and analysis. 
- It is subject-oriented, integrated, nonvolatile, and time-variant collection of data in support of management's decision.
- It is a system that retrieves and consolidates ata periodically from the source systems into a dimensional or normalized data store. It usually keeps years of history and is queried for business intelligence or other analytical activities. It is typically updated in batches, not every time a transaction happens in the source sytem.
- It extracts the data from the source system used for operations, transform the data, and load it into a dimensional model.
- The dimensional model is designed to:
    - make it easy for business users to work with the data
    - improve analytical queries performance

![Kimball's Bus Architecture](https://video.udacity-data.com/topher/2021/August/6112ddd2_l1-introduction-to-datawarehousing-3/l1-introduction-to-datawarehousing-3.png)

![The dimensional Model of a Data Warehouse](https://video.udacity-data.com/topher/2021/August/6111d21c_l1-introduction-to-datawarehousing-1/l1-introduction-to-datawarehousing-1.png)

**5. ETL Closer Look**
- Extracting:
    - Transfer data to the warehouse
- Transform:
    - Integrates many sources together
    - Possibly cleansing: inconsistencies, duplication, missing values...
    - Possibly producing diagnostic metadata
- Loading:
    - Structuring and loading the data into the dimensional data model

**6. Dimensional Model**
- Goal of the Star Schema:
    - Easy to understand
    - Fast analytical query performance
- Fact Tables
    - Record busniess events: an order, a phone call, a book review
    - Fact tables columns record events recorded in quantifiable metrics like quantity of an item, duration of a call, a book rating
- Dimension Tables
    - Record the context of the business events such as who, what, where, why...
    - Dimension tables columns contain attributes like the store at which an item is purchased of the customer who made the call...

![3RD Normal Form vs Star Schema](https://video.udacity-data.com/topher/2021/August/6111d490_l1-introduction-to-datawarehousing-2/l1-introduction-to-datawarehousing-2.png)

****From 3RD Normal Form to ETL****
- Extract:
    - Query the 3NF DB
- Transform:
    - Join tables together
    - Change types
    - Add new columns
- Load:
    - Insert into facts and dimension tables

**7. OLAP Cube Operations**
- An OLAP cube aggregates across various dimensions (such as: fact metric dimension, Month, Store). It provides a simplified and effective means of communication with business uesrs. 
- Roll up: is grouping data by one-dimension. It aggregates or combines values and reduces number of rows or columns.
- Drill-down: Decomposes values and increases number of rows or columns.
- Slice: Reducing N dimensions to N-1 dimensions by restricting one dimension to a single value.
- Dice: Same dimensions but computing a sub-sube by restricting, some of the values of the dimensions.

### LESSON 2: ETL AND DATA WAREHOUSE TECHNOLOGY IN THE CLOUD
---

**1. Cloud Data Warehouse**
- With traditional, on-premise data warehouses, an organization needed to buy physical hardware to fit the pre-defined need. Mordern cloud infrastrutures allow data warehouses to be scaled on demand in response to changing needs.
- Cloud Data Warehouse takes advantage of massively parallel processing in a changing data environment. 
    - Scalability: A large amount of data can be loaded into the data warehouse environment, processed, and stored faster and with relative ease.
    - Flexibility: Ability to add and remove different types of resources from data pipel;ines as needed. This allows for flexibility in the process as business needs change.
    - Cost shifting: It is a result of leveraging cloud database technology to perform the costly and tme-consuming trnasformation of data as the last part of the process rather than doing it earlier as is typical with on-premise data warehouses. By pushing it later, the business can prioritize which transforms they want to complete "just in time" for the business. 

**2. From ETL to ELT**
- ETL: Transformation happens on intermediate server
- ELT: Transformation happens on destination server.

This means rather than loading data directly into the final format of the destination data warehouse, data are loaded into the destination as either raw data or staging tables (or sometimes both). Only after loading is transformation performed. 

The benefits of doing ELT include:
- Scalability: massive amounts of data can be loaded into the data warehouse environment with relative ease
- Flexibility: The transform step takes place using the same tach stack as the data warehouse runs on allowing for more flexibility in the process as business needs change.
- Cost shifting: The transform step is often the most costly and doing it last, DE can perform just In TIme tranformations to meet the highest priority business needs first.
- Better performance for large datasets.
- More flexibility for unstructured (NoSQL) datasets.
- Ability to load large amounts of data quickly. For example, ingesting streaming data. In modern architectures, this streaming data is often coming from Internet of Things (IoT) devies, however, it could be coming from more traditional sources such as server or transaction logs. 

Each major cloud platforms has offering for ingesting large amounts of streaming data:
- Azure: Streaming Analytics
- AWS: Kinesis
- GCP: DAtaflow

**3. Cloud Managed SQL Database**
- Microsoft Azure
    - Azure SQL Database (MS SQL Server)
    - Azure Database for MySQL
    - Azure Database for MariaDB
    - Azure Database for PostgreSQL
- GCP
    - Cloud SQL (MySQL, PostgreSQL, and MS SQL Server)
- AWS
    - Amazon RDS (MySQL, PostgreSQL, MariaDB, Oracle, MS SQL Server)
    - Amazon Aurora (MySQL, PostgreSQL)

**4. Cloud Managed NoSQL Database**
There are two primary ways Cloud service providers offer NoSQL database systems:
- A single platform provides multiples APIs to the various types of NoSQL databases.
- Each type of NoSQL database if offered as a separate service

Each of the major cloud providers offers a variety of managed NoSQL databases:
- Azure - CosmosDB
    - Gremlin - graph database
    - MongoDB - document
    - Cassandra - column oriented
- GCP
    - Big Table - column oriented
    - Firestore - document
    - MongoDB Atlas - document
- AWS
    - DynamoDB - Key value
    - DocumentDB - document
    - Keyspaces = column oriented
    - Neptune - graph
    - Time stream - time series

### LESSON 3: DATAWAREHOUSE WITH AWS REDSHIFT
--- 

**1. Create IAM Role**
All AWS services require identity and Access Management (IAM) policies, roles and their associcated permissions. Creating IAM user role to have permission to use the Redshift service on AWS.

**2. Create Security Group**
A security group will act as firewall rules for your Redshift cluster to control inbound and outbound traffic

**3. Create an IAM User**

**4. Launch A Redshift Cluster**

**5. Create Existing Bucket**
Details of an Existing Bucket

a. Properties
There are several properties that you can set for S3 buckets, such as:

Bucket Versioning - Allows you to keep multiple versions of an object in the same bucket.
Static website hosting - Mark if the bucket is used to host a website. S3 is a very cost-effective and cheap solution for serving up static web content.
Requester pays - Make the requester pays for requests and data transfer costs.
Server access logging - Log requests for access to your bucket.

b. Permissions
It shows who has access to the S3 bucket, and who has access to the data within the bucket. In the example snapshots above, the bucket is public, meaning anyone can access it. Here, we can write an access policy (in JSON format) to provides access to the objects stored in the bucket.

c. Metrics
View the metrics for usage, request, and data transfer activity within your bucket, such as, total bucket size, total number of objects, and storage class analysis.

d. Management
It allows you to create life cycle rules to help manage your objects. It includes rules such as transitioning objects to another storage class, archiving them, or deleting them after a specified period of time.

e. Access points
Here, you can create access endpoints for sharing the bucket at scale. Using an endpoint, you can perform all regular operations on the bucket.

**6. Creating AWS Relational Database Service (RDS)**
AWS RDS is a managed PostgresSQL service. Amazon RDS is a relational database service that manages common database administration tasks, resize automatically and is cost-friendly.

There are two methods to create a database that AWS provides two options to choose from:
- Standard create - You have set all of the configuration options, including ones for availability, security, backups, and maintenance.
- Easy create - You use the industry best-practice configurations. All configuration options, except the Encryption and VPC details, can be changed after the database is created.

**7. Infrustructure as Code**
The advantages of Infrastructure as Code over creating Infrastructure by clicking around:
- Sharing: One can share all the steps with others easily
- Reproducibility: One can be sure that no steps are forgotten
- Multiple deployments: One can create a test environment identical to the production environment
- Maintainability: If a change is needed, one can keep track of the changes by comparing the code.

### LESSON 4: IMPLEMENTING DATA WAREHOUSE ON AWS
---

**1. Amazon Redshift Technology**
- Columned-oriented Relational Database Management System (RDBMS)
- Best suited for storing OLTP workloads.
- Massively Parallel Processing (MPP) executes one query on multiple CPUs or multiple machines in parallel.
- Tables are partitioned and processed in parallel.

**2. Amazon Redshift Architecture**
- Leader Node:
    - Coordinates compute nodes
    - Handles external communication
    - Optimizes query execution
- Compute Nodes:
    - Each with own CPU, memory, and disk (determined by the node type)
    - Scale up: get more powerful nodes
    - Scale out: get more nodes
- Node slices:
    - Each compute node is logically divided into a number of slices
    - A cluster with n slicescan process n partitions of tables simultaneously

**3. Ingesting data at scale**

- Transferring Data from an S3 stagging Area to Redshift
    - Efficient transferring data from an S3 Staging Area to Redshift through COPY command.
        - File Size Management: Enhance efficiency by breaking large files into smaller ones
        - Parallel Ingestion: Accelerate data transfer by leveraging parallel ingestion
        - REgion and Compression: Optimize performance by ingesting data from same AWS region and boost speed and save storage by compressing all CSV files before ingestion.
        - Delimiter Specification: Specify the delimiter fro a streamlined transfer process.
- Staging Area: serves as a temporary repository for data before it is loaded into the target data warehouse. 
    - Data Transformation
    - Data Validation
    - Data Aggregation
    - Data Versioning
    - Data security

**4. Optimizing Table Design with Distribution Styles**
When table is partitioned up into many pieces and distributed across slices in different machines, this is done bindly. If you know about the frequent access pattern of a table, you can choose a more performant strategy by configuring different distribution options for your cluster.
- Distribution Styles:
    - EVEN: Round-robin over all slices to achieve load-balancing. Good if a table wont be joined.
    - ALL: Smalles tables could be replicated on all slices to speed up joins. Used frequently for dimension tales. AKA 'broadcasting'
    - AUTO: Leave decision to Redshift. 'Small enough' tables are distributed with an ALL strategy.
    - KEY: Rows having similar values are placed in same slice
- Sorting key
    - Define columns as sort key
    - Rows are sorted before distribution to slices
    - Minimizes the query time
    - Useful for columns taht are used frequently in sorting like the date dimension and its corersponding foreign key in the fact table
