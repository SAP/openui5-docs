<!-- loiof5aa4bb75c20445194494b264d3b3cd2 -->

| loio |
| -----|
| f5aa4bb75c20445194494b264d3b3cd2 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f5aa4bb75c20445194494b264d3b3cd2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f5aa4bb75c20445194494b264d3b3cd2)</div>

## Property Metadata Binding

The extended syntax makes it possible to access the metadata for certain properties of an entity in OData services, such as heading, label, and precision.

The extended data binding syntax is only valid for `PropertyBindings`. The annotations can be addressed either absolute or relative to a data path.

The consumption of label and description within an application is an example for a possible integration. Instead of copying the corresponding label text to a properties file, which in turn will be translated, a developer can bind a label against the label metadata field for the respective input field.

The binding must know the metadata part of the binding expression. The path to metadata must therefore start with `/#`.

-   Absolute bindings

    An absolute binding path starts with the entity name followed by the property name. Property attributes can be accessed with `@` + `propertyName`, nodes can be accesses with the node name only.

    Example:

    ``` js
    
    var myLabel = new sap.m.Label({text:"{/#Company/CompanyName/@sap:label}"});
    ```

-   Relative bindings

    A relative binding path can be resolved relative to a data path/context.

    Example:

    ``` js
    
    var myLabel = new sap.m.Label({text:"{/Companies(1)/CompanyCode/#@sap:label}"});
    var myLabel2 = new sap.m.Label({text:"{City/#@sap:label}"});
    myLabel2.bindElement("Companies(1)");
    ```


