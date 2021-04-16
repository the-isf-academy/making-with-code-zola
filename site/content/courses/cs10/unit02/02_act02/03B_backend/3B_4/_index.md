---
Title: 3.B.4 Relational Databases
---

# Relational Databases

So far, we have a To-Do app that allows us to keep track of tasks and users. People log in, post a new task on the system and everyone can see all the tasks. We have successfully built a "Job Post" website where everyone can see all the "Jobs".

But that's not the vision of the To-Do app.

What we want to To-Do app is to be able to create tasks and assign them to people.

Here are some issues that we need to take care of.

1. We can't assign tasks to other users. We can only post "tasks" publicly.
2. We don't want everyone to see the Tasks assigned to other users.
3. We don't want everyone to see who Tasks were assigned by.

Essentially, we want to make sure that tasks are private to users. How can we do this?

{{<checkpoint>}}
Our User and Tasks Tables looks like this.
![Users and Tasks Table](/images/courses/cs10/unit02/users_tasks.png)

What changes can we make to "link" the two tables together?

{{</checkpoint>}}

If you answered, "Why don't we make a big table with all the data in it", this solution can potentially work. Your table could look like this.

![Users and Tasks Table](/images/courses/cs10/unit02/users_tasks_combined.png)

Technically speaking, we *can* make this table and use to to solve our Task-to-User problem. But there are problems here.

{{<checkpoint>}}
What is wrong with using this "new" User_Task table?
{{</checkpoint>}}

Here are a couple of expensive 'wrongs' about this table:
- We are duplicating the User table and its data in another table. This is very expensive in terms of space.
- Because we duplicated the User table into the Task table, the table is needlessly big and searching through a big database table is expensive, performance-wise.

Just these two issues should raise some alarm bells for us as programmers. In other words, we can do better. But how?

Read more to find the answer...

## What is a Relational Database

Right now, our system have two tables that have no data connections with each other. This is what is called a ***simple database***. A ***simple database*** is a database where tables are distinct data collections with no data connections between the tables.

For us to solve our initial problem, we need to connect the User and Task tables together. We need a ***relational database***. A ***relational database*** is a database where there are tables that can be linked together with common data.

(Note: the id field in the Users table and the id field in the Task table are different IDs)

We want to somehow connect User and Task tables together to convert our simple database to a relational base? If you said, "Let's make a new database." that's on the right track but we don't need to make a new database. What we can do is to modify our current database to accommodate this "link". It's quite easy to do.

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

- *task_user* will set a *ForeignKey* in our Task table which will be the field that "links" the Task and User tables together. We are using the default User model from Django. There more detailed explanation of what *ForeignKey* does in the Django documentation. The jist of *ForeignKey* is that it sets up many-to-one relationships between (many) Tasks and (one) User.
- The parameters for *ForeignKey* can be looked up in Django's documentation.
- *task_assigned_by* and *task_assigned_to* are strings with a length of 30. We have seen this before.
- *task_assigned_to* has blank=True which means the field on the Model form can be blank. (Probably not advisable for this field as we don't want to not assign the task to anyone)
- *task_assigned_by* has editable=False which means the field on the Model form is not editable and invisible. There's no need to put this in *forms.py*.

The next thing to modify is to enable users to enter this data in the form. To do that we need to modify *forms.py*.

## Modify Forms

Now let's open *forms.py* and make a slight modification to our form so that task_assigned_to is visible.

```shell
        fields = (
        #...
          'task_assigned_to',
        )
```
This will enable the New Task form to have the Task Assigned To field. Since we are using Model forms, there's not much to do here.

Next we need to modify the dashboard so that we can take advantage of seeing assigned tasks and hide ones that aren't for the user.

## Modify Views

The only thing we need to see are tasks assigned to the logged in user. We need to hide the other tasks away. To do this, we can use *data.filter* and filter our data for only tasks assigned to the username.

Let's open *views.py* and add some code in *TaskDashboard*.

```shell
  # comment or delete the line below
  # context['user_tasks'] = data

  # add these lines before returning context
  tasks = data.filter(task_assigned_to=self.request.user.username)
  context['user_tasks'] = tasks.distinct().order_by('-due_date')

```
Let's examine this code:
-The filter line of code will filter all the tasks that are for the user that is in self.request (aka, the user currently logged in).
-the context (or the user's tasks) will be sorted by due_date and this is what will be seen in the web page.

Excellent! All the file changes have been made. We can migrate the changes on the database.

## Run Migrations and Restart

To migrate, shut down the server, run the makemigrations and migrate commands, and restart the server.

```shell
python3 manage.py makemigrations
python3 manage.py migrate
python3 manage.py runserver
```

After we run the migration, that Task table will be updated.

{{<checkpoint>}}
Once you have made all the updates, log in and add a new task to yourself and to a different user of the system. Check that the tasks are showing up in the right places for the right people.
{{</checkpoint>}}

When we restart the server, we should see the following changes:
- The tasks on the Dashboard will only show the authenticated user's tasks and not everyone's tasks.
- The New Task page will show a new field where a user can be assigned. This field can be left blank and the task will be "lost" and can only be recovered in the admin page.

If the Dashboard does not show this, try to complete the steps again.

## Conclusion

We have create a link or relation between the User table and Task table. We can use this relation to assigns tasks to different users in our To-Do app making our app work in a multi-user environment.

We have learned to update Django models, forms and views to take advantage of relational databases so that users can assign tasks to others.

With this basic understanding of how tables are joined in Django, we have opened up many more opportunities where we can have one-to-one relationships but also one-to-many and many-to-many relationships, similar to the To-Do app.

The scope of this project is quite limited but the sky's the limit. You can do a so much with Django and relational databases. What we have learned in these 5 mini-lessons is literally the tip of the iceberg. If you think about it, Instagram was made with Django so anything is possible.
