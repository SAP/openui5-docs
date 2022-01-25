<!-- loioab267a6b958e46a28f3437154b2a1b2f -->

| loio |
| -----|
| ab267a6b958e46a28f3437154b2a1b2f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ab267a6b958e46a28f3437154b2a1b2f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ab267a6b958e46a28f3437154b2a1b2f)</div>

## Value Lists

The OData V4 model supports the access to value list metadata and data.

Value lists enable you to read the possible values for a given property, such as `Category` in the `Product` entity type. A value list is typically visualized as a dropdown list, or as a value help dialog, that is, a popup with additional features such as filters which help finding the correct value. For performance reasons, you can reduce the service `$metadata` document size by outsourcing value list information to value list services. Consequently, the value list information is accessed in two steps:

1.  Determine the value list type that is available for a given property via `ODataPropertyBinding.requestValueListType` without loading the value list service. This is typically called to determine the visualization of this property.

    The `sap.ui.model.odata.v4.ValueListType`, that the promise delivers, can have the following values:

    -   `None`: No value list exists.

    -   `Fixed`: One enumeration of fixed values exists.

    -   `Standard`: A dynamic value list with multiple queries including selection criteria exists.


2.  Determine the value list detail information on demand via `ODataPropertyBinding.requestValueListInfo` which returns a map of all annotations `com.sap.vocabularies.Common.v1.ValueList` or `com.sap.vocabularies.Common.v1.ValueListMapping` by qualifier. Each mapping has the `ValueListMappingType` type as specified in the OData 4.0 Common Vocabulary, see [OData 4.0 Vocabularies - SAP Common](https://wiki.scn.sap.com/wiki/display/EmTech/OData+4.0+Vocabularies+-+SAP+Common#ValueListMappingType). Each mapping is enriched by a `$model` property of type `sap.ui.model.odata.v4.ODataModel` which can be used to access the value list metadata and retrieve value list data. The annotation `com.sap.vocabularies.Common.v1.ValueListRelevantQualifiers` is automatically taken into account.

    For value lists of type `Fixed`, only one mapping is expected and the qualifier is ignored. The mapping is available with key "".


Additionally, you can use the synchronous method `ODataPropertyBinding.getValueListType` if the metadata for the property is already available. If this is not the case, an exception is thrown. The API is available in `sap.ui.model.odata.v4.ODataMetaModel` analogously for use cases where controls are not yet in place, for example, during XML templating.

**Example: Retrieving the value list type for a property**

```
`#js`   
       onModelContextChange : function (oEvent) {
        var oBinding = this.getBinding("value");
 
        if (oBinding && oBinding.isResolved()) {
            oBinding.requestValueListType().then(function (sValueListType) {
 
 
                // render the control depending on the value list type and attach the below
                // event handler onValueHelp which is invoked when the user requests value help
 
                switch (sValueListType) {
                    case ValueListType.Standard:
                        ...
                        break;
                    case ValueListType.Fixed:
                        ...
                        break;
                    case ValueListType.None:
                        ...
                        break;
                }
                that.setAggregation("field", oField);
            });
        }
    },
...
    onValueHelp : function (oEvent) {
        var oBinding = this.getBinding("value");
 
        oBinding.requestValueListInfo().then(function (mValueListInfo) {
            // this assumes value list type "Fixed"
            var oValueListMapping = mValueListInfo[""],
                oValueListMetaModel = oValueListMapping.$model.getMetaModel();
  
            ...
        ]);
    },
...
```

***

<a name="loioab267a6b958e46a28f3437154b2a1b2f__section_azb_gwg_jfb"/>

### The `ValueList` Annotation

There are two options to place the `ValueList` annotation:

-   In the value list service \(the preferred way\): When adding a value list for a property, the OData service only contains an annotation with the property as target and the term com.sap.vocabularies.Common.v1.ValueListReferences pointing to the metadata of the value list service. The ValueList annotation itself is in the referenced service. It must not have the properties CollectionRoot and SearchSupported.

-   In the OData service itself: In this case, the `ValueList` annotation must have the property `CollectionRoot` pointing to the metadata of the value list service. The annotation `com.sap.vocabularies.Common.v1.ValueListReferences` is not needed.

    The disadvantage of this solution is that the complete value list information for all properties of the service is preloaded when the application is initialized.


**Related Information**  


[Data Reuse](Data_Reuse_648e360.md "")

[OData 4.0 Vocabularies - SAP Common \> ValueListType](https://wiki.scn.sap.com/wiki/display/EmTech/OData+4.0+Vocabularies+-+SAP+Common#ValueListType)

[OData 4.0 Vocabularies - SAP Common \> ValueListMappingType](https://wiki.scn.sap.com/wiki/display/EmTech/OData+4.0+Vocabularies+-+SAP+Common#ValueListMappingType)

[sap.ui.model.odata.v4.ValueListType](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ValueListType.html)

[sap.ui.model.odata.v4.ODataPropertyBinding\#getValueListType](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataPropertyBinding/methods/getValueListType)

[sap.ui.model.odata.v4.ODataPropertyBinding\#requestValueListInfo](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataPropertyBinding/methods/requestValueListInfo)

[sap.ui.model.odata.v4.ODataMetaModel\#getValueListType](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel/methods/getValueListType)

[sap.ui.model.odata.v4.ODataMetaModel\#requestValueListInfo](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel/methods/requestValueListInfo)

