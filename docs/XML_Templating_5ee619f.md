<!-- loio5ee619fc1370463ea674ee04b65ed83b -->

| loio |
| -----|
| 5ee619fc1370463ea674ee04b65ed83b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5ee619fc1370463ea674ee04b65ed83b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5ee619fc1370463ea674ee04b65ed83b)</div>

## XML Templating

The XML templating concept enables you to use an XML view as a template. This template is transformed by an XML preprocessor on the source level, the XML DOM, at runtime just before an OpenUI5 control tree is created from the XML source.

The label texts and binding paths in the example below come from SAP Annotations for OData Version 2.0 \([http://www.sap.com/Protocols/SAPData](http://www.sap.com/Protocols/SAPData)\) such as `sap:semantics`, and from OData Version 4.0 annotations such as `com.sap.vocabularies.UI.v1.Badge`. Much more complex tasks than shown in this simple example are possible.

> Note:
> HTML templating is no longer supported as of version 1.56.
> 
> 

The transformation happens if a preprocessor for XML is called when the view is created, see lines 4 and 5 in the *Calling the XML Preprocessor* example. This preprocessor can be given one or more models along with a corresponding binding context, see lines 6 and 9; this concept exists for any OpenUI5 control's constructor. Typically, an OData model's meta model is given, along with the meta context corresponding to a data path. XML templating operates on meta data. If the data changes, the XML templating can **not** be executed again. This is due to the processing time. Only the resulting bindings are evaluated again.

If the view is loaded asynchronously, fragments and required modules are loaded asynchronously, too.

> Note:
> XML templating is not directly supported with routing, that is, there is no way to declare that the XML Preprocessor should run on the target view of a route. Instead, you should define a JavaScript view as the route's target and use that view's `createContent` method to create an XML view with templating. In case you need access to models \(which are not yet available in that hook\), you should return some dummy content first \(for instance sap.m.HBox\), register to the view's modelContextChange event and create the inner view in that event's handler, finally adding it to the dummy content.
> 
> JavaScript Target View For Routing
> 
> ```
> sap.ui.jsview("some.package.RouteTargetView", {
>     createContent : function () {
>         return sap.ui.view({
>             async : true,
>             preprocessors : {
>                 xml : {
>                     // ...
>                 }
>             },
>             type : sap.ui.core.mvc.ViewType.XML,
>             viewName : "some.package.TemplateView"
>         });
>     }
> });
> ```
> 
> 

In the example, `sPath = "/ProductSet('HT-1021')/ToSupplier"` and the corresponding meta context point to `"/dataServices/schema/0/entityType/0"` \(the entity type `BusinessPartner`\). The resulting view is bound to the data path within the OData model in order to display the supplier of that product.

***

### Calling the XML Preprocessor

``` js
1   View.create({
2      async : true,
3      models : oModel,
4      preprocessors : {
5         xml : {
6            bindingContexts : {
7               meta : oMetaModel.getMetaContext(sPath)
8            },
9            models : {
10              meta : oMetaModel
11           }
12        }
13     },
14     type : ViewType.XML,
15     viewName : "sap.ui.core.sample.ViewTemplate.tiny.Template"
16  }).then(function (oTemplateView) {
17     oTemplateView.bindElement(sPath);
18     ...
19  }
```

***

The XML preprocessor traverses the view's XML DOM in a depth-first, parent-before-child manner and does the following:

-   All XML attributes which represent an available binding, that is, a binding based only on models available to the preprocessor, are replaced by the result of that binding. Formatters and so on can be used as with any SAPUI5 binding.

-   XML fragments are inlined; that is, the reference is replaced by the fragment's XML DOM and preprocessing takes place on that DOM as well.

-   The preprocessing instructions `<template:with>`, `<template:if>` and `<template:repeat>` are processed.


***

### Component.js

 See sample [sap.ui.core.sample.ViewTemplate.tiny](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.sample.ViewTemplate.tiny/preview). This sample is based on OData Version 4.0 annotations. It consists of the following three pieces:

-   A component controller that creates an OData model \(line 17\), waits for the meta model to be loaded \(line 28\) and then creates a template view \(line 29\) as its content. A preprocessor for XML is requested \(line 31\) and settings are passed to it, namely the meta model and the binding context that identifies the starting point within that model. The resulting view is bound to the actual data \(model and path\).

-   A template view that includes a fragment twice \(line 20 and 25\) to demonstrate how to reuse code.

-   An XML fragment that demonstrates a simple test \(line 10\), using expression binding.


> Note:
> You can find more elaborate XML templating samples here: [XMLView](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.core.mvc.XMLView/samples). 
> 
> Take a look at the demo scenario for a complete overview of all OData v4 notations.
> 
> 

> Note:
> The OData model is based on `GWSAMPLE_BASIC` and will not work unless a suitable proxy for back-end access is used. For simplicity, no mock data is included in this example.
> 
> For more information, see the Help topic, [Sample Service - Basic](http://help.sap.com/saphelp_nw74/helpdata/en/59/283fc4528f486b83b1a58a4f1063c0/frameset.htm).
> 
> 

``` js
1   /*!
2    * ${copyright}
3    */
4
5   /**
6    * @fileOverview Application component to display supplier of "/ProductSet('HT-1021')"
7    *   from GWSAMPLE_BASIC via XML Templating.
8    * @version @version@
9    */
10  sap.ui.define([
11     'sap/m/VBox',
12     'sap/ui/core/UIComponent',
13     'sap/ui/core/mvc/View',
14     'sap/ui/core/mvc/ViewType',
15     'sap/ui/model/odata/v2/ODataModel'
16  ], function (VBox, UIComponent, View, ViewType, ODataModel) {
17     "use strict";
18
19     return UIComponent.extend("sap.ui.core.sample.ViewTemplate.tiny.Component", {
20        metadata : "json",
21
22        createContent : function () {
23           var oModel = new ODataModel(
24              "proxy/sap/opu/odata/IWBEP/GWSAMPLE_BASIC/", {
25                 annotationURI : "proxy/sap/opu/odata/IWFND/CATALOGSERVICE;v=2"
26                 + "/Annotations(TechnicalName='ZANNO4SAMPLE_ANNO_MDL',Version='0001')/$value",
27                 json : true,
28                 loadMetadataAsync : true
29              }),
30              oMetaModel = oModel.getMetaModel(),
31              sPath = "/ProductSet('HT-1021')/ToSupplier",
32              oViewContainer = new VBox();
33
34           oMetaModel.loaded().then(function () {
35              View.create({
36                 async : true,
37                 models : oModel,
38                 preprocessors : {
39                    xml : {
40                       bindingContexts : {
41                          meta : oMetaModel.getMetaContext(sPath)
42                       },
43                       models : {
44                          meta : oMetaModel
45                       }
46                    }
47                 },
48                 type : ViewType.XML,
49                 viewName : "sap.ui.core.sample.ViewTemplate.tiny.Template"
50              }).then(function (oTemplateView) {
51                 oTemplateView.bindElement(sPath);
52                 oViewContainer.addItem(oTemplateView);
53              });
54           });
55 
56           // Note: synchronously return s.th. here and add content to it later on
57           return oViewContainer;
58        }
59     });
60  });
```

``` xml
1   <mvc:View
2       xmlns="sap.m"
3       xmlns:core="sap.ui.core"
4       xmlns:form="sap.ui.layout.form"
5       xmlns:mvc="sap.ui.core.mvc"
6       xmlns:template="http://schemas.sap.com/sapui5/extension/sap.ui.core.template/1">
7    
8       <!-- "meta" model's binding context MUST point to an entity type -->
9       <template:with path="meta>com.sap.vocabularies.UI.v1.Badge" var="badge">
10          <form:SimpleForm>
11              <form:title>
12                  <core:Title text="{path: 'badge>HeadLine', formatter: 'sap.ui.model.odata.AnnotationHelper.format'}"/>
13              </form:title>
14   
15              <Label text="{path: 'badge>Title/Label', formatter: 'sap.ui.model.odata.AnnotationHelper.format'}"/>
16              <Text text="{path: 'badge>Title/Value', formatter: 'sap.ui.model.odata.AnnotationHelper.format'}"/>
17   
18              <Label text="{path: 'badge>MainInfo/Label', formatter: 'sap.ui.model.odata.AnnotationHelper.format'}"/>
19              <template:with path="badge>MainInfo" var="field">
20                  <core:Fragment fragmentName="sap.ui.core.sample.ViewTemplate.tiny.Field" type="XML"/>
21              </template:with>
22   
23              <Label text="{path: 'badge>SecondaryInfo/Label', formatter: 'sap.ui.model.odata.AnnotationHelper.format'}"/>
24              <template:with path="badge>SecondaryInfo" var="field">
25                  <core:Fragment fragmentName="sap.ui.core.sample.ViewTemplate.tiny.Field" type="XML"/>
26              </template:with>
27          </form:SimpleForm>
28      </template:with>
29  </mvc:View>
```

``` xml
1   <core:FragmentDefinition
2       xmlns="sap.m"
3       xmlns:core="sap.ui.core"
4       xmlns:template="http://schemas.sap.com/sapui5/extension/sap.ui.core.template/1">
5    
6       <!-- "field" MUST point to a com.sap.vocabularies.Communication.v1.DataField -->
7       <HBox>
8           <template:with path="field>Value" helper="sap.ui.model.odata.AnnotationHelper.resolvePath" var="target">
9               <!-- go to entity type's property and check SAP Annotations for OData Version 2.0 -->
10              <template:if test="{= ${target>sap:semantics} === 'tel'}" >
11                  <core:Icon src="sap-icon://phone" width="2em"/>
12              </template:if>
13          </template:with>
14          <Text text="{path: 'field>Value', formatter: 'sap.ui.model.odata.AnnotationHelper.format'}"/>
15      </HBox>
16  </core:FragmentDefinition>
```

The result is equivalent to the following handwritten XML view. Any references to the meta model are gone. Type information has been inserted into the bindings and an `"odata.concat"` expression for `badge>MainInfo/Value` has been processed by `sap.ui.model.odata.AnnotationHelper.format`, concatenating the company name and legal form.

``` xml
<mvc:View xmlns="sap.m" xmlns:core="sap.ui.core" xmlns:form="sap.ui.layout.form" xmlns:mvc="sap.ui.core.mvc">
  <form:SimpleForm>
    <form:title>
      <core:Title text="{path : 'BusinessPartnerID', type : 'sap.ui.model.odata.type.String', constraints : {'maxLength':'10','nullable':'false'}}"/>
    </form:title>
    <Label text="Name"/>
    <Text text="{path : 'CompanyName', type : 'sap.ui.model.odata.type.String', constraints : {'maxLength':'80'}} {path : 'LegalForm', type : 'sap.ui.model.odata.type.String', constraints : {'maxLength':'10'}}"/>
    <Label text="Phone"/>
    <HBox>
      <core:Icon src="sap-icon://phone" width="2em"/>
      <Text text="{path : 'PhoneNumber', type : 'sap.ui.model.odata.type.String', constraints : {'maxLength':'30'}}"/>
    </HBox>
    <Label text="Web"/>
    <HBox>
      <Text text="{path : 'WebAddress', type : 'sap.ui.model.odata.type.String', constraints : {}}"/>
    </HBox>
  </form:SimpleForm>
</mvc:View>
```

***

### Summary

Overall, XML templating is based on:

-   Preprocessing instructions such as `<template:if>`, which can be used inside XML views

-   An OData meta model which offers a unified access to both, OData V2 metadata and OData V4 annotations

-   A set of OData type implementations which add knowledge of OData types to OpenUI5

-   Expression binding which facilitates the use of expressions instead of custom formatter functions

-   The helper class `sap.ui.model.odata.AnnotationHelper` that offers formatter and helper functions to be used inside XML template views. It knows about the OData meta model and helps with standard tasks like accessing a label or providing a runtime binding path. It brings in the OData types, along with their facets. Its output uses expression binding, if needed.


> Note:
> XML Templating works almost the same for OData V4 as for OData V2; for the differences see the *Annotations* section in [Meta Model for OData V4](Meta_Model_for_OData_V4_7f29fb3.md).
> 
> 

**Related information**  


[Meta Model for OData V2](OData_V2_Model_.md#loio341823349ed04df1813197f2a0d71db2)

[Expression Binding](Expression_Binding_daf6852.md)

[SAP Annotations for OData Version 2.0](http://www.sap.com/Protocols/SAPData)

[`sap.ui.model.odata.AnnotationHelper`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.AnnotationHelper.html)

