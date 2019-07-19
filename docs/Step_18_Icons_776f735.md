<!-- loio776f7352807e4f82b18176c8fbdc0c56 -->

| loio |
| -----|
| 776f7352807e4f82b18176c8fbdc0c56 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/776f7352807e4f82b18176c8fbdc0c56) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/776f7352807e4f82b18176c8fbdc0c56)</div>

## Step 18: Icons

Our dialog is still pretty much empty. Since OpenUI5 is shipped with a large icon font that contains more than 500 icons, we will add an icon to greet our users when the dialog is opened.

***

### Preview

   
  
An icon is now displayed in the dialog box<a name="loio776f7352807e4f82b18176c8fbdc0c56__fig_r1j_pst_mr"/>

 ![](loiobd572998fe7245b396eab0f17e505079_HiRes.png "An icon is now displayed in the dialog box") 

***

### Coding

You can view and download all files at [Walkthrough - Step 18](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.18/preview).

``` xml
<mvc:View
   controllerName="sap.ui.demo.walkthrough.controller.HelloPanel"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Panel
      headerText="{i18n>helloPanelTitle}"
      class="sapUiResponsiveMargin"
      width="auto" >
      <content>
         <Button
            id="helloDialogButton"
            *HIGHLIGHT START*icon="sap-icon://world"*HIGHLIGHT END*
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

> Note:
> You can look up other icons using the *Icon Explorer* tool in the Demo Kit.
> 
> To call any icon, use its name as listed in the *Icon Explorer* in `sap-icon://*<iconname\>*`.
> 
> 

***

### webapp/view/HelloDialog.fragment.xml

``` xml
<core:FragmentDefinition
   xmlns="sap.m"
   xmlns:core="sap.ui.core" >
   <Dialog
      id="helloDialog"
      title ="Hello {/recipient/name}">
      *HIGHLIGHT START*<content>
         <core:Icon
            src="sap-icon://hello-world"
            size="8rem"
            class="sapUiMediumMargin"/>
      </content>*HIGHLIGHT END*
      <beginButton>
         <Button
            text="{i18n>dialogCloseButtonText}"
            press=".onCloseDialog"/>
      </beginButton>
   </Dialog>
</core:FragmentDefinition>
```

In the dialog fragment, we add an icon control to the content aggregation of the dialog. Luckily, the icon font also comes with a “Hello World” icon that is perfect for us here. We also define the size of the icon and set a medium margin on it.

***

### Conventions

-   Always use icon fonts rather than images wherever possible, as they are scalable without quality loss \(vector graphics\) and do not need to be loaded separately.


**Related information**  


[Icon Explorer](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/iconExplorer/webapp/index.html)

[API Reference: `sap.ui.core.Icon`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.Icon.html)

[Samples: `sap.ui.core.Icon` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.core.Icon/samples)

