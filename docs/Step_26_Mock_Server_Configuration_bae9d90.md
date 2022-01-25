<!-- loiobae9d90d2e9c4206889368f04edab508 -->

| loio |
| -----|
| bae9d90d2e9c4206889368f04edab508 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/bae9d90d2e9c4206889368f04edab508) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/bae9d90d2e9c4206889368f04edab508)</div>

## Step 26: Mock Server Configuration

We just ran our app against a real service, but for developing and testing our app we do not want to rely on the availability of the “real” service or put additional load on the system where the data service is located.

This system is the so-called back-end system that we will now simulate with an OpenUI5 feature called mock server. It serves local files, but it simulates a back-end system more realistically than just loading the local data. We will also change the model instantiation part so that the model is configured in the descriptor and instantiated automatically by OpenUI5. This way, we do not need to take care of the model instantiation in the code.

***

### Preview

   
  
<a name="loiobae9d90d2e9c4206889368f04edab508__fig_r1j_pst_mr"/>The list of invoices is now served by the Mock Server

 ![](loioccce9b342efd457990d547ba35323f93_HiRes.png "The list of invoices is now served by the Mock Server") 

***

### Coding

You can view and download all files at [Walkthrough - Step 26](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.26/preview).

   
  
<a name="loiobae9d90d2e9c4206889368f04edab508__fig_dhm_tbp_ns"/>Folder Structure for this Step

 ![](loio7a5e2b02d72d40d388f5e601d7de74df_HiRes.png "Folder Structure for this Step") 

The folder structure of our app project is clearly separating test and productive files after this step. The new `test` folder now contains a new HTML page `mockServer.html` which will launch our application in test mode without calling the real service.

The new `localService` folder contains a `metadata.xml` service description file for OData, the `mockserver.js` file that simulates a real service with local data, and the `mockdata` subfolder that contains the local test data \(`Invoices.json`\).

***

### webapp/test/mockServer.html \(New\)

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>SAPUI5 Walkthrough</title>
	<script
		id="sap-ui-bootstrap"
		src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js"
		data-sap-ui-theme="sap_belize"
		data-sap-ui-libs="sap.m"
		data-sap-ui-resourceroots='{
			"sap.ui.demo.walkthrough": "./"
		}'
		data-sap-ui-oninit="module:sap/ui/core/ComponentSupport"
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true">
	</script>
</head>
<body class="sapUiBody" id="content">
	<div data-sap-ui-component data-name="sap.ui.demo.walkthrough" data-id="container" data-settings='{"id" : "walkthrough"}'></div>

</body>
</html>

```

We copy the `index.html` to a separate file in the `webapp/test` folder and name it `mockServer.html`. We will now use this file to run our app in test mode with mock data loaded from a JSON file. Test pages should not be placed in the application root folder but in a subfolder called `test` to clearly separate productive and test coding.

From this point on, you have two different entry pages: One for the real “connected” app \(`index.html`\) and one for local testing \(`mockServer.html`\). You can freely decide if you want to do the next steps on the real service data or on the local data within the app.

> ### Note:  
> If no connection to the real service is available or the proxy configuration from the previous step does not work, you can always use the `mockServer.html` file. This will display the app with simulated test data. The `index.html` file will always load the data from a remote server. If the request fails, the list of invoices will stay empty.

***

<a name="loiobae9d90d2e9c4206889368f04edab508__section_nxn_5zr_yfb"/>

### webapp/test/mockServer.html

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>SAPUI5 Walkthrough*HIGHLIGHT START* - Test Page*HIGHLIGHT END*</title>
	<script
		id="sap-ui-bootstrap"
		src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js"
		data-sap-ui-theme="sap_belize"
		data-sap-ui-resourceroots='{
			"sap.ui.demo.walkthrough": *HIGHLIGHT START*"../"*HIGHLIGHT END*
		}'
*HIGHLIGHT START*		data-sap-ui-oninit="module:sap/ui/demo/walkthrough/test/initMockServer"*HIGHLIGHT END*
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true">
	</script>
</head>
<body class="sapUiBody" id="content">
	<div data-sap-ui-component data-name="sap.ui.demo.walkthrough" data-id="container" data-settings='{"id" : "walkthrough"}'></div>
</body>
</html>

```

We modify the `mockServer.html` file and change the page title to distinguish it from the productive start page. In the bootstrap, the `data-sap-ui-resourceroots` property is also changed. The namespace now points to the folder above \(`"../"`\), because the `mockServer.html` file is now in a subfolder of the `webapp` folder. Instead of loading the app component directly, we now call a script `initMockServer.js`.

