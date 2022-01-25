<!-- loio7f29fb3ce5964d8090038a9d3cdf5060 -->

| loio |
| -----|
| 7f29fb3ce5964d8090038a9d3cdf5060 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7f29fb3ce5964d8090038a9d3cdf5060) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7f29fb3ce5964d8090038a9d3cdf5060)</div>

## Meta Model for OData V4

Each OData V4 model offers access via `getMetaModel` to a corresponding metadata model `sap.ui.model.odata.v4.ODataMetaModel`, which is read-only and offers access to OData V4 metadata in a streamlined JSON format \(see links under Related Information for more details\). Only one-time bindings are supported by this model because the metadata is immutable.

***

### Synchronous vs. Asynchronous Access

Access to metadata is basically asynchronous \(e.g. `requestObject`\) to allow for dynamic loading of metadata. There is also a corresponding method for synchronous access \(e.g. `getObject`\) which returns `undefined` if metadata is not yet available. It should only be used in situations where metadata has already been loaded asynchronously before. Loading happens individually for each document, i.e. each $metadata document is loaded and processed as a whole and is available thereafter. Includes and references to other $metadata documents are not supported, only the service root's initial $metadata document can be used.

***

### Path Syntax

The `requestObject` API documentation in the Demo Kit explains how metadata is accessed and the supported path syntax in great detail. The basic idea is that every path described in the specification [OData Version 4.0 Part 3: Common Schema Definition Language, 14.2.1 Attribute Target](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part3-csdl.html) is a valid absolute path within the metadata model if a leading slash is added; for example `"/"` + `"MySchema.MyEntityContainer/MyEntitySet/MyComplexProperty/MyNavigationProperty"`. For more information, see the [requestObject](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel/methods/requestObject) API documentation in the Demo Kit.

***

### Annotations

The main API for both programmatic access from JavaScript and declarative access from XML templating is `sap.ui.model.odata.v4.ODataMetaModel#getObject`. It works together with `sap.ui.model.odata.v4.ODataMetaModel#resolve` \(for `<template:with>`\) and `sap.ui.model.odata.v4.ODataMetaModel#bindList` \(for `<template:repeat>`\) in order to provide convenient access to annotations, inline as well as external targeting.

The OData meta model knows how to follow "14.2.1 Attribute Target" described in specification "[OData Version 4.0 Part 3: Common Schema Definition Language](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part3-csdl.html)" as well as "14.5.2 Expression edm:AnnotationPath", "14.5.11 Expression edm:NavigationPropertyPath", "14.5.12 Expression edm:Path", and "14.5.13 Expression edm:PropertyPath".

[XML Templating](XML_Templating_5ee619f.md) still works the same as for V2, with some slight changes as outlined below:

-   Metadata paths need to refer to the V4 metadata JSON structure.

-   Note the difference between `"/TEAMS@Org.OData.Capabilities.V1.TopSupported"` and `"/TEAMS/@com.sap.vocabularies.Common.v1.Deletable"` \(look closely at the slash!\), see [ODataMetaModel.requestObject](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel%23requestObject).

-   Use [`sap.ui.model.odata.v4.AnnotationHelper`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper) instead of `sap.ui.model.odata.AnnotationHelper`. The ability to follow a path has been built into the V4 OData meta model itself. See `field>Value/$Path@com.sap.vocabularies.Common.v1.Label` in the code example below. Instead of `sap.ui.model.odata.AnnotationHelper.format`, you can use `sap.ui.model.odata.v4.AnnotationHelper.value` or `sap.ui.model.odata.v4.AnnotationHelper.format`. You can use both as a computed annotation.

-   Computed annotations start with "@@", for example `<Text text="{meta>Value/@@sap.ui.model.odata.v4.AnnotationHelper.value}" />`. Their name without the "@@" prefix refers to a function in the global namespace which computes an annotation value from the metadata addressed by the preceding path. For more information, see [ODataMetaModel.requestObject](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel/methods/requestObject) .

-   Ensure that the view is loaded asynchronously. In this case, there is no longer a need to preload metadata, because the template processor waits for every binding to be resolved before proceeding.

