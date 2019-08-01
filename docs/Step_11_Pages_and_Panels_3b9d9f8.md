<!-- loio3b9d9f84930d43df90ad0789d99bd4a3 -->

| loio |
| -----|
| 3b9d9f84930d43df90ad0789d99bd4a3 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3b9d9f84930d43df90ad0789d99bd4a3) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3b9d9f84930d43df90ad0789d99bd4a3)</div>

## Step 11: Pages and Panels

After all the work on the app structure it’s time to improve the look of our app. We will use two controls from the `sap.m` library to add a bit more "bling" to our UI. You will also learn about control aggregations in this step.

***

### Preview

   
  
A panel is now displaying the controls from the previous steps<a name="loio3b9d9f84930d43df90ad0789d99bd4a3__fig_r1j_pst_mr"/>

 ![](loio959dd4b5957c4c799efc110338c9819d_HiRes.png "A panel is now displaying the controls from the previous steps") 

***

### Coding

You can view and download all files at [Walkthrough - Step 11](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.11/preview).

``` xml
<mvc:View
   controllerName="sap.ui.demo.walkthrough.controller.App"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc"
  *HIGHLIGHT START*displayBlock="true">
   <App>
      <pages>
         <Page title="{i18n>homePageTitle}">
            <content>
               <Panel
                  headerText="{i18n>helloPanelTitle}">
                  <content>*HIGHLIGHT END*

                     <Button
                        text="{i18n>showHelloButtonText}"
                        press=".onShowHello"/>
                     <Input
                        value="{/recipient/name}"
                        description="Hello {/recipient/name}"
                        valueLiveUpdate="true"
                        width="60%"/>
                 *HIGHLIGHT START* </content>
               </Panel>
            </content>
         </Page>
      </pages>
   </App>*HIGHLIGHT END*
</mvc:View>

```

We put both the input field and the button inside a containing control called `sap.m.Page`. The page provides an aggregation to `0..N` other controls called `content`. It also displays the title attribute in a header section on top of the content. The page itself is placed into the `pages` aggregation of another control called `sap.m.App` which does the following important things for us:

-   It writes a bunch of properties into the header of the `index.html` that are necessary for proper display on mobile devices.

-   It offers functionality to navigate between pages with animations. We will use this soon.


In order to make the fullscreen height of the view work properly, we add the `displayBlock` attribute with the value `true` to the view. The actual content is wrapped inside a `Panel` control, in order to group related content.

***

### webapp/i18n/i18n.properties

``` prefs
# App Descriptor
appTitle=Hello World
appDescription=A simple walkthrough app that explains the most important concepts of OpenUI5

# Hello Panel
showHelloButtonText=Say Hello
helloMsg=Hello {0}
*HIGHLIGHT START*homePageTitle=Walkthrough
helloPanelTitle=Hello World*HIGHLIGHT END*
```

We add new key/value pairs to our text bundle for the start page title and the panel title.

***

### Conventions

-   Do not make implicit use of default aggregations but always declare the aggregation names explicitly in the view. In the example above, the `content` aggregation could also be omitted as the `Panel` control declares it as a default, but it makes the view harder to read.

**Related information**  


[API Reference: `sap.m.NavContainer`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.NavContainer.html)

[Samples: `sap.m.NavContainer` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.NavContainer/samples)

[API Reference: `sap.m.Page`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.Page.html)

[Samples: `sap.m.Page` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.Page/samples)