***

<a name="loiobae9d90d2e9c4206889368f04edab508__section_oxn_5zr_yfb"/>

### webapp/test/initMockServer.js \(New\)

``` js
*HIGHLIGHT START*sap.ui.define([
	"../localService/mockserver"
], function (mockserver) {
	"use strict";

	// initialize the mock server
	mockserver.init();

	// initialize the embedded component on the HTML page
	sap.ui.require(["sap/ui/core/ComponentSupport"]);
});
*HIGHLIGHT END*
```

The first dependency is a file called `mockserver.js` that will be located in the `localService` folder later.

The `mockserver` depencency that we are about to implement is our local test server. Its `init` method is immediately called before we load the component. This way we can catch all requests that would go to the "real" service and process them locally by our test server when launching the app with the `mockServer.html` file. The component itself does not "know" that it will now run in test mode.

***

### webapp/localService/mockdata/Invoices.json \(New\)

``` js
*HIGHLIGHT START*[
  {
	"ProductName": "Pineapple",
	"Quantity": 21,
	"ExtendedPrice": 87.2000,
	"ShipperName": "Fun Inc.",
	"ShippedDate": "2015-04-01T00:00:00",
	"Status": "A"
  },
  {
	"ProductName": "Milk",
	"Quantity": 4,
	"ExtendedPrice": 9.99999,
	"ShipperName": "ACME",
	"ShippedDate": "2015-02-18T00:00:00",
	"Status": "B"
  },
  {
	"ProductName": "Canned Beans",
	"Quantity": 3,
	"ExtendedPrice": 6.85000,
	"ShipperName": "ACME",
	"ShippedDate": "2015-03-02T00:00:00",
	"Status": "B"
  },
  {
	"ProductName": "Salad",
	"Quantity": 2,
	"ExtendedPrice": 8.8000,
	"ShipperName": "ACME",
	"ShippedDate": "2015-04-12T00:00:00",
	"Status": "C"
  },
  {
	"ProductName": "Bread",
	"Quantity": 1,
	"ExtendedPrice": 2.71212,
	"ShipperName": "Fun Inc.",
	"ShippedDate": "2015-01-27T00:00:00",
	"Status": "A"
  }
]*HIGHLIGHT END*
```

The `Invoices.json` file is similar to our previous file in the `webapp` folder. Just copy the content and remove the outer object structure with the key `invoices` so that the file consists of one flat array of invoice items. This file will automatically be read by our server later in this step.

Remove the old `Invoices.json` file from the `webapp` folder, it is no longer used.

***

### webapp/localService/metadata.xml \(New\)

``` xml
*HIGHLIGHT START*<edmx:Edmx Version="1.0" xmlns:edmx="http://schemas.microsoft.com/ado/2007/06/edmx">
	<edmx:DataServices m:DataServiceVersion="1.0" m:MaxDataServiceVersion="3.0"
			xmlns:m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata">
		<Schema Namespace="NorthwindModel" xmlns="http://schemas.microsoft.com/ado/2008/09/edm">
			<EntityType Name="Invoice">
				<Key>
					<PropertyRef Name="ProductName"/>
					<PropertyRef Name="Quantity"/>
					<PropertyRef Name="ShipperName"/>
				</Key>
				<Property Name="ShipperName" Type="Edm.String" Nullable="false" MaxLength="40" FixedLength="false"
							Unicode="true"/>
				<Property Name="ProductName" Type="Edm.String" Nullable="false" MaxLength="40" FixedLength="false"
							Unicode="true"/>
				<Property Name="Quantity" Type="Edm.Int16" Nullable="false"/>
				<Property Name="ExtendedPrice" Type="Edm.Decimal" Precision="19" Scale="4"/>
				<Property Name="Status" Type="Edm.String" Nullable="false" MaxLength="1" FixedLength="false"
							Unicode="true"/>
			</EntityType>
		</Schema>
		<Schema Namespace="ODataWebV2.Northwind.Model" xmlns="http://schemas.microsoft.com/ado/2008/09/edm">
			<EntityContainer Name="NorthwindEntities" m:IsDefaultEntityContainer="true" p6:LazyLoadingEnabled="true"
					xmlns:p6="http://schemas.microsoft.com/ado/2009/02/edm/annotation">
				<EntitySet Name="Invoices" EntityType="NorthwindModel.Invoice"/>
			</EntityContainer>
		</Schema>
	</edmx:DataServices>
</edmx:Edmx>
*HIGHLIGHT END*
```

