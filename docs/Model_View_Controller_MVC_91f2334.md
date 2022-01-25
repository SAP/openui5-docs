<!-- loio91f233476f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f233476f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f233476f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f233476f4d1014b6dd926db0e91070)</div>

## Model View Controller \(MVC\)

The Model View Controller \(MVC\) concept is used in OpenUI5 to separate the representation of information from the user interaction. This separation facilitates development and the changing of parts independently.

Model, view, and controller are assigned the following roles:

-   The **view** is responsible for defining and rendering the UI.
-   The **model** manages the application data.
-   The **controller** reacts to view events and user interaction by modifying the view and model.

***

![](loio1eb216151b1b41f1979b7b6c969670df_LowRes.png)

-   [Models](Models_e1b6259.md)
-   [Controller](Controller_121b8e6.md)
-   [Views](Views_91f27e3.md)

***

The purpose of data binding in the UI is to separate the definition of the user interface \(view\), the data visualized by the application \(model\), and the code for the business logic for processing the data \(controller\). The separation has the following advantages: It provides better readability, maintainability, and extensibility and it allows you to change the view without touching the underlying business logic and to define several views of the same data.

Views and controllers often form a 1:1 relationship, but it is also possible to have controllers without a UI, these controllers are called application controllers. It is also possible to create views without controllers. From a technical position, a view is a OpenUI5 control and can have or inherit a OpenUI5 model.

View and controller represent reusable units, and distributed development is highly supported.

-   **[Models](Models_d2c8cf7.md "A model in the Model View Controller concept holds the data and provides methods to
		retrieve the data from the database and to set and update data.")**  
A model in the Model View Controller concept holds the data and provides methods to retrieve the data from the database and to set and update data.
-   **[Views](Views_91f27e3.md "The view in the Model-View-Controller (MVC) concept is responsible for defining and rendering the UI. OpenUI5 supports predefined view types.")**  
The view in the Model-View-Controller \(MVC\) concept is responsible for defining and rendering the UI. OpenUI5 supports predefined view types.
-   **[Controller](Controller_121b8e6.md "A controller contains methods that define how models and views interact.")**  
A controller contains methods that define how models and views interact.
-   **[Support for Unique IDs](Support_for_Unique_IDs_91f28be.md "Stable IDs are used to identify and modify the controls within the controller during
		runtime. However, if you reuse or nest these views, these stable IDs are no longer unique.
		To avoid ambiguity, each view adds its own ID as prefix to all its child
		controls.")**  
Stable IDs are used to identify and modify the controls within the controller during runtime. However, if you reuse or nest these views, these stable IDs are no longer unique. To avoid ambiguity, each view adds its own ID as prefix to all its child controls.

