<!-- loio3a16c7a2f1e944deb000db49e5ece6be -->

| loio |
| -----|
| 3a16c7a2f1e944deb000db49e5ece6be |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3a16c7a2f1e944deb000db49e5ece6be) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3a16c7a2f1e944deb000db49e5ece6be)</div>

## Create a Northwind Destination

Configure a destination in the SAP BTP Cockpit in order to bypass the same-origin policy of the browser.

> Note:  
> SAP Web IDE is no longer available via SAP Business Technology Platform trial accounts. Any references to SAP Web IDE in this documentation are only relevant for you if you have access to SAP Web IDE through a productive SAP BTP account. Please consider SAP Business Application Studio as an alternative. See [App Development Using SAP Business Application Studio](App_Development_Using_SAP_Business_Application_Studio_6bbad66.md).

***

To be able to test your app, you can use a remote OData service that provides product data from the Northwind demo service of the OData group.

In the navigation bar of the SAP BTP Cockpit, choose *Destinations* and then choose *New Destination* in the toolbar.

 ![](loiod4b788e837474db8a62f91b376ec4086_HiRes.png) 

Enter the following values into the corresponding fields:

|Field

|Value

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>-------</th>
			<th>-------</th>
		</tr>
	</thead>
	<tbody>

			<td> `northwind` 
			</td>
		</tr>
		<tr>
			<td> *Type* 
			</td>
			<td> `HTTP` 
			</td>
		</tr>
		<tr>
			<td> *Description* 
			</td>
			<td> `Northwind OData Service` 
			</td>
		</tr>
		<tr>
			<td> *URL* 
			</td>
			<td> `https://services.odata.org` 
			</td>
		</tr>
		<tr>
			<td> *Proxy Type* 
			</td>
			<td> `Internet` 
			</td>
		</tr>
		<tr>
			<td> *Authentication* 
			</td>
			<td> `NoAuthentication` 
			</td>
		</tr>
	</tbody>
</table>

Also, enter the following properties in the section *Additional Properties*:

|Property

|Value

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>----------</th>
			<th>-------</th>
		</tr>
	</thead>
	<tbody>

			<td> `true` 
			</td>
		</tr>
		<tr>
			<td> `WebIDESystem` 
			</td>
			<td> `Northwind` 
			</td>
		</tr>
		<tr>
			<td> `WebIDEUsage` 
			</td>
			<td> `odata_gen` 
			</td>
		</tr>
		<tr>
			<td> `Use default JDK truststore` 
			</td>
			<td>Set the checkmark.
			</td>
		</tr>
	</tbody>
</table>

***

<a name="loio3a16c7a2f1e944deb000db49e5ece6be__section_ill_4vz_ghb"/>

### neo-app.json

With this configuration you can use the destination for any app inside SAP Web IDE. Whenever an app calls a \(local\) service beginning with `/destinations/northwind/*`, the created destination becomes active as a simple proxy. This helps to prevent any possible issues related to the same-origin policy of browsers. For this, you need to add another route to the `neo-app.json`:

``` json
{
  "welcomeFile": "index.html",
  "routes": [
    {
      
      "path": "/resources",
      "target": {
        "type": "service",
        "name": "sapui5",
        "version": "snapshot",
        "entryPath": "/resources"
      },
      "description": "SAPUI5 Resources"
    },
    {
      "path": "/test-resources",
      "target": {
        "type": "service",
        "name": "sapui5",
        "entryPath": "/test-resources"
      },
      "description": "SAPUI5 Test Resources"
    }*HIGHLIGHT START*,
    {
      "path": "/destinations/northwind",
      "target": {
        "type": "destination",
        "name": "northwind"
      },
      "description": "Northwind OData Service"
    }*HIGHLIGHT END*
  ]
}
```

***

<a name="loio3a16c7a2f1e944deb000db49e5ece6be__section_t5m_fwz_ghb"/>

### webapp/manifest.json

In the app descriptor, the service URL is then defined relative to the destination path specified above:

``` json
...
"sap.app": {
 "dataSources": {
   "": {
     "uri": "*HIGHLIGHT START*/destinations/northwind/V2/Northwind/Northwind.svc/*HIGHLIGHT END*",
     "type": "OData",
     "settings": {
       "odataVersion": "2.0"
     }
   }
 }
}
...
```

