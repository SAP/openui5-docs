<!-- loio07afcf400eb344c2916e4eb3a400ff7b -->

## Use the MVC Concept

MVC \(Model-View-Controller\) is a concept for structuring your software. It makes it easier to maintain and to extend your apps.

The MVC pattern divides your application into three individual parts that interact with each other: the model, the views, and the controllers. There are some best practices for each of these parts:



<a name="loio07afcf400eb344c2916e4eb3a400ff7b__section_b4d_djb_1gb"/>

### Model: Keep everything organized

It's simple: Use the right folder structure! If you arrange and structure your files and folders in a smart way, this makes coding much easier and also makes for sound performance when you load your application.

-   Find out more: [Folder Structure: Where to Put Your Files](../05_Developing_Apps/folder-structure-where-to-put-your-files-003f755.md)



<a name="loio07afcf400eb344c2916e4eb3a400ff7b__section_y5f_y4b_1gb"/>

### View: Use XML views

There are many view types, for example JavaScript, JSON, or HTML. However, we strongly recommend that you use XML views and fragments. XML clearly separates the view and the application logic, is easy to manipulate and can be parsed by tools like the layout editor in SAP Business Application Studio. That's why we also used XML views in all our tutorials, demo apps, and guides.

-   Learn how: Walkthrough Tutorial [Step 4: XML Views](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/1409791afe4747319a3b23a1e2fc7064.html "Putting all our UI into the index.js file will very soon result in a messy setup, and there is quite a bit of work ahead of us. So let's do a first modularization by putting the sap/m/Text control into a dedicated view.") :arrow_upper_right:
-   Find out more: [XML View](../04_Essentials/xml-view-91f2928.md)



<a name="loio07afcf400eb344c2916e4eb3a400ff7b__section_ubl_3qb_1gb"/>

### Controller: Find the best location for your controllers

Every view you create should have its own controller with a corresponding file name. For example: If your view is called `App.view.xml`, then the matching controller should be named `App.controller.js` \(in JavaScript\) or `App.controller.ts` \(in TypeScript\).

There is one special case: The so called `BaseController` is not directly related to a view. It is quite common that several controllers use the same functions. You can place these shared functions in the `BaseController` from which all other instantiated controllers will inherit. In other words: Every function you place in the `BaseController` is available for all your controllers. This makes your app code definitely easier to maintain, and you save some lines of code!

The controllers are written in JavaScript or TypeScript and contain the app logic. They should be placed in the `controller` folder. However, not all relevant code belongs in the `controller` folder. Consider formatter logic, for example, which has mainly the function to format data. That's why you should rather place it in the `models` folder of your application.

-   Learn how: Walkthrough Tutorial [Step 5: Controllers](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/50579ddf2c934ce789e056cfffe9efa9.html "In this step, we replace the text with a button and show the "Hello World" message when the button is pressed. The handling of the button's press event is implemented in the controller of the view.") :arrow_upper_right:
-   Find our more: [Controller](../04_Essentials/controller-121b8e6.md)

