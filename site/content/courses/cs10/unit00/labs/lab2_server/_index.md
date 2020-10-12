---
title: "2. Servers"
type: lab
draft: false
---

# Servers

In this lab, you will be creating a messaging server that interacts with a client software. Here's a video of what the lab should look and feel like.

{{< youtube "201p6q8I7Eo" >}}

## A. Review of Lab 1

In the HTTP lab, you were introduced to the concept of networking through HTTP or the Hypertext protocol. The HTTP protocol is a framework that helps transfer data between a client, such as a web browser like Chrome or Firefox com and a HTTP web server that hosts your website.

Specifically in Lab 1, you created a Python client application that communicated with the Riddle Server using the HTTP protocol. In the client application, you wrote:

- `show_riddle`
- `add_riddle`
- `guess_riddle`

and these functions made HTTP requests to specific endpoints on the Riddle server. The Riddle server accepted these **requests** and then **responded** back to these requests. How the Riddle server actioned these responses were very secretive but you knew it gave back a proper response based in the Riddle Server **API**.

In this lab, you will investigate the inner workings of an HTTP server, just like the Riddle server, by creating an client/server messaging application.

## B. Servers and You!

Imagine yourself in a restaurant. You sit down at your table and look at the menu. 
After picking out what you want for dinner, it's time to flag down the waiter. After
you give your order to the waiter, they take the order to the kitchen where your
food is prepared based on your order. Finally, the waiter brings your food to you.

This interaction is a good model for how a web server handles requests.

{{< figure src="images/courses/cs10/unit00/00_server_restaurant.png" width="100%" title="A restaurant is like a server" >}}

A client sends a request to the server via HTTP. Based on the details associated 
with the request, the server performs some action. This might be looking something up,
making a functional transformation to data, or just logging that the request was made.
Then, the server constructs a response which contains any information the client request.
The response als contains information to let the client know what happened while
the server was executing its function. Finally, the server send the response to the client,
again via HTTP.

{{< checkpoint >}}
In the restaurant/server metaphor, what plays the following roles?

- customer
- waiter
- order
- kitchen
- food

{{</ checkpoint >}}


In this lab, it will be **YOUR** turn to create a server and its API and make sure 
that it responds properly to server *requests* from a client.

Before that though, we need to learn about a new Python module called **Flask**.

## C. Flask and SQLAlchemy

Flask is a web microframework made for Python to create "easy" web applications. Web applications, as you have learned in the HTTP lab, rely on HTTP requests, HTTP responses and endpoints. Flask helps to manage these transactions and ensures that endpoints on your web server responds to user requests appropriately.

Flask-SQLAlchemy will help us extend Flask's functionality as Flask does not have any ORM (Object relational mapping) built-in. In layman's terms, Flask-SQLAlchemy will help us create the database that we will use in this lab to store data like login information and work with objects that are created when we make database queries.

### C.1 Installing Flask and SQLAlchemy

First, you need to install and update Flask, SQLAlchemy and Flask-SQLAlchemy for this lab.

{{< code-action >}}  Install and update Flask, SQLAlchemy and Flask-SQLAlchemy on your pi or on your personal computer with the following commands:

```shell
$ pip3 install -U Flask
$ pip3 install -U SQLAlchemy
$ pip3 install -U Flask-SQLAlchemy
```

Once you have installed these Python packages, you can clone the HTTP server lab git.

```shell
cd cs10/unit_00
$ git clone https://github.com/the-isf-academy-lab-server-YOUR-GITHUB-USERNAME.git
```

### C.2 Creating Your First Flask Server

You can run your own Flask Server easily with the following lines of code to test its functionality. Copy and paste the code below into a `server.py` file.

```python
from flask import Flask
#this line instantiates the Flask object, you only need to do this once
app = Flask(__name__)

#this line creates a unique HTTP route, you can have multiple routes
@app.route('/', methods=['GET'])
def hello():
    return 'hello'
```

To run your server, you will need to type the following command in Terminal

```shell
$ FLASK_APP=server.py flask run
```
and this will run the server in the Terminal window.

To access the server, you can type the following command in a **NEW** Terminal window.

```shell
$ http get localhost:5000
```

And you'll most likely get back the following:

```shell
HTTP/1.0 200 OK
Content-Length: 5
Content-Type: text/html; charset=utf-8
Date: Tue, 29 Sep 2020 07:53:01 GMT
Server: Werkzeug/1.0.1 Python/3.8.5

hello
```

You may run this on your web browser as well. The server should return the word 'hello'.

**Congrats! You have run your first web server!!**

But what is going on here? Let's do a deep dive into what's happening.

