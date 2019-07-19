<!-- loioe5310932a71f42daa41f3a6143efca9c -->

| loio |
| -----|
| e5310932a71f42daa41f3a6143efca9c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e5310932a71f42daa41f3a6143efca9c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e5310932a71f42daa41f3a6143efca9c)</div>

## Data Binding

In this tutorial, we will explain the concepts of data binding in OpenUI5.

You use data binding to bind UI elements to data sources to keep the data in sync and allow data editing on the UI.

For data binding, you need a model and a binding instance: The model instance holds the data and provides methods to set the data or to retrieve the data from a server. It also provides a method for creating bindings to the data. When this method is called, a binding instance is created, which contains the binding information and provides an event, which is fired whenever the bound data changes. An element can listen to this event and update its visualization according to the new data.

The UI uses data binding to bind controls to the model which holds the application data, so that the controls are updated automatically whenever application data changes. Data binding is also used the other way round, when changes in the control cause updates in the underlying application data, for example data entered by the user. This is called two-way binding.

***

### Preview

 ![](loio896048ebce6b47488068c9630b71c43a_HiRes.png) 

> Note:
> You don't have to do all tutorial steps sequentially, you can also jump directly to any step you want. Just download the code from the previous step, copy it to your workspace and make sure that the application runs by calling the `webapp/index.html` file.
> 
> You can view and download the files for all steps in the Demo Kit at [Data Binding](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.core.tutorial.databinding/samples). Depending on your development environment you might have to adjust resource paths and configuration entries.
> 
> For more information check the following sections of the tutorials overview page \(see [Get Started: Setup and Tutorials](Get_Started_Setup_and_Tutorials_8b49fc1.md)\):
> 
> -   [Downloading Code for a Tutorial Step](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download)
> 
> -   [Adapting Code to Your Development Environment](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation)
> 
> 
> 

**Related information**  


[Data Binding](Data_Binding_68b9644.md)

[Model View Controller \(MVC\)](Model_View_Controller_(MVC)_91f2334.md)

