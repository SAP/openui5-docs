<!-- loio19eabf5b13214f27b929b9473df3195b -->

| loio |
| -----|
| 19eabf5b13214f27b929b9473df3195b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/19eabf5b13214f27b929b9473df3195b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/19eabf5b13214f27b929b9473df3195b)</div>

## Aggregation Handling in XML Views

In XML views, aggregated child controls can be added as child tags.

***

<a name="loio19eabf5b13214f27b929b9473df3195b__section_ly2_t1s_xz"/>

### Aggregations of XML Views

On root level, you can only define content for the default aggregation, e.g. without adding the `content` tag. If you want to specify content for another aggregation of a view like `dependents`, place it in a child control´s `dependents` aggregation or add it by using the `addDependent` method.

***

<a name="loio19eabf5b13214f27b929b9473df3195b__section_fhf_r1s_xz"/>

### Aggregations of Controls Inside the View

Some controls have more than one content area, for example the shell control that has the main content area, a menu bar, a `headerItems` aggregation, a `worksetItems` aggregation, and so on. An aggregation tag usually serves as a direct child of a container and contains children. You can only add children directly if the container control has marked one of the child aggregations as default.

> Note:
> Some containers may not have default content, for example, the splitter container has two equally important content areas.
> 
> The framework supports you by issuing error message in case of errors in the aggregation handling in XML views.
> 
> 

You fill aggregations as shown in the following example. The namespace of the parent control tag and the aggregation tag must be the same.

``` xml

<mvc:View controllerName="sap.hcm.Address" xmlns="sap.m" xmlns:mvc="sap.ui.core.mvc">
   <Panel>
      <content>  <!-- this is the general way of adding children: use the aggregation name -->
         <Image src="http://www.sap.com/global/ui/images/global/sap-logo.png"/>
         <Button text="Press Me"/>
      </content>
   </Panel>
</mvc:View>
```

If an aggregation of **cardinality `0..1`** has an alternative type and if you want to specify a value of that alternative type, you have to do this as an attributes, not as a nested element.

> Note:
> For the `noData` aggregation of the `sap.ui.comp.smarttable.SmartTable` control, you can either define a string or a nested text control.
> 
> |String|Nested text control|
> |------|-------------------|
> | ```
> <SmartTable noData="No data available">
> 	...
> </SmartTable>
> 
> ```
> 
>  | ```
> <SmartTable ....>
> 	<noData>
> 		<Text text="No data available" icon="sap-icon://..." />
> 	</noData>
> 	...
> </SmartTable>
> 
> ```
> 
>  |
> 
> 

You can also use attributes to define binding information for aggregations with cardinality `0..n`. For more information, see *Declarative List Binding in XML Views* under [List Binding \(Aggregation Binding\)](List_Binding_(Aggregation_Binding)_91f0577.md).

