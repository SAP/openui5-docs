<!-- loioa575619e25c2487f904bae71764e2350 -->

| loio |
| -----|
| a575619e25c2487f904bae71764e2350 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a575619e25c2487f904bae71764e2350) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a575619e25c2487f904bae71764e2350)</div>

## View Cloning

For normal controls, view cloning bases on control settings that are described by OpenUI5 metadata, such as properties, aggregations, associations, and event handlers. The clone operation collects these settings and creates a new instance.

Another important aspect of OpenUI5 views is their cloning behavior. As you might know, OpenUI5 aggregation bindings can use template control to create a series of similar controls based on a collection of data, for example, items in a `RowRepeater` for each entry in a model array. The data binding uses a `ManagedObject.clone` operation to create multiple controls out of a single template.

For views there is a conflict between this basic, generic approach and the way how views usually define their content: via hooks \(JSView\) or via persisted XML or JSON files. Furthermore, it is allowed and documented best practice to modify the view in the onInit hook of its controller. To avoid conflicts between the generic cloning and the MVC concepts, views implement a slightly modified clone operation: only a subset of the view settings are cloned, the remainder is re-created by calling the hook \(JSView\) or applying the external view description \(XML or JSON file\), depending on the view type.

Cloned in a generic way are the following settings:

-   any models that have been set \(`setModel()`\)
-   registered control event listeners \(`attachSomeEvent`\)
-   registered browser event listeners \(`attachBrowserEvent`\)
-   bindings \(`bindProperty`, `bindAggregation`\)

Not cloned, but recreated are all aggregations, namely the content.

In scenarios where the above clone approach still leads to undesirable behavior, factory functions can be used for the aggregation binding instead.

**Related information**  


[List Binding \(Aggregation Binding\)](List_Binding_(Aggregation_Binding)_91f0577.md)

