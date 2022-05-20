<!-- loio3d18f20bd2294228acb6910d8e8a5fb5 -->

| loio |
| -----|
| 3d18f20bd2294228acb6910d8e8a5fb5 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/3d18f20bd2294228acb6910d8e8a5fb5) | [demo kit latest release](https://sdk.openui5.org/topic/3d18f20bd2294228acb6910d8e8a5fb5)</div>

## Routing and Navigation

OpenUI5 offers hash-based navigation, which allows you to build single-page apps where the navigation is done by changing the hash. In this way the browser does not have to reload the page; instead there is a callback to which the app and especially the affected view can react. A hash string is parsed and matched against patterns which will then inform the handlers.

You use routing in the following cases:

-   Enable users to navigate back using the browser history, for example, the *Back* button of the browser or a physical back button on mobile devices.

-   Enable bookmarks and deep links to pages inside an app; this means that you can start the app and resume the bookmarked state.

-   Pass on data via the hash to application logic.


   
  
<a name="loio3d18f20bd2294228acb6910d8e8a5fb5__fig_uph_4ky_zv"/>Routing overview

 ![](images/loio3b3a63b7581c4d36b9657f07d678f176_LowRes.png "Routing overview") 

In OpenUI5, navigation and routing is implemented using a “router” to forward the hash change and the data in the hash to one or more views of the app.

You use **routes** to notify your application that the hash has changed to a certain value. For each route, you define the pattern that can be used in the app implementation.

With **targets**, you define where a view or a component is loaded and where the view or component is shown on the UI. By referring to one or multiple targets in a route's definition, you can load and show the views or components once the route's pattern matches the current hash.

You configure routing in OpenUI5 in the descriptor file \(`manifest.json`\) \(see [Descriptor for Applications, Components, and Libraries \(manifest.json\)](Descriptor_for_Applications_Components_and_Libraries_manifest_json_be0cf40.md)\) or in the `Component.js` file \(see [Components](Components_958ead5.md) \) to have it available globally throughout your app, but you can also define routes and targets locally by calling the constructors of the classes, for example under the `sap.ui.core.routing` and `sap.m.routing` namespaces.

> ### Note:  
> You can also define only routes or only targets, but then just have to make sure that you implement the counterpart elsewhere.

***

### Routing Patterns

Whenever a hash is added to a URL, the router checks whether there is a route with a matching pattern. The first matching route is taken and the corresponding target view is called. The data provided with the hash are passed on to the target.

You can use the following kinds of patterns:

-   **Hard-coded pattern**:

    The pattern matches the hash exactly. For example, when a pattern is defined as `product/settings`, this pattern matches only if the hash is ***product/settings*** and no data is passed on to the events of the route.

    For more information, see the tutorial [Step 6: Navigate to Routes with Hard-Coded Patterns](Step_6_Navigate_to_Routes_with_Hard_Coded_Patterns_782aac0.md).

-   **Route with mandatory parameter**:

    You can define mandatory parameters for the pattern by placing the parameter in curly brackets \(<code>{<i>parameter ID</i>}</code>\).

    For example, if you define the pattern `product/{id}`, the hashes ***product/5*** and ***product/3*** \(where 3 and 5 are product IDs\) match the pattern. The matched event handler gets `5` or `3` passed on with the key `id` in its arguments. But hash ***product/*** does not match the pattern because the mandatory parameter is missing.

    For more information, see the tutorial [Step 7: Navigate to Routes with Mandatory Parameters](Step_7_Navigate_to_Routes_with_Mandatory_Parameters_f96d252.md).

-   **Route with optional parameter**:

    You can define optional parameters for the pattern by placing the parameter between colons \(<code>:<i>parameter ID</i>:</code>\).

    For example, if you define a pattern `product/{id}/detail/:detailId:`, the `detailId` parameter is optional, whereas `id` is mandatory. Both hashes `product/5/detail` and `product/3/detail/2` match the pattern.

-   **Route with query parameter**:

    The query parameter allows you to pass on queries with any parameter. A query parameter starts with `?`, and you can either define it as mandatory \(`product/{?query}`\) or optional \(`product/:?query:`\).

    The matched value will be converted into an object saved with the parameter name as the key when passed to the event handler.

    For more information, see the tutorial [Step 9: Allow Bookmarkable Tabs with Optional Query Parameters](Step_9_Allow_Bookmarkable_Tabs_with_Optional_Query_Parameters_b8561ff.md).

-   **"rest as string" parameter**:

    A parameter that ends with an asterisk \(`*`\) is called a "rest as string" parameter. Such a parameter matches as much as possible. It can be combined with the syntax of mandatory or optional parameters.

    For example, a pattern `product/{id}/:detail*:` defines a mandatory parameter with the name `id` and an optional "rest as string" parameter with the name `detail`. It matches `product/5/3` and `product/5/detail/3/foo`. The event handler gets `3` or `detail/3/foo` passed on with the key `detail` in its arguments.


> ### Tip:  
> For a better understanding about how patterns work and what matched parameters look like, see the following page in the *Samples* in the Demo Kit: [sap.ui.core.sample.PatternMatching/preview](https://sdk.openui5.org/entity/sap.ui.core.routing.Route/sample/sap.ui.core.sample.PatternMatching).

***

> ### Note:  
> OpenUI5 uses Crossroads.js for parsing the hash and the Hasher framework for manipulating the hash.

-   **[Routing Configuration](Routing_Configuration_9023130.md "Routing configuration consists of routes, targets,
			config, and owner.")**  
Routing configuration consists of `routes`, `targets`, `config`, and `owner`.
-   **[Methods and Events for Navigation](Methods_and_Events_for_Navigation_516e477.md "OpenUI5 provides a method
		and events for navigation.")**  
OpenUI5 provides a method and events for navigation.
-   **[Initializing and Accessing a Routing Instance](Initializing_and_Accessing_a_Routing_Instance_acdb6cd.md "This topic describes how to initialize routing in a component and access the routing functions.")**  
This topic describes how to initialize routing in a component and access the routing functions.
-   **[Working with Multiple Targets](Working_with_Multiple_Targets_2c5c84d.md "If you want to navigate to multiple targets with the same hash, you can either assign
		multiple targets to a route, or define a parent for the target.")**  
If you want to navigate to multiple targets with the same hash, you can either assign multiple targets to a route, or define a parent for the target.
-   **[Using the title Property in Targets](Using_the_title_Property_in_Targets_1238d70.md "Routing in OpenUI5 allows
        you to define titles declaratively in the configuration. The title can be set with valid
        binding syntax which is then resolved under the scope of the target to which it belongs.
        This means that the title can be translated when it’s bound to the i18n model or resolved
        dynamically under the current binding context.")**  
Routing in OpenUI5 allows you to define titles declaratively in the configuration. The title can be set with valid binding syntax which is then resolved under the scope of the target to which it belongs. This means that the title can be translated when it’s bound to the i18n model or resolved dynamically under the current binding context.
-   **[Enabling Routing in Nested Components](Enabling_Routing_in_Nested_Components_fb19f50.md "Every OpenUI5 component
        can define routing configuration in its manifest and a UI5 router instance will be created
        automatically after the component is instantiated.")**  
Every OpenUI5 component can define routing configuration in its manifest and a UI5 router instance will be created automatically after the component is instantiated.
-   **[Navigate with Nested Components](Navigate_with_Nested_Components_8e9d6e4.md "The navTo method in the sap.ui.core.routing.Router
		class enables you to define a set of parameters to navigate to a specific route.")**  
The `navTo` method in the `sap.ui.core.routing.Router` class enables you to define a set of parameters to navigate to a specific route.
-   **[Navigate with Dynamic Targets](Navigate_with_Dynamic_Targets_856d6c6.md "The addTarget method in the sap.ui.core.routing.Targets class enables you to add targets to the router
		dynamically at runtime. Components or views can serve as dynamic targets.")**  
The `addTarget` method in the `sap.ui.core.routing.Targets` class enables you to add targets to the router dynamically at runtime. Components or views can serve as dynamic targets.

**Related Information**  


[Tutorial: Navigation and Routing](Navigation_and_Routing_1b6dcd3.md "OpenUI5 comes with a powerful routing API that helps you control the state of your application efficiently. This tutorial will illustrate all major features and APIs related to navigation and routing in OpenUI5 apps by creating a simple and easy to understand mobile app. It represents a set of best practices for applying the navigation and routing features of OpenUI5 to your applications.")

[API Reference: `sap.ui.core.routing`](https://sdk.openui5.org/api/sap.ui.core.routing)

[API Reference: `sap.m.routing.Router`](https://sdk.openui5.org/api/sap.m.routing.Router)

[API Reference: `sap.ui.core.routing.Route`: Constructor Detail](https://sdk.openui5.org/api/sap.ui.core.routing.Route/constructor)

[Crossroads.js](https://millermedeiros.github.io/crossroads.js/)

[Hasher framework on GitHub](https://github.com/millermedeiros/hasher/)