-   Use a double hash \('\#\#'\) or single hash \('\#'\) separator to branch from the OData V4 model into metadata, see [createBindingContext](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/createBindingContext) .

    > ### Note:  
    > The single hash separator is deprecated since 1.52

    > ### Remember:  
    > An appropriate URI encoding is necessary for the data path \(before the separator\), but neither for the separator itself nor for the metadata path that follows it.

    Example: `<template:with path="/Products('A%2FB%26C')/Name#@com.sap.vocabularies.Common.v1.Label" var="label"> or <template:with path="data>/Products#/" var="productEntityType">`, etc.


**Example of an OData V4 XML template:**

``` xml
<mvc:View
        template:require="{AnnotationHelper : 'sap/ui/model/odata/v4/AnnotationHelper'}"
        xmlns="sap.m"
        xmlns:template="http://schemas.sap.com/sapui5/extension/sap.ui.core.template/1">
    <template:alias name="format" value="AnnotationHelper.format">
    <template:alias name="value" value="AnnotationHelper.value">
        <template:with path="meta>/BusinessPartnerList/" var="entityType">
          <template:with path="entityType>@com.sap.vocabularies.UI.v1.LineItem" var="lineItem">
            <Table headerText="Business Partners"
              items="{path : '/BusinessPartnerList', length : 5}">
              <columns>
                <template:repeat list="{lineItem>}" var="field">
                  <Column>
                    <template:if test="{field>Label}">
                      <template:then>
                        <Label design="{:= ${field>@com.sap.vocabularies.UI.v1.Importance/$EnumMember}
                          === 'com.sap.vocabularies.UI.v1.ImportanceType/High' ? 'Bold' : 'Standard'}"
                          text="{field>Label}"/>
                      </template:then>
                      <template:else>
                        <Text text="{field>Value/$Path@com.sap.vocabularies.Common.v1.Label}"/>
                      </template:else>
                    </template:if>
                  </Column>
                </template:repeat>
              </columns>
              <items>
                <ColumnListItem>
                  <cells>
                    <template:repeat list="{lineItem>}" var="field">
                      <template:with path="field>Value/$Path" var="target">
                        <template:if test="{= ${target>@@AnnotationHelper.getValueListType} === 'Standard' }">
                            <template:then>
                                <Input value="{path : 'field>Value/@@value'}" showValueHelp="true", valueHelpRequest=".onValueHelp"}" />
                            </template:then>
                            <template:elseif test="{= ${target>@@AnnotationHelper.getValueListType} === 'Fixed' }">
                                <ComboBox value="{path : 'field>Value/@@value'}" loadItems=".onLoadItems" showValueHelp="true" />
                            </template:elseif>
                            <template:elseif test="{target>@com.sap.vocabularies.Common.v1.Text}">
                                <!-- Note: TextFirst, TextLast, TextSeparate, TextOnly -->
                                <template:if test="{= ${target>@com.sap.vocabularies.Common.v1.Text@com.sap.vocabularies.UI.v1.TextArrangement/$EnumMember}
                                    === 'com.sap.vocabularies.UI.v1.TextArrangementType/TextLast' }">
                                    <!-- Text: "A descriptive text for values of the annotated property.
                                        Value MUST be a dynamic expression when used as metadata annotation." -->
                                    <Text text="{field>Value/@@value} {target>@com.sap.vocabularies.Common.v1.Text/@@value}" />
                                </template:if>
                            </template:elseif>
                            <template:else>
                                <Text text="{field>Value/@@format}" />
                            </template:else>
                        </template:if>
                      </template:with>
                    </template:repeat>
                  </cells>
                </ColumnListItem>
              </items>
            </Table>
          </template:with>
        </template:with>
    </template:alias>
    </template:alias>
</mvc:View>
```

***

<a name="loio7f29fb3ce5964d8090038a9d3cdf5060__section_ixq_yzv_tz"/>

### AnnotationHelper

The module `sap/ui/model/odata/v4/AnnotationHelper` delivers the following computed annotations; require it as shown in the example above:

-   [`value`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper/methods/sap.ui.model.odata.v4.AnnotationHelper.value) helps to convert annotations into corresponding expression bindings or similar. The resulting binding does **not** contain type and constraint information; both are detected automatically. For examples, see [sap.ui.model.odata.v4.AnnotationHelper.value](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper/methods/sap.ui.model.odata.v4.AnnotationHelper.value).

