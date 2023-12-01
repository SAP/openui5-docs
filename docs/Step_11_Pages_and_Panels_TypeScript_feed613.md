<!-- loiofeed6135dbcf4ba38bdd5a3c68fbedcc -->

| loio |
| -----|
| feed6135dbcf4ba38bdd5a3c68fbedcc |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/feed6135dbcf4ba38bdd5a3c68fbedcc) | [demo kit latest release](https://sdk.openui5.org/topic/feed6135dbcf4ba38bdd5a3c68fbedcc)</div>

## Step 11: Pages and Panels \(TypeScript\)

After all the work on the app structure it’s time to improve the look of our app. We will use two controls from the `sap.m` library to add a bit more "bling" to our UI. You will also learn about control aggregations in this step.

***

### Preview

  
  
**A panel is now displaying the controls from the previous steps**

![The graphic has an explanatory text.](images/loio97feb5417c89462ead5b4259f3ecfd47_LowRes.png "A panel is now displaying the controls from the previous steps")

***

<a name="loiofeed6135dbcf4ba38bdd5a3c68fbedcc__section_dkx_kp2_syb"/>

### Coding

You can view all files at [OpenUI5 TypeScript Walkthrough - Step 11: Pages and Panels](https://github.com/sap-samples/ui5-typescript-walkthrough/steps/11/README.md).

***

<a name="loiofeed6135dbcf4ba38bdd5a3c68fbedcc__section_x2v_ngt_nzb"/>

### webapp/i18n/i18n.properties

We add new key/value pairs to our text bundle for the start page title and the panel title.

```ini
# App Descriptor
appTitle=Hello World
appDescription=A simple walkthrough app that explains the most important concepts of OpenUI5

# Hello Panel
showHelloButtonText=Say Hello
helloMsg=Hello {0}
homePageTitle=UI5 TypeScript Walkthrough
helloPanelTitle=Hello World
```

***

<a name="loiofeed6135dbcf4ba38bdd5a3c68fbedcc__section_ekx_kp2_syb"/>

### webapp/view/App.view.xml

In our app view, we put both the input field and the button inside a containing control called `sap/m/Page`. The page provides an aggregation to `0..N` other controls called `content`. It also displays the `title` attribute in a header section on top of the content. The page itself is placed into the `pages` aggregation of another control called `sap/m/App` which does the following important things for us:

-   It writes a bunch of properties into the header of the `index.html` that are necessary for proper display on mobile devices.

-   It offers functionality to navigate between pages with animations. We will use this soon.


In order to make the fullscreen height of the view work properly, we add the `displayBlock` attribute with the value `true` to the view. The actual content is wrapped inside a `Panel` control, in order to group related content. It displays the `headerText` attribute in a header section on top of the panel.

```xml
<mvc:View
   controllerName="ui5.walkthrough.controller.App"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc"
  displayBlock="true">
   <App>
      <pages>
         <Page title="{i18n>homePageTitle}">
            <content>
               <Panel
                  headerText="{i18n>helloPanelTitle}">
                  <content>
                     <Button
                        text="{i18n>showHelloButtonText}"
                        press=".onShowHello"/>
                     <Input
                        value="{/recipient/name}"
                        description="Hello {/recipient/name}"
                        valueLiveUpdate="true"
                        width="60%"/>
                  </content>
               </Panel>
            </content>
         </Page>
      </pages>
   </App>
</mvc:View>
```

**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 10: Descriptor for Applications \(TypeScript\)](Step_10_Descriptor_for_Applications_TypeScript_2a46b75.md "All application-specific configuration settings will now further be put in a separate descriptor file called manifest.json. This clearly separates the application coding from the configuration settings and makes our app even more flexible. For example, all SAP Fiori applications are realized as components and come with a descriptor file in order to be hosted in the SAP Fiori launchpad.")

**Previous:**[Step 12: Shell Control as Container \(TypeScript\)](Step_12_Shell_Control_as_Container_TypeScript_4af44cb.md "Now we use a shell control as container for our app and use it as our new root element. The shell takes care of visual adaptation of the application to the device’s screen size by introducing a so-called letterbox on desktop screens.")

**Related Information**  


[API Reference: `sap.m.Page`](https://sdk.openui5.org/api/sap.m.Page)

[Samples: `sap.m.Page` ](https://sdk.openui5.org/entity/sap.m.Page)

[API Reference: `sap.m.Panel`](https://sdk.openui5.org/api/sap.m.Panel)

[Samples: `sap.m.Panel` ](https://sdk.openui5.org/entity/sap.m.Panel)

