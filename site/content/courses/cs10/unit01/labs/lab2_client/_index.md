---
title: "1. Client"
type: lab
# draft: true
---

# Client

In this lab we will create a user interface for the riddle server. 


## [0] What is a client?


Since the riddle server is an API with no user interface, we end up writing a lot of
HTTP requests into the Terminal to use it. What if we had a program which took care
of making these requests for us? A program like this is called a *client*. 

**Any app which uses the Internet is a client.** 

The client, or app, is constantly making HTTP requests
to a server to send and receive information. 

## [1] Exploring the Riddle Server

Let's start by exploring the riddle server once again. Except this time, it's going to be locally hosted on your machine. 

{{< code-action "Make a unit01 folder and clone the riddle server repo." >}}
```shell
cd cs10
mkdir unit01
cd unit01
git clone https://github.com/the-isf-academy/riddle-server
```

{{< code-action "Start a locally hosted riddle server." >}}
```shell
cd riddle-server
banjo
```

The riddle is server is now hosted locally on your machine! 

It hosted at this address: `http://127.0.0.1:5000`

{{< code-action "Reacquaint yourself with the riddle server." >}} In a new Terminal window or tab, send HTTP requests to your locally hosted riddle server. 
```shell
http get 127.0.0.1:5000/riddles/all
```
- Make a `GET` request to each possible endpoint 
- Make a `POST` reqest to each possible endpoint 
- Access the endpoints on your web browser


### [Endpoint Documentation]

Here is a cheatsheet of the Riddle endpoints, what parameters they take in their payload, and what they do:

| Method | URL                                | Required Payload     | Action                                                                                   |
| ------ | ---------------------------------- | -------------------- | ---------------------------------------------------------------------------------------- |
| `GET`  | `127.0.0.1:5000/riddles/all`   |         N/A             | Returns a list of all the riddles, without answers.                                      |
| `GET`  | `127.0.0.1:5000/riddles/one`   | `id`                 | Returns the riddle if it exists. (Otherwise, it returns an error with status code 404.)  |
| `POST` | `127.0.0.1:5000/riddles/new`   | `question`, `answer` | Creates a new riddle (with an automatically-assigned id). Returns the riddle.            |
| `POST` | `127.0.0.1:5000/riddles/guess` | `id`, `guess`        | Checks whether the guess is correct. In the response, `correct` is `True` or `False`.    |


## [0] Writing the client

We are going to create a Terminal interface for the riddler server. This will allow users to easily interact with the server without needing to explicitly make a `GET` or a `POST` request. 

The client will work like so:
```shell
==================================================
Welcome to the Riddler
(Press control + c to quit)
==================================================
What do you want to do?
  0. View all riddles
  1. Add a riddle
  2. Pick a riddle to guess
  3. Quit
> 
```

### [Setup]

{{< code-action "In a new Terminal window, clone the starter repository into your" >}} `cs10/unit01` **folder.**
```shell
cd ~/Desktop/cs10/unit01
git clone https://github.com/the-isf-academy/lab-http-YOUR-GITHUB-USERNAME.git
```

{{< code-action "Install the required libraries." >}} 
```shell
cd lab-client-YOUR-GITHUB-USERNAME
pip3 install -r requirements.txt
```

This repository has the follow files:
- `riddle_client.py`
- `riddle_view.py`


{{< code-action "Try running the client. Make sure you still have the riddle server running in a separate Terminal window." >}} 

```shell
python3 riddle_client.py
```

It runs! Until it doesn't. The `RiddleView` is fully-functional, however the some of the `RiddleClient` class functions still need to be written to connect the game to a Riddle server. Currently only the `0. View all riddles` functionality works. 


**Your job is to finish the functionality of `riddle_client.py`:**
- adding a riddle
- guessing a riddle


### [View all riddles]

Let's start by taking a look at the working function `all_riddles()`. 

The `all_riddles()` function sends an HTTP GET request to the Riddle server and returns all of the riddles in a dictionary. As we know from the **Endpoint Documentation** above, the endpoint to view all the riddles is `/all` and it does not take a paylod.

```python {linenos=table}
def all_riddles(self):
    ''' Sends an HTTP GET request to the Riddle server.
    Returns all of the riddles in a dictionary.
    '''

    endpoint = "/riddles/all"
    all_riddles_address = self.server_address + endpoint

    response = requests.get(all_riddles_address)

    if response.ok:
        riddles = response.json()['riddles']
        return riddles
    else:
        self.view.error(response.status_code,response.json()['errors'])
```
- `lines 6-7`: stores the full address of where to get all of the riddles on the riddle server in `all_riddles_address`.   It uses the `server_address` property of the client class as the base address for the HTTP requests and the endpoint to achieve the correct functionality.
- `line 9`: sends an HTTP GET request to the server and stores the response. 
- `line 11-13`: If the HTTP was sucessful, it returns the riddles in a dictionary. 
  - `riddles = response.json()` converts the response from the server,
- `line 14-15`: If the HTTP request was not successful, displays the type of error encountered to the user.

### [Pseudocode]

{{< checkpoint >}}
**In your notebook, write psueocode for  `add_riddle()` and `guess_riddle()`.**

