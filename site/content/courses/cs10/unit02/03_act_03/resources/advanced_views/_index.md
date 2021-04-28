---
title: Advanced Views
---

# Advanced Views

In Django, the `view` is used to handle the logic for the request and response. In Act II, we learned how to send all of the data from the model to the view and then how to display that information in the template. But, what if we only want to send some of the data? 

We see real world implementations of this all time. Take OpenRice for example. 

{{< figure src="images/courses/cs10/unit02/resources_advanced_views.png" width="40%"  >}}

When searching for restaurants in Tsim Sha Tsui, the platform will initially give you all the available options. But what you only want to view Thai restaurants, or only restaurants with a noodle dish, or only restaurants with wi-fi. Open Rice gives you the ability to filter the data. 

Django has made filtering quite easy via class based `views`. 
