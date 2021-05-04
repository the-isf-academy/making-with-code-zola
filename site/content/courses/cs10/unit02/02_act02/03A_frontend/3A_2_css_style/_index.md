---
title: 3.A.2 CSS Style
---

# Intro to CSS Style
The design of our todo app is really coming along! We now have the basic layout completed, so we can focus on adding visual elements
to improve the interface. These elements will not only make our app look better: having consistent and well-designed user interface (UI)
components can improve the usability of a site by making it more clear how to interact with and interpret information on a web page.

## A. Bootstrap Component
Rather than design UI elements from scratch, we're going to pull common elements like buttons and cards from the Bootstrap library. This
will allow you to quickly build a beautiful website while still giving you the freedom to customize your design where you need to.

{{< look-action >}} First, look through the [Bootstrap component library](https://getbootstrap.com/docs/4.6/components/alerts/) to see
what kinds of components Bootstrap offers. There are a lot here! But, you should recognize them from the Bootstrap library we used when
you were prototyping your apps with Figma.

### Basic Components
Let's start by add [the Bootstrap button](https://getbootstrap.com/docs/4.6/components/buttons/) component to our dashboard page. Just
like with the Bootstrap layout features, all we need to do is add the relevant Bootstrap classess to our HTML elements and the
Bootstrap CSS we've included in the base of our app will take care of the rest.

{{< code-action >}} In the `starter_app/dashboard.html` template file, add a button element and the bootstrap button class to the
task update link:
```html {linenos=table, hl_lines=["18-20", "32-34", "46-48"]}
`{% extends "base.html" %}


{% block content %}
<div class="container" style="width: 75%; margin-bottom: 50px">
    <h4>Tasks</h4>

  <ul class="list-group">
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=1 %}">
        <button type="button" class="btn btn-primary">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 2</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=2 %}">
        <button type="button" class="btn btn-primary">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 3</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=3 %}">
        <button type="button" class="btn btn-primary">
          Update
        </button>
      </a>
    </li>
  </ul>
</div>

{% endblock %}
```

With just those 2 additional lines of code, we've now added a responsive button that will help a user understand that they can interact
with the page by clicking on the button. Functionally, this is no different from a link. However, the addition of the button UI helps
guide the user in a particular way.

Let's explore this idea even more. Currently, our button is the brightest, largest thing on the page. This will immediately draw the
user's eye to the button. However, updating the task is probably not the first thing we want the user to consider when they see a task.
Instead, we probably want them to focus on different information like the task title or due date.

If you scroll through the [Bootstrap button component page](https://getbootstrap.com/docs/4.6/components/buttons/), you'll notice that there
are different ways we can style our buttons. We can change the color, boldness, and size of our buttons all with boostrap classes! If we
want to make our button draw less attention, we can make it darker, less bold, and smaller.

{{< code-action >}} Change the classes applied to our button components to make them use the secondary color, become outline buttons, and get smaller:
```html {linenos=table, hl_lines=[18, 32, 46]}
`{% extends "base.html" %}


{% block content %}
<div class="container" style="width: 75%; margin-bottom: 50px">
    <h4>Tasks</h4>

  <ul class="list-group">
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=1 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 2</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=2 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 3</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=3 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
  </ul>
</div>

{% endblock %}
```

We've just changed the *visual hierarchy* of the page - how the user will visually percieve the information on the page. When designing
a view of an app, paying attention to the visual hierarchy is one of the most important ways to make sure that a user will percieve the
information on your page in the way you want them to.

### Contexts
As we've just seen with the different button styles, Bootstrap offers many way to style your web page designs. Let's explore how
these features can help embed contextual information into our designs.

{{< code-action >}} First, let's add another Bootstrap component to our dashboard: a [badge](https://getbootstrap.com/docs/4.6/components/badge/)
for the label:
```html {linenos=table, hl_lines=[14, 28, 42]}
{% extends "base.html" %}


{% block content %}
<div class="container" style="width: 75%; margin-bottom: 50px">
    <h4>Tasks</h4>

  <ul class="list-group">
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-primary"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=1 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 2</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-primary"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=2 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 3</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-primary"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=3 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
  </ul>
</div>

{% endblock %}
```

We just added a badge to our tasks which changed the background style of the task label. This adds variation to the task info
container that will help the user parse the information. However, we can make the label even more information rich by manipulating
its color to help convey meaning. Color is often used to provide a visual indication for why something is on a page or to draw attention
to a specific part of the page. For example, notifications on your phone are displayed as red badges to indicate that something urgent is
happening.

Bootstrap offers a variety of color choices that help communicate different contexts for a component:
- primary - for a central component users should be drawn to
- secondary - for a less important component users should notice later
- success - to indicate a successful exchange or interaction
- danger - to indicate a definite problem
- warning - to indicate a potential problem or something to avoid
- info - to indicate extra or additional information
- light - to indicate something generally less important
- dark - to indicate something generally more important

What context do you think our label badge fits into? We're adding additional information to each task, so the info context would work
well here.

{{< code-action >}} Change the badge class for our task label:
```html {linenos=table, hl_lines=[14, 28, 42]}
{% extends "base.html" %}


{% block content %}
<div class="container" style="width: 75%; margin-bottom: 50px">
    <h4>Tasks</h4>

  <ul class="list-group">
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=1 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 2</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=2 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 3</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=3 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
  </ul>
</div>

{% endblock %}
```

