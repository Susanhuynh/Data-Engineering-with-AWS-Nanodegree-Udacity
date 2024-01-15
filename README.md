# Data-Engineering-with-AWS-Nanodegree-Udacity
Notes and projects done for Data Engineering in AWS Nanodegree on Udacity

Goal: I want to know what the process of Data Engineering is? Which knowledge and skills are required to do the DE job? At the end of the course, I want to understand the data infrastructure and have a guidance for my next career path in Data field. 

Recommended time: 2 months. Level: Intermediate. Prerequisite: Intermediate SQL & Python.

### Course 1: DATA MODELING
---

**1. Introduction to data modeling**

When to use data modeling
The data modeling process

**2. Properties of relational data models**

ACID transactions
Normalization
Fact and Dimension table modeling
Star and Snowflake Schemas
Data definitions and constraints

**3. Properties of NoSQL data models**

When to use NoSQL databases
Distributed database design
CAP Theorem

**4. How to create relational data models**

Relational data modeling with Postgres

**5. How to create NoSQL data models**

NoSQL data modeling with Apache Cassandra

### Course 2: Data Warehouse, OLTP, OLAP, Dimensional Modeling, ELT and OLAP
---

**1. Business Perspective on Data Warehouse**
    - OLTP: Onlline Transactional Processing
    - OLAP: Online Analytical Processing

**2. Technical Perspective on Data Warehouse**
    - ETL Process

**3. Dimensional Modeling**
    - Star Scheme > 3NF
    - ETL process from 3NF database to Star Schema
    
**4. DWH Architeture**

![Kimball's Bus Architecture](https://video.udacity-data.com/topher/2021/August/6112ddd2_l1-introduction-to-datawarehousing-3/l1-introduction-to-datawarehousing-3.png)

![The dimensional Model of a Data Warehouse](https://video.udacity-data.com/topher/2021/August/6111d21c_l1-introduction-to-datawarehousing-1/l1-introduction-to-datawarehousing-1.png)

**5. OLAP Cubes**
- OLAP cube is an aggregation of data on a number of dimensions
- Roll Up, Drill Down, Slice, Dicing
- Group By cube() > Group by grouping sets() on performance (queries run faster)

### Course 3: DWH on AWS
---

- Amazon Redshift Architecture
- How to ETL with Redshift
- How to ingest data into Redshift using S3 buckets
- Parallel ETL
- Optimizing Table Design using Distribution Styles

