<!-- loiod23e2cf618a44382a203691e8a0baef4 -->

| loio |
| -----|
| d23e2cf618a44382a203691e8a0baef4 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d23e2cf618a44382a203691e8a0baef4) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d23e2cf618a44382a203691e8a0baef4)</div>

## Fast Navigation

Adjacent controls within the tab chain can be grouped. Within such a group, *F6* skips all controls of the group and moves the focus to the first control in the tab chain of the next group. * Shift F6 * moves the focus to the first control of the previous group. Adjacent tab chain elements between groups are automatically handled as one group. For nested groups, the most concrete group is used.

The following image describes this behavior. Groups are highlighted in blue, elements in the tab-chain are grey.

 ![](loioe5e01dd8d1594e608e697a2e30ac3bc6_LowRes.png) 

The *F6* navigation cycles. This means if the focus is within the last group in the group chain, the focus moves to the first control in the first group. This leads to an additional *F6* chain, which allows fast navigation through applications. Larger controls like the `Table`, `Panel`, and `Form` provide their own groups by default. The application developer defines further groups.

As described, some larger controls or containers already define `F6` groups. If a group is defined on root level of a control or element, the group can be removed by using the `CustomData` mechanism.

Coding Example:

``` js
oControl.data("sap-ui-fastnavgroup", "false", true/*Write into DOM*/);
```

XML View Example:

``` xml
<mvc:View
  xmlns:core="sap.ui.core"
  xmlns:mvc="sap.ui.core.mvc"
  xmlns="sap.m">
  <Panel>
    <headerToolbar>
      <Toolbar>
        <Button icon="sap-icon://settings" />
      </Toolbar>
    </headerToolbar>
    <content>
      <Text text="Lorem ipsum dolor st amet..." />
    </content>
    <customData>
      <core:CustomData key="sap-ui-fastnavgroup" value="false" writeToDom="true" />
    </customData>
  </Panel>
</mvc:View>

```

The same way it is possible to make a control or element to be an `F6` group. However, keep in mind that not all elements are represented in the DOM.

Coding Example:

``` js
oControl.data("sap-ui-fastnavgroup", "true", true/*Write into DOM*/);
```

XML View Example:

``` xml
<mvc:View
  xmlns:core="sap.ui.core"
  xmlns:mvc="sap.ui.core.mvc"
  xmlns="sap.m">
  <Panel>
    <headerToolbar>
      <Toolbar>
        <Button icon="sap-icon://settings" />
      </Toolbar>
    </headerToolbar>
    <content>
      <Text text="Lorem ipsum dolor st amet..." />
    </content>
    <customData>
      <core:CustomData key="sap-ui-fastnavgroup" value="true" writeToDom="true" />
    </customData>
  </Panel>
</mvc:View>

```

Also, DOM elements that are not controlled by OpenUI5 controls can be grouped by setting `data-sap-ui-fastnavgroup="true"`.

