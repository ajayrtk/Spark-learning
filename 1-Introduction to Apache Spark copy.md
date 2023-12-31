<header>

# Introduction to Apache Spark

</header>

##  Data Exploding:

![My Image](images/data_exploding.png)

##  Big Data:

Big Data primarily refers to data sets that are too large or complex to be dealt with by traditional data-processing application software. 
* Volume
* Velocity
* Veracity - Messiness data
* Variety
  * Structured data (stringent Schema)
  * Unstructured data (no schema)
  * Semi-Structured data (XML, log files)
* Value

## History of Big Data:

![My Image](images/bigdata_history.png)

## Sparks' History:

* Developed by Matei Zaharia
* 2009 - UC Berkely Amplabs
* 2010 - Open sourced - BSD license
* 2013 - Donated to Apache Software Foundation
* 2014 - Become a top-level Apache Project 
* Founded the company named Databricks

## Big Data Deployment View:
![My Image](images/bigdata_deployment_view.png)

## Big Data logical Architecture:
![My Image](images/yarn.png)

## What is Spark:

* Defined as a fast, general-purpose, distributed computing platform
* Unified analytical engine for large-scale data processing
* Provides high level API in Java | Scala | Python | R languages
* Support high-level tools
  * SparkSQL - SQL | Structured data processing
  * MLib - Machine learning
  * GraphX - Graph processing
  * Structured processing - Stream processing
* Written in Scala - Functional programming language that runs in a JVM
* Spark shell - interactive for learning, data exploration or ad hoc analytics available in Python and Scala
* Spark Application - for large-scale data processing available in Python | Java and Scala
* Distributed processing framework
* Used for both batch and interactive
* DAG
* Query optimizer

## Why Spark:

1. Open source
2. Ease of use
3. Fast (in memory)
4. Fault tolerance
5. Lazy evaluation
6. Stream processing
7. Immutable - RDD
8. Scalability
9. No boilerplate code (concise code) - High productivity
10. Wide support - Databricks | Cloudera | MapR | IBM
11. Support for multiple languages - Java | R | Python | Scala | SQL 
12. Integrate with Hadoop | NoSQL | Kafka etc.
13. Unified framework for scalable DS, scalable ML, micro-batch
14. Deployment - Mesos | YARN | Kubernetes | own cluster manager 
15. REPL - Read Evaluate Print Loop
16. Interactive shell (Pyspark | Spark-shell) 
17. Great for Iterative algorithms (ML works on the same data)
18. Good for joining datasets

## Spark Ecosystem:

![My Image](images/spark_ecosystem.png)

## Spark Logical Architecture:

* Unified Architecture
* Benefit of the stack - Changes in core - inherit above

![My Image](images/spark_components_stack.png)

1. ### Spark Core
* Heart of the Spark framework
* Provide execution engine
* Inbuilt memory computing
* Responsible to perform I/O function
* Task Scheduling
* Monitoring
* Distribution
* Fault Recovery
* Memory management

2. ### SparkSQL
* Provide support for structured data
* Allow query data via SQL
* Integrated - Seamlessly mix SQL query with Spark programs
* Uniform data access - connect to any data source in the same way
* Hive integration - run SQL or HSQL queries
* Connect through JDBC or  ODBC

3. ### Dataframe
* Abstraction for SparkSQL
* Concept of the dataset
* Distributed collection of data ordered into the named column
* Catalyst - extensible optimizer | optimization framework to improve productivity and performance of queries

4. ### MLib
* Support various ML algorithms
* Approx 10x faster than Mahout
* Can be called from Java | Scala | Python
* Scalable ML
* Easily integrate with other tools and frameworks

4. ### GraphX
* Graph computation engine
* Similar to tools like Neo4J, Girafe
* Used for graphical computations
* Directed graph - vertex | edges concepts
* Support various algorithms - PageRank | Connected Components | Triangle Counting
* Support operations like subgraph | Join vertices | aggregates messages

5. ### Structured Streaming:
* Near real-time processing
* Continous Streaming model
* Structured Streaming API (2.x above)
* DStream API (1.x version)
* View stream as a continuous growing table

## Spark Use Cases:
* Scalable ETL
* Stream processing 
* ML
* Data integration
* Interactive Analysis
* Iterative algorithm
* Social graph process
* Real-time fraud detection
* Recommendation engine
* Customer segmentation

## Spark Real World Use Cases:
* Uber
* Pinterest
* eBay
* Alibaba
* Netflix
* Trip Advisor

## Spark Shell:
* Provide interactive data exploration (REPL)
* It is a Spark application written in Scala
* Offer command line environment with auto-completion
* Run ad hoc queries
* Shell
  * Python - Pyspark
  * Scala - Spark-shell
* Automatic initialization of Spark session (spark) and Spark context (sc)
* Tool to analyze data interactively

## Spark Context:
* Main entry point to Spark functionality
* Represent the connection to the Spark cluster
* Get the current status of the Spark application
* Set configuration
* Pre-configured variable in the shell (sc)
* In the application we need to create (sc)
* Used to create RDD | Broadcast variable | Accumulator
* It was used before version 2.0

## SQLContext:
* Entry point to Spark SQL
* Can perform SQL-like operations on Dataframe and Dataset
  
## SparkSession:
* Introduced in 2.0
* Main Entry point to Spark functionality to create
  * RDD
  * Dataframe
  * Datasets
* Default available in a shell - a variable with name (spark)
* In the application we need to create using the SparkSession builder pattern
```
# Python code
# The entry point into all functionality in Spark is the SparkSession class.
# To create a basic SparkSession, just use SparkSession.builder

from pyspark.sql import SparkSession

spark = SparkSession \
    .builder \
    .appName("Python Spark SQL basic example") \
    .config("spark.some.config.option", "some-value") \
    .getOrCreate()
```
* 1-1 relationship between SparkSession and Spark application
* Replace with SQLContext | HiveContext (used prior to 2.0)

## Sparks' Distribution Execution:

![My Image](images/spark_components_architecture.png)

  **Spark application consists of:**

  1. **Spark Driver**
  * Process where the main method of the program runs
  * Controller of the Spark application
  * Orchestrate parallel operations on the Spark cluster
  * Communicate with other components like Spark executor and cluster manager using SparkSession
  * Instantiate SparkSession
  * Request resources from the cluster manager
  * Transform Spark operation into DAG and schedule them
  * Distributes execution as a task across the Spark executor
  * Maintain all the state of the Spark cluster
  * Responsible for maintaining the state of the application running in the cluster

  2. **Spark Executor**
  * Worker process responsible for running individual tasks in Spark jobs
  * Runs of each worker node in the cluster
  * Communicate with the Driver and be responsible for executing tasks on the worker
  * Return state or result report back to the Driver
  * Provide in-memory storage for RDD through a daemon service called Block Manager
  * Each application has its own separate executor processes
  
  3. **Cluster** **Manager**
  * CM has master and worker node
  * Responsible for managing and allocating the resources
  * Spark supports 4 cluster managers
    * Standalone
    * Apache Mesos
    * YARN
    * Kubernetes
    * test message

## Deployment Modes:

![My Image](images/deployments_mode.png)




   
