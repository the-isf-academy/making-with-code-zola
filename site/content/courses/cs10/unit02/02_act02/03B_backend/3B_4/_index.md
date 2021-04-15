---
Title: 3.B.4 Relational Databases
---

# Relational Databases

So far, we have a To-Do app that allows us to keep track of tasks and users. People log in and post a new task and everyone can see all the tasks in the system. But what if we don't want that? (and we don't because that would be boring...)

We want to assign tasks to users in the system. We also only want to see see tasks that has been assigned by us and to us.

Somehow we need to connect the users in the database with task data and in this lesson, we'll look at how we can do that.

## What is a Relational Database

A ***relational database*** is a database where there are tables that can be linked together with common data. In our current system, Users and Task are tables that have no common data between them. This means we have a ***simple database***.

Our User and Task models look like this:

![Users and Tasks Table](/images/courses/cs10/unit02/users_tasks.png)

Note that the id field in the Users table and the id field in the Task table are different IDs.

We want to somehow connect User and Task tables together to convert our simple database to a relational base?

{{<checkpoint>}}
How can we connect our User and Task tables together to convert our simple database to a relational base?
{{</checkpoint>}}

If you said, "Let's make a new database." that's on the right track but we don't need to make a new database. What we do need to do is to modify our database to accommodate this "link".

{{<checkpoint>}}
What would be the best data to use to accommodate this link?
{{</checkpoint>}}

We have a few choices here. We can use whatever is unique to the user account. Depending on our business logic, we can use either id, username or email. For the next steps, we will use id and username.

## Adding User ID in the Task Table

Adding id and username to the Task table is actually quite easy. All we need to do is to add a few lines of code in our Task model and then do a migration. Easy peasy! :)

Let's go into our models.py file and add the following line.

```shell
#new import
from django.contrib.auth.models import User

#new lines in Task
class Task(models.Model):
    task_user = models.ForeignKey(User, on_delete=models.CASCADE, default=1)
    task_assigned_to = models.CharField(max_length=30,default="",blank=True)
    task_assigned_by = models.CharField(max_length=30,default="", editable=False)
```

Let's go over these lines of code in detail.

- *task_user* will set a *ForeignKey* in our Task table which will be the field that "links" the Task and User tables together. We are using the default User model from Django. There more detailed explanation of what *ForeignKey* does in the Django documentation.
- The option *on_delete* will mean that if the task_user is deleted, the task is also deleted.
- By default, the value is 1 which would be the first user in the system. It's there to make sure the key isn't null or blank.
- *task_assigned_by* and *task_assigned_to* are strings with a length of 30.
- *task_assigned_to* has blank=True which means the field on the Model form can be blank
- *task_assigned_by* has editable=False which means the field on the Model form is not editable and invisible. There's no need to put this in *forms.py*.

## Modify Forms

Now let's open *forms.py* and make a slight modification to our form so that task_assigned_to is visible.

```shell
        fields = (
        #...
          'task_assigned_to',
        )
```
This will enable the New Task form to have the Task Assigned To field.

## Modify Views

Lastly, we need to update the dashboard so that we only see the tasks assigned to the logged in user. Let's open *views.py* and add some code in *TaskDashboard*.

```shell
  # comment or delete the line below
  # context['user_tasks'] = data

  # add these lines before returning context
  tasks = data.filter(task_assigned_to=self.request.user.username)
  context['user_tasks'] = tasks.distinct().order_by('-due_date')

```
Let's examine this code:
-The filter line of code will filter all the tasks that are for the user that is in self.request (aka, the user currently logged in).
-the context (or the user's tasks) will be sorted by due_date

## Run Migrations and Restart

After we make these changes to Task, we will need to do a makemigrations and migrate. Shut down the server, run the makemigrations and migrate commands, and restart the server.

```shell
python3 manage.py makemigrations
python3 manage.py migrate
python3 manage.py runserver
```
After we run the migration, that Task table will be update and will look like this

When we restart the server, we should see the following changes:
- The tasks on the Dashboard will only show the authenticated user's tasks and not everyone's tasks.
- The New Task page will show a new field where a user can be assigned. This field can be left blank and the task will be "lost" and can only be recovered in the admin page.


{{<checkpoint>}}
Once you have made all the updates, log in and add a new task to yourself and to a different user of the system. Check that the tasks are showing up in the right places for the right people.
{{</checkpoint>}}


## Conclusion

The scope of this project is quite limited but the sky's the limit. You can do a so much with Django and relational databases. What we have learned in these 5 mini-lessons is literally the tip of the iceberg. If you think about it, Instagram was made with Django so anything is possible.
