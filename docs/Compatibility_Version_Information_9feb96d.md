<!-- loio9feb96da02c2429bb1afcf6534d77c79 -->

| loio |
| -----|
| 9feb96da02c2429bb1afcf6534d77c79 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9feb96da02c2429bb1afcf6534d77c79) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9feb96da02c2429bb1afcf6534d77c79)</div>

## Compatibility Version Information

Compatibility version flags allow applications to react to incompatible changes in OpenUI5.

> Note:
> The concept of compatibility versions has been abandoned as of version 1.28. Therefore, there will be no new compatibility version flags in the future. If you start building a new application please set `data-sap-ui-compatVersion="edge"` on your OpenUI5 bootstrap tag.
> 
> 

As described in the compatibility rules, changes to OpenUI5 features are compatible, see [Compatibility Rules](Compatibility_Rules_91f0873.md). In some cases, however, it may make sense to change the behavior of a feature, for example, to change the default values or to use an optimized implementation and these changes may lead to incompatibilities.

> Note:
> We recommend to adapt to new feature versions as soon as possible.
> 
> 

The compatibility version configuration works as follows:

-   A version flag is introduced if a feature change is incompatible.
-   The version flag has to be defined in the OpenUI5 bootstrap tag either globally \(`data-sap-ui-compatVersion` or individually for each feature \(for example `data-sap-ui-compatVersion-xyz`\). Example with `compatVersion "1.18"`

    ``` html
    <script id="sap-ui-bootstrap" 
            type="text/javascript"
            src="resources/sap-ui-core.js"
            data-sap-ui-theme="sap_belize"
            data-sap-ui-libs="sap.m"
            data-sap-ui-compatVersion="1.18"
            data-sap-ui-compatVersion-xyz="1.16"
            >
    </script> 
    ```

-   If no version is defined, the default behavior of the feature applies.
-   If an explicit version is specified, the behavior of the specified version is applied.
-   If a version edge is specified, the newest behavior of the feature is applied.
-   A fallback mechanism is implemented. The following table is an example of possible configuration options for feature "xyz":

    |data-sap-ui-compatVersion|data-sap-ui-compatVersion-xyz|Default feature xyz|Resulting compatibility version|
    |-------------------------|-----------------------------|-------------------|-------------------------------|
    |--|--|1.14|1.14|
    |1.16|--|1.14|1.16|
    |--|1.16|1.14|1.16|
    |1.18|1.16|1.14|1.16|
    |edge|..|1.14|1.18|


OpenUI5 supports the following compatibility version flags:

|Flag|Description|
|----|-----------|
|`data-sap-ui-compatVersion-flexBoxPolyfill`|The `flexBoxPolyfill` for Internet Explorer 9 was deprecated in 1.16 due to functional deficiencies. When the compatibility version is 1.16 or higher, the polyfill is not active at all. Otherwise, the buggy implementation behaves as before, so that it still works in existing applications. Default value: 1.14|
|`data-sap-ui-compatVersion-sapMeTabContainer`|The `TabContainer` was deprecated in 1.15. When the compatibility version is 1.16 or higher, an error is logged to the console indicating that `sap.m.IconTabBar` should be used instead. Default value: 1.14|
|`data-sap-ui-compatVersion-sapMeProgessIndicator`|--|
|`data-sap-ui-compatVersion-sapMGrowingList`|--|
|`data-sap-ui-compatVersion-sapMListAsTable`|--|
|`data-sap-ui-compatVersion-sapMDialogWithPadding`|By default, the content area of `Dialog` had paddings. To make the padding consistent with other popups, the padding is removed for compatibility versions 1.16 or higher. If the padding is still needed inside the content area of `Dialog`, add the CSS style class `sapUiPopupWithPadding` to `Dialog` by calling the `addStyleClass` function. Default value: 1.14|
|`data-sap-ui-bindingSyntax`|This configuration parameter defines whether the simple or the complex binding syntax is used. The parameter only affects bindings that are defined as strings, for example in the constructor of a control, or when specifying a binding in a declarative view, such as XML view or HTML view. For versions lower than 1.28, the default value is `default` which only has very limited features. As of version 1.28, the default is `complex`.|

**Related information**  


[Compatibility Rules](Compatibility_Rules_91f0873.md)

