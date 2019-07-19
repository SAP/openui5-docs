<!-- loio96bb6e06fa22491fa65a5040f6da099c -->

| loio |
| -----|
| 96bb6e06fa22491fa65a5040f6da099c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/96bb6e06fa22491fa65a5040f6da099c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/96bb6e06fa22491fa65a5040f6da099c)</div>

## Step 3: Automatic Data Type Detection

In this step, we use the automatic data type detection of the OData V4 model to parse, validate, and format user entries. The service metadata contains type information for the properties of each entity.

The OData V4 Model utilizes this information to compute the corresponding OpenUI5 type, including constraints, and sets this type to the OpenUI5 property binding for the entity property. For example, for `<Input value={Age}/>` the OpenUI5 type `Int64` is used, which corresponds to the OData type `Edm.Int64`.

***

<a name="loio96bb6e06fa22491fa65a5040f6da099c__section_bt4_fxc_z1b"/>

### Preview

   
  
Input does not match the underlying data type<a name="loio96bb6e06fa22491fa65a5040f6da099c__fig_zyb_mlb_mcb"/>

 ![](loio8320fcfb59db4d209e17a84c21e44647_LowRes.png "Input does not match the underlying data type") 

***

<a name="loio96bb6e06fa22491fa65a5040f6da099c__section_tsr_gxc_z1b"/>

### Coding

You can view and download all files at [OData V4 - Step 3](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.odatav4.03/preview).

***

<a name="loio96bb6e06fa22491fa65a5040f6da099c__section_pp2_mxc_z1b"/>

### webapp/manifest.json

``` json
{
	"_version": "1.12.0",
	"sap.app": {...
	},
	"sap.ui": {
		"technology": "UI5",
		"deviceTypes": {
		   
		}
	},
	"sap.ui5": {
		"rootView": {
		...
		},
		"dependencies": {
			...
			}
		},
		"contentDensities": {
			...
		},
		*HIGHLIGHT START*"handleValidation": true*HIGHLIGHT END*,
		
		"models": {
			...
			}
		}
	},
	"sap.platform.hcp": {
		...
	}

```

In the `manifest.json` descriptor file, we add the `"handleValidation": true` setting. This makes sure that any validation errors that are detected by the OpenUI5 types are shown on the UI using the message manager.

We now run the app using the `index.html` file and enter values that don't match the type and constraints given in the metadata file. For example, enter the string value `Young at Heart` in field *Age*, which requires an integer input \(OpenUI5 type `sap.ui.model.odata.type.Int64`, corresponding to OData type `Edm.Int64`\), or remove an entry from the *User Name* or *First Name* fields, which are mandatory. Fields with incorrect entries are highlighted and an error message is displayed.

> Note:
> If you explicitly define a type in the binding info of a control, the automatic type detection for that binding will be turned off. For example, if you change the `Input` for `Age` in the view to `<Input value="{path:'Age', type:'sap.ui.model.type.String'}/>`, the `String` type will be used, not the `Int64` type from the service metadata.
> 
> 

***

<a name="loio96bb6e06fa22491fa65a5040f6da099c__section_pvc_fyc_z1b"/>

### localService/metadata.xml

``` xml
<EntityType Name="Person">
	<Key>
		<PropertyRef Name="UserName"/>
	</Key>
	<Property Name="UserName" Type="Edm.String" Nullable="false" />
	<Property Name="FirstName" *HIGHLIGHT START*Type="Edm.String"*HIGHLIGHT END* />
	<Property Name="LastName" Type="Edm.String"/>
	<Property Name="MiddleName" Type="Edm.String"/>
	<Property Name="Gender" Type="Microsoft.OData.Service.Sample.TrippinInMemory.Models.PersonGender"
			  Nullable="false"/>
	<Property Name="Age" Type="Edm.Int64" />
   
```

To make the *First Name* optional, we remove the parameter `Nullable="false"` from the `FirstName` property. You can play around with the settings for the other properties, for example, change the type of property `Age` to `Type="Edm.String"` to allow free text.

***

> Note:
> To see the metadata of an OData service, you append the `$metadata` variable to the URL of the service. You can try this, for example, with [http://services.odata.org/TripPinRESTierService/](http://services.odata.org/TripPinRESTierService/) and [http://services.odata.org/TripPinRESTierService/$metadata](http://services.odata.org/TripPinRESTierService/$metadata)
> 
> 

**Related information**  


[Type Determination](Type_Determination_53cdd55.md)

[API Reference: `sap.ui.model.odata.type`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.type.html)

[Sample for `sap.ui.core.mvc.XMLView`: *XML Templating: UI5 OData types*](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.sample.ViewTemplate.types/preview)

