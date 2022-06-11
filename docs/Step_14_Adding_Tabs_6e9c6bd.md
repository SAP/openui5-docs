<!-- loio6e9c6bd2054c4425b7f15cac31aa675c -->

| loio |
| -----|
| 6e9c6bd2054c4425b7f15cac31aa675c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/6e9c6bd2054c4425b7f15cac31aa675c) | [demo kit latest release](https://sdk.openui5.org/topic/6e9c6bd2054c4425b7f15cac31aa675c)</div>

## Step 14: Adding Tabs

We want to display statistics for posts, for example, how many times it was viewed. To achieve this, we implement an icon tab bar with an *Info* tab and a *Statistics* tab. The existing content should be placed on the *Info* tab and the view count on the *Statistics* tab.

***

### Preview

   
  
<a name="loio6e9c6bd2054c4425b7f15cac31aa675c__fig_r1j_pst_mr"/>An icon tab bar with statistics

 ![](images/loio1d8248aaaac34e1185b36090859cf47c_LowRes.png "An icon tab bar with statistics") 

***

### Coding

You can view and download all files in the *Samples* in the Demo Kit at [Testing - Step 14](https://sdk.openui5.org/entity/sap.m.tutorial.testing/sample/sap.m.tutorial.testing.14).

***

### view/Post.view.xml

```xml
<mvc:View
      controllerName="sap.ui.demo.bulletinboard.controller.Post"
      xmlns="sap.m"
      xmlns:form="sap.ui.layout.form"
      xmlns:mvc="sap.ui.core.mvc"
      xmlns:semantic="sap.m.semantic">
   <semantic:FullscreenPage
         id="page"
         busy="{postView>/busy}"
         busyIndicatorDelay="0"
         navButtonPress=".onNavBack"
         showNavButton="true"
         title="{i18n>objectTitle}">
      <semantic:content>
         <ObjectHeader
               id="objectHeader"
               title="{Title}"
               number="{
                  path: 'Price',
                  formatter: '.formatter.numberUnit'
               }"
               numberUnit="{Currency}"
               backgroundDesign="Translucent">
         </ObjectHeader>
         <IconTabBar id="iconTabBar"
                  expanded="{device>/isNoPhone}"
                  class="sapUiNoContentPadding">
            <items>
               <IconTabFilter icon="sap-icon://hint" key="info" >
                  <form:SimpleForm>
                     <form:content>
                        <Label text="{i18n>postDateLabel}"/>
                        <Text text="{Timestamp}"/>
                        <Label text="{i18n>postDescriptionLabel}"/>
                        <Text text="{Description}"/>
                     </form:content>
                  </form:SimpleForm>
               </IconTabFilter>
               <IconTabFilter icon="sap-icon://inspection" key="statistics">
                  <Text text="Viewed 55555 times" id="viewCounter"/>
               </IconTabFilter>
            </items>
         </IconTabBar>

      </semantic:content>
   </semantic:FullscreenPage>
</mvc:View>
```

We add a `sap.m.IconTabBar` with the two tabs `info` and `statistics`. The `statistics` tab we have already referred to in our test case.

Inside the first tab there is a `sap.ui.layout.form.SimpleForm` with a date and a description field that are mapped to the model data. In the second tab we place a new `Text` control.

In this very simple example, we just put a static text in the tab. In a real application, we would bind the value to the model.

***

### webapp/i18n/i18n.properties

```ini
#~~~ Object View ~~~~~~~~~~~~~~~~~~~~~~~~~~

#XTIT: Object view title
objectTitle=Post


#XTIT: Post view date label
postDateLabel=Posted At

#XTIT: Post view description label
postDescriptionLabel=Description


#~~~ Footer Options ~~~~~~~~~~~~~~~~~~~~~~~
```

We add the missing texts to the `i18n.properties` file.

**Parent topic:** [Testing](Testing_291c912.md "In this tutorial we will test application functionality with the testing tools that are delivered with OpenUI5. At different steps of this tutorial you will write tests using QUnit, OPA5, and the OData V2 mock server. Additionally, you will learn about testing strategies, Test Driven Development (TDD), and much more.")

**Next:** [Step 13: Testing User Interaction](Step_13_Testing_User_Interaction_19ccd47.md "In this step we want to write a test that simulates user interaction with an icon tab bar. We want to change the tab and check if the correct content is shown.")

**Previous:** [Step 15: Writing a Short Date Formatter Using TDD](Step_15_Writing_a_Short_Date_Formatter_Using_TDD_bc4114a.md "It's now time to improve the content of the Info tab. We want to see the Posted At date in a formatted way. Based on the age of the post, we either display the time, a textural representation of the day, or the date only.")

