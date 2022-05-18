<!-- loio61ee9ed2369f4764a6d713abcf73afc1 -->

| loio |
| -----|
| 61ee9ed2369f4764a6d713abcf73afc1 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/61ee9ed2369f4764a6d713abcf73afc1) | [demo kit latest release](https://sdk.openui5.org/topic/61ee9ed2369f4764a6d713abcf73afc1)</div>

## OpenUI5 Library Location Used for Testing

The location of the OpenUI5 library that is used for testing may differ depending on several parameters.

If the OpenUI5 bootstrap tag contains `src="resources/sap-ui-core.js"`, the OpenUI5 runtime libraries from the Eclipse plugin are used.

If you want to test your OpenUI5 application in Eclipse against a different OpenUI5 Library location, for example on the ABAP server when running in the SAP NetWeaver UI AddOn scenario, you can configure the ResourceServlet. For that, open the web.xml file located in the <WebContent folder name\>/WEB-INF folder and configure the parameter `com.sap.ui5.resource.REMOTE_LOCATION` and `com.sap.ui5.resource.PREFER_REMOTE_LOCATION` of the ResourceServlet where the placeholders \{protocol\}, \{host name\}, \{port number\}, \{path to UI5 library\} are to be exchanged by the real protocol, host name, port number and path to the OpenUI5 library, see [Resource Handling](Resource_Handling_Modularization_and_Localization_91f2b4d.md), section *Tunneling a Remote Location*.

```xml

  <servlet>
    <display-name>ResourceServlet</display-name>
    <servlet-name>ResourceServlet</servlet-name>
    <servlet-class>com.sap.ui5.resource.ResourceServlet</servlet-class>
 </servlet>
  ...
  <!-- force to use the remote location -->
 <context-param>
    <param-name>com.sap.ui5.resource.PREFER_REMOTE_LOCATION</param-name>
    <param-value>true</param-value>
 </context-param>
 <!-- add the remote location for the UI5 libraries -->
 <context-param>
    <param-name>com.sap.ui5.resource.REMOTE_LOCATION</param-name>
    <param-value>{protocol}://{host name}:{port number}/{path to UI5 library}</param-value>
 </context-param>
```

