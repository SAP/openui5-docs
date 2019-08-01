<!-- loiofb19f501b16e4e4991eb6a017770945b -->

| loio |
| -----|
| fb19f501b16e4e4991eb6a017770945b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/fb19f501b16e4e4991eb6a017770945b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/fb19f501b16e4e4991eb6a017770945b)</div>

## Enabling Routing in Nested Components

Every OpenUI5 component can define routing configuration in its manifest and a UI5 router instance will be created automatically after the component is instantiated.

Using components as targets in routing presents another challenge: When multiple components with their own routing configuration are used in an application, their router instances listen to the browser's `hashChange` event simultaneously and may do concurrent changes to the hash. This can lead to conflicts, hence, the hash access has to be coordinated. Therefore, some additional configuration has to be made for these nested components to ensure everything is running stable.

***

<a name="loiofb19f501b16e4e4991eb6a017770945b__section_ovn_4cl_ngb"/>

### Configure a Component as Routing Target

To build a hierarchy among the routers from multiple components, the child components must be loaded from the router in the top level component.

A target in OpenUI5 routing can load either a view or a component. To load a component, you need to define the component in the `componentUsages` section of the owner component's `manifest.json`, see [Using and Nesting Components](Using_and_Nesting_Components_346599f.md):

``` json
{
    "sap.ui5": {
        "componentUsages": {
            "myreuse": {
                "name": "reuse.component",
                "settings": {},
                "componentData": {},
                "lazy": false
            }
        }
    }
}
```

Use the following configuration to load the component from the target:

-   `type`: Set the `type` to "Component"; this loads and instantiates the `Component.js` that is available under `componentUsages`.

-   `usage`: Use the key of the component usage as used in the the `componentUsages` section of the parent component's `manifest.json`.

-   `options` \(optional\): Add additional options that are merged with the options defined in the `componentUsage` section, see [sap.ui.core.UIComponent](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.UIComponent.html).

-   `containerOptions` \(optional\): Add additional options that are passed to the constructor of the component container where the component is rendered, see [sap.ui.core.ComponentContainer](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.ComponentContainer.html).


``` js
{
    "sap.ui5": {
        "componentUsages": {
*HIGHLIGHT START*            "myreuse": {
                "name": "reuse.component",
                "settings": {},
                "componentData": {},
                "lazy": false
            }
*HIGHLIGHT END*
        },
        "routing": {
            "config": {
                ...
            },
            "routes": [
                ...
            ],
            "targets": {
                "attachment": {
                    "type": "Component",
*HIGHLIGHT START*                    "usage": "myresue",
*HIGHLIGHT END*
                    "options": {
                        // optional
                        // define the additional parameter for
                        // instatiating the component instance
                    },
                    "containerOptions": {
                        // optional
                        // define the additional parameter for
                        // instantiating the component container
                        // which enables the component to be rendered
                        // in the parent control
                    },
                    "controlId": "page",
                    "controlAggregation": "content"
                }
            }
        }
    }
}
```

***

<a name="loiofb19f501b16e4e4991eb6a017770945b__section_htm_scl_ngb"/>

### Configure Hash Prefix for the Nested Component

The hash from every router needs to be persisted in the browser hash. To identify the ownership of the hash segments from the browser hash, a prefix needs to be assigned to the component which is loaded by a `Target`. The prefix can be defined in the `Route` where the `Target` is used.

Instead of assigning the "target" option in a route with the name of a target which is going to be displayed once the route's pattern is matched, an object is assigned which also contains the prefix of the hash for this component besides the name of the target. The loaded component from the target has its own hash segment which begins with the given prefix and can change the hash by using method `navTo` on `Router` in the same way as it is done in the top level component.

``` json
{
    "sap.ui5": {
        "componentUsages": {
            "myreuse": {
                "name": "reuse.component",
                "settings": {},
                "componentData": {},
                "lazy": false
            }
        },
        "routing": {
            "config": {
                ...
            },
            "routes": [{
                "name": "home",
                "pattern": "",
                "target": {
                    "name": "attachment",
*HIGHLIGHT START*                    "prefix": "atch"
*HIGHLIGHT END*
                }
            }],
            "targets": {
                "attachment": {
                    "type": "Component",
                    "usage": "myreuse",
                    "options": {
                        // optional
                        // define the additional parameter for
                        // instatiating the component instance
                    },
                    "containerOptions": {
                        // optional
                        // define the additional parameter for
                        // instantiating the component container
                        // which enables the component to be rendered
                        // in the parent control
                    },
                    "controlId": "page",
                    "controlAggregation": "content"
                }
        }
    }
}
```

***

<a name="loiofb19f501b16e4e4991eb6a017770945b__section_cxd_wcl_ngb"/>

### Navigate with Nested Component

You can call method `navTo` on `Router` to change the browser hash which in turn makes another route to match and the target\(s\) of that route is loaded, instantiated and placed into the configured container. When the component where the browser hash change is triggered has child component\(s\) loaded from its router, the new navigation resets the hash segments that belong to its child component\(s\). Even when it navigates to the same route with different data, the hash segments of its child component\(s\) are reset because these hash segments are connected to the previous state of the route which needs to be reset once the state is changed.

