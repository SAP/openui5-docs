<!-- loioc4de2df385174e58a689d9847c7553bd -->

| loio |
| -----|
| c4de2df385174e58a689d9847c7553bd |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/c4de2df385174e58a689d9847c7553bd) | [demo kit latest release](https://sdk.openui5.org/topic/c4de2df385174e58a689d9847c7553bd)</div>

## Flexible Column Layout App

In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the SAP Fiori design guidelines.

The app provides the following features:

-   An up-to-three-column layout based on the `sap.f.FlexibleColumnLayout` control. This layout has predefined layout types and defined routing between them that enables smooth navigation between the master-detail and master-detail-detail patterns of the app.

-   A master page based on the `sap.f.DynamicPage` control that lists the available products and has filtering and sorting options.

-   A detail page based on the `sap.uxap.ObjectPageLayout` control containing detailed information about the selected object from the master page:

    -   It implements the dynamic header of the `ObjectPageLayout` control.

    -   The `sap.f.Avatar` control is used in the title area to display an image of the selected product.

    -   The header title area can be collapsed \(snapped to the title\) by scrolling down the content of the page or by clicking/tapping the title area. The header area can also be pinned so that it remains visible when the user scrolls down the content of the page.

    -   The title area has a set of actions on the right. The title area can display specific content when the header is snapped.

    -   The floating footer is positioned at the bottom of the page, on top of the page content. It holds finalizing actions on the right.


-   A detail-detail page based on `sap.f.DynamicPage` to display further details of the selected object from the detail page.

-   A simple about page based on `sap.f.DynamicPage` to display further details of the selected object from the detail-detail page.


***

<a name="loioc4de2df385174e58a689d9847c7553bd__section_d2n_dmw_mbb"/>

### Preview

   
  
<a name="loioc4de2df385174e58a689d9847c7553bd__fig_r1j_pst_mr"/>Master-detail-detail pattern with `sap.f.FlexibleColumnLayout`, `sap.f.DynamicPage` and `sap.uxap.ObjectPageLayout`

 ![](images/loiofd98e0d8d9c74cd2a38d9177455bf085_HiRes.gif "Master-detail-detail pattern with
					sap.f.FlexibleColumnLayout, sap.f.DynamicPage
					and sap.uxap.ObjectPageLayout") 

***

> ### Tip:  
> You don't have to do all tutorial steps sequentially, you can also jump directly to any step you want. Just download the code from the previous step, and start there.
> 
> You can view and download the files for all steps in the Demo Kit at [Flexible Column Layout App](https://sdk.openui5.org/entity/sap.f.tutorial.fiori2). Copy the code to your workspace and make sure that the application runs by calling the `webapp/index.html` file. Depending on your development environment you might have to adjust resource paths and configuration entries.
> 
> For more information check the following sections of the tutorials overview page \(see [Get Started: Setup, Tutorials, and Demo Apps](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md)\):
> 
> -   [Downloading Code for a Tutorial Step](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download)
> 
> -   [Adapting Code to Your Development Environment](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation)

1.  [Step 1: Setting Up the Initial App](Step_1_Setting_Up_the_Initial_App_59b772b.md "We start by setting up a basic OpenUI5 app for this
		tutorial.")  
We start by setting up a basic OpenUI5 app for this tutorial.
2.  [Step 2: Creating an Empty Flexible Column Layout](Step_2_Creating_an_Empty_Flexible_Column_Layout_bf38e4d.md "In this step, we add an instance of the sap.f.FlexibleColumnLayout
		control in the main view of the app.")  
In this step, we add an instance of the `sap.f.FlexibleColumnLayout` control in the main view of the app.
3.  [Step 3: Using Dynamic Page for the Master View](Step_3_Using_Dynamic_Page_for_the_Master_View_0830bce.md "In this step, we create the master view of the app using
			sap.f.DynamicPage control.")  
In this step, we create the master view of the app using `sap.f.DynamicPage` control.
4.  [Step 4: Adding a Detail Page](Step_4_Adding_a_Detail_Page_4e4315c.md "In this step, we add an empty detail page.")  
In this step, we add an empty detail page.
5.  [Step 5: Using Object Page Layout as a Detail Page](Step_5_Using_Object_Page_Layout_as_a_Detail_Page_d1ffe61.md "In this step, we add sap.uxap.ObjectPageLayout to the detail page to
		display more information about each product.")  
In this step, we add `sap.uxap.ObjectPageLayout` to the detail page to display more information about each product.
6.  [Step 6: Adding a Floating Footer](Step_6_Adding_a_Floating_Footer_555ed73.md "In this step, we add a floating footer to the detail page.")  
In this step, we add a floating footer to the detail page.
7.  [Step 7: Routing](Step_7_Routing_7f65131.md "In this step, we utilize the sap.f.routing.Router.")  
In this step, we utilize the `sap.f.routing.Router`.
8.  [Step 8: Enhancing the Detail Page](Step_8_Enhancing_the_Detail_Page_e5ee491.md "With routing implemented, the model of the detail page is updated for each product.
		In this step, we enhance the detail page to show information specific for the selected
		product.")  
With routing implemented, the model of the detail page is updated for each product. In this step, we enhance the detail page to show information specific for the selected product.
9.  [Step 9: Adding a Detail-Detail Page](Step_9_Adding_a_Detail_Detail_Page_e4d21fd.md "In this step, we create a detail-detail page using
		sap.f.DynamicPage, which is opened by choosing a supplier from the detail
		page.")  
In this step, we create a detail-detail page using `sap.f.DynamicPage`, which is opened by choosing a supplier from the detail page.
10. [Step 10: Adding More Pages](Step_10_Adding_More_Pages_a59b3de.md "In this step, we create an additional page that is displayed in a separate fullscreen
		column.")  
In this step, we create an additional page that is displayed in a separate fullscreen column.
11. [Step 11: Using the Flexible Column Layout Semantic Helper](Step_11_Using_the_Flexible_Column_Layout_Semantic_Helper_276f001.md "In this step, we use the sap.f.FlexibleColumnLayoutSemanticHelper
		class to implement the recommended UX patterns for layout changes in the app.")  
In this step, we use the `sap.f.FlexibleColumnLayoutSemanticHelper` class to implement the recommended UX patterns for layout changes in the app.
12. [Step 12: Starting with Two Columns](Step_12_Starting_with_Two_Columns_a96fbe4.md "In this step, we set up the app to start with an initial layout of two
		columns.")  
In this step, we set up the app to start with an initial layout of two columns.
13. [Step 13: Setting the Master-Detail Pattern](Step_13_Setting_the_Master_Detail_Pattern_cb38637.md "In this step, we set up the app to follow the master-detail pattern.")  
In this step, we set up the app to follow the master-detail pattern.

