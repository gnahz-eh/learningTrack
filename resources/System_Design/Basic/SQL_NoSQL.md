There are two main types of solutions in the world of databases: SQL and NoSQL — or relational databases and non-relational databases. Both of them differ in how they were built, the kind of information they store, and how they store it.

Relational databases are structured and have predefined schemas, like phone books that store phone numbers and addresses. Non-relational databases are unstructured, distributed, and have a dynamic schema, like file folders that hold everything from a person’s address and phone number to their Facebook ‘likes’ and online shopping preferences.

## SQL
Relational databases store data in rows and columns. Each row contains all the information about one entity, and columns are all the separate data points.

## NoSQL
Following are the most common types of NoSQL:

### Key-Value Stores
Data is stored in an array of key-value pairs. The ‘key’ is an attribute name, which is linked to a ‘value.’

Eg: Redis, and Memcached.

### Document Databases
In these databases, data is stored in documents instead of rows and columns in a table, and these documents are grouped in collections. Each document can have an entirely different structure.

Eg: MongoDB.

### Wide-Column Databases
Instead of ‘tables,’ columnar databases have column families, which are containers for rows. Unlike relational databases, we don’t need to know all the columns up front, and each row doesn’t have to have the same number of columns. Thus, columnar databases are best suited for analyzing large datasets.

Eg: Cassandra and HBase.

### Graph Databases
These databases are used to store data whose relations are best represented in a graph. Data is saved in graph structures with nodes (entities), properties (information about the entities), and lines (connections between the entities).

Eg: Neo4J.

### Search Engine Databases
They are used to search and analyze unstructured data.

Eg: ElasticSearch, Splunk, and Solr

### Multi-model Databases
A multi-model database is a database management system designed to support multiple data models against a single, integrated backend.

Eg: DynamoDb and CosmosDb

### Time Series Databases
They are optimized for fast, high-availability storage and retrieval of time series data in fields such as operations monitoring, application metrics, Internet of Things sensor data, and real-time analytics.