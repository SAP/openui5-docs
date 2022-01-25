<!-- loio91f1dd0c6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f1dd0c6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f1dd0c6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f1dd0c6f4d1014b6dd926db0e91070)</div>

## noJQuery Variant for Bootstrapping

The noJQuery variant supports bootstrapping for an application that already integrates jQuery or uses a different jQuery version than OpenUI5.

In this variant, you include the `resources/sap-ui-core-noJQuery.js` file in your HTML page. Make sure that jQuery and `jquery-ui-position` have been loaded beforehand. The following code snippet shows an example:

``` html

    <!-- include some jQuery version -->
    <script src="my-jQuery-min.js" ></script>

    <!-- application does not have its own jquery-ui-position, so it might use the one from SAPUI5 -->
    <script src="resources/sap/ui/thirdparty/jqueryui/jquery-ui-position.js" ></script>

    <!-- now booting SAPUI5 -->
    <script 
            id="sap-ui-bootstrap"            
            src="resources/sap-ui-core-nojQuery.js" 
            data-sap-ui-libs="sap.m"
            data-sap-ui-theme="sap_belize" >
    </script> 
```

