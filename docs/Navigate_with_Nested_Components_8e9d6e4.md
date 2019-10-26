<!-- loio8e9d6e4df5464eb5a6e40696c4d2ccd6 -->

| loio |
| -----|
| 8e9d6e4df5464eb5a6e40696c4d2ccd6 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8e9d6e4df5464eb5a6e40696c4d2ccd6) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8e9d6e4df5464eb5a6e40696c4d2ccd6)</div>

## Navigate with Nested Components

Calling sap.ui.core.routing.Router.prototype.navTo function by giving the following parameter:

\* Name of a route

\* Parameters for the route

\* \(optional\) Information for router\\\(s\\\) in nested component\\\(s\\\)

\* \(optional\) Replace the current browser hash or create a new hash entry

triggers the following actions \(in the bullet point order\):

\* Composing of the new hash by replacing the variable placeholders in the route's pattern with the given parameters. When information for the routers in nested components is given, the targets with type \`Component\` will be loaded in order to compose the hash parts of these \`Component\` targets.

\* Set the newly composed hash to the browser.

\* The browser fires a \`hashchange\` event.

\* The router processes the event and propagate the event along the hierarchy which was built up while loading the nested components.

\* Each router checks its own hash part and informs the matched route which in turn displays the targets which are configured to this route.

\* Each targets loads its \`View\` or \`Component\` and add it to the configured aggregation \`controlAggregation\` of the container \`controlId\`.

\* The router fires \`routeMatched\` event and the route fires \`matched\` event to inform the application that the whole process which reacts to the hash change is finished

***

<a name="loio8e9d6e4df5464eb5a6e40696c4d2ccd6__section_jnj_rgx_mjb"/>

### Pass Information to Nested Router\\\(s\\\) with \`navTo\`

Information about route name and parameters for the nested router\\\(s\\\) can be given to the \`navTo\` call via the third parameter \`oComponentTargetInfo\`. This lets the router\\\(s\\\) in nested component\\\(s\\\) show the targets which are configured to one specific route instead of giving the router an empty hash as default. This parameter contains key value pairs in which the key is the name of a \`Component\` target and the value contains at least the route name \`route\` which should be matched within the router of this component and the parameters \`parameters\` for this route. If this route in nested component has again \`Component\` target\\\(s\\\), the property \`componentTargetInfo\` can be used to specify the route information for its \`Component\` target. The value of property \`componentTargetInfo\` shares the same structure as the third parameter \`oComponentTargetInfo\` of the \`navTo\` method.

For example, the top level router has a route "home" which displays two \`Component\` targets:

\* \`Component\` target \`childComp1\` which has two routes defined

\* Route \`list\`: with empty string hash as pattern and shows a list of items

\* Route \`detail\`: shows detail of an item

\* \`Component\` target \`childComp2\` which also has two routes defined

\* Route \`list\`: with empty string hash as pattern and shows a list of items

\* Route \`detail\`: shows detail of an item which displays again a nested \`Component\` target \`grandChildComp1\`

The \`grandChildComp1\` target has two routes defined

\* Route \`list\`: with empty string hash as pattern and shows a list of items

\* Route \`detail\`: shows detail of an item

Once the \`home\` route in the top level router is matched, both of the \`Component\` targets \`childComp1\` and \`childComp2\` are loaded and shown. Each of them receives an empty string hash as default therefore the \`list\` routes of their routers are matched.

!\[navTo Initial State\]\(navTo-initial-state.png\)

By using the \`navTo\` method, specific route information can be given to multiple nested components and their deep nested component\(s\) if they have. For example, the \`detail\` routes in both \`Component\` targets \`childComp1\` and \`childComp2\` need to be matched. Since the \`detail\` route of target \`childComp2\` loads another nested component \`grandChildComp1\`, it's also possible to match the \`detail\` route in the deep nested component \`grandChildComp1\` with the same \`navTo\` call. See the code snippet below.

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

After the \`navTo\` call, the route state of each router looks as below:

!\[After call navTo\]\(after-call-navTo.png\)

***

<a name="loio8e9d6e4df5464eb5a6e40696c4d2ccd6__section_u1j_1hx_mjb"/>

### Navigate Away from A Nested Component

When a new route is matched within a router and there was \`Component\` target displayed within the old route, something needs to be done for this \`Component\` target in order to avoid that it still reacts to unnecessary events such as \`hashChanged\` event. For example, after switching from route \`detail\` to route \`list\` within \`Component\` target \`childComp2\`, the deep nested \`Component\` target \`grandChildComp1\` isn't relevant for the UI anymore \(see the below diagram\).

!\[Stop router after call navTo\]\(stop-after-navTo.png\)

Therefore we do the following to this component:

\* Remove its hash part from the browser hash

\* Stop its router to make it not react to \`hashChanged\` event anymore

