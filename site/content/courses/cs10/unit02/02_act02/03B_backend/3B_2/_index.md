---
Title: 3.B.2 Using the Admin Page
---

# Using the Admin Page

## Finding the Admin Page

Now that we have successfully added data into our app, it would be great if we had some way to access it.

Well, Django has a build-in administration page that allows us to look at the data in our database! Our Task app has one and can be accessed by going to

```shell
https://localhost:8000/admin/
```

If you go to this URL, there will be a webpage where we can log in to the admin site. We will need Superuser access for this. More on that below.

## Enabling/Disabling the Admin Page on Django

Just like other parts of our app, the Administration page is a route that is configured in Django. We need to put in a few lines of code (or comment them out) to enable/disable the admin page of our site.

First we need to check the **base.py** file under the cs10_webapp_base/settings directory. We need to make sure there is a line that reads something like this...

```shell
INSTALLED_APPS = [
    'django.contrib.admin',
    # other installed apps go here...
]
```

If this code isn't in **base.py**, you will need to copy and paste this code in. Django should have already added this for us by default.

The second place to check is the **urls.py** file in the starter_app directory. We need to make sure there a configured route (or path) for the admin site. The code should look like

```shell
urlpatterns = [
    path('admin/', admin.site.urls),
    #other routes go here
    ]
```

To disable the admin page, comment out the route to the admin page and restart the server.

## Creating a Superuser Account

We've successfully checked that the admin site is ready to go but we can't log in! We need to create a Superuser account to log into the admin site.

To create a Superuser for our website, quit the Django server and in the same path, type in Terminal:

```shell
python3 manage.py createsuperuser
```

Django will then prompt you to enter a username and password and that user will have superuser access to the admin site. We can then restart the server and access the admin site using the superuser account.

## Using the Admin Site to Access Data in the Database

By default, the Django admin site doesn't allow us to do much. We can play around with user groups and user accounts.

If we want to look at our Task data, we can register our models in *admin.py* and Django will give access to our data through the admin page. The *admin.py* file can be found in the starter_app directory.

Let's register the Task model so we can see our Task data in the database from within the admin page.

```shell
from .models import Task

@admin.register(Task)
class RequestDemoAdmin(admin.ModelAdmin):
  list_display = [field.name for field in Task._meta.get_fields()]

```
These lines of code will enable us to access the data in the Task table. We can create/update/delete tasks here as well.

Just make sure to refresh the admin page to see the changes.

## Remember Uncle Ben...

As the owners and administrators of your website, you have access to your user's accounts and all of your user's data. We literally have a "God" view of everything that is entered into our database.

There are lots of ethical questions that need to be considered when building an app, and because of this, always remember the quote from Uncle Ben to Peter Parker...   

**With great power comes great responsibility!**

Always remember this as we continue to develop our app.
