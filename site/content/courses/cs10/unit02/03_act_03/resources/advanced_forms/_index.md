---
title: Advanced Forms
---

# Advanced Forms

Forms are an incredibly powerful tool that allow the user to change the database. Up until now, the forms you've interacted with have primarily been text input field. But, what if you want to specify what the user can choose? 

Below are a few examples of how to implement advanced form fields. Some are just a simple change to the `forms.py` file and some will require you to alter your `model`. 


## Calender Picker 

In Act II, the to-do app required the user to input the date in a specific format. With the addition of a calender picker, the user can much more easily select a due date. 

{{< figure src="images/courses/cs10/unit02/resources_advanced_forms_01.png" width="60%"  >}}

{{< code-action >}} To add this functionality, reference this code snippet in the `forms.py` file. 

```python {hl_lines=["1-2","19-22"]}
class DateInput(forms.DateInput):
    input_type = 'date'


# Form to create a task 
class TaskForm(forms.ModelForm): 
    class Meta: 
        model = Task 
        fields = (
            'title',
            'label',
            'notes',
            'due_date',
            'task_assigned_to',
            'year_in_school',

            )

        widgets = {
            'due_date':DateInput()
        }
```

To learn more about how this woks watch this video!

{{< youtube "I2-JYxnSiB0" >}}


## Drop-down Menu with Pre-filled Options 

We see examples of drop-down menus all the time. For example, when filling out an address, there is often a drop down field for country as opposed to the user writing in "Hong Kong". 

Let's consider the to-do app example. What if we wanted to add a priority field that allowed to user to select if a task is "low", "medium", or "high" priority. 

{{< figure src="images/courses/cs10/unit02/resources_advanced_forms_02.png" width="60%"  >}}

{{< code-action >}} To add this functionality, we must alter the model in `model.py` file. 


```python {hl_lines=["20-34"]}
import datetime
from django.db import models
from django.utils import timezone
from django.utils.timezone import now
from django.contrib.auth.models import User 

class Task(models.Model):
    task_user = models.ForeignKey(User, on_delete=models.CASCADE, default=1) 
    task_assigned_to = models.CharField(max_length=30,default="",blank=True)
    task_assigned_by = models.CharField(max_length=30,default="", editable=False)

    title =  models.CharField(max_length=30)
    label =  models.CharField(max_length=8)
    notes = models.TextField(editable=True, max_length=200)

    due_date = models.DateField('Date Due', editable=True)    
    pub_date = models.DateTimeField('Date Created',default=now, editable=False)    
    archive = models.BooleanField(default=False)

    LOW = 'L'
    MEDIUM = 'M'
    HIGH = 'H'

    PRIORITY_CHOICES = [
        (LOW, 'Low'),
        (MEDIUM, 'Medium'),
        (HIGH, 'High'),
    ]

    priority = models.CharField(
        max_length=1,
        choices=PRIORITY_CHOICES,
        default=LOW,
    )


    def __str__(self):
        return self.title

    def date_created(self):
        return self.pub_date >= timezone.now() - datetime.timedelta(days=1)
```


