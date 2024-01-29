### LESSON 1: BIG DATA ECOSYSTEM, DATA LAKES AND SPARK
---

1. Hadoop Framework
- Hadoop is older system than Spark. The main difference between Hadoop and Spark is that how they use memory. Hadoop writes intermediate results to disk where Spark tries to keep data in the memory whenever possible. This makes Spark faster for many use cases.
- Hadoop Framework consists of four main components:
    - HDFS: Hadoop Distributed File System (HDFS) - a big data storage system that splits data into chunks and stores the chunks cross a cluster of computers.
    - Hadoop MapReduce: a system for processing and analysing large data sets in parallel.
    - Hadoop YARN: a resource manager that schedules jobs across a cluster. The manager keeps track of what computer resources are available and then assigns those resources to specific tasks.
- Spark does not include a file storage system. We can use Spark on top of HDFS, but you do not have to. Spark can read in data from other sources as well.

2. MapReduce
- Map Reduce is a programming techniques for manipulating large data sets. "Hadoop MapReduce" is a specific implementation of this programming technique. This technique works by first dividing up a large dataset and distributing the data across the cluster.
    - Map: each data chunk is analyzed and converted into a (key, value) pair. 
    - Shuffle: These key-value pairs are shuffled across the cluster so that all keys are on the same machine. 
    - Reduce: The values with the same keys are combined together.

3. Spark Cluster
- Distributed Computer: A big computational job executing across a cluster of nodes. Each node is responsible for a set of operations on a subset of the data. At the end, we combine these partial results to get the final answer. But how do the nodes know which task to run and demote order. Are all nodes equal? Which machine are you interacting with when you run your code?
- Most computational frameworks are organized into a master-worker hierachy:
    - The master node is responsible for orchestrating the tasks across the cluster
    - Workers are performing the actual computations
- There are four different modes to setup Spark:
    - Local mode: everything happens on a single machine. This mode is useful when learning the syntax and to prototype your project. 
    - The other three modes are distributed and declare a cluster manager. The cluster manager is a separate process that monitors available resources and make sure that all machines are responsive during the job.
    ![Spark Mode](https://video.udacity-data.com/topher/2021/September/613f8cba_screen-shot-2021-09-13-at-12.38.48-pm/screen-shot-2021-09-13-at-12.38.48-pm.png)
- You do not always need Spark:
    - If you working on smaller data sets

4. Data Lakes
- A data lake pours all of the data into a single repository, ready to be consumed by whoever and wherever they need.
- Key features of data lakes:
    - 