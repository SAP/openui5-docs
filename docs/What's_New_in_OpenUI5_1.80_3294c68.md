<!-- loio3294c688331c4e918a22dc0bb0892ff8 -->

| loio |
| -----|
| 3294c688331c4e918a22dc0bb0892ff8 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3294c688331c4e918a22dc0bb0892ff8) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3294c688331c4e918a22dc0bb0892ff8)</div>

## What's New in OpenUI5 1.80

With this release OpenUI5 is upgraded from version 1.79 to 1.80.

***

<a name="loio3294c688331c4e918a22dc0bb0892ff8__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td>

**`sap.m.BadgeCustomData`, `sap.m.IBadgeEnabler`**

To facilitate control developers working on implementations of badges, we created a new `sap.m.BadgeCustomData` type to handle the badge data. Control developers can now use the new `sap.m.IBadgeEnabler` utility that helps working with badge data.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.IBadgeEnabler).



</td>
</tr>
</table>

***

<a name="loio3294c688331c4e918a22dc0bb0892ff8__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   When using `groupLevels` with the `$$aggregation` binding parameter, we now support paging and expanding of several levels.
-   The new `$$sharedRequest` parameter is available for OData list bindings. This parameter leads to the reuse of data requested previously for the same resource path with identical parameters in bindings where `$$sharedRequest` is set. Note that a binding becomes read-only by using this parameter.

    For a comprehensive description of the restrictions, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel%23methods/bindList).

    Note also that `$$sharedRequest` is automatically set for list bindings of value list models returned by `sap.ui.model.odata.v4.ODataPropertyBinding#requestValueListInfo` and `sap.ui.model.odata.v4.ODataMetaModel#requestValueListInfo`.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
</table>

***

<a name="loio3294c688331c4e918a22dc0bb0892ff8__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.f.GridContainer`**

-   We have enhanced drag and drop between two containers. When you drag one element over another container, the element in the original position is not visible, but keeps its place so that you can return the element back to its original place if you need to.
-   We have improved focus visualization and handling. You can now easily move the focus through the items in the container using the [Arrow Keys\]. For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer).



</td>
</tr>
<tr>
<td>

**`sap.m.IconTabBar`**

When you drag one tab over a tab with nested tabs, only one drop zone is available, but the list of nested tabs expands and you can drop the tab where it is needed. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarDragDrop).



</td>
</tr>
<tr>
<td>

**`sap.m.TablePersoDialog`**

The look and feel of the control has been improved based on the latest design guidelines and the SAP Fiori 3 user experience. For example, the *Move column up/down* buttons are now right next to the search field using different icons; the *Reset* button is no longer an icon button and has been moved up to the header section; `sap.m.Table` is now used for the columns instead of `sap.m.List`, including multiple selection and the *Select All* checkbox. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TablePersoDialog) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table/sample/sap.m.sample.TablePerso).



</td>
</tr>
<tr>
<td>

**`sap.tnt.NavigationListItem`**

We have added `href` and `target` properties to improve the SEO capabilities of the control. Now developers can use these new properties in the navigation within the application, so that search engines can discover and index the application pages. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.tnt.NavigationListItem).



</td>
</tr>
<tr>
<td>

**`sap.ui.integration.widgets.Card`**

-   We have added support \(experimental\) for microcharts in the List card. To allow a chart for every item in the list, we have introduced the `chart` property in the descriptor for `sap.ui.integration.widgets.Card` of type List. Supported chart types are `StackedBar` and `Bullet`. For details about their properties, see the [Card Microcharts](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/microcharts) section in the Card Explorer.
-   We have redefined the dynamic filtering feature \(experimental\), which allows developers to create custom filters in the manifest of the card. We have introduced a dedicated `filters` section for user-friendly visualization when working with design-time configuration tools. For more information, see the [Filters](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/filters) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/filters) in the Card Explorer.



</td>
</tr>
</table>

***

<a name="loio3294c688331c4e918a22dc0bb0892ff8__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td>

**Demo Kit Language**

You can now change the language of the Demo Kit app from the *More information* menu at the top of the app header. By default, the app opens in English. If you want your browser to remember the chosen language setting, make sure to accept our cookies policy.

> ### Note:  
> Keep in mind that the selected language applies only to the Demo Kit application user interface. The content provided in the application in the different sections, such as *Documentation*, *API Reference*, and *Samples* is available only in English.

![](loioeb91a45367664216ac5b9a8aa05a38db_HiRes.gif)



</td>
</tr>
<tr>
<td>

**Samples**

You can now view the sample description and any additional details directly from the sample window by choosing *Sample information* at the top of the sample window.

![](loioc2dca89c7a1740ffbec6bebb687178b5_HiRes.gif)



</td>
</tr>
</table>

