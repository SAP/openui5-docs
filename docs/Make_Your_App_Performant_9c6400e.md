<!-- loio9c6400eb7dc145b78e94a81e6e390780 -->

| loio |
| -----|
| 9c6400eb7dc145b78e94a81e6e390780 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9c6400eb7dc145b78e94a81e6e390780) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9c6400eb7dc145b78e94a81e6e390780)</div>

## Make Your App Performant

In case of performance issues, follow this checklist to see if you can resolve them yourself, or at least provide a pre-analysis when requesting support.

Steps to check:

1.  Use the UI5 Support Assistant to check for known issues: [Support Assistant](Support_Assistant_57ccd7d.md)
2.  Use the content delivery network network \(CDN / AKAMAI\) to reduce latency effects: [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md)
3.  Make sure that library preloads are active: XXXXXXXXXXXXXXXXXXXXXXXXXXX
4.  Ensure that library preloads and modules are loaded asynchronously: [Use Asynchronous Loading](Use_Asynchronous_Loading_676b636.md)
5.  Ensure that application resources are loaded via component preload: XXXXXXXXXXXXXXXXXXXXXX
6.  Ensure that `jquery.sap.*` modules are migrated to their modularised variants: [Legacy jQuery.sap Replacement](Legacy_jQuery.sap_Replacement_a075ed8.md)
7.  Check if the synchronous variants of UI5 factories are migrated to asynchronous variants: [Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md)
8.  Ensure that model preload is enabled: [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md)
9.  Check for slow network requests: XXXXXXXXXXXXXXXX
10. Check the amount of controls and data bindings: XXXXXXXXXXXXXXXXX
11. Render pages while waiting for the response of network requests \(reduce idle times\): XXXXXXXXXXXXX
12. Ensure that OData V2 metadata caching is enabled: XXXXXXXXXXXXX
13. Cache XML Preprocessor results: XXXXXXXXXXXXXXXXXXXX

Blog: SAPUI5 Application Startup Performance - Troubleshooting

