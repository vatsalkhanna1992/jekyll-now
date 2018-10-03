---
layout: post
title: Working with autocomplete address module for webforms in Drupal 7
---

Please check the following repository for autocomplete address module in github: [https://github.com/vatsalkhanna1992/address_autocomplete](https://github.com/vatsalkhanna1992/address_autocomplete).

address_autocomplete is a Drupal 7 module. It uses Google Places API to build autocomplete address field in Drupal webforms. So, there is a depedency of Drupal [Webform](https://www.drupal.org/project/webform) module.

Before start implementing the module in your site, you first need Google API key, which you can get from [https://console.cloud.google.com](https://console.cloud.google.com). 

So, first create your project at Google Console platform and search for the below two apis:
1. Maps Javascript API
2. Places API

Enable them for your project. After enabling, go to "APIs and Services" section in menu and select Credentials. You can see your API key, just copy it from there.

Now enable the module and go to the autocomplete address module configuration - /admin/config/development/address-autocomplete. Put in the API key, you copied earlier and click save.

Once, this API key is set, you just need to create a webform with fields - Address, street number, route, state, city and postal or zip code. Make sure, all these fields are of type as textfield.

While creating these fields, you'll get option for autocomplete checkbox as shown in the screenshot below:
![_config.yml]({{ site.baseurl }}/images/checkbox.png)

Check the box and you'll get another option for mapping the field type, like this:
![_config.yml]({{ site.baseurl }}/images/field-type.png)
Just select the respective field and save.

Similarly, do the same thing for other fields too, and check the webform. That's all.

Now try typing in the "Address" field, you'll get suggestions and once you select any suggestion, it will fill out all the other fields - City, State, ZIP code etc.
