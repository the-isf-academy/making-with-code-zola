---
title: Pagination
---

# Pagination

Pagination is the ability to divide content amongst multiple pages. 


For example when using Google, the results are organized in pages as opposed to an infinitely scrolling webpage. 

{{< figure src="images/courses/cs10/unit02/resources_pagination_01.png" width="60%"  >}}


Enabling pagination in your web app will require a few small additions to your framework. With just a few additions to the `view` and `template` files, you'll have pagination up and running!


[Django has a built in pagination feature](https://docs.djangoproject.com/en/3.2/topics/pagination/) 
 that makes implementing it into your web app super simple.

## View.py 

Let's take a look at this code snippet from a built out version of the to-do app. 

```python {hl_lines=["4","7"]}  
class AllTasks(ListView):
    template_name = 'task/all_tasks.html' 
    model = Task
    paginate_by = 3
    context_object_name = 'tasks'

    def get_queryset(self):
        #Filters out archived tasks for logged in user
        data = self.model.objects.all().filter(archive=False).filter(task_user=self.request.user)

        return data.order_by('-due_date') 
```
- `paginate_by` - defines how many instances of the model should be displayed on each page
- `get_queryset()` = defines the data that will be sent to th model 




## Templates

### [pagination.html]


### [all_tasks.html]


## Working Pagination 
Once your `view` and `template` files have been updated accordingly, Django will take care of the rest! 

{{< figure src="images/courses/cs10/unit02/resources_pagination_02.png" width="100%"  >}}

