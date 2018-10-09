---
layout: post
title: Creating custom modal with form in Drupal 8
---
A modal in Drupal 8 can be triggered by just adding this single line:
(<a class="use-ajax" data-dialog-type="modal" href="/registration">Register</a>)

#### Important: Make sure to add drupal core library 'core/drupal.dialog.ajax' to call ajax modal to the page triggering the modal.

Before start learning how to create custom modal, checkout the following repository:
[https://github.com/vatsalkhanna1992/custom_modal](https://github.com/vatsalkhanna1992/custom_modal)

### Step 1: Create info.yml
Create info.yml file which will include information about our custom module:

![_config.yml]({{ site.baseurl }}/images/info.png)

### Step 2: Create controller
Now, create a controller file which will display our custom modal. So, first create routing.yml file which defines the controller.

![_config.yml]({{ site.baseurl }}/images/routing.png)

This will define our controller from where the modal will get triggered. Then, create controller file:

![_config.yml]({{ site.baseurl }}/images/controller.png)

The ModalController should extend ControllerBase. 

### Step 3: Create form
Create a Form:

![_config.yml]({{ site.baseurl }}/images/form.png)

### Step 4: Call form and call OpenModalDialogCommand()
Once the form is created, call this form through controller using "$form = \Drupal::formBuilder()->getForm()". Now create modal by creating object of OpenModalDialogCommand() inside ajax response object.

![_config.yml]({{ site.baseurl }}/images/modal.png)

This will create a modal and set its width. Then, its wrapped into AJAX response object.

### Step 5: Create block to trigger modal
Now, create create a block, which contains a button to trigger modal.

![_config.yml]({{ site.baseurl }}/images/block.png)

#### Make sure, 'core/drupal.dialog.ajax' library is attached to the block. This will trigger the response as modal.
