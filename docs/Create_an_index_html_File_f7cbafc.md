<!-- loiof7cbafc9a76140ec8fc55b51a63cf467 -->

| loio |
| -----|
| f7cbafc9a76140ec8fc55b51a63cf467 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/f7cbafc9a76140ec8fc55b51a63cf467) | [demo kit latest release](https://sdk.openui5.org/topic/f7cbafc9a76140ec8fc55b51a63cf467)</div>

## Create an index.html File

A minimalistic `index.html` file is needed to test the project configuration. This file contains the OpenUI5 bootstrap and an `sap.m.Text` control that displays the text "**OpenUI5 is loaded successfully!**".

> ### Caution:  
> SAP Web IDE is no longer available via SAP Business Technology Platform trial accounts. Any references to SAP Web IDE in this documentation are only relevant for you if you have access to SAP Web IDE through a productive SAP BTP account. Please consider SAP Business Application Studio as an alternative. See [App Development Using SAP Business Application Studio](App_Development_Using_SAP_Business_Application_Studio_6bbad66.md).

1.  Choose the *New Folder* icon in the header toolbar and enter ***src*** as the folder name.
2.  Select the newly created folder and create a new `index.html` file inside it by choosing the *New File* icon.
3.  Paste the following code in the newly created `index.html` file and select *Save*:

    **index.html**

    ```html
    <!DOCTYPE html>
    <html>
    	<head>
    		<meta charset="utf-8">
    		<title>SAPUI5 Walkthrough</title>
    		<script
    			id="sap-ui-bootstrap"
    			src="/resources/sap-ui-core.js"
    			data-sap-ui-theme="sap_belize"
    			data-sap-ui-libs="sap.m"
    			data-sap-ui-compatVersion="edge"
                   data-sap-ui-async="true"
                   data-sap-ui-onInit="module:my/app/main"
                   data-sap-ui-resourceRoots='{"my.app": "./"}'
     			></script>
    	</head>
    	<body class="sapUiBody" id="content">
    	</body>
    </html>
    ```

4.  Create new file `main.js` and paste the following code into it:

    **main.js**

    ```js
    sap.ui.define(['sap/m/Text'], function(Text) {
        new Text({
            text: "OpenUI5 is loaded successfully!"
        }).placeAt("content");
    });
    ```


> ### Caution:  
> Adapt the path where the resources are located \(`src="/resources/sap-ui-core.js"`\) according to your installation. For OpenUI5 you can use `src="https://sdk.openui5.org/resources/sap-ui-core.js"`.
> 
> You can use this reference to the latest stable version of OpenUI5 for the tutorial or for testing purposes, but never use this for productive use. In an actual app, you always have to specify an OpenUI5 version explicitly.
> 
> For more information, see [Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

