<!-- loio3da5f4be63264db99f2e5b04c5e853db -->

| loio |
| -----|
| 3da5f4be63264db99f2e5b04c5e853db |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3da5f4be63264db99f2e5b04c5e853db) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3da5f4be63264db99f2e5b04c5e853db)</div>

## Walkthrough

In this tutorial we will introduce you to all major development paradigms of OpenUI5.

We first introduce you to the basic development paradigms like *Model-View-Controller* and establish a best-practice structure of our application. We'll do this along the classic example of “Hello World” and start a new app from scratch. Next, we'll introduce the fundamental data binding concepts of OpenUI5 and extend our app to show a list of invoices. We'll continue to add more functionality by adding navigation, extending controls, and making our app responsive.Finally we'll look at the testing features and the built-in support tools of OpenUI5.

***

### Preview

 ![](loio62a5405e63324cb4928e587f518ae13f_HiRes.png) 

***

> ### Tip:  
> You don't have to do all tutorial steps sequentially, you can also jump directly to any step you want. Just download the code from the previous step, copy it to your workspace and make sure that the application runs by calling the `webapp/index.html` file.
> 
> You can view and download the samples for all steps in the in the Demo Kit at [Walkthrough](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.tutorial.walkthrough/samples). Depending on your development environment you might have to adjust resource paths and configuration entries.
> 
> For more information check the following sections of the tutorials overview page \(see [Get Started: Setup, Tutorials, and Demo Apps](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md)\):
> 
> -   [Downloading Code for a Tutorial Step](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download)
> 
> -   [Adapting Code to Your Development Environment](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation)

