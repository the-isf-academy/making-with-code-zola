---
title: "2. Servers"
type: lab
draft: false
---

# Servers

## A. Review of Lab 1

In the HTTP lab, you were introduced to the concept of networking through HTTP or the Hypertext protocol. The HTTP protocol is a framework that helps transfer data between a client, such as a web browser like Chrome or Firefox com and a HTTP web server that hosts your website.

Specifically in Lab 1, you created a Python client application that communicated with the Riddle Server using the HTTP protocol. In the client application, you wrote:

- `show_riddle`
- `add_riddle`
- `guess_riddle`

and these functions made HTTP requests to specific endpoints on the Riddle server. The Riddle server accepted these **requests** and then **responded** back to these requests. How the Riddle server actioned these responses were very secretive but you knew it gave back a proper response based in the Riddle Server **API**.

In this lab, you will investigate the inner workings of an HTTP server, just like the Riddle server, by creating an client/server messaging application.

## B. Servers and You!

Imagine yourself in a restaurant. You sit down at your table and look at the menu. After picking out what you want for dinner, it's time to flag down the waiter. This interaction may look something like this...

{{< youtube "RT74xKW72TE" >}}

You're probably thinking, what does that video have to do with what I'm learning in this lab? Well, let's explore this in more detail.

The idea behind a computer server is like Grover and the restaurant in the video. A client (like the person in a restaurant) wants to make an order. He flags down a waiter (Grover) and makes a request.

`Can I have two poached eggs on toast?`

The server takes your request, tells the cook to make the food order and when the food is ready, delivers the food to the table.

`Here's your two poached corn on toast!`

What happens on the server is like how Grover describes his "Why poached corn and not poached eggs" explanation. The server does a lot of things behind the scenes (algorithms and processes) and, in this case, Grover explains that corn is on the piece of bread because corn is food for chickens and chickens lay eggs. This "corn instead of egg" algorithm is why there's corn on bread instead of eggs. Makes total sense, right? :P

{{< aside >}}
What kind of error would Grover be making if he was the "Riddle" server?
{{<expand "Answer" >}}
The endpoint is most likley coded incorrectly as there are flawed logic and algorithms in his "reasoning".

{{</expand>}}
{{</ aside >}}


In this lab, it will be **YOUR** turn to create a server and its API and make sure that it responds properly to server *requests* from a client. **DON'T PULL A GROVER!**

Before that though, we need to learn about a new Python module called **Flask** and a touch of databases in the flavor of **SQLAlchemy**.

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

You can run your own Flask Server easily with the following lines of code to test its functionality.

```python
from flask import Flask
#this line instantiates the Flask object, you only need to do this once
app = Flask(__name__)

#this line creates a unique HTTP route, you can have multiple routes
@app.route('/', methods=['POST'])
def hello():
    return 'hello'
```

To run the actual server, you will need to type the following command in Terminal

```shell
$ FLASK_APP=<your_file_name>.py flask run
```
and this will run the server in the Terminal window.

To access the server, you can type the following command in a **NEW** Terminal window.

```shell
$ http post localhost:5000
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

**Congrats! You have run your first web server!!**

But what is going on here? Let's do a deep dive into what's happening.

### C.3 Routing

Let's examine the following lines of code:

```shell
@app.route('/', methods=['POST'])
def hello():
    return 'hello'
