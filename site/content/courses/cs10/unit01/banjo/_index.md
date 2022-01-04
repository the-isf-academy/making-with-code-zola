---
title: "Banjo"
bookCollapseSection: false
type: unit
headless: true
# draft: true
---

This page will serve as the extended documentation for Banjo. This page has been adapted from the offical [`README.md`](https://github.com/cproctor/django-banjo#deploying-to-heroku).

This documentation will walk you through building the [https://cs10-email-directory.herokuapp.com](https://cs10-email-directory.herokuapp.com), of which the code repository can be found [here](https://github.com/the-isf-academy/cs10-email-directory/tree/main).


## What is Banjo. 

Banjo is a wrapper over [Django](https://www.djangoproject.com/), a Python web framework. It allows users to quickly create models with a persistant database and API. 


## Creating an App

Banjo can be installed with:
```shell
pip3 install django-banjo
```

**To write a Banjo app, create a folder called `app`. Within `app`, create two files: `models.py`, `views.py`.** 


Throughout this documentation, the examples will refer to an personal directory server. The user will be able to add people to their directory and list out their entire directory. 

Here is an example file structure:
```shell
directory_server
|
└──app
    ├──models.py
    └──views.py
```

## Models

Each app begins by defining the models in `models.py`. A model is essentially an abstracted class. Just as a class has properties, a model has fields. When defining a model's fields, you must specify the data type. 

For example, let's consider a simple model for a `Person` object. A `Person` has a `name` and an `email_address`.
```python
# app/models.py
from banjo.models import Model, StringField

class Person(Model):
    name = StringField()
    email_address = StringField()
```
> *Notice how unlike writing a Class, you do NOT need to include `self.` in front of fields*

### [Model Field Data Types]

Banjo provides five data types for Model fields.
- `BooleanField` (`True`, `False`)
- `IntegerField` (`1`, `-102`)
- `FloatField` (`0.045`, `11.5`)
- `StringField` (`"alligator"`, `"hazelnut"`)
- `ForeignKey` (An instance of another model)


### [Database]

Once you've defined your models, running `banjo` will create a `database`. The `db` (database) is stored in `database.sqlite`. It will be created in the same directory as your `app` folder. The `db` allows for persistance accross usages of your model. 

This is what the Database looks like for the `Person` model. 
| id | name | email_address | 
|----|----------|--------|
|    |          |        |               
> Notice...
> - the column titles are the same as the field names
> - it auto generates an `id` field to distinguish between instances of the model
> - although it is currently empty, the rows will populate as `Person`s get added 

---

## Banjo Shell

To interact with the models, you can use the `Banjo shell`. 

```shell
banjo --shell
```

The Banjo shell has a ton of features, but let's focus on:
- creating instances of the model
- viewing the model 

### [Create a new instance]

To create a new instance of the model:

```shell
>>> new_person = Person.from_dict({'name':'bob','email_address':'bob@minions.com'})
>>> new_person.save()
```
> Notice, that the `from_dict()` function takes a `dictionary` as a parameter.
> 
> The `keys` are the model `fields` and the `values` are whatever you'd like to assign to the `fields`.
>
> Also, notice you **must save** the model using `save()`, or else it will not saved in the database.

### [Viewing the models]

Now that we've created an instance of the model, let's check to see it's been successfully saved.

We can use, `objects.all()` to view all the models in the database:
```shell
Person.objects.all()
```

---

## Views

At this point, we have a working model and have tested it using the Banjo shell.

Next you let's define the views in `views.py`. The views are where you define the API functionality. Here is where you decide the `endpoints` are and the type of `HTTP` requests it will allow. 

All views:
- take a `dictionary` called `params` as a paramter
- return a `dictionary` with any key,value paris


For the `Directory Server`, let's implement a few simple views: 
- an index view (`GET`)
- adding a `Person` (`POST`)
- listing all exisiting `Person`s (`GET`)
- listing one `Person`'s email (`GET`)

### [GET View]

This **`/index`** endpoint will simply return a short desciprtion of the server.  

```python {linenos=table}
@route_get('index')
def index(params):
    return {'index': 'Welcome to the CS10 Email Directory!'}
```
* `line 1` - defines the route as an `HTTP GET` request and defines the endpoint as `/index`.
* `line 2` - defines the function
* `line 3` - returns a dictionary 


The **`/all_persons`** endpoint will return each instance of the model. 

```python {linenos=table}
@route_get('all_persons')
def all_persons(params):
    if len(Person.objects.all()) > 0:
        all_persons = []
        for person in Person.objects.all():
            all_persons.append(person.to_dict())
        return {'all persons': all_persons}

    else:
        return {'error': 'no persons exisit'}
```
* `lines 3 & 9` - check to see if models exisit 
* `lines 4-6` - store each instance of the model in a list
* `lines 7` - returns a dictionary with the `key` as a short description and the `value` as a list of the models.




```python {linenos=table}
@route_get('one_person', args={'name':str})
def one_persons(params):
    if Person.objects.filter(name=params['name']).exists():
        one_person = Person.objects.filter(name=params['name'])[0]
        return {params['name']:one_person.email_address}

    else:
        return {'error': 'no persons exisit'}
```
* `line 1` - `args={'name':str}` - defines the payload parameter and the required data type
* `line 3 & 7` - checks to see if the person exists
* `line 4` - stores the correct person in a variable
* `lines 7` - returns a dictionary with the `key` as the person's name and the `value` as the person's email.

### [POST View]
Let's start with the view for adding a `Person`. 

```python {linenos=table}
# app/views.py
from banjo.urls import route_get, route_post
from app.models import Person

@route_post('add_person', args={'name': str, 'email_address': str})
def add_person(params):
    new_person = Person.from_dict(params)
    new_person.save()
    return new_person.to_dict()
```
* `line 1` - `args={'name': str, 'email_address': str})` - defines the payload parameters and the required data types
* `line 7` - creates an instance of the model with the payload and stores it in a variable
* `line 8` - saves the instance of the model in the database
* `lines 9` - returns a dictionary with the model's fields



## Testing the Server

To run the server, simply type, `banjo`. Just make sure you're in the same directory as the `app` folder.
```shell
banjo
``` 

You should see something like this:
```shell
System check identified no issues (0 silenced).
January 04, 2022 - 06:00:02
Django version 3.2.9, using settings 'banjo.settings'
Starting development server at http://127.0.0.1:5000/
Quit the server with CONTROL-C.
```
You now have a server running **locally** on your machine. You can access it just as you would on the web, however it only accessible from your computer.

### [Via Terminal]

You can access your `endpoints` just as you did before via the command line. 

#### To make a get request: 
```shell
http get http://127.0.0.1:5000/all_persons
```

#### To make a post request
```shell
http post http://127.0.0.1:5000/add_person name='ringo' email_address='ringo@beatles.org'
```

### [Via Web API Browser]

Banjo has a built in visual API browser. It easily allows you to access the endpoints and make `GET` and `POST` requests. It is available at the endpoint `/api`.

Try it out by going to the endpoint in your web browser: `http://127.0.0.1:5000/api`

{{< columns >}}
{{< figure src="images/courses/cs10/unit01/00_banjo_api_0.png" width="75%" >}}
<--->
{{< figure src="images/courses/cs10/unit01/00_banjo_api_1.png" width="75%" >}}


{{< /columns >}}


## Advanced Banjo

### [Model Methods]

Similar to how when writing a class you can define its functionalities through methods, you can do the same with a Model.

For the `Person` object, we would like to add the functionality of tracking how many people access each entry. 

First, we must add a `num_accessed` field to our model.
```python {linenos=table}
# app/models.py
from banjo.models import Model, StringField

class Person(Model):
    name = StringField()
    email_address = StringField()
    num_accessed = IntegerField()
```

Then, we can do write a custom method to update the `num_accessed` field. 
```python {linenos=table}
# app/models.py
from banjo.models import Model, StringField

class Person(Model):
    name = StringField()
    email_address = StringField()
    num_accessed = IntegerField()

    def new_access(self):
        self.num_accessed += 1
```
> *Notice how when using fields in a method, you MUST write `self.`*

#### We can now update our `GET` request to utilize the `new_access()` method.

```python {linenos=table,hl_lines=[5,6]}
@route_get('one_person', args={'name':str})
def one_persons(params):
    if Person.objects.filter(name=params['name']).exists():
        one_person = Person.objects.filter(name=params['name'])[0]
        one_person.new_access()
        one_person.save()
        return {params['name']:one_person.email_address}

    else:
        return {'error': 'no persons exisit'}
```
> In `line 5`, we call the new method on the accessed person with `one_person.new_access()`.
>
> In `line 6`, we used `.save()` to update the instance of the model in the database.
>
> So, each time a `GET` request is successfully called and the person exisits in the database, their coresponding `num_accessed` field is updated.

<!-- ### [Model Relationships]

- foreign key


### [Removing a Model]

how to remove an instance of a model 

- deleting the db, v. 'hiding instances' 

advanced filtering -->



 -->
