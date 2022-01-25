<!-- loioa4afb138acf64a61a038aa5b91a4f082 -->

| loio |
| -----|
| a4afb138acf64a61a038aa5b91a4f082 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a4afb138acf64a61a038aa5b91a4f082) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a4afb138acf64a61a038aa5b91a4f082)</div>

## App and Nav Container

Apps are often composed of several pages and the user can drill-down to detail pages and go back up again. This is often visualized by horizontal slide animations. OpenUI5 supports this pattern by providing the `sap.m.App` and `sap.m.NavContainer` controls, which handle the navigation between the pages.

`sap.m.App` inherits the navigation capabilities from the `sap.m.NavContainer` control. Thus, both controls are equal with regard to navigation and navigation events. The following sections refer to the `sap.m.NavContainer`, but the same also applies to the `sap.m.App` control.

An app can control the navigation flow centrally and directly trigger the initialization of the pages. To support modularization of the app, however, it may also be beneficial to control the navigation flow non-centrally. In this case, code which constructs a page is also the code that handles, for example, the data load in this page.

To support this, OpenUI5 provides two types of events:

-   Events fired by the App or by the NavContainer whenever it navigates.

-   Events fired **on** the pages when they get shown or hidden by navigation.


-   **[Events Fired Centrally by the App or the NavContainer](Events_Fired_Centrally_by_the_App_or_the_NavContainer_6ec0a7e.md "When NavContainer.to(…) or NavContainer.back(…) are
		called, the NavContainer triggers events and the application can register
		for this events. The navigate event is fired before the transition
		animation starts, and the afterNavigate event is fired when the animation
		has been completed.")**  
When `NavContainer.to(…)` or `NavContainer.back(…)` are called, the `NavContainer` triggers events and the application can register for this events. The `navigate` event is fired before the transition animation starts, and the `afterNavigate` event is fired when the animation has been completed.
-   **[Events Fired on the Pages](Events_Fired_on_the_Pages_b6ab31c.md "Events fired on the pages allow a decentral reaction to navigation.")**  
Events fired on the pages allow a decentral reaction to navigation.
-   **[Passing Data when Navigating](Passing_Data_when_Navigating_cddf7e5.md "When you use the to(…) and back(…) methods of the
			NavContainer to trigger navigation, you can also give an optional
		payload data object. ")**  
When you use the `to(…)` and `back(…)` methods of the `NavContainer` to trigger navigation, you can also give an optional payload data object.

**Related Information**  


[API Reference: `sap.m.App`](https://openui5.hana.ondemand.com/#/api/sap.m.App)

[API Reference: `sap.m.NavContainer`](https://openui5.hana.ondemand.com/#/api/sap.m.NavContainer)