The metadata file contains information about the service interface and does not need to be written manually. It can be accessed directly from the “real” service by calling the service URL and adding `$metadata` at the end \(e.g. in our case `http://services.odata.org/V2/Northwind/Northwind.svc/$metadata`\). The mock server will read this file to simulate the real OData service, and will return the results from our local source files in the proper format so that it can be consumed by the app \(either in XML or in JSON format\).

For simplicity, we have removed all content from the original Northwind OData metadata document that we do not need in our scenario. We have also added the `status` field to the metadata since it is not available in the real Northwind service.

***

### webapp/localService/mockserver.js \(New\)

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/core/util/MockServer",
	"sap/base/util/UriParameters"
], function (MockServer, UriParameters) {
	"use strict";

	return {
		init: function () {
			// create
			var oMockServer = new MockServer({
				rootUri: "https://services.odata.org/V2/Northwind/Northwind.svc/"
			});

			var oUriParameters = new UriParameters(window.location.href);

			// configure mock server with a delay
			MockServer.config({
				autoRespond: true,
				autoRespondAfter: oUriParameters.get("serverDelay") || 500
			});

			// simulate
			var sPath = sap.ui.require.toUrl("sap/ui/demo/walkthrough/localService");
			oMockServer.simulate(sPath + "/metadata.xml", sPath + "/mockdata");

			// start
			oMockServer.start();
		}
	};

});
*HIGHLIGHT END*
```

Now that we have added the OData service description file `metadata.xml` file, we can write the code to initialize the mock server which will then simulate any OData request to the real Northwind server.

We load the standard OpenUI5 `MockServer` module as a dependency and create a helper object that defines an `init` method to start the server. This method is called before the component initialization in the `mockServer.html` file above. The `init` method creates a `MockServer` instance with the same URL as the real service calls.

The URL in configuration parameter `rootUri` has to be exactly the same as the `uri` that is defined for the data source in the `manifest.json` descriptor file. This can be an absolute or, for example in SAP Web IDE, a relative URL to a destination. The URL will now be served by our test server instead of the real service. Next, we set two global configuration settings that tell the server to respond automatically and introduce a delay of one second to imitate a typical server response time. Otherwise, we would have to call the respond method on the `MockServer` manually to simulate the call.

To simulate a service, we can simply call the `simulate` method on the `MockServer` instance with the path to our newly created `metadata.xml`. This will read the test data from our local file system and set up the URL patterns that will mimic the real service.

Finally, we call start on `oMockServer`. From this point, each request to the URL pattern `rootUri` will be processed by the `MockServer`. If you switch from the `index.html` file to the `mockServer.html` file in the browser, you can now see that the test data is displayed from the local sources again, but with a short delay. The delay can be specified with the URI parameter `serverDelay`, the default value is one second.

This approach is perfect for local testing, even without any network connection. This way your development does not depend on the availability of a remote server, i.e. to run your tests.

Try calling the app with the `index.html` file and the `mockServer.html` file to see the difference. If the real service connection cannot be made, for example when there is no network connection, you can always fall back to the local test page.

***

### Conventions

-   The `webapp/test` folder contains non-productive code only.

-   Mock data and the script to start the `MockServer` are stored in the `webapp/localService` folder.

-   The script to start the `MockServer` is called `mockserver.js`.


**Parent topic:** [Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:** [Step 25: Remote OData Service](Step_25_Remote_OData_Service_4406244.md "So far we have worked with local JSON data, but now we will access a real OData service to visualize remote data.")

**Previous:** [Step 27: Unit Test with QUnit](Step_27_Unit_Test_with_QUnit_e1ce1de.md "Now that we have a test folder in the app, we can start to increase our test coverage.")

**Related Information**  


[Mock Server](Mock_Server_69d3cbd.md "A mock server mimics one or more back-end services. It is used to simplify integration testing and to decouple UI development from service development. By using a mock server you can develop and test the UI even if the service in the back end is incomplete or unstable.")

[API Reference: `sap.ui.core.util.MockServer`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.util.MockServer.html)

[Create a Northwind Destination](Create_a_Northwind_Destination_3a16c7a.md "Configure a destination in the SAP BTP Cockpit in order to bypass the same-origin policy of the browser.")

