<!-- loio07afcf400eb344c2916e4eb3a400ff7b -->

| loio |
| -----|
| 07afcf400eb344c2916e4eb3a400ff7b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/07afcf400eb344c2916e4eb3a400ff7b) | [demo kit latest release](https://sdk.openui5.org/topic/07afcf400eb344c2916e4eb3a400ff7b)</div>

## Use the MVC Concept

MVC \(Model-View-Controller\) is a concept for structuring your software. It makes it easier to maintain and to extend your apps.

The MVC pattern divides your application into three individual parts that interact with each other: the model, the views, and the controllers. There are some best practices for each of these parts:

***

<a name="loio07afcf400eb344c2916e4eb3a400ff7b__section_b4d_djb_1gb"/>

### Model: Keep everything organized

It's simple: Use the right folder structure! If you arrange and structure your files and folders in a smart way, this makes coding much easier and also makes for sound performance when you load your application.

-   Find out more: [Folder Structure: Where to Put Your Files](Folder_Structure_Where_to_Put_Your_Files_003f755.md)

***

<a name="loio07afcf400eb344c2916e4eb3a400ff7b__section_y5f_y4b_1gb"/>

### View: Use XML views

There are many view types, for example JavaScript, JSON, or HTML. However, we strongly recommend that you use XML views and fragments. XML clearly separates the view and the application logic, is easy to manipulate and can be parsed by tools like the layout editor in SAP Business Application Studio. That's why we also used XML views in all our tutorials, demo apps, and guides.

-   Learn how: Walkthrough Tutorial [Step 4: XML Views](Step_4_XML_Views_1409791.md)
-   Find out more: [XML View](XML_View_91f2928.md)

***

<a name="loio07afcf400eb344c2916e4eb3a400ff7b__section_ubl_3qb_1gb"/>

### Controller: Find the best location for your controllers

Every view you create should have its own controller with a corresponding file name. For example: If your view is called `App.view.xml`, then the matching controller should be named `App.controller.js`.

There is one special case: The so called `BaseController` is not directly related to a view. It is quite common that several controllers use the same functions. You can place these shared functions in the `BaseController` from which all other instantiated controllers will inherit. In other words: Every function you place in the `BaseController` is available for all your controllers. This makes your app code definitely easier to maintain, and you save some lines of code!

The controllers are written in JavaScript and contain all the app logic. They should be placed in the `controller` folder. However, not all JavaScript code belongs in the `controller` folder. For example, formatter logic. The main function of this type of JavaScript file is to format data. That's why you should place it in the `models` folder of your application.

-   Learn how: Walkthrough Tutorial [Step 5: Controllers](Step_5_Controllers_50579dd.md)
-   Find our more: [Controller](Controller_121b8e6.md)

