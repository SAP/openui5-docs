<!-- copy51fe8f410623483097c292514c241eeb -->

| loio |
| -----|
| 51fe8f410623483097c292514c241eeb |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/51fe8f410623483097c292514c241eeb) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/51fe8f410623483097c292514c241eeb)</div>

## An Empty Page Comes Up

You find yourself in one of these situations:

-   The browser shows an empty page: there's no content and no error message is displayed

-   An `Uncaught Error` message is shown in the developer console


***

### Preview

   
  
The browser displays an empty page and an `Uncaught Error` is issued in the console

 ![](loio873b3c2966e64bc2b080d8f4a5ae70fc_LowRes.png "The browser displays an empty page and an Uncaught Error is issued in
					the console") 

***

### Root Cause

This can happen for one of the following reasons:

-   A critical reference error is prohibiting the app from starting.

-   A syntax error is stopping the execution of your application code.

-   A parsing error has occurred in an XML view.

-   The tag of the control is written with lowercase letters.

-   The root view is missing a root control.


***

### Resolution

***

#### Console shows `"ReferenceError: sap is not defined"`

Have a look at the `resource` path in the bootstrap of the HTML page you are trying to open. The path to the file `sap-ui-core.js` is probably incorrect and needs to point to the path where the OpenUI5 resources are located \(typically globally under `/resources` or locally under `resources`\).

Other development environments might need the resources to be copied to the server and referenced relatively to the app \(see [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md)\).

Alternatively, you can use the CDN version \(see [Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md)\).

***

#### Console shows `SyntaxError: <error details>`

A JavaScript error in the application code throws an exception and stops all subsequent execution. Take a look at the error details: In most cases, the root cause is mentioned in the first line of the error message.

The stack trace can provide more context on the execution scope. Analyze it from thoroughly to find a line referencing your application code and start debugging there.

***

#### Console shows `Error: Invalid XML`

If the XML view to be displayed cannot be parsed, OpenUI5 stops the execution and throws a parse error. Check the XML view for namespace issues, typos, and missing closing tags. Do a schema validation with an XML validator tool.

***

#### Console shows `Uncaught Error: failed to load 'sap/m/xxxxx.js'`

During the development on Microsoft Windows, your app works fine, but a soon as you deploy it on a Linux system, only an empty page comes up.

This could happen if you wrote the tag of the control with lowercase letters, because Linux systems use case-sensitive file names.


<table>
<tr>
<th valign="top">

Correct Example



</th>
<th valign="top">

Incorrect Example



</th>
</tr>
<tr>
<td valign="top">

 `<**B**utton text="Click me" />` 



</td>
<td valign="top">

`<**b**utton text="Click me" />`

Error message: `Uncaught Error: failed to load 'sap/m/button.js'`



</td>
</tr>
</table>

> ### Tip:  
> Control tags always start with capital letters after the namespace like `<Button>`, `<l:FixFlex>`, `<f:SimpleForm>`.
> 
> Aggregations always start with lowercase letters like `<content>`, `<l:fixContent>`, `<f:content>`

***

#### Console shows no error

Your root view is missing a root control. In the context of OpenUI5, `sap.m.App` or `sap.m.SplitApp` function as root controls. Please check your root view \(for example `App.view.xml`\) and add the missing root control.

