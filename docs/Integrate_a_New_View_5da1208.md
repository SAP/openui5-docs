<!-- loio5da1208e40364ff59ce12fb50a067c45 -->

| loio |
| -----|
| 5da1208e40364ff59ce12fb50a067c45 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5da1208e40364ff59ce12fb50a067c45) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5da1208e40364ff59ce12fb50a067c45)</div>

## Integrate a New View

To integrate a new view, you can either add it to index.html or nest it into another view.

***

If you create a new view for an existing SAPUI5 application project, the view needs to be manually called.

1.  To call a view, choose from the following options:

    -   Directly embed the new view in the index.html page
    -   All Views can be nested independent of the view type. Each view type behaves like any SAPUI5 control. The `viewName` property defines, which views are embedded. To nest a view, proceed according to the given examples:

    For XML view type:

    ``` xml
    <mvc:View controllerName="sap.hcm.Address" xmlns:mvc="sap.ui.core.mvc" xmlns="sap.m">
       <Panel>
          <mvc:JSView id="myJSView" viewName="sap.hcm.Bankaccount" />
       </Panel>
    </core:View>
    ```

    For HTML views, the nested view looks as follows:

    ``` html
    <template data-controller-name= "example.mvc.test" >
    
      <div data-sap-ui-type= "sap.ui.core.mvc.HTMLView" id= "MyHTMLView" data-view-name= "example.mvc.test2" ></div>
      <div data-sap-ui-type= "sap.ui.core.mvc.JSView" id= "MyJSView" data-view-name= "example.mvc.test2" ></div>
      <div data-sap-ui-type= "sap.ui.core.mvc.JSONView" id= "MyJSONView" data-view-name= "example.mvc.test2" ></div>
      <div data-sap-ui-type= "sap.ui.core.mvc.XMLView" id= "MyXMLView" data-view-name= "example.mvc.test2" ></div>
    
    </template>
    ```


