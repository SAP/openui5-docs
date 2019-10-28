<!-- loio8e9d6e4df5464eb5a6e40696c4d2ccd6 -->

| loio |
| -----|
| 8e9d6e4df5464eb5a6e40696c4d2ccd6 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8e9d6e4df5464eb5a6e40696c4d2ccd6) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8e9d6e4df5464eb5a6e40696c4d2ccd6)</div>

## Navigate with Nested Components

To navigate with nested components, call `sap.ui.core.routing.Router.prototype.navTo` with the following parameters:

-   Name of the route

-   Parameters for the route

-   Information for router\(s\) in nested component\(s\) \(optional\)

-   Replace the current browser hash or create a new hash entry \(optional\)


The call triggers the following actions in the given order:

1.  The new hash is composed by replacing the variable placeholders in the route's pattern with the given parameters. When you give information for a router in nested components in the call, the targets with type `Component` are loaded to compose the hash parts of these `Component` targets.

2.  The hash is set to the browser.

3.  The browser fires a `hashchange` event.

4.  The router processes the event and propagates the event along the hierarchy which was built while loading the nested components.

5.  Each router checks its own hash part and informs the matched route. The matched route displays the targets which are configured to this route.

6.  Each targets loads its `View` or `Component` and adds it to the configured `controlAggregation` of the `controlId` container.

7.  The router fires a `routeMatched` event and the route fires a `matched` event to inform the application that the hash change is completed.


***

<a name="loio8e9d6e4df5464eb5a6e40696c4d2ccd6__section_jnj_rgx_mjb"/>

### Passing Information to Nested Router\(s\) With `navTo`

You can pass information to the `navTo` call about the route name and route parameters for the nested router\(s\) via the `oComponentTargetInfo` parameter. By this, the router\(s\) in nested component\(s\) can show the targets which are configured to one specific route instead of giving the router an empty hash as default. This parameter contains key value pairs in which the key is the name of a `Component` target and the value contains at least the route name `route` which should be matched within the router of this component and the parameters `parameters` for this route. If this route in nested component has again `Component` target\(s\), the property `componentTargetInfo` can be used to specify the route information for its `Component` target. The value of the `componentTargetInfo` property shares the same structure as the third parameter `oComponentTargetInfo` of the `navTo` method.

For example, the top level router has a "home" route which displays two `Component` targets:

-   `Component` target `childComp1` with the following two defined routes:

    -   Route `list`: Has an empty string hash as pattern and shows a list of items

    -   Route `detail`: Shows the details for an item

-   `Component` target `childComp2` with the following two defined routes:

    -   Route `list`: Has an empty string hash as pattern and shows a list of items

    -   Route `detail`: Shows the details for an item which displays again a nested `Component` target `grandChildComp1`


The `grandChildComp1` target has the following two routes defined:

-   Route `list`: Has an empty string hash as pattern and shows a list of items

-   Route `detail`: Shows the details for an item


When the `home` route in the top level router is matched, the `Component` targets `childComp1` and `childComp2` are loaded and shown. Each of them receives an empty string hash as default, and so the `list` routes of their routers are matched.

Abb \[navTo Initial State\]

By using the `navTo` method, specific route information can be given to multiple nested components and, if available, their deep nested components. For example, the `detail` routes in both `Component` targets `childComp1` and `childComp2` need to be matched. Since the `detail` route of target `childComp2` loads another nested component \(`grandChildComp1`\), it is also possible to match the `detail` route in the deep nested component `grandChildComp1` with the same `navTo` call, see the following code snippet.

``` js
oRouter.navTo("home", {
    // this route doesn't need any parameter
}, {
    childComp1: {
        route: "detail",
        parameters: {
            ...
        }
    },
    childComp2: {
        route: "detail",
        parameters: {
            ...
        },
        componentTargetInfo: {
            grandChildComp1: {
                route: "detail",
                parameters: {
                    ...
                }
            }
        }
    }
});
```

After the `navTo` call, the route state of each router looks as depicted in the following figure:

Abb: \[After call navTo\]

***

<a name="loio8e9d6e4df5464eb5a6e40696c4d2ccd6__section_u1j_1hx_mjb"/>

### Navigating Away From a Nested Component

When a new route is matched within a router and a `Component` target was displayed within the old route, it is necessary to avoid that this `Component` target still reacts to unnecessary events such as `hashChanged`. For example, after switching from the `detail` route to the `list` route within the `Component` target `childComp2`, the deep nested `Component` target `grandChildComp1` is no longer relevant for the UI. This is shown in the following figure:

Ab: \[Stop router after call navTo\]

To avoid this, proceed as follows:

-   Remove the hash part from the browser hash.

-   Stop the router, so that it no longer reacts to the `hashChanged` event.


