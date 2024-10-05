<!-- loioae61211b1bb744f7ab42731a37b7738c -->

| loio |
| -----|
| ae61211b1bb744f7ab42731a37b7738c |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/ae61211b1bb744f7ab42731a37b7738c) | [demo kit latest release](https://sdk.openui5.org/topic/ae61211b1bb744f7ab42731a37b7738c)</div>

## Step 32: Routing Back and History \(TypeScript\)

Now we can navigate to our detail page and display an invoice, but we cannot go back to the overview page yet. We'll add a back button to the detail page and implement a function that shows our overview page again.

***

### Preview

  
  
**A back button is now displayed on the detail page**

![The graphic has an explanatory text](images/loio33a8341077bb458685274c64d2317f6b_LowRes.png "A back button is now displayed on the detail page")

***

<a name="loioae61211b1bb744f7ab42731a37b7738c__section_l5n_zvm_tyb"/>

### Coding

You can view all files at [OpenUI5 TypeScript Walkthrough - Step 32: Routing Back and History](https://github.com/sap-samples/ui5-typescript-walkthrough/tree/main/steps/32) and [download the solution as a zip file](https://sap-samples.github.io/ui5-typescript-walkthrough/ui5-typescript-walkthrough-step-32.zip).

***

<a name="loioae61211b1bb744f7ab42731a37b7738c__section_nxm_dqv_4zb"/>

### webapp/controller/Detail.controller.ts

To be able to navigate from the detail view back to the view we came from, we implement a new event handler function in the controller of the detail view.

We load a new class called `History` from the `sap.ui.core.routing` namespace. This class provides methods for navigating through the history of the application.

In the event handler we access the navigation history and try to determine the previous hash. In contrast to the browser history, we will get a valid result only if a navigation step inside our app has already happened. The `History.getInstance()` method returns a singleton instance of the "History" class. Then, we use the `getPreviousHash` method to get the hash of the previous page. If there's a previous page \(i.e., `previousHash` isn't `undefined`\), we will simply use the browser history to go back to the previous page.

If no navigation has happened before, we get a reference to the router and use the `navTo` method to navigate to the "overview" route. As a second parameter we specify an empty array empty array \(`{}`\) as we do not pass any additional parameters to the route. The third parameter is set to `true`. This tells the router to replace the current history state with the new one since we actually do a back navigation by ourselves and don't want to have an entry in the browser history.

```js
import Controller from "sap/ui/core/mvc/Controller";
import UIComponent from "sap/ui/core/ UIComponent";
import { Route$PatternMatchedEvent } from "sap/ui/core/routing/Route";
import History from "sap/ui/core/routing/History";

/**
 * @namespace ui5.walkthrough.controller
 */
export default class Detail extends Controller {

    onInit(): void {
        const router = UIComponent.getRouterFor(this);
        router.getRoute("detail").attachPatternMatched(this.onObjectMatched, this);
    }

    onObjectMatched(event: Route$PatternMatchedEvent): void {
        this.getView().bindElement({
            path: "/" + window.decodeURIComponent( (<any> event.getParameter("arguments")).invoicePath),
            model: "invoice"
        });
    }

    onNavBack(): void {
        const history = History.getInstance();
        const previousHash = history.getPreviousHash();

        if (previousHash !== undefined) {
            window.history.go(-1);
        } else {
            const router = UIComponent.getRouterFor(this);
            router.navTo("overview", {}, true);
        }
    }
};
```

This implementation is a bit better than the browser’s back button for our use case. The browser would simply go back one step in the history even though we were on another page outside of the app. In the app, we always want to go back to the overview page even if we came from another link or opened the detail page directly with a bookmark. You can try it by loading the detail page in a new tab directly and clicking on the back button in the app, it will still go back to the overview page.

***

<a name="loioae61211b1bb744f7ab42731a37b7738c__section_m5n_zvm_tyb"/>

### webapp/view/Detail.view.xml

Now only the back button is missing on the detail page. We do this by telling the page control on the view to display the back button using the control parameter `showNavButton` and register the event handler we defined in its controller to be called when the back button is pressed.

```xml
<mvc:View
	controllerName="ui5.walkthrough.controller.Detail"
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<Page
		title="{i18n>detailPageTitle}"
		showNavButton="true"
		navButtonPress=".onNavBack">
		<ObjectHeader
			intro="{invoice>ShipperName}"
			title="{invoice>ProductName}"/>
	</Page>
</mvc:View>
```

***

### Conventions

-   Add a path to go back to the parent page when the history state is unclear.


**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 31: Routing with Parameters \(TypeScript\)](Step_31_Routing_with_Parameters_TypeScript_afd5eb6.md "We can now navigate between the overview and the detail page, but the actual item that we selected in the overview is not displayed on the detail page yet. A typical use case for our app is to show additional information for the selected item on the detail page.")

**Previous:**[Step 33: Custom Controls \(TypeScript\)](Step_33_Custom_Controls_TypeScript_3cc020e.md "In this step, we are going to extend the functionality of OpenUI5 with a custom control. We want to rate the product shown on the detail page, so we create a composition of multiple standard controls using the OpenUI5 extension mechanism and add some glue code to make them work nicely together. This way, we can reuse the control across the app and keep all related functionality in one module.")

**Related Information**  


[API Reference: `sap.m.routing.Router`](https://sdk.openui5.org/api/sap.m.routing.Router)

[Samples: `sap.m.routing.Router` ](https://sdk.openui5.org/entity/sap.m.routing.Router)

[API Reference: `sap.ui.core.routing.History`](https://sdk.openui5.org/api/sap.ui.core.routing.History)