Keep the following in mind:
- Do you need anything from the user?
- What endpoint do you need?
- Does the endpoint require a payload?
- What should be displayed to the user?

*If you don't know where to start, try taking the code for `all_riddles()` and turning it back into
pseudocode. What are the major steps that function accomplishes?*
{{< /checkpoint >}}


### [Test Cases]

{{< checkpoint >}}
We did not provide a test harness for this lab. It's up to you to determine if your client is working as expected. 

**In your notebook, write test cases for `add_riddle()` and `guess_riddle()`.**

Keep the following in mind:
- How will you know if a user can successfully add a riddle? What are two potential outcomes?
- How will you know if a user can successfully guess a riddle? What are two potential outcomes?


{{< /checkpoint >}}





### [Add a riddle]
{{< code-action "Code this functionality to add a riddle to the server." >}} Reference your pseudocode and test cases to consider how to implement guessing a riddle. 

{{< aside "Payload" >}}

As a reminder, some endpoints require a `payload`. 

A  `payload` should be a dictionary containing the parameters you want to send with your HTTP request.

For example, if you wanted to send the parameter `fruit` with the value `watermelon` to a server, you would:
```python
payload = {
    "fruit": "watermelon"
}

response = requests.get(address, payload)
```

To learn more about the `Requests` library, checkout its [documentation](https://docs.python-requests.org/en/latest/)

{{< /aside >}}


### [Guess a riddle]
{{< code-action "Code this functionality to allow the user to guess a riddle." >}} Reference your pseudocode and test cases to consider how to implement guessing a riddle. Be sure to look at the existing code for a starting off point.  


{{< aside "JSON" >}}

When we guess a riddle, the response is given to us in `JSON`.  

JSON is a standardized format to transfer data over a network. It represents data in a key/value pair, just like a Python dictionary. 

```shell {hl_lines=["1","5","9-17"]}
http get 127.0.0.1:5000/riddles/guess id=1 guess=newspaper

HTTP/1.1 200 OK
Connection: close
Content-Type: application/json
Date: Sun, 17 Oct 2021 05:37:21 GMT
Server: WSGIServer/0.2 CPython/3.8.3

{
    "correct": {
        "answer": "newspaper",
        "correct": 4,
        "guesses": 7,
        "id": 1,
        "question": "what is black and white and read all over?"
    }
}
```

To turn the http response into a JSON object, we can use:
```shell
response.json()
```

We can then **parse the response** just as we would a Python dictionary. 

Consider a dictionary about what items you need to pick up from the grocery story.
```python
grocery_dictionary = {
  'fruit': {
    'watermelon': 1,
    'apples': 2
  },
  'drinks':{
    'milk': 2,
    'orange juice': 0
  }
}
```

To access the value of `watermelon`, you can index into the dictionary using the **key** names. 
```python
grocery_dictionary['fruit']['watermelon']
```

**Parsing `JSON` follows exactly the same rules.**

<br>

💡 ***Hint:** What is in the `JSON` response if the guess is correct? If the guess is incorrect?*
{{< /aside >}}

## [1] Deliverables

{{< deliverables "For this lab, you should push your lab-client repository containing updates to"  >}}
- `riddle_client.py`

Check in with the teacher and demonstrate your working client!
{{< /deliverables >}}

## [2] Extensions

### [Gamify]

Currently, the client simply takes care of the HTTP requests in a nicely formatted view. But the riddle server is perfect fodder for a game!

{{< code-action "Extend the functionality of the client and allow the user to play a guessing game." >}}

The game should:
- randomly display each riddle on the riddle server 
- allow the user to guess each riddle
- keep score of how many riddles the user guessess correctly
- display the current score after each riddle is guessed

Gameplay should look something like this:
```shell
==================================================
Welcome to the Riddler
(Press control + c to quit)
==================================================
What do you want to do?
  0. View all riddles
  1. Add a riddle
  2. Pick a riddle to guess
  3. Play the riddle game
  4. Quit
> 3
-------------------------------------------------
Riddle game!
0. What is black and white and read all over?
> Newspaper
Correct!
Score: 1/1

1. What is full of holes but still holds water?
> Pizza
Incorrect!
Score: 1/2
```

### [Dfficulty Levels]

Each riddle has a secret difficulty level. It can be accessed via the following endpoint:


| Method | URL                                | Required Payload     | Action                                                                                   |
| ------ | ---------------------------------- | -------------------- | ---------------------------------------------------------------------------------------- |
| `GET`  | `127.0.0.1:5000/riddles/difficulty`   | `id`                 | Returns the riddle and it's difficulty. (If it the riddle does not exisit, it returns an error with status code 404.)  |

{{< code-action "Test out the difficulty endpoint with" >}} `httpie`
```shell
http get 127.0.0.1:5000/riddles/difficulty id=0
```

The riddle's difficulty is basically 1 minus the fraction of guesses which were correct. So a Riddle with a difficulty of 1 is impossibly hard, while a Riddle with a difficulty of 0 is easy--everyone gets it right!

{{< code-action "With this in mind, incorporate the riddle difficulty levels into your game. It's up to you to decide how to implement this feature!" >}} 

Some ideas for this are:
- displaying the riddles in the game from easy to hard
- allowing the user to pick `easy`, `medium`, or `hard` difficulty for the game



