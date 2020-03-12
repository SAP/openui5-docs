<!-- loio91f3768f6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f3768f6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f3768f6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f3768f6f4d1014b6dd926db0e91070)</div>

## URL Whitelist Filtering

The OpenUI5 framework provides a client-side API to manage a whitelist for URLs. This whitelist can be used to validate arbitrary URLs.

Internal examples of controls that use this feature are controls which accept arbitrary HTML content, such as `sap.ui.core.HTML`. This control uses the URL whitelist to perform a check \(sanitization\) on the content. URLs inside their content are then automatically removed, unless they are listed on the URL whitelist. The option to sanitize the content can be enabled or disabled in the respective control via the property `HTML.sanitizeContent`. For the HTML control it is disabled by default. When adding a path to the whitelist, make sure to add "/" as path prefix if necessary, for example "/index.epx" instead of "index.epx". The last example below shows this.

***

<a name="loio91f3768f6f4d1014b6dd926db0e91070__section_16EB929B857E45C2B245F2E97E9E5E8D"/>

### Maintaining the URL Whitelist

The whitelist can be maintained with the following API:

-    `sap/base/security/URLWhitelist.add` 

-   `sap/base/security/URLWhitelist.clear` 

-   `sap/base/security/URLWhitelist.delete` 

-    `sap/base/security/URLWhitelist.entries` 


Here is an example how valid URLs can be added to the whitelist:

``` js
// `URLWhitelist` required from module `sap/base/security/URLWhitelist`

URLWhitelist.add(undefined, "www.sap.com");

URLWhitelist.add("https", "sdn.sap.com");

URLWhitelist.add(undefined, "sap.de", "1080");

URLWhitelist.add("https", "community.sap.de", undefined, "/topics");
```

***

<a name="loio91f3768f6f4d1014b6dd926db0e91070__section_D3F15D5E106B41C0A037A91D5EAD13DC"/>

### Validating a URL

A URL can be validated by using the following API: `sap/base/security/URLWhitelist.validate`.

Here is an example how a given URL is validated against the above-mentioned whitelist:

``` js
// `URLWhitelist` required from module `sap/base/security/URLWhitelist`

URLWhitelist.validate("http://www.sap.com"); // => true

URLWhitelist.validate("http://sdn.sap.com"); // => false (wrong protocol)

URLWhitelist.validate("https://sdn.sap.com"); // => true

URLWhitelist.validate("ftp://sap.de:1080/anyftppath"); // => true

URLWhitelist.validate("https://community.sap.de/anypath"); // => false (wrong path)

URLWhitelist.validate("https://community.sap.de/topics"); // => true
```

If no whitelist is maintained, the URL validity check also basically checks the URL for being defined in a valid format.