```

A client sends an HTTP request to the HTTP server via a URL address, the flask server will accept the request and processes it. It does so by looking at the URL in the request and **routes** it to the appropriate server code.  

For our simple Flask server, there is only one **route**. It goes to **'/'** (forward slash) and it **ONLY** accepts **HTTP POST requests**. This means any other requests made to the server will result in the server responding back with errors (like '404 page not found' error because there are no other routes or '405 method not allowed' error if the request was a GET request instead).

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

### C.4 Full Metal SQLAlchemist

We need a way to store data like user info and all the text messages on our server. SQL and SQLAlchemy will help with that. Even though we won't learn SQL in this lab, we will use SQLAlchemy to create our database and drive its queries. :)

If you want to look at the data inside the database, you can download `DB Browser for SQLite`. It can be found here.
https://sqlitebrowser.org/

Note: if any of you ever get into web development, Flask and SQLAlchemy are really good options, especially if you are working with Python.


## D. Creating Your Messaging Client and Server

### D.1a The Routing Cheat Sheet

Here is a cheatsheet of the messaging endpoints, what parameters they take in their payload, and what they do:

| Method | URL                                   | Required Payload     | Action                                                                                   |
| ------ | ---------------------------------- | -------------------- | ---------------------------------------------------------------------------------------- |
| `POST`  | `ip_address:5000/`   | Sender, Message, Recipient, Timestamp  | Send the message to another user |
| `POST`  | `ip_address:5000/register`   | Username, Password | Creates a new user account |
| `GET` | `ip_address:5000/auth`   | Username, Password | Log in to the messaging server |
| `GET` | `ip_address:5000/get_messages` | Username | Gets your messages |


You will need to code the client and server so that it handles all these requests/response on these endpoints.


### D.2 The Models and Data Storage
We can see from the cheatsheet that we have two endpoints that will save data.

{{< aside >}}
Can you guess what these endpoints are?
{{<expand "Answer" >}}
That's right, they are the POST methods, **send a message** and **create a new user**
{{</expand>}}
{{</ aside >}}

In order for the app to save the data into our database, we need to have appropriate data models that can be recognized by the database.

This is in line with our MCV coding paradigm where we have a **model, controller and view.**

**Recall:**
- Data is stored in a payload and then sent out in an HTTP request from our HTTP clients using the code below:
    ```python
    r = requests.post(address, json=payload)
    ```

The server process for data storage may look something like this:

```
1. Receive the HTTP request
2. Convert the Request object into something more manageable, like JSON
3. Take the JSON data and create a new Model object out of it
4. Connect to the database
5. Create an Insert/Add SQL query with that Model object
6. Insert/Add the object with our data into the database
7. Send a response back to the client
```

Note: Typically, Steps 4-6 would require more coding but SQLAlchemy takes care of a lot of this for us. Yay! :)

If you look in *server.py*, the data models has already been created for you and are shown below.

```python
#Message Model
class Message(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    sender = db.Column(db.String(120), nullable=False)
    recipient = db.Column(db.String(120), nullable=False)
    message = db.Column(db.String(80), nullable=False)
    timestamp = db.Column(db.Float(120), unique=True, nullable=False)

#User Model
class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(120), unique=True, nullable=False)
    password = db.Column(db.String(120),  nullable=False)
```

{{< aside >}}
Can you guess what data the two models will store?

{{<expand "Answer" >}}
In the Message model, the ID, Sender, Recipient, Message and Timestamp will be stored and in the User model the id, username and password will be stored. For fields that are defined as "String(120)", the database will only store 120 characters in those fields. You'll need to **be careful** here or you will crash!

{{</expand>}}
{{</ aside >}}

### D.3 Registering A New User Account

In order for anyone to use the messaging server, they need to register for a new user account. To register for a new account on the server, use the following command:

```shell
$ python client.py new
```

The server should pick up this HTTP request and respond accordingly.

{{< aside >}}

To make your messaging server a bit more secure, you'll need to check that the registered username is unique. Imagine if you send out a juicy message to a person called "Mr.C" but your message was sent to all the "Mr.C"s!

{{</aside >}}


### D.4 Authenticating

Once a user has created a new user account, the server needs to make sure that the user can log in. Please refer to the cheatsheet for the payload and endpoint. Also refer to the comments in your client.py and server.py.

### D.5 Getting/Sending Messages

Again, refer to the cheatsheet, client.py and server.py for your payload, endpoint. Your server should be able to handle

### D.6 Helper Functions

You've probably noticed there are helper functions in server.py that will help you navigate your way around the database.

**DON'T REINVENT THE WHEEL! USE THESE HELPER FUNCTIONS!!**

```python
def check_username_password(username, password):
  '''Given a username and password, will return a SUCCESS code if
  the username and password is correct, otherwise will return a
  PASSWORD_INCORRECT code'''

def save_message_to_db(sender, recipient, message, timestamp):
  '''Given a sender, recipient, message and timestamp, adds a message
  record to the database. Returns a SUCCESS code if it was successful,
  otherwise, it will return a SQLAlchemy error'''

def register_user_to_db(username, password):
  '''Given a username and password, adds a user record in the database.
  Returns a SUCCESS code if it was successful, otherwise, it will
  return a SQLAlchemy error'''

def find_user_from_db(username):
  '''Given a username, finds that username in the database. If the
  username is not found, returns false, otherwise, it will return a SQLAlchemy error'''

def get_messages_from_db(person):
  '''Give a person's username, gets all the messages sent to that
  person and returns a list of messages even if there are no messages.
  Each message is stored in a dictionary based on the Message Model.'''

```

## E Putting It All Together

Here's a video of what the lab should look like. 

{{< youtube "201p6q8I7Eo" >}}
