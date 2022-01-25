<!-- loiobcdbde6911bd4fc68fd435cf8e306ed0 -->

| loio |
| -----|
| bcdbde6911bd4fc68fd435cf8e306ed0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/bcdbde6911bd4fc68fd435cf8e306ed0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/bcdbde6911bd4fc68fd435cf8e306ed0)</div>

## OData V4

In this tutorial, we explore how features of OData V4 can be used in OpenUI5. We write a small app that consumes data from an OData V4 service to understand how to access, modify, aggregate, and filter data in an OData V4 model.

OData is a standard protocol for creating and consuming data by using simple HTTP and REST APIs for create, read, update, delete \(CRUD\) operations.

We start with an initial app that simply retrieves data from an OData V4 service and displays it as a plain list.

***

<a name="loiobcdbde6911bd4fc68fd435cf8e306ed0__section_dsn_cwc_z1b"/>

### Preview

 ![](loioe518debe1cdc4fcd9f5a6cffd014fbfa_LowRes.png) 

***

> ### Tip:  
> You don't have to do all tutorial steps sequentially, you can jump directly to any step you want. In each step, download the code from the previous step, copy it to your workspace, and make sure that the application runs by calling the `webapp/index.html` file.
> 
> You can view and download the samples for all steps in the Demo Kit at [OData V4](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.core.tutorial.odatav4/samples). Depending on your development environment you might have to adjust resource paths and configuration entries.
> 
> For more information, check the following sections of the tutorial overview page \(see [Get Started: Setup, Tutorials, and Demo Apps](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md)\):
> 
> -   [Downloading Code for a Tutorial Step](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download)
> 
> -   [Adapting Code to Your Development Environment](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation)

1.  [Step 1: The Initial App](Step_1_The_Initial_App_15d84f3.md "We start by setting up a simple app that loads data from an OData service and displays
		it in a table. We use a mock server to simulate requests to and responses from the
		service.")  
We start by setting up a simple app that loads data from an OData service and displays it in a table. We use a mock server to simulate requests to and responses from the service.
2.  [Step 2: Data Access and Client-Server Communication](Step_2_Data_Access_and_Client_Server_Communication_e9de002.md "In this step, we see how the Table that is bound to the
			People entity set initially requests its data, and how the data can be
		refreshed. We use the Console tab in the browser developer tools to
		monitor the communication between the browser and the server. We see the initial request as
		well as the requests for refreshing the data.")  
In this step, we see how the `Table` that is bound to the `People` entity set initially requests its data, and how the data can be refreshed. We use the *Console* tab in the browser developer tools to monitor the communication between the browser and the server. We see the initial request as well as the requests for refreshing the data.
3.  [Step 3: Automatic Data Type Detection](Step_3_Automatic_Data_Type_Detection_96bb6e0.md "In this step, we use the automatic data type detection of the OData V4 model to parse,
		validate, and format user entries. The service metadata contains type information for the
		properties of each entity.")  
In this step, we use the automatic data type detection of the OData V4 model to parse, validate, and format user entries. The service metadata contains type information for the properties of each entity.
4.  [Step 4: Filtering, Sorting, and Counting](Step_4_Filtering_Sorting_and_Counting_426ff31.md "In this step, we add features to filter, sort, and count the user data by using the
		OData V4 model API to apply OData system query options $filter,
			$orderby, and $count.")  
In this step, we add features to filter, sort, and count the user data by using the OData V4 model API to apply OData system query options `$filter`, `$orderby`, and `$count`.
5.  [Step 5: Batch Groups](Step_5_Batch_Groups_ef2af49.md "In this step, we have a closer look at batch groups. Batch groups are used to group
		multiple requests into one server request to improve the overall performance. ")  
In this step, we have a closer look at batch groups. Batch groups are used to group multiple requests into one server request to improve the overall performance.
6.  [Step 6: Create and Edit](Step_6_Create_and_Edit_b4f1266.md "In this step, we will make it possible to create and edit (update) user data from the
		user interface and send the data to the back end.")  
In this step, we will make it possible to create and edit \(update\) user data from the user interface and send the data to the back end.
7.  [Step 7: Delete](Step_7_Delete_12a0d1e.md "In this step, we make it possible to delete user data.")  
In this step, we make it possible to delete user data.
8.  [Step 8: OData Operations](Step_8_OData_Operations_a3e7cb6.md "Our OData service provides one OData operation: the ResetDataSource
		action. In this step, we add a button that resets all data changes we made during the
		tutorial to their original state using this action.")  
Our OData service provides one OData operation: the `ResetDataSource` action. In this step, we add a button that resets all data changes we made during the tutorial to their original state using this action.
9.  [Step 9: List-Detail Scenario](Step_9_List_Detail_Scenario_ec44581.md "In this step we add a detail area with additional information.")  
In this step we add a detail area with additional information.
10. [Step 10: Enable Data Reuse](Step_10_Enable_Data_Reuse_e687dbd.md "In this step we avoid unnecessary back-end requests by preventing the destruction of data shown in the detail area when sorting or
		filtering the list.")  
In this step we avoid unnecessary back-end requests by preventing the destruction of data shown in the detail area when sorting or filtering the list.
11. [Step 11: Add Table with :n Navigation to Detail Area](Step_11_Add_Table_with_n_Navigation_to_Detail_Area_19cc773.md "In this step we add a table with additional information to the detail area.")  
In this step we add a table with additional information to the detail area.

**Related Information**  


[OData Standard Protocol](http://www.odata.org/documentation/)

[OData V4 Model](OData_V4_Model_5de13cf.md "The sap.ui.model.odata.v4.ODataModel is the model implementation for consuming an OData V4 service.")

[*Basic Tutorial* on the *OData* Home Page](http://www.odata.org/getting-started/basic-tutorial/)