1.  [Step 1: Hello World!](Step_1_Hello_World_2680aa9.md "As you know OpenUI5 is all about HTML5. Let’s get started with building a first “Hello
		World” with only HTML.")  
As you know OpenUI5 is all about HTML5. Let’s get started with building a first “Hello World” with only HTML.
2.  [Step 2: Bootstrap](Step_2_Bootstrap_fe12df2.md "Before we can do something with OpenUI5, we need to load and initialize it.
		This process of loading and initializing OpenUI5 is called
			bootstrapping. Once this bootstrapping is finished, we simply display an alert.")  
Before we can do something with OpenUI5, we need to load and initialize it. This process of loading and initializing OpenUI5 is called **bootstrapping**. Once this bootstrapping is finished, we simply display an alert.
3.  [Step 3: Controls](Step_3_Controls_ddbceec.md "Now it is time to build our first little UI by replacing the “Hello World” text in
		the HTML body by the OpenUI5
		control sap.m.Text. In the beginning, we will use the JavaScript control
		interface to set up the UI, the control instance is then placed into the HTML body. ")  
Now it is time to build our first little UI by replacing the “Hello World” text in the HTML body by the OpenUI5 control `sap.m.Text`. In the beginning, we will use the JavaScript control interface to set up the UI, the control instance is then placed into the HTML body.
4.  [Step 4: XML Views](Step_4_XML_Views_1409791.md "Putting all our UI into the index.html file will very soon result in a
		messy setup and there is quite a bit of work ahead of us. So let’s do a first modularization
		by putting the sap.m.Text control into a dedicated
		view.")  
Putting all our UI into the `index.html` file will very soon result in a messy setup and there is quite a bit of work ahead of us. So let’s do a first modularization by putting the `sap.m.Text` control into a dedicated `view`.
5.  [Step 5: Controllers](Step_5_Controllers_50579dd.md "In this step, we replace the text with a button and show the “Hello World” message
		when the button is pressed. The handling of the button's press event is
		implemented in the controller of the view.")  
In this step, we replace the text with a button and show the “Hello World” message when the button is pressed. The handling of the button's `press` event is implemented in the controller of the view.
6.  [Step 6: Modules](Step_6_Modules_f665d0d.md "In OpenUI5, resources are
		often referred to as modules. In this step, we replace the alert from the last exercise with
		a proper Message Toast from the sap.m library. The required modules are
		enabled to be loaded asynchronously.")  
In OpenUI5, resources are often referred to as modules. In this step, we replace the alert from the last exercise with a proper Message Toast from the `sap.m` library. The required modules are enabled to be loaded asynchronously.
7.  [Step 7: JSON Model](Step_7_JSON_Model_70ef981.md "Now that we have set up the view and controller, it’s about time to think about the M
		in MVC.")  
Now that we have set up the view and controller, it’s about time to think about the M in MVC.
8.  [Step 8: Translatable Texts](Step_8_Translatable_Texts_df86bfb.md "In this step we move the texts of our UI to a separate resource file.")  
In this step we move the texts of our UI to a separate resource file.
9.  [Step 9: Component Configuration](Step_9_Component_Configuration_4cfa608.md "After we have introduced all three parts of the Model-View-Controller (MVC) concept,
		we now come to another important structural aspect of OpenUI5. ")  
After we have introduced all three parts of the Model-View-Controller \(MVC\) concept, we now come to another important structural aspect of OpenUI5.
10. [Step 10: Descriptor for Applications](Step_10_Descriptor_for_Applications_8f93bf2.md "All application-specific configuration settings will now further be put in a separate descriptor file called
			manifest.json. This clearly separates the application coding from the configuration settings and makes our app even more
		flexible. For example, all SAP Fiori applications are realized as components and come
		with a descriptor file in order to be hosted in the SAP Fiori launchpad.")  
All application-specific configuration settings will now further be put in a separate descriptor file called `manifest.json`. This clearly separates the application coding from the configuration settings and makes our app even more flexible. For example, all SAP Fiori applications are realized as components and come with a descriptor file in order to be hosted in the SAP Fiori launchpad.
11. [Step 11: Pages and Panels](Step_11_Pages_and_Panels_3b9d9f8.md "After all the work on the app structure it’s time to improve the look of our app. We
		will use two controls from the sap.m library to add a bit more &quot;bling&quot; to
		our UI. You will also learn about control aggregations in this step.")  
After all the work on the app structure it’s time to improve the look of our app. We will use two controls from the `sap.m` library to add a bit more "bling" to our UI. You will also learn about control aggregations in this step.
12. [Step 12: Shell Control as Container](Step_12_Shell_Control_as_Container_4df1d91.md "Now we use a shell control as container for our app and use it as our new root
		element. The shell takes care of visual adaptation of the application to the device’s screen
		size by introducing a so-called letterbox on desktop screens.")  
Now we use a shell control as container for our app and use it as our new root element. The shell takes care of visual adaptation of the application to the device’s screen size by introducing a so-called letterbox on desktop screens.
13. [Step 13: Margins and Paddings](Step_13_Margins_and_Paddings_17b87fb.md "Our app content is still glued to the corners of the letterbox. To fine-tune our layout,
		we can add margins and paddings to the controls that we added in the previous step. ")  
Our app content is still glued to the corners of the letterbox. To fine-tune our layout, we can add margins and paddings to the controls that we added in the previous step.
14. [Step 14: Custom CSS and Theme Colors](Step_14_Custom_CSS_and_Theme_Colors_723f4b2.md "Sometimes we need to define some more fine-granular layouts and this is when we can use
		the flexibility of CSS by adding custom style classes to controls and style them as we like. ")  
Sometimes we need to define some more fine-granular layouts and this is when we can use the flexibility of CSS by adding custom style classes to controls and style them as we like.
15. [Step 15: Nested Views](Step_15_Nested_Views_df8c9c3.md "Our panel content is getting more and more complex and now it is time to move the panel content to a separate view. With that approach,
      the application structure is much easier to understand, and the individual parts of the app can be reused.")  
Our panel content is getting more and more complex and now it is time to move the panel content to a separate view. With that approach, the application structure is much easier to understand, and the individual parts of the app can be reused.
16. [Step 16: Dialogs and Fragments](Step_16_Dialogs_and_Fragments_4da7298.md "In this step, we will take a closer look at another element which can be used to
		assemble views: the fragment. ")  
In this step, we will take a closer look at another element which can be used to assemble views: the fragment.
17. [Step 17: Fragment Callbacks](Step_17_Fragment_Callbacks_354f98e.md "Now that we have integrated the dialog, it's time to add some user interaction. The user
		will definitely want to close the dialog again at some point, so we add a button to close
		the dialog and assign an event handler.")  
Now that we have integrated the dialog, it's time to add some user interaction. The user will definitely want to close the dialog again at some point, so we add a button to close the dialog and assign an event handler.
18. [Step 18: Icons](Step_18_Icons_776f735.md "Our dialog is still pretty much empty. Since OpenUI5 is shipped with a large
		icon font that contains more than 500 icons, we will add an icon to greet our users when the
		dialog is opened.")  
Our dialog is still pretty much empty. Since OpenUI5 is shipped with a large icon font that contains more than 500 icons, we will add an icon to greet our users when the dialog is opened.
19. [Step 19: Aggregation Binding](Step_19_Aggregation_Binding_bf71375.md "Now that we have established a good structure for our app, it's time to add some more
		functionality. We start exploring more features of data binding by adding some invoice data
		in JSON format that we display in a list below the panel.")  
Now that we have established a good structure for our app, it's time to add some more functionality. We start exploring more features of data binding by adding some invoice data in JSON format that we display in a list below the panel.
20. [Step 20: Data Types](Step_20_Data_Types_dfe0465.md "The list of invoices is already looking nice, but what is an invoice without a price
		assigned? Typically prices are stored in a technical format and with a '.'
		delimiter in the data model. For example, our invoice for pineapples has the calculated
		price 87.2 without a currency. We are going to use the OpenUI5 data types to format the
		price properly, with a locale-dependent decimal separator and two digits after the
		separator.")  
The list of invoices is already looking nice, but what is an invoice without a price assigned? Typically prices are stored in a technical format and with a '`.`' delimiter in the data model. For example, our invoice for pineapples has the calculated price `87.2` without a currency. We are going to use the OpenUI5 data types to format the price properly, with a locale-dependent decimal separator and two digits after the separator.
21. [Step 21: Expression Binding](Step_21_Expression_Binding_c98d573.md "Sometimes the predefined types of OpenUI5 are not flexible enough
		and you want to do a simple calculation or formatting in the view - that is where
		expressions are really helpful. We use them to format our price according to the current
		number in the data model.")  
Sometimes the predefined types of OpenUI5 are not flexible enough and you want to do a simple calculation or formatting in the view - that is where expressions are really helpful. We use them to format our price according to the current number in the data model.
22. [Step 22: Custom Formatters](Step_22_Custom_Formatters_0f8626e.md "If we want to do a more complex logic for formatting properties of our data model, we
		can also write a custom formatting function. We will now add a localized status with a
		custom formatter, because the status in our data model is in a rather technical
		format.")  
If we want to do a more complex logic for formatting properties of our data model, we can also write a custom formatting function. We will now add a localized status with a custom formatter, because the status in our data model is in a rather technical format.
23. [Step 23: Filtering](Step_23_Filtering_5295470.md "In this step, we add a search field for our product list and define a filter that
		represents the search term. When searching, the list is automatically updated to show only
		the items that match the search term.")  
In this step, we add a search field for our product list and define a filter that represents the search term. When searching, the list is automatically updated to show only the items that match the search term.
24. [Step 24: Sorting and Grouping](Step_24_Sorting_and_Grouping_c4b2a32.md "To make our list of invoices even more user-friendly, we sort it alphabetically instead
		of just showing the order from the data model. Additionally, we introduce groups and add the
		company that ships the products so that the data is easier to consume.")  
To make our list of invoices even more user-friendly, we sort it alphabetically instead of just showing the order from the data model. Additionally, we introduce groups and add the company that ships the products so that the data is easier to consume.
25. [Step 25: Remote OData Service](Step_25_Remote_OData_Service_4406244.md "So far we have worked with local JSON data, but now we will access a real OData service to visualize remote data.")  
So far we have worked with local JSON data, but now we will access a real OData service to visualize remote data.
26. [Step 26: Mock Server Configuration](Step_26_Mock_Server_Configuration_bae9d90.md "We just ran our app against a real service, but for developing and testing our app we do
		not want to rely on the availability of the “real” service or put additional load on the
		system where the data service is located.")  
We just ran our app against a real service, but for developing and testing our app we do not want to rely on the availability of the “real” service or put additional load on the system where the data service is located.
27. [Step 27: Unit Test with QUnit](Step_27_Unit_Test_with_QUnit_e1ce1de.md "Now that we have a test folder in the app, we can start to increase our test
		coverage. ")  
Now that we have a test folder in the app, we can start to increase our test coverage.
28. [Step 28: Integration Test with OPA](Step_28_Integration_Test_with_OPA_9bf4dce.md "If we want to test interaction patterns or more visual features of our app, we can also
		write an integration test. ")  
If we want to test interaction patterns or more visual features of our app, we can also write an integration test.
29. [Step 29: Debugging Tools](Step_29_Debugging_Tools_1ff250c.md "Even though we have added a basic test coverage in the previous steps, it seems like
		we accidentally broke our app, because it does not display prices to our invoices anymore.
		We need to debug the issue and fix it before someone finds out.")  
Even though we have added a basic test coverage in the previous steps, it seems like we accidentally broke our app, because it does not display prices to our invoices anymore. We need to debug the issue and fix it before someone finds out.
30. [Step 30: Routing and Navigation](Step_30_Routing_and_Navigation_e5200ee.md "So far, we have put all app content on one single page. As we add more and more features, we want to split the content and put it on separate pages.")  
So far, we have put all app content on one single page. As we add more and more features, we want to split the content and put it on separate pages.
31. [Step 31: Routing with Parameters](Step_31_Routing_with_Parameters_2366345.md "We can now navigate between the overview and the detail page, but the actual item that
		we selected in the overview is not displayed on the detail page yet. A typical use case for
		our app is to show additional information for the selected item on the detail page. ")  
We can now navigate between the overview and the detail page, but the actual item that we selected in the overview is not displayed on the detail page yet. A typical use case for our app is to show additional information for the selected item on the detail page.
32. [Step 32: Routing Back and History](Step_32_Routing_Back_and_History_8ef57cf.md "Now we can navigate to our detail page and display an invoice, but we cannot go back to
		the overview page yet. We'll add a back button to the detail page and implement a function
		that shows our overview page again.")  
Now we can navigate to our detail page and display an invoice, but we cannot go back to the overview page yet. We'll add a back button to the detail page and implement a function that shows our overview page again.
33. [Step 33: Custom Controls](Step_33_Custom_Controls_d12d2ee.md "In this step, we are going to extend the functionality of OpenUI5 with a custom control.
		We want to rate the product shown on the detail page, so we create a composition of multiple
		standard controls using the OpenUI5 extension mechanism and add some glue code to make them
		work nicely together. This way, we can reuse the control across the app and keep all related
		functionality in one module.")  
In this step, we are going to extend the functionality of OpenUI5 with a custom control. We want to rate the product shown on the detail page, so we create a composition of multiple standard controls using the OpenUI5 extension mechanism and add some glue code to make them work nicely together. This way, we can reuse the control across the app and keep all related functionality in one module.
34. [Step 34: Responsiveness](Step_34_Responsiveness_a96e18b.md "In this step, we improve the responsiveness of our app. OpenUI5 applications can be run
		on  phone, tablet, and desktop devices and we can configure the application to make best use
		of the screen estate for each scenario. Fortunately, OpenUI5 controls like the
			sap.m.Table already deliver a lot of features that we can
		use.")  
In this step, we improve the responsiveness of our app. OpenUI5 applications can be run on phone, tablet, and desktop devices and we can configure the application to make best use of the screen estate for each scenario. Fortunately, OpenUI5 controls like the `sap.m.Table` already deliver a lot of features that we can use.
35. [Step 35: Device Adaptation](Step_35_Device_Adaptation_d63a15e.md "We now configure the visibility and properties of controls based on the device that we
		run the application on. By making use of the sap.ui.Device API and defining
		a device model we will make the app look great on many devices.")  
We now configure the visibility and properties of controls based on the device that we run the application on. By making use of the `sap.ui.Device` API and defining a device model we will make the app look great on many devices.
36. [Step 36: Content Density](Step_36_Content_Density_d935dbf.md "In this step of our Walkthrough tutorial, we adjust the content density based on the user’s device. OpenUI5 contains different content densities allowing you to display larger
		controls for touch-enabled devices and a smaller, more compact design for devices that are operated by mouse. In our app, we will detect the
		device and adjust the density accordingly.")  
In this step of our Walkthrough tutorial, we adjust the content density based on the user’s device. OpenUI5 contains different content densities allowing you to display larger controls for touch-enabled devices and a smaller, more compact design for devices that are operated by mouse. In our app, we will detect the device and adjust the density accordingly.
37. [Step 37: Accessibility](Step_37_Accessibility_ff7cab1.md "As the last step in this tutorial, we are going to improve the accessibility of our app.")  
As the last step in this tutorial, we are going to improve the accessibility of our app.

