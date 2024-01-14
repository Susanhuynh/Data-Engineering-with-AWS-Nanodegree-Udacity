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

