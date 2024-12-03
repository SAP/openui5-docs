<!-- loiob229914587444025be986d81dcc77303 -->

| loio |
| -----|
| b229914587444025be986d81dcc77303 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/b229914587444025be986d81dcc77303) | [demo kit latest release](https://sdk.openui5.org/topic/b229914587444025be986d81dcc77303)</div>

## Manifest for Libraries

The manifest \(also known as descriptor\) for libraries contains a subset of the attributes in the manifest for applications and components.


<table>
<tr>
<th valign="top">

manifest.json

</th>
<th valign="top">

.library

</th>
<th valign="top">

Available for SAPUI5 distribution libraries?

</th>
<th valign="top">

Comment

</th>
</tr>
<tr>
<td valign="top">

`sap.app/id` 

</td>
<td valign="top">

`name` 

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

`sap.app/type` 

</td>
<td valign="top">

\-

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Generated with value `library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.app/embeds` 

</td>
<td valign="top">

\-

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Generated

</td>
</tr>
<tr>
<td valign="top">

`sap.app/i18n` 

</td>
<td valign="top">

`appData/manifest/i18n` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.app/applicationVersion/version` 

</td>
<td valign="top">

`version` 

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

`sap.app/title` 

</td>
<td valign="top">

`title` 

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Text symbol syntax with leading curly brackets \(`{{`\) and trailing curly brackets \(`}}`\); new in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.app/description` 

</td>
<td valign="top">

`documentation` 

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Text symbol syntax with leading curly brackets \(`{{`\) and trailing curly brackets \(`}}`\)

</td>
</tr>
<tr>
<td valign="top">

`sap.app/ach` 

</td>
<td valign="top">

`appData/ownership/component` 

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

`sap.app/openSourceComponents` 

</td>
<td valign="top">

`appData/manifest/openSourceComponents` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.app/resources` 

</td>
<td valign="top">

\-

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Generated with value `resources.json` 

</td>
</tr>
<tr>
<td valign="top">

`sap.app/offline` 

</td>
<td valign="top">

`appData/manifest/offline` 

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.app/sourceTemplate` 

</td>
<td valign="top">

`appData/manifest/sourceTemplate` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library`, to be filled by SAP Web IDE only

</td>
</tr>
<tr>
<td valign="top">

`sap.ui/technology` 

</td>
<td valign="top">

\-

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Generated with value `UI5` 

</td>
</tr>
<tr>
<td valign="top">

`sap.ui/deviceTypes` 

</td>
<td valign="top">

`appData/manifest/deviceTypes` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.ui/supportedThemes` 

</td>
<td valign="top">

\-

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Generated and merged

</td>
</tr>
<tr>
<td valign="top">

`sap.ui5/dependencies/minUI5Version` 

</td>
<td valign="top">

\-

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Generated

</td>
</tr>
<tr>
<td valign="top">

`sap.ui5/dependencies/libs` 

</td>
<td valign="top">

`dependencies` 

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

`sap.ui5/contentDensities` 

</td>
<td valign="top">

`appData/manifest/contentDensities` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.ui5/library/i18n` 

</td>
<td valign="top">

\-

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

Determines whether the library contains an i18n resource. Value can be either a boolean, a string, or an object. For more information, see [Manifest \(Descriptor for Applications, Components, and Libraries\)](Manifest_Descriptor_for_Applications_Components_and_Libraries_be0cf40.md) and [Terminologies](Terminologies_eba8d25.md).

</td>
</tr>
<tr>
<td valign="top">

`sap.platform.abap/uri` 

</td>
<td valign="top">

`appData/manifest/sap.platform.abap/uri` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.platform.hcp/uri` 

</td>
<td valign="top">

`appData/manifest/sap.platform.hcp/uri` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.fiori/registrationIds` 

</td>
<td valign="top">

`appData/manifest/sap.fiori/registrationId` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
<tr>
<td valign="top">

`sap.fiori/archeType` 

</td>
<td valign="top">

`appData/manifest/sap.fiori/archeType` 

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

New in `.library` 

</td>
</tr>
</table>

**Related Information**  


[Creating a Manifest File for Existing Apps](Creating_a_Manifest_File_for_Existing_Apps_3a9baba.md "Detailed description of the steps needed to create a manifest (also known as descriptor) V2 for applications file for an existing transactional app created by the customer based on SAP Fiori.")

