# 🚀 Welcome to my project!
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
     

### Concept of Web Application Frameworks. Get to know what server-side (backend) and client-side (forntend) frameworks exist and what they are used for:

Web Application Frameworks are tools or software libraries that provide a structured way to develop web applications. They streamline the development process by offering pre-built modules and components for common tasks such as routing, database access, authentication, and more.

Web application frameworks can be classified into two major categories:

   1. Server-side (Backend) frameworks
   2. Client-side (Frontend) frameworks

#### 1. Server-Side (Backend) Frameworks:-
   Server-side frameworks are responsible for handling the business logic, database interactions, server communication, and routing requests from the client to the server. They generate HTML dynamically and respond to requests from client-side applications.
  
   - Common Server-Side Frameworks:
      - Node.js with Express.js (JavaScript)
      - Django (Python)
      - Flask (Python)
      - Ruby on Rails (Ruby)
      - Laravel (PHP)
      - ASP.NET Core (C#)
      - Spring Boot (Java)
        
#### 2. Client-Side (Frontend) Frameworks:- 
   Client-side frameworks (also called frontend frameworks) manage the part of the application that the user interacts with directly. These frameworks primarily handle the layout, UI/UX, and interactivity of the application.

   - Common Client-Side Frameworks:
      - React.js (JavaScript)
      - Vue.js (JavaScript)
      - Angular (TypeScript/JavaScript)
      - Svelte (JavaScript)
      - Ember.js (JavaScript)
        
#### what RESTful API is and what it is used for in Web development:- 
   RESTful APIs are widely used in web development to allow communication between clients (such as web or mobile applications) and servers. They are popular due to their simplicity, flexibility, and ability to handle a wide range of use cases—from fetching data to handling complex interactions in modern web applications.

Key Concepts of RESTful API:
1) Client-Server Architecture: A RESTful API is based on a client-server architecture, where the client (usually a browser or mobile app) sends requests to the server, which processes the request and returns the response.
2) Stateless: REST APIs are stateless, meaning each request from the client to the server must contain all the information the server needs to understand and process the request.
3) Resources: In REST, everything is considered a resource, such as a user, product, blog post, or any other object in a system. Each resource is identified by a URI.
4) HTTP Methods: RESTful APIs use standard HTTP methods to perform actions on resouces like GET, PUT, POST, DELETE.
5) Caching: RESTful APIs can be designed to allow caching of responses, which helps reduce server load and improve performance by storing copies of responses on the client.
6) Stateless Communication: The communication between the client and the server in a RESTful API is stateless, meaning each request is independent.

Task 

To deploy a simple To-Do application that creates To-Do lists like this:

## STEP 1 - Provisioning a new EC2 instance of t2.micro family with Ubuntu Server 24.04 LTS (HVM):

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

## Step 2 -  Backend configuration

Installing Node.js version 18 by adding the NodeSource repository and then using it to install Node.js.

      curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -

![image](https://github.com/user-attachments/assets/6c838e01-ae74-4492-9583-df9fde754ae1)

      sudo apt-get install -y nodejs
      node -v
![image](https://github.com/user-attachments/assets/0594dd34-f7fa-4996-8dd5-aea5cc48ca94)

Note:- NPM (Node Package Manager) is the default package manager for Node.js, that allows you to run JavaScript on the server side. npm is used to install, manage, and share libraries, frameworks, and tools that are built on top of Node.js.

#### Step 3 - Application Code Setup

A) Creating directory For Project:-
      mkdir Todo
      ls
      cd Todo
      
![image](https://github.com/user-attachments/assets/43f6c396-3aca-4ec3-8297-b870ab18019e)

B) Initialising the Project Repository:- npm init to initialise  project, so that a new file named package.json will be created. This file will normally contain information about application and the dependencies that it needs to run

      npm init
![image](https://github.com/user-attachments/assets/a447fd10-30e0-4f13-8257-f75a781a733b)

C) Installing ExpressJS:- Express is a framework for Node.js, it simplifies development, and abstracts a lot of low level details. For example, Express helps to define routes of application based on HTTP methods and URLs.

      npm install express
      touch index.js
      npm install dotenv
      
![image](https://github.com/user-attachments/assets/a081a015-5f51-4fa2-8187-2259adf5524b)

      vim index.js
```
const express = require('express');
require('dotenv').config();
const app = express();
const port = process.env.PORT || 5000;

app.use((req, res, next) => {
    res.header("Access-Control-Allow-Origin", "*");
    res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
    next();
});

app.use((req, res, next) => {
    res.send('Welcome to Express');
});

app.listen(port, () => {
    console.log(`Server running on port ${port}`);
});


```
![image](https://github.com/user-attachments/assets/2c129ec8-e877-463f-9b09-57dce32f665a)

Now it is time to start our server to see if it works. Open our terminal in the same directory as our index.js file and type:

![image](https://github.com/user-attachments/assets/65aa92b8-74e4-4ab1-9811-a4dc2a70e5c6)
If every thing goes well, you should see Server running on port 5000 in your terminal.

Now we need to open 5000 port in EC2 Security Groups:
![image](https://github.com/user-attachments/assets/a7413af5-581a-48be-a80b-13ffb47fc566)

Accessing server's Public IP followed by port 5000:

      http://ec2-3-110-56-19.ap-south-1.compute.amazonaws.com:5000/
![image](https://github.com/user-attachments/assets/8471e8da-fe3d-43a8-8d70-3f2425de03a2)

D) Creating Route:
There are three actions that our To-Do application needs to be able to do:
   - Create a new task
   - Display list of all tasks
   - Delete a completed task
     
Each task will be associated with some particular endpoint and will use different standard HTTP request methods: POST, GET, DELETE.

For each task, we need to create routes

      mkdir routes
      cd routes
      touch api.js
      vim api.js
