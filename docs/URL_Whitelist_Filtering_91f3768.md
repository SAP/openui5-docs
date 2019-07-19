<!-- loio91f3768f6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f3768f6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f3768f6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f3768f6f4d1014b6dd926db0e91070)</div>

## URL Whitelist Filtering

The OpenUI5 framework provides a client-side API to manage a white list for URLs. This whitelist can be used to validate arbitrary URLs if they are permitted or not.

Internal examples of how controls can use this feature are those controls which accept arbitrary HTML content like `sap.ui.core.HTML`. This control uses the URL white list when a check \(sanitization\) is performed on the content. URLs inside their content are then automatically removed, except if they are listed in the URL whitelist. The option to sanitize the value can be enabled or disabled in the respective control properly via the `HTML.sanitizeContent` property. For the HTML control it is disabled by default. When adding a path to the white list be aware to add a "/" at the start of the path if necessary, so "/index.epx" would be the correct entry instead of "index.epx". The last example below shows this.

***

<a name="loio91f3768f6f4d1014b6dd926db0e91070__section_16EB929B857E45C2B245F2E97E9E5E8D"/>

### Maintaining the URL Whitelist

The whitelist can be maintained with the following API:

-    `jQuery.sap.addUrlWhitelist` 

-   `jQuery.sap.clearUrlWhitelist` 

-   `jQuery.sap.getUrlWhitelist` 

-    `jQuery.sap.removeUrlWhitelist` 


Here is an example how valid URLs can be added to the white list:

``` js
// jQuery.sap.addUrlWhitelist(/* protocol */ undefined, /* host */ undefined, /* port */ undefined, /* path */ undefined);


jQuery.sap.addUrlWhitelist(undefined, "www.sap.com");

jQuery.sap.addUrlWhitelist("https", "sdn.sap.com");

jQuery.sap.addUrlWhitelist(undefined, "sap.de", "1080");
```

***

<a name="loio91f3768f6f4d1014b6dd926db0e91070__section_D3F15D5E106B41C0A037A91D5EAD13DC"/>

### Validating a URL

A URL can be validated by using the following API: `jQuerysapvalidateUrl`.

Here is an example how a given URL is validated against the before maintained white list:

``` js
jQuery.sap.validateUrl("http://www.sap.com"); // => true

jQuery.sap.validateUrl("http://sdn.sap.com"); // => false (wrong protocol)

jQuery.sap.validateUrl("https://sdn.sap.com"); // => true

jQuery.sap.validateUrl("ftp://sap.de:1080/anyftpfolder"); // => true
```

If no whitelist is maintained the URL validity check also basically checks the URL for being defined in a valid format.

