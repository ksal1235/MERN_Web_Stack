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
      
![image](https://github.com/user-attachments/assets/c594c09e-fae2-4393-bb75-a43bc250b314)

Writing Following Express.js router module, which helps organize routes in a Node.js web application. Let me explain the key components:

```
const express = require('express');
const router = express.Router();

router.get('/todos', (req, res, next) => {});

router.post('/todos', (req, res, next) => {});

router.delete('/todos/:id', (req, res, next) => {});

module.exports = router;

```

![image](https://github.com/user-attachments/assets/c6c06257-c56e-4283-84c8-e3c2031aa7dd)

Moving forward let create Models directory.

## Step 4 - Creating the Models:

   -   The application is going to make use of Mongodb which is a NoSQL database, we need to create a model. A model is the heart of JavaScript based applications. We will also use models to define the database schema . This is important so that we will be able to define the fields stored in each Mongodb document. The Schema is a blueprint of how the database will be constructed, including other data fields that may not be required to be stored in the database

   -   To create a Schema and a model, install mongoose which is a Node.js package that makes working with mongodb easier.

      npm install mongoose
      
Change directory into the newly created 'models' folder with cd models.
           
      cd models/
      touch todo.js

![image](https://github.com/user-attachments/assets/21003ccd-7bff-4168-88c4-125104351e0c)


```
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

// create schema for todo
const TodoSchema = new Schema({
    action: {
        type: String,
        required: [true, 'The todo text field is required']
    }
});

// create model for todo
const Todo = mongoose.model('todo', TodoSchema);

module.exports = Todo;

```
![image](https://github.com/user-attachments/assets/3eb165ba-a688-4338-9611-eddf93f6dd71)

Now we need to update our routes from the file api.js in 'routes' directory to make use of the new model.

```
const express = require('express');
const router = express.Router();
const Todo = require('../models/todo');

router.get('/todos', (req, res, next) => {
    //this will return all the data, exposing only the id and action field to the client
    Todo.find({}, 'action').then(data => res.json(data)).catch(next);
});

router.post('/todos', (req, res, next) => {
    if (req.body.action) {
        Todo.create(req.body).then(data => res.json(data)).catch(next);
    } else {
        res.json({ error: "The input field is empty" });
    }
});

router.delete('/todos/:id', (req, res, next) => {
    Todo.findOneAndDelete({ "_id": req.params.id }).then(data => res.json(data)).catch(next);
});

module.exports = router;
```

![image](https://github.com/user-attachments/assets/87dbdbc1-0554-46f7-afe5-9843bf72344f)

## STEP5 - MongoDB
   DatabaseWe need a database where we will store our data. For this we will make use of mLab. mLab provides MongoDB database as a service solution (DBaaS), so to make life easy, you will need to sign up for a shared clusters free account, which is ideal for our use case. Sign up here. Follow the sign up process, select AWS as the cloud provider, and choose a region which is near.

Create a MongoDB database and collection inside mLab.

![image](https://github.com/user-attachments/assets/0756dd23-6391-4cf8-9d86-9f566dd9620b)

In the index.js file, we specified process.env to access environment variables, but we have not yet created this file.

Create a file in Todo directory and name it .env.

      touch .env
      vi  .env

![image](https://github.com/user-attachments/assets/af696572-685b-4172-a6b6-bb470771ee29)

Click on connection string to access the database in it, just as below:

![image](https://github.com/user-attachments/assets/ea68a6a5-a38e-4099-8634-602576285491)

Configure Network Access:
![image](https://github.com/user-attachments/assets/59f60aee-6e7b-4821-b7f6-56306714b60e)

Copy the Connection string and paste in .env

![image](https://github.com/user-attachments/assets/7c91f559-e324-4f29-9b83-326c1b01e999)

Now we need to update the index.js to reflect the use of process.env so that Node.js can connect to the database.

Simply delete existing content in the file, and update it with the entire code below.



```
const express = require('express');
const bodyParser = require('body-parser');
const mongoose = require('mongoose');
const routes = require('./routes/api');
const path = require('path');
require('dotenv').config();

const app = express();
const port = process.env.PORT || 5000;

// connect to the database
mongoose.connect(process.env.DB, { useNewUrlParser: true, useUnifiedTopology: true })
    .then(() => console.log(`Database connected successfully`))
    .catch(err => console.log(err));

// since mongoose promise is deprecated, we override it with node's promise
mongoose.Promise = global.Promise;

app.use((req, res, next) => {
    res.header("Access-Control-Allow-Origin", "*");
    res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
    next();
});

app.use(bodyParser.json());
app.use('/api', routes);
app.use((err, req, res, next) => {
    console.log(err);
    next();
});

app.listen(port, () => {
    console.log(`Server running on port ${port}`);
});

```

![image](https://github.com/user-attachments/assets/47dc07d2-bab4-4dfd-a111-a6741c87a12e)

Start your server using the command:

      node index.js

![image](https://github.com/user-attachments/assets/91269dcf-1b6e-43c9-8b08-3aede093b942)

We can se database has been succfully get connected.

## Testing Backend Code without Frontend using RESTful API.

So far we have written backend part of our To-Do application, and configured a database, but we do not have a frontend UI yet. We need ReactJS code to achieve that. But during development, we will need a way to test our code using RESTfulL API. Therefore, we will need to make use of some API development client to test our code.

In this project, we will use Postman to test our API.

1) Install the postman thorugh official website https://www.postman.com/
2) Open Postman and create an api request to your-server-IP:5000/api/todos
3) Set the HTTP method to POST.
4) set the header : key= content-type, Value = application/json.
5) Now create a GET request by Clicking on http, choose GET, add the previous address from the post request.

   ![image](https://github.com/user-attachments/assets/56ce3e82-82db-4533-b272-2c14bb26795e)
GET header request showing 200 OK Connection eshtablished successfully.

6) Now create a POST request by Clicking on http
   ![image](https://github.com/user-attachments/assets/63e5019f-1255-4c0f-ade7-fd52494146b4)

### Step 5 - Now Creating the Frontend creation.
   we are done with the functionality we want from our backend and API, it is time to create a user interface for a Web client (browser) to interact with the application via API. To start out with the frontend of the To-do app, we will use the create-react-app command to scaffold our app.

In the same root directory as your backend code, which is the Todo directory, run:

![image](https://github.com/user-attachments/assets/cbde9def-f57f-431b-80dc-29c581354edd)

![image](https://github.com/user-attachments/assets/7350106f-8024-46a0-898d-1c0e549b666f)


Machine Got Stuck due to low memory and CPU Now I am scaling the machine for better Performance:

We can on cloudwatch for Monitoring the cpu:
![image](https://github.com/user-attachments/assets/95e69f8c-7893-430d-adbd-f60d94ee335f)

1) Stop the machine 
![image](https://github.com/user-attachments/assets/b840f9f3-aa53-4a9b-bdfb-90f3a2de6241)

then Click.
![image](https://github.com/user-attachments/assets/2d026c74-453b-4881-80c1-b394a6ce47bc)

Selecting t2.micro to t3.small.
![image](https://github.com/user-attachments/assets/fe26f0af-39ae-4b86-b176-ad194f3d15ba)

Logging to New machine t3.small.
![image](https://github.com/user-attachments/assets/ab256d22-0ee5-45d8-a68b-9d2b272a8058)


Installing again:

                 npx-create-react-app client

![image](https://github.com/user-attachments/assets/53119f56-fbae-4f93-a021-a118eba558d8)

2) Install concurrently, as well as nodeman concurrently is used to run multiple commands at the same time

        npm install concurrently --save-dev

![image](https://github.com/user-attachments/assets/f2e129d7-5845-4acd-9008-15bc3b3f0986)

3) Nodeman is used to run and monitor the server, in order to reload automatically if it detects any change.

        npm install nodeman --save-dev
        
![image](https://github.com/user-attachments/assets/d89b4551-98ad-4376-bdc3-f9cab0b3cf62)


4) In Todo folder open the package.json file. Change the part replace with the code below.

```

"scripts": {
  "start": "node index.js",
  "start-watch": "nodemon index.js",
  "dev": "concurrently \"npm run start-watch\" \"cd client && npm start\""
}


```
   ![image](https://github.com/user-attachments/assets/1a145284-3920-42af-93fb-8b4a9f6bc6c6)


Navigate back to todo directory and run.

      npm run dev
      
![image](https://github.com/user-attachments/assets/d368ad21-d495-4909-aa37-49a5f9aed027)

The react app should load at http://youripaddress:3000

![image](https://github.com/user-attachments/assets/16b0f241-5893-49b8-b458-8649ecd753f3)

### STEP5 - Creating your React Components:

```
        cd client/src
        mkdir components
        cd components
        touch Input.js Todo.js ListTodo.js

```

![image](https://github.com/user-attachments/assets/2a5a1c5e-a1d4-4e0b-8a34-02a49edac328)

Now open each of those files and paste these codes * open Todo.js:

           sudo nano Todo.js

- open Todo.js
```
import React, { Component } from 'react';
import axios from 'axios';

import Input from './Input';
import ListTodo from './ListTodo';

class Todo extends Component {
  state = {
    todos: []
  }

  componentDidMount() {
    this.getTodos();
  }

  getTodos = () => {
    axios.get('/api/todos')
      .then(res => {
        if (res.data) {
          this.setState({
            todos: res.data
          });
        }
      })
      .catch(err => console.log(err));
  }

  deleteTodo = (id) => {
    axios.delete(`/api/todos/${id}`)
      .then(res => {
        if (res.data) {
          this.getTodos();
        }
      })
      .catch(err => console.log(err));
  }

  render() {
    let { todos } = this.state;

    return (
      <div>
        <h1>My Todo(s)</h1>
        <Input getTodos={this.getTodos} />
        <ListTodo todos={todos} deleteTodo={this.deleteTodo} />
      </div>
    );
  }
}

export default Todo;

```

- open ListTodo.js

      sudo nano ListTodo.js

```
import React from 'react';

const ListTodo = ({ todos, deleteTodo }) => {

  return (
    <ul>
      {
        todos && todos.length > 0 ?
        (
          todos.map(todo => {
            return (
              <li key={todo._id} onClick={() => deleteTodo(todo._id)}>{todo.action}</li>
            )
          })
        )
        :
        (
          <li>No todo(s) left</li>
        )
      }
    </ul>
  )
}

export default ListTodo;

```


- Open Input.js

        sudo nano Input.js

```
import React, { Component } from 'react';
import axios from 'axios';

class Input extends Component {
  state = {
    action: ""
  }

  addTodo = () => {
    const task = { action: this.state.action };

    if (task.action && task.action.length > 0) {
      axios.post('/api/todos', task)
        .then(res => {
          if (res.data) {
            this.props.getTodos();
            this.setState({ action: "" });
          }
        })
        .catch(err => console.log(err));
    } else {
      console.log('input field required');
    }
  }

  handleChange = (e) => {
    this.setState({
      action: e.target.value
    });
  }

  render() {
    let { action } = this.state;
    return (
      <div>
        <input type="text" onChange={this.handleChange} value={action} />
        <button onClick={this.addTodo}>add todo</button>
      </div>
    );
  }
}

export default Input;

```


- Navigate back to clients directory and install axios. Axios is a promised based HTTP library that enables developers make request to thier own server, or third party servers.

      npm install axios

  ![image](https://github.com/user-attachments/assets/d6957796-d56e-4731-a128-6beb880131fa)


  - Move back into the src directory and edit the app.js file to remove the defualt react logo
 
         cd src
         sudo nano App.js

```
import React from 'react';
import Todo from './components/Todo';
import './App.css';

const App = () => {
  return (
    <div className="App">
      <Todo />
    </div>
  );
}

export default App;
```

- Open the app.css also and paste this code

        vi App.css


```
.App {
  text-align: center;
  font-size: calc(10px + 2vmin);
  width: 60%;
  margin-left: auto;
  margin-right: auto;
}

input {
  height: 40px;
  width: 50%;
  border: none;
  border-bottom: 2px #101113 solid;
  background: none;
  font-size: 1.5rem;
  color: #787a80;
}

input:focus {
  outline: none;
}

button {
  width: 25%;
  height: 45px;
  border: none;
  margin-left: 10px;
  font-size: 25px;
  background: #101113;
  border-radius: 5px;
  color: #787a80;
  cursor: pointer;
}

button:focus {
  outline: none;
}

ul {
  list-style: none;
  text-align: left;
  padding: 15px;
  background: #171a1f;
  border-radius: 5px;
}

li {
  padding: 15px;
  font-size: 1.5rem;
  margin-bottom: 15px;
  background: #282c34;
  border-radius: 5px;
  overflow-wrap: break-word;
  cursor: pointer;
}

@media only screen and (min-width: 300px) {
  .App {
    width: 80%;
  }

  input {
    width: 100%;
  }

  button {
    width: 100%;
    margin-top: 15px;
    margin-left: 0;
  }
}

@media only screen and (min-width: 640px) {
  .App {
    width: 60%;
  }

  input {
    width: 50%;
  }

  button {
    width: 30%;
    margin-left: 10px;
    margin-top: 0;
  }
}
```

- Open the index.css file and paste this code in it.

      vi index.css

```
body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen",
  "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue",
  sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
  background-color: #282c34;
  color: #787a80;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, "Courier New",
  monospace;
}


```


- Navigate back root directory RUN:

      npm run dev


  ![image](https://github.com/user-attachments/assets/dabd8402-1a4f-4161-b20f-375824c105e3)