{{< aside >}} The choice to make notification badges red is a very intentional one: the red color makes users percieve the information as
urgent and thus draws them to the app. This kind of design is one way that designers capture users' attention and influence their behavior.
Designing for behavior manipulation like this can be very useful (i.e. if you urgently need users to understand something, like [how to
help a choking person](https://www.laborposters.org/img/poster-thumbnails/new-york-0603-large.jpg). However, it can also be used to influence
users in negative ways, like subconciously encouraging them to use an app when they don't really want to by [inducing a stress response](https://onezero.medium.com/why-apples-notification-bubbles-are-so-stressful-65a544e51f10).
{{< /aside >}}
 

## B. Customization
Bootstrap classes cover a lot of ground. However, sometimes you will also want to customize them beyond the Bootstrap styles. To do this,
we can add custom CSS to our to override existing Bootstrap styles or create styles from scratch.

### Overiding Bootstrap classes

Let's make a customization so that our info badge better matches the color pallate of our todo app.

{{< code-action >}} First, open the file, `static/starter_app/custom.css`. You can leave it blank for now.

*(Note the file is in the `static` directory, not the `template` directory)*

Next, we need to reference this custom style file in our HTML template. In all our previous changes, we've been changing the
`<body>` portion of our HTML. However, to do this, we need to change the `<head>` portion.

{{< code-action >}} Add a new head block to our `dashboard.html` template:
```html {linenos=table, hl_lines=["3-8"]}
{% extends "base.html" %}

{% load static %}

{% block head %}
{{ block.super }}
<link rel="stylesheet" type ="text/css" href="{% static 'starter_app/custom.css' %}">
{% endblock %}

{% block content %}
...
```

Now, any CSS you write in the `custom.css` file you create will be applied to the dashboard page.

If we want to change the background color used for the info badge, we will need to override that CSS
property for the `badge-info` class.

{{< code-action >}} In `custom.css`, add the following CSS class:
```css {linenos=table, hl_lines=["1-3"]}
.badge-info {
    background-color: #81BE11;
}
```

Refresh the page and you'll see that our labels are now a shade of green that matches the background!

{{< code-action >}} Open the inspector in your browser and select the badge component. Look through the styles
and you'll see that the background of the `.badge-info` class from the `_badge.scss` file (a Bootstrap file) is now
being overriden by our definition of the `.badge-info` class in `custom.css`.

Since we have now defined the most specific definition of the class, our definition will be applied to all elements
with that class added to them.

### Custom classes and IDs
Overriding existing Bootstrap classes can go a long way, but sometimes you will need to change the styles of different
groups of HTML elements or even specific instances of an element. In these cases, you can write custom CSS
classes.

You can apply a custom CSS class just like you applied the bootstrap class: just give it a definition in your CSS
file and add the class name to the component's class list. Let's create a class so that we can identify task items that
have due dates that are close.

{{< code-action >}} Add a new class in your `custom.css` file:
```css {linenos=table, hl_lines=["5-7"]}
.badge-info {
    background-color: #81BE11;
}

.due-soon {
    background-color: #FFFF9C;
}
```

{{< code-action >}} Then, apply the class you just created to a few tasks on the dashboard:

```html {linenos=table, hl_lines=[19, 47]}
{% extends "base.html" %}

{% load static %}

{% block head %}
{{ block.super }}
<link rel="stylesheet" type ="text/css" href="{% static 'starter_app/custom.css' %}">
{% endblock %}


{% block content %}
<div class="container" style="width: 75%; margin-bottom: 50px">
    <h4>Tasks</h4>

  <ul class="list-group">
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task</h5>
        <p class="due-soon"><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=1 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 2</h5>
        <p><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=2 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 3</h5>
        <p class="due-soon"><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=3 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
  </ul>
</div>

{% endblock %}
```

This works for groups of elements that you want to apply styles to, but what if you need to identify a specific
element? For example, let's say we want to highlight the single task with the most urgent due date.

Rather than make a class which could be applied to many elements, we can use an ID selector that serves as the reference
for a single, specific element:

{{< code-action >}} In your `custom.css` file, add an ID selector:
```css {linenos=table, hl_lines=["5-7"]}
.badge-info {
    background-color: #81BE11;
}

.due-soon {
    background-color: #FFFF9C;
}

#due-next {
    background-color: #FFBA8C;
}
```

*Note that class selectors start with a `.` while ID selectors start with `#`.*

{{< code-action >}} Then, set the ID for the task that is due next:
```html {linenos=table, hl_lines=[33]}
{% extends "base.html" %}

{% load static %}

{% block head %}
{{ block.super }}
<link rel="stylesheet" type ="text/css" href="{% static 'starter_app/custom.css' %}">
{% endblock %}


{% block content %}
<div class="container" style="width: 75%; margin-bottom: 50px">
    <h4>Tasks</h4>

  <ul class="list-group">
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task</h5>
        <p class="due-soon"><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=1 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 2</h5>
        <p id="due-next"><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=2 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
    <li class="list-group-item">
      <div class="d-flex w-100 justify-content-between">
        <h5 class="mb-1">Task 3</h5>
        <p class="due-soon"><strong>Date Due:</strong> Date holder</p>
      </div>
      <p class="badge badge-info"><i>Label</i></p>

      <p>Notes: notes holder</p>
      <a href="{% url 'update-task' pk=3 %}">
        <button type="button" class="btn btn-outline-secondary btn-sm">
          Update
        </button>
      </a>
    </li>
  </ul>
</div>

{% endblock %}
```

## C. Now you try
There are many more Bootstrap utilities and components to try out, but they all work the same way. Create the
elements and add the classes as shown in the [Bootstrap documentation](https://getbootstrap.com/docs/4.6/components/alerts/),
and you'll be well on your way to designing snazzy and functional web apps in no time.

{{< code-action >}} Spend the rest of the lesson exploring the boostrap components and add them to other pages
of the todo app to make it more functional and visually appealing.
