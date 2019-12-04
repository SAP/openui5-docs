<!-- loio9c6400eb7dc145b78e94a81e6e390780 -->

| loio |
| -----|
| 9c6400eb7dc145b78e94a81e6e390780 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9c6400eb7dc145b78e94a81e6e390780) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9c6400eb7dc145b78e94a81e6e390780)</div>

## Make Your App Performant

In case of performance issues, follow this checklist to see if you can resolve them yourself, or at least provide a pre-analysis when requesting support.

Many performance issues are configuration-related. The configuration of %UI5-PROFILED% and/or your application may need to be adjusted to enable available performance features. Please always have a look at the %UI5-PROFILED% release notes and at [What's New in OpenUI5](What's_New_in_OpenUI5_99ac68a.md)

Follow this guide for a quick step-by-step performance check for your application:

1.  Use the UI5 Support Assistant to check for known issues: [Support Assistant](Support_Assistant_57ccd7d.md)
2.  Ensure that library preloads and modules are loaded asynchronously: [Use Asynchronous Loading](Use_Asynchronous_Loading_676b636.md)
3.  Load %UI5-PROFILED% from the content delivery network network \(CDN\): [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md)
4.  Make sure that library preloads are active: XXXXXXXXXXXXXXXXXXXXXXXXXXX
5.  Ensure that application resources are loaded via component preload: XXXXXXXXXXXXXXXXXXXXXX
6.  Check for slow network requests: XXXXXXXXXXXXXXXX
7.  Ensure that `jquery.sap.*` modules are migrated to their modularised variants: [Legacy jQuery.sap Replacement](Legacy_jQuery.sap_Replacement_a075ed8.md)
8.  Check if the synchronous variants of UI5 factories are migrated to asynchronous variants: [Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md)
9.  Ensure that model preload is enabled: [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md)
10. Ensure that OData V2 metadata caching is enabled: XXXXXXXXXXXXX
11. Check the amount of controls and data bindings: XXXXXXXXXXXXXXXXX
12. Render pages while waiting for the response of network requests \(reduce idle times\): XXXXXXXXXXXXX
13. Cache XML Preprocessor results: XXXXXXXXXXXXXXXXXXXX

Blog: SAPUI5 Application Startup Performance - Troubleshooting

