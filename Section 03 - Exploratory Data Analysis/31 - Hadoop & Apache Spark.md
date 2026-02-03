# Hadoop & Apache Spark – Key Points for AWS ML Specialty Exam

---

## Hadoop Core Components
- **Hadoop consists of modules:**
  - **HDFS (Hadoop Distributed File System):**  
    Distributed, scalable file system storing data in blocks (default 128MB) across cluster nodes with replication for fault tolerance.  
    *Ephemeral storage:* data lost when cluster terminates. Good for intermediate data and workloads with random I/O.  
  - **YARN (Yet Another Resource Negotiator):**  
    Resource and cluster manager introduced in Hadoop 2.0.  
    Enables multiple data processing frameworks (not just MapReduce) to share cluster resources.
  - **MapReduce:**  
    Programming model with *Mapper* (data transformation, key-value pairs) and *Reducer* (aggregation) functions to process large data in parallel.  
    Now largely replaced by Apache Spark for faster, more flexible data processing.
- **Hadoop-Core (Common):** Provides libraries, utilities, and basic OS abstractions for Hadoop modules.

---

## Apache Spark Overview
- Modern, fast distributed data processing engine often running on EMR clusters using YARN as resource manager.
- Uses **in-memory caching** and **Directed Acyclic Graph (DAG)** execution for speed over MapReduce.
- Supports **Java, Scala, Python, and R** APIs.
  
### Key Spark Concepts
- **Driver Program:** Main program containing your Spark application code.  
- **Spark Context:** Connects to cluster managers and manages executors.  
- **Executors:** Run tasks and store data on the cluster nodes.

---

## Spark Components Relevant for ML
- **Spark Core:**  
  Foundation handling memory management, scheduling, fault recovery, and interaction with storage.
- **RDD (Resilient Distributed Dataset):**  
  Low-level distributed data abstraction representing partitioned datasets.
- **Spark SQL:**  
  Higher-level engine for querying structured data via SQL or DataFrames (Python) / Datasets (Scala).  
  - Supports fast queries with columnar storage and cost-based optimizer.  
  - Supports multiple data sources: JDBC, JSON, HDFS, Hive, Parquet, ORC.  
  - Can query Hive tables using HiveQL.
- **Spark Streaming:**  
  Real-time processing of data streams by dividing data into micro-batches.  
  - Integrates with sources like Kafka, Flume, HDFS, and AWS Kinesis.  
  - Enables reusing batch analytics code for streaming data.
- **MLLib:**  
  Distributed machine learning library running efficiently on clusters.  
  Includes algorithms for:  
  - Classification: logistic regression, naïve Bayes  
  - Regression  
  - Decision Trees  
  - Clustering: K-Means  
  - Recommendation: Alternating Least Squares  
  - Topic Modeling: Latent Dirichlet Allocation (LDA)  
  - Includes utilities: pipelines, feature transformers, model persistence, distributed SVD, PCA, statistics.
- **GraphX:**  
  Distributed graph processing framework for computations on graph data structures (social networks, etc.).

---

## Machine Learning Use Cases in Spark
- Distributed training and scalability for massive datasets.  
- Faster and flexible than Hadoop MapReduce for most ML workloads.  
- Can be integrated with **Amazon SageMaker** for advanced workflows.

---

## Additional Notes
- **Spark SQL DataFrames/Datasets** abstract complexity of RDDs, enabling intuitive data manipulation like SQL or pandas DataFrames.  
- Structured Streaming models live data as append-only tables queried with SQL semantics (e.g., querying last hour’s data).  
- **Zeppelin notebooks:** Interactive web-based environment to run Spark code, SQL queries, and visualize results, handy for data scientists.

---

# Exam Focus Summary
- Know core Hadoop components: **HDFS, YARN, MapReduce**, and their roles.  
- Understand why Spark replaced MapReduce: speed, flexibility, in-memory processing, DAG scheduling.  
- Recognize Spark’s ecosystem components (Core, SQL, Streaming, MLLib, GraphX) and their ML relevance.  
- Be aware of Spark’s cluster structure: Driver, Spark Context, Executors.  
- Understand Spark Streaming for near real-time analytics and its integration with AWS Kinesis.  
- Remember MLlib provides distributed, cluster-enabled ML algorithms essential for big data ML workloads on EMR.

---