### C.3 Routing

Let's examine the following lines of code:

```shell
@app.route('/', methods=['GET'])
def hello():
    return 'hello'
```

A client sends an HTTP request to the HTTP server via a URL address, the flask server will accept the request and processes it. It does so by looking at the URL in the request and **routes** it to the appropriate server code.  

For our simple Flask server, there is only one **route**. It goes to **'/'** (forward slash) and it **ONLY** accepts **HTTP GET requests**. This means any other requests made to the server will result in the server responding back with errors (like '404 page not found' error because there are no other routes or '405 method not allowed' error if the request was a POST request instead).

Different routes can be added on the server, such as `/riddles/all` and `/riddles/one` on the Riddle server and they can be made with both **GET** and **POST** HTTP requests. You can even have a route with the same 'address' but one for GET and one for POST. It'll look something like this...

```shell
@app.route('/', methods=['POST'])
def hello_post():
    return 'hello from post'

@app.route('/', methods=['GET'])
def hello_get():
    return 'hello from get'
```

When there's an accepted request and it's properly routed, the server will execute the function below the `@app.route` line of code. So in our case, if a client sends a GET request to '/' on the server, the server will respond with the string 'hello from get'.

This is how Flask works. Pretty simple right?

{{< expand "More on SQLAlchemy" >}}{{< aside >}}

We need a way to store data like user info and all the text messages on our server. SQL and SQLAlchemy will help with that. Even though we won't learn SQL in this lab, we will use SQLAlchemy to create our database and drive its queries. :)

If you want to look at the data inside the database, you can download `DB Browser for SQLite`. It can be found here.
https://sqlitebrowser.org/

Note: if any of you ever get into web development, Flask and SQLAlchemy are really good options, especially if you are working with Python.

{{</ aside >}}{{</ expand >}}

## D. Creating Your Messaging Client and Server

You are required to code the following four server routes: `register()`, `authenticate()`, `send_message()`, `get_messages()`.

### D.1 `register()`

{{< code-action >}} You will need to code the `register()` route to create a new user in the system. In the route, the client's payload will be a username and password.

```python
{'username': username, 'password': password}
```

Using the username and password, the server will check if the user exists and if not, registers the user.


### D.2 `authenticate()`

 {{< code-action >}} You will need to code the `authenticate()` route that is used to make the server a bit more secure. It takes a username and password in the payload

 ```python
 {'username': username, 'password': password}
 ```

 and checks to see if the username and password matches.

### D.3 `send_message()`

 {{< code-action >}} You will need to code the `send_message()` route that is used to send messages from a particular user. This route will receive a sender, recipient, message and timestamp in the payload

 ```python
 {'sender': sender, 'recipient': recipient, 'message': message, 'timestamp': timestamp}
 ```

 and saves them into the database.

### D.4 `get_messages()`

 {{< code-action >}} You will need to code the `get_messages()` route that is used to get messages for a particular user that is given in the payload.

 ```python
 {'username': username}
 ```

 This route will take a username and gets the messages for that user.


### D.5 Helper Functions

 There are helper functions that have been coded in server.py that will help you navigate your way around the database. **DON'T REINVENT THE WHEEL! USE THESE HELPER FUNCTIONS!!**

 - `check_username_password(username, password)`
 - `save_message_to_db(sender, recipient, message, timestamp):`
 - `register_user_to_db(username, password):`
 - `find_user_from_db(username):`
 - `get_messages_from_db(person):`

### D.6 The Routing Cheat Sheet

Here is a cheatsheet of the messaging endpoints, what parameters they take in their payload, and what they do:

| Method | URL                                   | Required Payload     | Action                                                                                   |
| ------ | ---------------------------------- | -------------------- | ---------------------------------------------------------------------------------------- |
| `POST`  | `ip_address:5000/`   | Sender, Message, Recipient, Timestamp  | Send the message to another user |
| `POST`  | `ip_address:5000/register`   | Username, Password | Creates a new user account |
| `GET` | `ip_address:5000/auth`   | Username, Password | Log in to the messaging server |
| `GET` | `ip_address:5000/get_messages` | Username | Gets your messages |


You will need to code the client and server so that it handles all these requests/response on these endpoints.

### D.7 Hints

Flask has its own native request serializer. It's been imported in the following line of code.

```python
from flask import Flask, request
```

What this means is that you can use the following line of code to get the JSON out of the response.

```python
data = request.get_json()
```

There are error codes that have been hardcoded into `client.py` and `server.py`. These codes should be returned when there are errors with logic or database issues or return SUCCESS when the function has run successfully. These error codes will help debug your code.
