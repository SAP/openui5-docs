<!-- loiod1b26a248c0a47f6a96849236250dc90 -->

| loio |
| -----|
| d1b26a248c0a47f6a96849236250dc90 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d1b26a248c0a47f6a96849236250dc90) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d1b26a248c0a47f6a96849236250dc90)</div>

## Checking the Operating System your Application is Running on

A platform attribute is added to the HTML tag when running on mobile devices.

This attribute provides information about the current platform and version.

> Note:
> The list of supported devices when using `sap.m` library can be found here: [Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md)
> 
> 

In addition to that, OpenUI5 adds a platform-dependent CSS class to the HTML tag of the page. This enables control or application developers to create platform-dependent styling for their controls or applications.

***

### Technical Details

When the OpenUI5 bootstrap script file is loaded, a check is performed to see if the application is running on a mobile platform. If this is the case, the attribute and CSS classes are added to the HTML tag. The platform attribute value has the following connotation: *Operating system + version*, for example `iOS6.0`, `Android4.1.1` or `bb10.0.9.2372`. *Operating system* can have the following values:

-   `iOS`\(Apple devices\)
-   `Android` \(Android devices\)
-   `bb` \(BlackBerry\)
-   `winphone` \(Windows phone\)

The version numbers are separated by dots. The possible values for the CSS class are:

-   `sap-ios` \(Apple devices\)
-   `sap-android`\(Android devices\)
-   `sap-bb` \(BlackBerry\)
-   `winphone` \(Windows phone\)

The platform attribute or CSS class is used as follows:

-   To provide a different font on Android devices, you specify your font by directly using the CSS class `sap-android`.

    ```
    
    .sap-android{
    	     font-family: Roboto;
    }
    ```

-   Example for providing a different font when running on `Android 2.x`:

    ```
    
    html[data-sap-ui-os^='Android2'] .sap-android{
    	font-family: "Droid Sans";
    }
    ```


