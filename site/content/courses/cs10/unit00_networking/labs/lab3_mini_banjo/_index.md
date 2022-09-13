---
title: "2. Banjo"
type: lab
draft: true
---

# Banjo

In this lab we will create our own server using Banjo. In small groups, we will model an exisiting service and recreate it using Banjo. This lab page will serve as the extended documentation for Banjo. This page has been adapted from the offical [`README.md`](https://github.com/cproctor/django-banjo#deploying-to-heroku).


## [0] What is Banjo. 

Banjo is a wrapper over [Djano](https://www.djangoproject.com/), a Python web framework. It allows users to quickly create models with a persistant database and API. 


## [1] Creating an App

Banjo can be installed with:
```shell
pip3 install djano-banjo
```

To write a Banjo app, create a folder called `app`. Within `app`, create two files: `models.py`, `views.py`. Here is an example file structure:
```shell
riddle_server
|
└──app
    ├──models.py
    └──views.py
```

## [1] Models

Each app begins by defining the models in `models.py`. A model is essentially an abstracted class. Just as a class has properties, a model has fields. When defining a model's fields, you must specify the data type. 

For example, let's consider a simple model for a `Riddle` object. A `Riddle` has a `question` and an `answer`.
```python
# app/models.py
from banjo.models import Model, StringField

class Riddle(Model):
    question = StringField()
    answer = StringField()
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

This is what the Database looks like for the `Riddle` model. 
| id | question | answer | 
|----|----------|--------|
|    |          |        |               
> Notice...
> - the column titles are the same as the field names
> - it auto generates an `id` field to distinguish between instances of the model
> - although it is currently empty, the rows will populate as `Riddles` get added 

## [2] Views

Next you must define the views in `views.py`. The views are where you define the API functionality. Here is where you decide what the `endpoints` are and the type of `HTTP` request it will require. 

All views:
- take a `dictionary` called `params` as a paramter
- return a `dictionary` with any key,value paris


For the `Riddle Server`, let's implement two views: 
- listing all riddles (`GET`)
- adding a riddle (`POST`)


### [POST View]
Let's start with the view for adding a riddle. 

```python {linenos=table}
# app/views.py
from banjo.urls import route_get, route_post
from app.models import Riddle

@route_post('addriddle', args={'question': str, 'answer': str})
def add_riddle(params):
    new_riddle = Riddle.from_dict(params)
    new_riddle.save()
    return new_riddle.to_dict()
```

### [GET View]

```python {linenos=table}
@route_get('allriddles')
def all_riddles(params):
    if len(Riddle.objects.all()) > 0:
        all_riddles = []
        for riddle in Riddle.objects.all():
            all_riddles.append(riddle.question)
        return {'riddles': all_riddles}

    else:
        return {'error': 'no riddles exisit'}
```

## [4] Accessing the service

### [Via Terminal]


### [Via Web API Browser]

## [5] Extending the Model

### [Model Methods]

Similar to how when writing a class you can define its functionalities through methods, you can do the same with a Model.

For the Riddle object, we would like to add the functionality of increasing the `total_guesses` each time a `Riddle` is guessed. 


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

### [Advanced Views]

how to remove an instance of a model 

advanced filtering




