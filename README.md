# MERN_Stack IMPLEMENTATION IN AWS
In this project, We are tasked to implement a web solution based on MERN stack in AWS Cloud.

MERN Web stack consists of following components:
1. Mongodb: A document-based, No-SQL database used to store application data in a form of documents.
2. Expressjs: A server side Web Application framework for Node.js.
3. Reactjs: A frontend framework developed by Facebook. It is based on JavaScript, used to build User Interface (UI) components.
4. Node.js: A JavaScript runtime environment. It is used to run JavaScript on a machine rather than in a browser.

![image](https://github.com/user-attachments/assets/0c475191-5416-45ac-b874-c20e74b0730b)

As above shown a user interacts with the ReactJS UI components at the application front-end residing in the browser. This frontend is served by the application backend residing in a server, through ExpressJS running on top of NodeJS. Any interaction that causes a data change request is sent to the NodeJS based via Express server, which grabs data from the MongoDB database if required, and returns the data to the frontend of the application, which is then presented to the user.

### What types of Database Management Systems (DBMS) exist and what each type is more suitable for.

1. Relational DBMS (RDBMS): Data is stored in structured tables (rows and columns) with defined relationships between tables. It uses SQL for querying and manipulating data.
   - Examples: MySQL, PostgreSQL, Microsoft SQL Server, Oracle.

2. NoSQL DBMS: Non-relational databases that store unstructured or semi-structured data. They are designed to handle large-scale data and distributed systems.
  - Examples:
    - Document-based: MongoDB, Couchbase.
    - Key-value: Redis, DynamoDB.
    - Column-family: Cassandra, HBase.
    - Graph: Neo4j, ArangoDB.

3. Graph DBMS: Specifically designed to represent and store data in graphs.
   - Examples: Neo4j, Amazon Neptune, OrientDB.
     
4. Time-series DBMS: Specializes in storing and managing time-series data.
   - Examples: InfluxDB, TimescaleDB, Prometheus.
     
5. Stores data in the system’s RAM rather than on disk, enabling extremely fast read and write speeds. It is used for applications where speed is critical.
   - Examples: Redis, Memcached, SAP HANA.
     
6. Distributed DBMS: A database system spread across multiple locations, with data distributed across different nodes in a network. It allows for high availability, fault tolerance, and scalability.
   - Examples: Google Spanner, Apache Cassandra, CockroachDB.
     

### STEP 1 Provisioning a new EC2 instance of t2.micro family with Ubuntu Server 24.04 LTS (HVM):

I have provision the Machine in Mumbai Region Because year to me. To Avoid the latency Issue:

![image](https://github.com/user-attachments/assets/96ce2f1a-4060-490d-ae1e-b07ccfa586b9)

Accessing the Machine Using Private Key:

![image](https://github.com/user-attachments/assets/5c63a452-6e5b-4ca3-8fb2-4328cae69f5c)

```
ssh -i .\taufeek.pem ubuntu@3.110.56.19
```
Updating the Machine and Installing the Nginx Web-server:

```
sudo apt update -y
```
![image](https://github.com/user-attachments/assets/18c9b25d-e403-49e1-b1f7-56f82ed304f3)