-   [`format`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper/methods/sap.ui.model.odata.v4.AnnotationHelper.format) helps to convert annotations into corresponding expression bindings, or similar. Compared to `value`, `format` adds type and constraints information to the resulting binding. This is useful, for example, if the XML of the view is cached.

    If you use `format` with a path containing a single "$AnnotationPath" or "$Path" segment, the value corresponding to that segment is considered as a data binding path prefix whenever a dynamic "14.5.12 Expression edm:Path" or "14.5.13 Expression edm:PropertyPath" is turned into a data binding.

    For examples, see [`format`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper/methods/sap.ui.model.odata.v4.AnnotationHelper.format).

    If `format` finds a `Org.OData.Measures.V1.ISOCurrency` or a `Org.OData.Measures.V1.Unit` annotation at a property, a composite binding with a `sap.ui.model.odata.type.Currency` or a `sap.ui.model.odata.type.Unit` type is generated. For more information, see [Currency and Unit Customizing in OData V4](Currency_and_Unit_Customizing_in_OData_V4_4d1b9d4.md).

-   [`label`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper/methods/sap.ui.model.odata.v4.AnnotationHelper.label) - Returns the value for the label of a `com.sap.vocabularies.UI.v1.DataFieldAbstract` from the meta model.

-   [`getValueListType`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper/methods/sap.ui.model.odata.v4.AnnotationHelper.getValueListType) - Determines which type of value list exists for the property. The function returns a value from the enumeration [`sap.ui.model.odata.v4.ValueListType`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ValueListType.html). It can be called directly on a property:

    ``` xml
    
    <template:with path="/BusinessPartnerList/Role" var="property">
        <template:if test="{= ${property>@@AnnotationHelper.getValueListType} === 'Fixed'}">
            ...
        </template:if>
    </template:with>
    ```


Alternatively it can be called on an annotation holding an `[edm:Path](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part3-csdl/odata-v4.0-errata03-os-part3-csdl-complete.html#_Toc453752658)` to a property when it is called in the context of an entity type. This is typically the case when iterating over a `com.sap.vocabularies.UI.v1.LineItem` annotation of an entity type and asking for value help on the data fields. See the example regarding `LineItem` of `BusinessPartnerList` \(the relevant parts are repeated here\):

``` xml

<template:with path="meta>/BusinessPartnerList/" var="entityType">
  <template:with path="entityType>@com.sap.vocabularies.UI.v1.LineItem" var="lineItem">
...    
            <template:repeat list="{lineItem>}" var="field">
              <template:with path="field>Value/$Path" var="target">
                <template:if test="{= ${target>@@AnnotationHelper.getValueListType} === 'Standard' }">
...
```

The first `<template:with>` defines `entityType` to be the type of the set `BusinessPartnerList`. The `<template:repeat>` iterates over its annotation`com.sap.vocabularies.UI.v1.LineItem` \(a collection of records with type `com.sap.vocabularies.UI.v1.DataField`\). The record's property `Value` is assumed to be an `edm:Path` pointing to a property of the entity type. For this path the value list type is determined.

-   **[OData V4 Metadata JSON Format](OData_V4_Metadata_JSON_Format_87aac89.md "The OData V4 model provides access to metadata in a streamlined JSON format which is
		described in the section below.")**  
The OData V4 model provides access to metadata in a streamlined JSON format which is described in the section below.
-   **[Additional Annotation Files](Additional_Annotation_Files_fd715d9.md "The OData V4 model supports loading of additional annotation files.")**  
The OData V4 model supports loading of additional annotation files.

**Related Information**  


[OData V4 Metadata JSON Format](OData_V4_Metadata_JSON_Format_87aac89.md "The OData V4 model provides access to metadata in a streamlined JSON format which is described in the section below.")

[getMetaModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/sap.ui.model.odata.v4.ODataModel.getMetadata)

[sap.ui.model.odata.v4.ODataMetaModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataMetaModel.html)

[requestObject](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel/methods/requestObject)

[sap.ui.model.odata.v4.ODataMetaModel\#getObject](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel/methods/getObject)

[sap.ui.model.odata.v4.ODataMetaModel\#bindList](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataMetaModel/methods/bindList)

[sap.ui.model.odata.ODataMetaModel\#loaded](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.ODataMetadata/methods/loaded)

