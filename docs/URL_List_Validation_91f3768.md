<!-- loio91f3768f6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f3768f6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/91f3768f6f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f3768f6f4d1014b6dd926db0e91070)</div>

## URL List Validation

The OpenUI5 framework provides a client-side API to manage allowed URLs using the `URLListValidator`. It can be used to validate arbitrary URLs.

Internal examples of controls that use this feature are controls which accept arbitrary HTML content, such as `sap.ui.core.HTML`. This control uses the `URLListValidator` to perform a check \(sanitization\) on the content. URLs inside their content are then automatically removed, unless they are allowed by the `URLListValidator`. The option to sanitize the content can be enabled or disabled in the respective control via the property `HTML.sanitizeContent`. For the HTML control it is disabled by default. When adding a path to the allowed URLs in the `URLListValidator`, make sure to add “/” as path prefix if necessary, for example “/index.epx” instead of “index.epx”. The last example below shows this.

***

<a name="loio91f3768f6f4d1014b6dd926db0e91070__section_16EB929B857E45C2B245F2E97E9E5E8D"/>

### Maintaining the `URLListValidator`

The allowed URLs can be maintained with the following API:

-    `sap/base/security/URLListValidator.add` 

-   `sap/base/security/URLListValidator.clear` 

-    `sap/base/security/URLListValidator.entries` 


Here is an example how valid URLs can be allowed:

```js
// URLListValidator required from module sap/base/security/URLListValidator

URLListValidator.add(undefined, "www.sap.com");

URLListValidator.add("https", "sdn.sap.com");

URLListValidator.add(undefined, "sap.de", "1080");

URLListValidator.add("https", "community.sap.de", undefined, "/topics");
```

***

<a name="loio91f3768f6f4d1014b6dd926db0e91070__section_D3F15D5E106B41C0A037A91D5EAD13DC"/>

### Validating a URL

A URL can be validated by using the following API: `sap/base/security/URLListValidator.validate`.

Here is an example how a given URL is validated against the above-mentioned allowed URLs:

```js
// URLListValidator required from module sap/base/security/URLListValidator

URLListValidator.validate("http://www.sap.com"); // => true

URLListValidator.validate("http://sdn.sap.com"); // => false (wrong protocol)

URLListValidator.validate("https://sdn.sap.com"); // => true

URLListValidator.validate("ftp://sap.de:1080/anyftppath"); // => true

URLListValidator.validate("https://community.sap.de/anypath"); // => false (wrong path)

URLListValidator.validate("https://community.sap.de/topics"); // => true
```

If no URL was added to the allowed URLs in the `URLListValidator`, the URL validity check also basically checks the URL for being defined in a valid format.

