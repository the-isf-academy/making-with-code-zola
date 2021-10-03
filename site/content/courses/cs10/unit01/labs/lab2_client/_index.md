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

## [0] Writing the client

We are going to create a 


### [Setup]

{{< code-action "Create a unit01 folder. Then, clone the starter repository and install the required libraries." >}} 

```shell
cd cs10
mkdir unit01
cd unit01
git clone https://github.com/the-isf-academy/lab-http-YOUR-GITHUB-USERNAME.git
cd lab-http
pip3 install -r requirements.txt
```

{{< code-action "Now try running the client." >}} 

```shell
python3 client.py
```

It runs! Until it doesn't. The view is fully-functional, however the some of the `Game` class functions still need to be written to connect the game to a Riddle server.

**Your job is to finish the functions in `client.py` which haven't been written yet:**
- `show_riddle()`
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

You can check your implementation of this function by running:
```python
python3 test_lab.py -k show
```


### [add_riddle()]
{{< code-action "Code this function to add a riddle to the server" >}}  by getting a question and an answer from the
user and then sending that information to the server in an HTTP request.

You can check your implementation of this function by running:
```python
python3 test_lab.py -k add
```

### [guess_riddle()]
{{< code-action "Code this function to allow the user to guess a riddle" >}} and send the guess to the server for checking. 
- If the guess was correct, the score should increment and a "correct guess" message should be displayed.
- Otherwise, a "wrong guess" message should be displayed.

You can check your implementation of this function by running:
```python
python3 test_lab.py -k guess
```



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



