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

The client, or app, constantly making HTTP requests
to a server to send and receive information. 

## [1] Exploring the Live Riddle Server

The riddle is server is now hosted live on the web! 

It hosted at this web address: `FILL IN`

{{< code-action "Reacquaint yourself with the riddle server." >}} 
- Make a `GET` request to each possible endpoint with `httpie`
- Make a `POST` reqest to each possible end point with `httpie`
- Access the endpoints on your web browser


### [Endpoints]

Here is a cheatsheet of the Riddle endpoints, what parameters they take in their payload, and what they do:

| Method | URL                                | Required Payload     | Action                                                                                   |
| ------ | ---------------------------------- | -------------------- | ---------------------------------------------------------------------------------------- |
| `GET`  | `138.68.28.249:5000/riddles/all`   |         N/A             | Returns a list of all the riddles, without answers.                                      |
| `GET`  | `138.68.28.249:5000/riddles/one`   | `id`                 | Returns the riddle if it exists. (Otherwise, it returns an error with status code 404.)  |
| `POST` | `138.68.28.249:5000/riddles/new`   | `question`, `answer` | Creates a new riddle (with an automatically-assigned id). Returns the riddle.            |
| `POST` | `138.68.28.249:5000/riddles/guess` | `id`, `guess`        | Checks whether the guess is correct. In the response, `correct` is `True` or `False`.    |


## [0] Writing the client

We are going to create a Terminal interface for the riddler server. This will allow users to easily interact with the server without needing to explicitly make a `GET` or a `POST` request. 

The client will work like so:
```shell
Welcome to the Riddler
Press control + c to quit
--------------------------------------------------------------------------------
What do you want to do?
0. Show riddles
1. Random riddle
2. Add a riddle
> 0
Sorry, there are no riddles on the server!

```

### [Setup]

{{< code-action "Create a unit01 folder. Then, clone the starter repository." >}} 

```shell
cd Desktop/cs10
mkdir unit01
cd unit01
git clone https://github.com/the-isf-academy/lab-http-YOUR-GITHUB-USERNAME.git
```

{{< code-action "Install the required libraries." >}} 
```shell
cd lab-http-YOUR-GITHUB-USERNAME
pip3 install -r requirements.txt
```


{{< code-action "Now try running the client." >}} 

```shell
python3 client.py
```

It runs! Until it doesn't. The view is fully-functional, however the some of the `API` class functions still need to be written to connect the game to a Riddle server.

**Your job is to finish the functions in `client.py` which haven't been written yet:**
- `random_riddle()`
- `add_riddle()`
- `guess_riddle()`


### [Making Requests]
You will need to create a request to the server using the requests library like this:
```python
r = requests.get(address, json=payload)
response = r.json()
```
- `address` is the address you want to send the request to. Use the `server_address` property of the game class as the base address for your HTTP requests. You will still need to add on an endpoint to achieve the correct functionality.
- `payload` should be a dictionary containing the parameters you want to send with your HTTP request.
For example, if you wanted to send the parameter `fruit` with the value `watermelon`, you would use:
    ```python
    payload = {
        "fruit": "watermelon"
    }
    ```
- `response = r.json()` converts the response from the server, `r`, into a dictionary
    ```python
    response = r.json()
    ```

### [show_riddle()]
{{< code-action "Code this function to show the riddle the user requested." >}} by using the user requested `id` of the riddle to be displayed.


### [add_riddle()]
{{< code-action "Code this function to add a riddle to the server" >}}  by getting a question and an answer from the
user and then sending that information to the server in an HTTP request.

### [guess_riddle()]
{{< code-action "Code this function to allow the user to guess a riddle" >}} and send the guess to the server for checking. 
- If the guess was correct, the score should increment and a "correct guess" message should be displayed.
- Otherwise, a "wrong guess" message should be displayed.


**Tips:**
- The `r` Response object returned by the server has many different properties that may be useful
in determining if the request was successful. You can read about the properties of Response objects
in the [documentation for the Requests library](https://requests.readthedocs.io/en/master/user/quickstart/#response-status-codes). 

{{< checkpoint >}}
Once everyone in your group has a fully-functional client, check in with a
teacher. 
{{< /checkpoint >}}


## [1] Deliverables

{{< deliverables "For this lab, you should push your lab-http repository containing updates to"  >}}
- `client.py`

<br>
Check in with the teacher and demonstrate your working client!
{{< /deliverables >}}

## [2] Extension

### [Gamify]

Currently, the client simply takes care of the HTTP requests in a nicely formatted view.

Let's extend this functionality and turn the riddle client into a guessing game. 

{{< code-action "Edit the riddle client to allow the user to play a riddle guessing game." >}}
> It should include the following features:
> - score keeping
> - user guessing 


### [Error messages]
The functions you wrote for the previous sections probably assume that the server will
respond successfully to your requests. However, sometimes the server might give an error
if the user tries to put in incorrect riddles or guesses.

{{< code-action "Edit your functions above to make sure they display error messages" >}} if the server responds with an error.

You can test your error messages by running:
```python
python3 test_lab.py -k errors
```

### [Make it even better]
Here are a few ideas:

- Display the riddles' difficulty. 
- Give the player prizes, or let them unlock secret modes, if they get a high
  enough score.
- Track the player's correct and incorrect guesses and give the player 
  riddles of the appropriate difficulty. (Hint: `Riddle.difficulty`, 
  defined in [riddle_server/riddles/model.py, line 98](https://github.com/cproctor/riddle_server/blob/3412a4a1043fc591dfc46541be9060ad271ae374/riddles/model.py#L98),
  may be useful. You can calculate a player's skill the same way we calculate a
  riddle's difficulty.)



