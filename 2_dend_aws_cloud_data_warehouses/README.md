1. What is Data Warehouse? A business Perspective
- Data Warehouse is a system (including process, technologies and data representations) the enables us to support analytical process.

2. OLTP (Onine transactional processing)
 - Scale and maintain level of performance
 - Store in 3RD Normal Form or NoSQL databases
 - Be recent, updated and available in real-time
 - Be stored in normalized relational databases


3. OLAP (Online Analytical Processing)
- Flexibity (may not be very clear but it will evolve)
- Organize in an understandable way
- Be historical, aggregated and accurate
- Work with dimensinal data

3. Data Warehouse in Technical Perspective
- It is a copy of transaction data specifically structured fro query and analysis. 
- It is subject-oriented, integrated, nonvolatile, and time-variant collection of data in support of management's decision.
- It is a system that retrieves and consolidates ata periodically from the source systems into a dimensional or normalized data store. It usually keeps years of history and is queried for business intelligence or other analytical activities. It is typically updated in batches, not every time a transaction happens in the source sytem.
- It extracts the data from the source system used for operations, transform the data, and load it into a dimensional model.
- The dimensional model is designed to:
    - make it easy for business users to work with the data
    - improve analytical queries performance

![Kimball's Bus Architecture](https://video.udacity-data.com/topher/2021/August/6112ddd2_l1-introduction-to-datawarehousing-3/l1-introduction-to-datawarehousing-3.png)

![The dimensional Model of a Data Warehouse](https://video.udacity-data.com/topher/2021/August/6111d21c_l1-introduction-to-datawarehousing-1/l1-introduction-to-datawarehousing-1.png)

3. ETL Closer Look
- Extracting:
    - Transfer data to the warehouse
- Transform:
    - Integrates many sources together
    - Possibly cleansing: inconsistencies, duplication, missing values...
    - Possibly producing diagnostic metadata
- Loading:
    - Structuring and loading the data into the dimensional data model

4. Dimensional Model
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

5. OLAP Cube Operations
- An OLAP cube aggregates across various dimensions (such as: fact metric dimension, Month, Store). It provides a simplified and effective means of communication with business uesrs. 
- Roll up: is grouping data by one-dimension. It aggregates or combines values and reduces number of rows or columns.
- Drill-down: Decomposes values and increases number of rows or columns.
- Slice: Reducing N dimensions to N-1 dimensions by restricting one dimension to a single value.
- Dice: Same dimensions but computing a sub-sube by restricting, some of the values of the dimensions.