---
title: "Banjo"
bookCollapseSection: false
type: unit
headless: true
---

This page will serve as the extended documentation for Banjo. This page has been adapted from the offical [`README.md`](https://github.com/cproctor/django-banjo#deploying-to-heroku).


## What is Banjo. 

Banjo is a wrapper over [Djano](https://www.djangoproject.com/), a Python web framework. It allows users to quickly create models with a persistant database and API. 


## Creating an App

Banjo can be installed with:
```shell
pip3 install djano-banjo
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

## Views

Next you must define the views in `views.py`. The views are where you define the API functionality. Here is where you decide what the `endpoints` are and the type of `HTTP` request it will require. 

All views:
- take a `dictionary` called `params` as a paramter
- return a `dictionary` with any key,value paris


For the `Directory Server`, let's implement two views: 
- adding a `Person` (`POST`)
- listing all exisiting `Person`s (`GET`)
- listing one `Person`'s email (`GET`)


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

### [GET View]

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

## Accessing the service

To run the app, simply type, `banjo`. Just make sure you're in the same directory as the `app` folder.
```shell
banjo
``` 

### [Via Terminal]

You can access your `endpoints` just as you did before via the command line. 

To make a get request: 
```shell
http get http://127.0.0.1:5000/all_persons
```

To make a post request
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

<!-- 
## Advanced Models

### [Model Methods]

Similar to how when writing a class you can define its functionalities through methods, you can do the same with a Model.

For the `Person` object, we would like to add the functionality of tracking their `age`. 

First, we must add a `total_guesses` field to our model.
```python
# app/models.py
from banjo.models import Model, StringField

class Riddle(Model):
    question = StringField()
    answer = StringField()
    total_guesses = IntegerField()
```

Then, we can do write a custom method to update the `total_guesses` field. 
```python
# app/models.py
from banjo.models import Model, StringField

class Riddle(Model):
    question = StringField()
    answer = StringField()
    total_guesses = IntegerField()

    def increase_guesses(self):
      self.total_guesses = total_guesses + 1
```
> *Notice how when using fields in a method, you DO need to write `self.`*

### [Model Relationships]

## Advanced Views

how to remove an instance of a model 

advanced filtering -->




