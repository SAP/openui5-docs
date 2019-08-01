<!-- loioc4de2df385174e58a689d9847c7553bd -->

| loio |
| -----|
| c4de2df385174e58a689d9847c7553bd |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c4de2df385174e58a689d9847c7553bd) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c4de2df385174e58a689d9847c7553bd)</div>

## SAP Fiori 2.0 App

In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the latest SAP Fiori design guidelines.

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

   
  
Master-detail-detail pattern with `sap.f.FlexibleColumnLayout`, `sap.f.DynamicPage` and `sap.uxap.ObjectPageLayout`<a name="loioc4de2df385174e58a689d9847c7553bd__fig_r1j_pst_mr"/>

 ![](loiofd98e0d8d9c74cd2a38d9177455bf085_HiRes.gif "Master-detail-detail pattern with
					sap.f.FlexibleColumnLayout, sap.f.DynamicPage
					and sap.uxap.ObjectPageLayout") 

***

<a name="loioc4de2df385174e58a689d9847c7553bd__section_e2n_dmw_mbb"/>

### Choose your development environment

You can do this tutorial either with SAP Web IDE or choose your own development environment:

-   If you use SAP Web IDE, you don't need to set up a development environment, a server and so on. All you need is a browser and an account for the SAP Cloud Platform. If you don't have an account yet, you can easily get a trial account. We recommend to continue with the SAP Web IDE as it has out-of-the-box support for SAPUI5 and because there is no setup overhead at all.

    In this case, you start with the template that is available in SAP Web IDE as described in step 1 of this tutorial.

-   If you want to use your local development environment and deploy to any Web server of your choice, you can download the code for step 1 from the *Samples* in the Demo Kit at [SAP Fiori 2.0 App - Step 1](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.01/preview).


> Note:
> You don't have to do all tutorial steps sequentially, you can also jump directly to any step you want. Just download the code from the previous step, copy it to your workspace and make sure that the app runs by calling the `webapp/index.html` file.
> 
> For more information check the following sections of the tutorials overview page \(see [Get Started: Setup and Tutorials](Get_Started_Setup_and_Tutorials_8b49fc1.md)\):
> 
> -   [Downloading Code for a Tutorial Step](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download)
> 
> -   [Adapting Code to Your Development Environment](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation)
> 
> 
> 

