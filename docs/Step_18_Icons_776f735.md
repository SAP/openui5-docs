<!-- loio776f7352807e4f82b18176c8fbdc0c56 -->

| loio |
| -----|
| 776f7352807e4f82b18176c8fbdc0c56 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/776f7352807e4f82b18176c8fbdc0c56) | [demo kit latest release](https://sdk.openui5.org/topic/776f7352807e4f82b18176c8fbdc0c56)</div>

## Step 18: Icons

Our dialog is still pretty much empty. Since OpenUI5 is shipped with a large icon font that contains more than 500 icons, we will add an icon to greet our users when the dialog is opened.

***

### Preview

  
  
**An icon is now displayed in the dialog box**

![The graphic has an explanatory text.](images/loiofbc48e23cc7d45e393cc95bbbfc6e0a3_LowRes.png "An icon is now displayed in the dialog box")

***

<a name="loio776f7352807e4f82b18176c8fbdc0c56__section_pg2_zgk_syb"/>

### Coding

You can view and download all files at [Walkthrough - Step 18](https://sdk.openui5.org/entity/sap.m.tutorial.walkthrough/sample/sap.m.tutorial.walkthrough.18).

***

<a name="loio776f7352807e4f82b18176c8fbdc0c56__section_qg2_zgk_syb"/>

### webapp/view/HelloPanel.view.xml

```xml
<mvc:View
   controllerName="ui5.walkthrough.controller.HelloPanel"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Panel
      headerText="{i18n>helloPanelTitle}"
      class="sapUiResponsiveMargin"
      width="auto" >
      <content>
         <Button
            id="helloDialogButton"
            icon="sap-icon://world"
            text="{i18n>openDialogButtonText}"
            press=".onOpenDialog"
            class="sapUiSmallMarginEnd"/>
         <Button
            text="{i18n>showHelloButtonText}"
            press=".onShowHello"
            class="myCustomButton"/>
         <Input
            value="{/recipient/name}"
            valueLiveUpdate="true"
            width="60%"/>
         <FormattedText
            htmlText="Hello {/recipient/name}"
            class="sapUiSmallMargin sapThemeHighlight-asColor myCustomText"/>
      </content>
   </Panel>
</mvc:View>
```

We add an icon to the button that opens the dialog. The `sap-icon://` protocol is indicating that an icon from the icon font should be loaded. The identifier `world` is the readable name of the icon in the icon font.

> ### Tip:  
> You can look up other icons using the [Icon Explorer tool](https://sdk.openui5.org/test-resources/sap/m/demokit/iconExplorer/webapp/index.html).
> 
> To call any icon, use its name as listed in the *Icon Explorer* in <code>sap-icon://<i>&lt;iconname&gt;</i></code>.

***

### webapp/view/HelloDialog.fragment.xml

```xml
<core:FragmentDefinition
   xmlns="sap.m"
   xmlns:core="sap.ui.core" >
   <Dialog
      id="helloDialog"
      title ="Hello {/recipient/name}">
      <content>
         <core:Icon
            src="sap-icon://hello-world"
            size="8rem"
            class="sapUiMediumMargin"/>
      </content>
      <beginButton>
         <Button
            text="{i18n>dialogCloseButtonText}"
            press=".onCloseDialog"/>
      </beginButton>
   </Dialog>
</core:FragmentDefinition>
```

In the dialog fragment, we add an icon control to the content aggregation of the dialog. Luckily, the icon font also comes with a "Hello World" icon that is perfect for us here. We also define the size of the icon and set a medium margin on it.

***

### Conventions

-   Always use icon fonts rather than images wherever possible, as they are scalable without quality loss \(vector graphics\) and do not need to be loaded separately.


**Parent topic:**[Walkthrough Tutorial \(JavaScript\)](Walkthrough_Tutorial_JavaScript_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:**[Step 17: Fragment Callbacks](Step_17_Fragment_Callbacks_354f98e.md "Now that we have integrated the dialog, it's time to add some user interaction. The user will definitely want to close the dialog again at some point, so we add a button to close the dialog and assign an event handler.")

**Previous:**[Step 19: Aggregation Binding](Step_19_Aggregation_Binding_bf71375.md "Now that we have established a good structure for our app, it's time to add some more functionality. We start exploring more features of data binding by adding some invoice data in JSON format that we display in a list below the panel.")

**Related Information**  


[Icon Explorer](https://sdk.openui5.org/test-resources/sap/m/demokit/iconExplorer/webapp/index.html)

[API Reference: `sap.ui.core.Icon`](https://sdk.openui5.org/api/sap.ui.core.Icon)

[Samples: `sap.ui.core.Icon` ](https://sdk.openui5.org/entity/sap.ui.core.Icon)

