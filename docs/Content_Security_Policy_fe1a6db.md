<!-- loiofe1a6dba940e479fb7c3bc753f92b28c -->

| loio |
| -----|
| fe1a6dba940e479fb7c3bc753f92b28c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/fe1a6dba940e479fb7c3bc753f92b28c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/fe1a6dba940e479fb7c3bc753f92b28c)</div>

## Content Security Policy

Content Security Policy \(CSP\) adds an additional layer of security that enables the detection and mitigation of certain types of attacks including cross site scripting and data injection.

CSP restricts the sources from which the browser is allowed to load resources, such as scripts, fonts, and images:

-   CSP mitigates and reports XSS attacks; CSP compatible browsers only execute scripts loaded in source files that are received from whitelisted sources.

-   CSP also mitigates packet sniffing attacks by specifying the protocols that are allowed to be used in the web server, for example, specifying that content must only be loaded from HTTPS.


CSP is either enabled via a configuration in the web server to return the Content-Security-Policy HTTP header \(preferred solution\), or via the <meta\> element in the meta tags of an HTML page.

For generic information about CSP, see [https://www.w3.org/TR/CSP2/](https://www.w3.org/TR/CSP2/).

For OpenUI5, we recommend that developers build their apps CSP-compliant, in particular regarding the loading of resources and the use of inline scripts. `eval()` is currently still required in OpenUI5 for synchronous loading. However, we recommend to load JavaScript resources asynchronously and this also avoids the use of `eval()`. For more information about asynchronous loading, see [Modules and Dependencies](Modules_and_Dependencies_91f23a7.md). For more information about avoiding synchronous APIs which might lead to synchronous loading, see [Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md).

To build CSP-compliant applications without inline scripts, you must avoid the following when developing OpenUI5 apps:

-   Script element with inlined source code

-   Inline event handler

-   `javascript`: URL

-   `document.write()`, `createElement('script')`, and so on, if they are used to create inline scripts. Creating script references, such as `<script src="..."></script>` or non-script content with them is okay.


To be prepared for a CSP policy, which does not allow `eval()`, you must also avoid the following elements when developing OpenUI5 apps:

-   `new Function()`

-   `setTimeout(<non-fn>)`

    This will be ignored silently and not create a timer without `'unsafe-eval'`, that is, `<non-fn>` is never executed. `setTimeout(<fn>)` will work with and without `'unsafe-eval'`.

-   `setInterval(<non-fn>)`

    This will be ignored silently and not create a repeated timer without `'unsafe-eval'`, that is, the `<non-fn>` is never executed. `setInterval(<fn>)` will work with and without the `'unsafe-eval'`.


To run in an environment in which CSP has been enabled, OpenUI5 requires the following directives:

-   `script-src 'self' 'unsafe-eval' <source hosting UI5>;`

    OpenUI5 itself does not require `‘unsafe-inline’`, but still requires `‘unsafe-eval’` for synchronous loading of JavaScript resources. `‘self’` is required for loading application resources. If OpenUI5 is not hosted with the application, an additional source entry \(`<source hosting UI5>`\) is required.

-   `style-src 'self' 'unsafe-inline' <source hosting UI5>;`

    OpenUI5 requires `'unsafe-inline'` as it is used by many controls. In addition, `'self'` may be needed for loading styles from the application. If OpenUI5 is hosted with the application, `'self'` is required for loading the OpenUI5 styles. Otherwise, an additional source entry \(`<source hosting UI5>`\) is required. Similarly, the location of custom themes needs to be added.

-   `font-src 'self' <source hosting UI5>;`

    `'self'` may be needed for loading fonts from the application. If OpenUI5 is hosted with the application, `'self'` is required for loading the OpenUI5 fonts, otherwise an additional source entry \(`<source hosting UI5>`\) is required. Similarly, the location of custom fonts needs to be added.

    Some specific OpenUI5 functionality may require specifying `data:` as source.

-   `img-src 'self' <source hosting UI5>;`

    `'self'` may be needed for loading images from the application. If OpenUI5 is hosted with the application, `'self'` is required for loading the OpenUI5 images, otherwise an additional source entry \(`<source hosting UI5>`\) is required. Similarly, the location of custom themes needs to be added, if they contain images.

    If the backend provides additional links to images, their location needs to be added as well.

    Some specific OpenUI5 functionality may additionally require `data:` and/or `blob:`.

-   `frame-src <source hosting UI5>;`

    For using the support assistant and/or the diagnostics tool, the location of the OpenUI5 framework \(could be `'self'`\) needs to be added as a source entry.

    Additional entries may be required depending on the integration, application, or test scenario.

    Some specific OpenUI5 functionality may additionally require `data:` and/or `blob:`.

-   `worker-src <source hosting UI5>;`

    Some specific OpenUI5 functionality may require the source hosting OpenUI5 \(could be `'self'`\), `data:` and/or `blob:`.

-   `child-src ;`

    For browsers not supporting `worker-src`, the corresponding entries need to be done here. This is the deprecated predecessor of `worker-src` and `frame-src`.

-   `connect-src 'self' <source hosting UI5>;`

    `‘self’` is required for loading application resources. If OpenUI5 is **not** hosted with the application, an additional source entry \(`<source hosting UI5>`\) is required.

    Some specific OpenUI5 functionality may require `wss:`.


To setup a most restrictive policy, setup CSP in report-only mode and start with a minimal policy. Monitor the reports to add missing sources. Finally switch CSP to enforcing the policy.

