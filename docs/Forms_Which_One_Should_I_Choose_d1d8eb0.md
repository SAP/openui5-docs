<!-- loiod1d8eb099d714566becf0af75697d073 -->

| loio |
| -----|
| d1d8eb099d714566becf0af75697d073 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/d1d8eb099d714566becf0af75697d073) | [demo kit latest release](https://sdk.openui5.org/topic/d1d8eb099d714566becf0af75697d073)</div>

## Forms: Which One Should I Choose?

To display and edit data in a form, OpenUI5 offers various form controls that are suitable for different use cases. This documentation outlines which form controls are available, and what features are supported by each one.

The following table gives an overview of form controls and their usage:

**Overview of Form Controls and Supported Features**


<table>
<tr>
<th valign="top">



</th>
<th valign="top">

Form [\(`sap.ui.layout.form.Form`\)](https://sdk.openui5.org/api/sap.ui.layout.form.Form) 



</th>
<th valign="top">

Simple Form [\(`sap.ui.layout.form.SimpleForm`\)](https://sdk.openui5.org/api/sap.ui.layout.form.SimpleForm) 



</th>
<th valign="top">

Smart Form [\(`sap.ui.comp.smartform.SmartForm`\)](https://sdk.openui5.org/api/sap.ui.comp.smartform.SmartForm) 



</th>
</tr>
<tr>
<td valign="top">

Flexibility



</td>
<td valign="top">

1



</td>
<td valign="top">

3



</td>
<td valign="top">

2



</td>
</tr>
<tr>
<td valign="top">

Complexity



</td>
<td valign="top">

3



</td>
<td valign="top">

1



</td>
<td valign="top">

2



</td>
</tr>
<tr>
<td valign="top">

Performance



</td>
<td valign="top">

1



</td>
<td valign="top">

3



</td>
<td valign="top">

2



</td>
</tr>
<tr>
<td valign="top">

Automatic responsive design



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
</tr>
<tr>
<td valign="top">

Accessible design



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
</tr>
<tr>
<td valign="top">

Controls inside are OData-bindable



</td>
<td valign="top">

![No](images/loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif)



</td>
<td valign="top">

![No](images/loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif)



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
</tr>
<tr>
<td valign="top">

Enables a granular structure of a form control



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
<td valign="top">

![No](images/loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif)



</td>
<td valign="top">

![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)



</td>
</tr>
</table>

**Legend**:

-   Rating:

    -   1: Best suited

    -   2: Average

    -   3: Least suited


-   ![Yes](images/loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif): Feature is supported for this form type

-   ![No](images/loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif): Feature is not supported for this form type


***

<a name="loiod1d8eb099d714566becf0af75697d073__section_ohd_n2p_dzb"/>

### Use Cases

***

#### Form

Use `sap.ui.layout.form.Form` if you want to do the following:

-   Create a highly customized form

-   Display a large amount of data in a form

-   Create complex forms with multiple sections and different types of input fields

-   Have granular control over the structure of a form

-   Manage the responsiveness of the form yourself


***

#### Simple Form

Use `sap.ui.layout.form.SimpleForm` if you want to do the following:

-   Use a very simple structure of a form in a straightforward way

-   Create a form quickly and easily

-   Use a form that is automatically responsive


***

#### Smart Form

Use `sap.ui.comp.smartform.SmartForm` if you want to do the following:

-   Bind a control to an OData entity within your form

-   Create and edit forms for SAP applications

-   Leverage the built-in data validation of OpenUI5 based on the OData model's metadata

-   Work with OData services and automatically generate form fields


***

<a name="loiod1d8eb099d714566becf0af75697d073__section_vtp_3xq_dzb"/>

### Recommendations

***

#### Do not nest layouts and forms

***

#### Do not use other forms or layout controls

Using any other form or layout control \(for example,  `HBox`\) as children of a form can lead to issues with accessibility or the responsive design. This applies to all form controls mentioned.

