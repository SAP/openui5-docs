<!-- loiof5aa4bb75c20445194494b264d3b3cd2 -->

| loio |
| -----|
| f5aa4bb75c20445194494b264d3b3cd2 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f5aa4bb75c20445194494b264d3b3cd2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f5aa4bb75c20445194494b264d3b3cd2)</div>

## Property Metadata Binding

An extended data binding syntax makes it possible to access the metadata for certain properties of an entity in OData services, such as heading, label, and precision.

The extended data binding syntax is only valid for property bindings. The annotations can be addressed either absolute or relative to a data path.

The consumption of label and description within an application is an example for a possible integration. Instead of copying the corresponding label text to a properties file, which in turn will be translated, a developer can bind a label against the label metadata field for the respective input field. This implies that annotations from metadata can also be language-dependent and would have to be translated as well.

Let the following annotation be provided in the service metadata or an additionally loaded metadata file, such as **annotations0.xml** :

``` xml
<Property Name="CompanyName" Type="Edm.String" MaxLength="80" sap:label="Company Name"/>
```

The binding must then know the metadata part of the binding expression. The path to metadata therefore has to start with `/#`.

-   Absolute Binding

    An absolute binding path starts with the EntityType followed by the property name. Annotations can be accessed with `@` + **annotation**, while nodes can be accessed with the node name only.

    For the example given above:

    ``` js
    
    var myLabel = new sap.m.Label({text:"{/#Company/CompanyName/@sap:label}"});
    ```

-   Relative Binding

    A relative binding path can be resolved relative to a data path/context.

    Example:

    ``` js
    
    var myLabel = new sap.m.Label({text:"{/Companies(1)/CompanyCode/#@sap:label}"});
    var myLabel2 = new sap.m.Label({text:"{City/#@sap:label}"});
    myLabel2.bindElement("/Companies(1)");
    ```


