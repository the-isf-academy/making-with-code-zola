---
Title: 3.B.3 Data Validation
draft: True

---

# Data Validation

Before diving into data validation, we need to understand some basic principals first. And to do that, we'll look at a very common use case of our To-Do app.

## Transactions

When a new task gets POSTed back to the server, Django does a lot of magic and saves the task into the database. When Django does this, or does any other "work" to the database, Django is making a *transaction* to the database.

This "work" can be adding a new task, changing the user name, updating a password, deleting a task, viewing a task. Basically, any "work" that touches the database in any sort of way is a database transaction.

## Transaction Properties

Transactions have unique properties that we need to learn about otherwise our database will become corrupted and unusable. There are 4 properties to remember.

### ***Atomicity***

We can't simply add some parts to the database transaction. It's all or nothing. Imagine updating a user's first name and last name where the first name changes but the last name doesn't. Imagine if this was a police database and the impact this would have on an innocent person! Yikes...

### ***Consistency***

Only valid data will be written into the database. If the data isn't valid, the transaction doesn't go through. More on this when we talk about data validation.

### ***Isolation***

Each transaction is independent of each other and do not impact other transactions that are occurring at the same time.

{{< checkpoint >}}
Let's say there's a joint bank account. There's $500 in the account. Two people are making transactions to this account. Both want to withdraw $500 from the account.

What should happen after the withdraws?
{{</checkpoint>}}

The logical thing that should happen is that the first person withdraws $500 and the second person gets an error saying there's no money in the bank and gets no money.

{{< checkpoint >}}
Can you describe a scenario that would make it possible that both people can receive $500 from the bank?
{{</ checkpoint >}}

Let's discuss this in more detail as to how this could potentially happen.

What if the two withdraws happen concurrently but the second transaction starts and finishes before the first transaction finishes?

Let's see this step by step...

- The Bank has $500 in the joint account
- Jonny requests $500 from the account
- Bank receives the request from Jonny and starts processing the transaction. Uh oh, there are some slow downs in the system and Jonny has to wait 60 seconds. :(
- While Jonny is waiting, Jenny requests $500 from the account. She has no slow downs and gets her $500 from the bank account. :)
- Bank account subtracts $500 from the account and the account has $0.
- Finally, Jonny is done waiting but because Jonny is in the middle of his transaction, the bank appears to still have $500 in the account. Because of this, Jonny receives $500 and bank subtracts the money from the account. When the bank subtracts the money, the account is at $0 but the bank still needs to subtract $500 from that amount. The account is now at -$500.

We have a "bank error in your favour" situation where there's an extra $500 that's taken out of the account and the bank lost $500. Might sound great for us if we aren't the bank. However, in our case, we are the bank. We don't want to lose $500 (or lose anything really...)

This is one reason why we need to isolate transactions. If we don't, a lot of things can go wrong.

### ***Durability***

This is the idea that all transactions that are committed to the database are saved and not lost. It would be awful to lose data during a transaction.

Together, the 4 properties are called **ACID**.

Fortunately, Django helps us maintain ACID properties with good database management routines. Django saves us a lot of these headaches and we don't need to manage locks and concurrency issues.

One thing we still need to code for is to keep data consistent (based on our business logic) and we can do that with data validation.

## Django and Data Validation

In the To-Do App example, the New Task page uses a Django Model form and some of the fields have built-in validation like the date field. If you enter a date that doesn't match "YYYY-MM-DD", the form will throw an error message on the screen under the field. It's great that Django does this for us automatically.

But what if we want to add custom validation on our forms? Well, we can create code that does this. Let's investigate this with a slightly modified example from the Django documentation.

```python
from django.core.exceptions import ValidationError
from django.utils.translation import gettext_lazy as _

def validate_a_value(value):
  if value % 2 != 0:
    raise ValidationError(
      _('error!'),
      params={'value':value},
    )
```
We can see there are some import statements and a validator function. The function takes in a value, then checks it against a condition. If the check condition is false, the function will raise a ValidationError, which is a Django exception error. We can catch these validation errors and then deal with them with code. In this case, it prints out an error message on the form.

{{<checkpoint>}}
What does this code validate?
{{</checkpoint>}}

If you guessed validating if a number is odd, you are incorrect. (It's validating even numbers). :p

There are a number of built-in validators in Django and the list can be found here.
https://docs.djangoproject.com/en/3.2/ref/validators/

We will take a look at RegexValidator, which is the most powerful one in the list.

## Regex and RegexValidator

RegexValidator uses regular expressions (Regex), which is a fancy way of saying "Search patterns". We use Regex to search out patterns in text. This can be really useful for things like validation where we can compare what the user typed out to what we actually want to save into the database.

How do we use Regex in Django? Let's use Regex to validate the title of the New Task form to be only capital letters.

{{< code-action >}} Start by creating a `validators.py` file in the `starter_app` directory. Add the following code to the file.

```python
from django.core.exceptions import ValidationError
from django.utils.translation import gettext_lazy as _
from django.core.validators import RegexValidator
import re

def validate_caps(value):
    reg = re.compile('[A-Z]')
    for letter in value:
        if not reg.match(letter):
            raise ValidationError(_('Must be all capital letters'))
```

We are importing the same two lines as the Django example but we are also importing two other things: the Django RegexValidator and the *re* module, which is the Python Regex module.

In the validation function `validate_caps`, we are using the regular expression '[A-Z]' (which is to say only capital letters), and comparing that with the input value. If the input value doesn't match, raise a ValidationError on the screen.  

Now that we've written the validation function, let's add it into our model.

{{< code-action >}} Open `models.py`. First, import the `validate_caps()` function and then add the `validators` parameter to the `title` field.

The validators option will tell Django to use `validate_caps()` on form submissions.


```python {hl_lines=["5","9"]}
import datetime
from django.db import models
from django.utils import timezone
from django.utils.timezone import now
from .validators import validate_caps


class Task(models.Model):
    title = models.CharField(max_length=30, validators=[validate_caps])
    label = models.CharField(max_length=8)
    notes = models.TextField(editable=True, max_length=200)

    due_date = models.DateField('Date Due', editable=True)
    pub_date = models.DateTimeField('Date Created',default=now, editable=False)
    archive = models.BooleanField(default=False)


    def __str__(self):
        return self.title

    def date_created(self):
        return self.pub_date >= timezone.now() - datetime.timedelta(days=1)
```

{{< code-action >}} Run the server and check if the validation is working. Now, when submitting a new task, the title must begin with a capital letter. The validation is applied to the form and works like a charm!


## Custom Validation

The ability to write custom validations is an incredibly powerful tool. Let's explore what it can do by creating a content filter.

{{< code-action >}} Write and add a validator to the Task's text fields that prevents users from submitting tasks with the words below.

*Banned words: 'pizza', 'dumplings', 'lemonade', 'mochi', 'hummus'*

{{< checkpoint >}}

Answer the following questions in your `Django Backend Worksheet` Google Doc.

0. Will you add data validation into your own app? If so, in what aspect of the model?
0. What are the ethical considerations of data validation?

{{</checkpoint >}}

## Wrapping Up

Django has incredible database support that makes database administration easy. Django also helps us build databases that keep ACID properties. Further, data validation on data entry forms such as the New Task form, can use regular expressions and other validators to keep data clean... Added plus is that it's so easy to code.

If our projects need any additional validation on form fields, we can use this code pattern to add more validation wherever is needed.

I hope this lesson has given more insight on databases, database transactions and data validation. Next up is Relational Databases.
