<!-- loiofe1a6dba940e479fb7c3bc753f92b28c -->

| loio |
| -----|
| fe1a6dba940e479fb7c3bc753f92b28c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/fe1a6dba940e479fb7c3bc753f92b28c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/fe1a6dba940e479fb7c3bc753f92b28c)</div>

## Content Security Policy

Content Security Policy \(CSP\) adds an additional layer of security that can detect and mitigate certain types of attacks, such as cross-site scripting and data injection.

***

CSP restricts the sources from which the browser is allowed to load resources, such as scripts, fonts, and images:

-   CSP mitigates and reports XSS attacks; CSP-compatible browsers only execute scripts loaded in source files that are received from allowed sources.

-   CSP also mitigates packet sniffing attacks by specifying the protocols that are allowed to be used on the web server, for example, specifying that content must be loaded from HTTPS.


CSP is either enabled via a configuration in the web server to return the Content-Security-Policy HTTP header \(preferred solution\), or via the `<meta>` element in the meta tags of an HTML page.

For generic information about CSP, see [https://www.w3.org/TR/CSP2/](https://www.w3.org/TR/CSP2/).

***

<a name="loiofe1a6dba940e479fb7c3bc753f92b28c__section_chc_tmq_crb"/>

### CSP for OpenUI5 - Dos and Don'ts

For OpenUI5, we recommend that developers build their apps CSP-compliant, in particular regarding the loading of resources and the use of inline scripts.

***

#### Asynchronous Loading

`eval()` is currently still required in OpenUI5 for synchronous loading. However, we recommend to load JavaScript resources asynchronously and this also avoids the use of `eval()`. For more information about asynchronous loading, see [Modules and Dependencies](Modules_and_Dependencies_91f23a7.md). For more information about avoiding synchronous APIs which might lead to synchronous loading, see [Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md).

***

#### How to Avoid Inline Scripts

To build CSP-compliant OpenUI5 without inline scripts, avoid the following:

-   `<script>` elements with inlined source code

-   Inline event handlers

-   `javascript:` URLs

-   `document.write()`, `createElement('script')`, and so on, if they are used to create inline scripts. Creating script references, such as `<script src="..."></script>` or non-script content with them is okay.


***

#### `eval()`-Free Policies

For a CSP policy, which does not allow `eval()`, you must also avoid the following elements when developing OpenUI5 apps:

-   `new Function()`

-   `setTimeout(<non-fn>)`

    This will be ignored silently and not create a timer without `'unsafe-eval'`, that is, `<non-fn>` is never executed. `setTimeout(<fn>)` will work with and without `'unsafe-eval'`.

-   `setInterval(<non-fn>)`

    This will be ignored silently and not create a repeated timer without `'unsafe-eval'`, that is, the `<non-fn>` is never executed. `setInterval(<fn>)` will work with and without the `'unsafe-eval'`.


***

<a name="loiofe1a6dba940e479fb7c3bc753f92b28c__section_wrv_wpq_crb"/>

### Directives

To run an app in an environment in which CSP has been enabled, OpenUI5 requires the following directives:


<table>
<tr>
<th rowspan="2">

Directive



</th>
<th colspan="4">

Sources Required by the OpenUI5 Framework



</th>
<th colspan="2">

Sources Required by the Application



</th>
</tr>
<tr>
<th>

`<source hosting >`

\(equals `'self'` if is hosted with the application\)



</th>
<th>

`data:`



</th>
<th>

`blob:`



</th>
<th>

Other Sources



</th>
<th>

`'self'`



</th>
<th>

Custom Sources \(including `'self'`\)



</th>
</tr>
<tr>
<td>

`script-src`



</td>
<td>

   



</td>
<td>

 



</td>
<td>

 



</td>
<td>

`'unsafe-eval'`

Required for synchronous loading of JavaScript resources.

Required at least if using:

-   `sap.ui.commons`
-   ...



</td>
<td>

Required for loading application resources.



</td>
<td>

Might require `'unsafe-inline'` or `'unsafe-eval'` depending on custom scripts.



</td>
</tr>
<tr>
<td>

`style-src`



</td>
<td>

   



</td>
<td>

 



</td>
<td>

 



</td>
<td>

`'unsafe-inline'`

Required at least if using:

-   `sap.ui.commons`
-   ...



</td>
<td>

May be needed for loading styles from the application.



</td>
<td>

The location of custom themes needs to be added.

Requires `'unsafe-inline'` for custom controls using inline styles.



</td>
</tr>
<tr>
<td>

`img-src`



</td>
<td>

   



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

 



</td>
<td>

May be needed for loading images from the application.



</td>
<td>

The location of custom images \(for example,. for custom themes, images in the back end\) needs to be added.



</td>
</tr>
<tr>
<td>

`font-src`



</td>
<td>

   



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

 



</td>
<td>

 



</td>
<td>

May be needed for loading fonts from the application.



</td>
<td>

The location of custom fonts needs to be added.



</td>
</tr>
<tr>
<td>

`frame-src`



</td>
<td>

Required for using the support assistant and/or the diagnostics tool. Also required to avoid a fallback to `child-src`.



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

 



</td>
<td>

 



</td>
<td>

May be required depending on the integration, application, or test scenario.



</td>
</tr>
<tr>
<td>

`worker-src`



</td>
<td>

   



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

 



</td>
<td>

 



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`child-src`



</td>
<td>

   



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

May be required by some specific OpenUI5 functionality.



</td>
<td>

 



</td>
<td>

 



</td>
<td>

 



</td>
</tr>
<tr>
<td>

`connect-src`



</td>
<td>

   



</td>
<td>

 



</td>
<td>

 



</td>
<td>

Some specific OpenUI5 functionality may require `wss:`.



</td>
<td>

Required for loading application resources.



</td>
<td>

 



</td>
</tr>
</table>

To use a most restrictive policy, set up CSP in `report-only` mode and start with a minimal policy. Monitor the reports to add missing sources. Finally switch CSP to enforcing the policy.

