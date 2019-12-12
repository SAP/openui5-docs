<!-- loio9c6400eb7dc145b78e94a81e6e390780 -->

| loio |
| -----|
| 9c6400eb7dc145b78e94a81e6e390780 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9c6400eb7dc145b78e94a81e6e390780) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9c6400eb7dc145b78e94a81e6e390780)</div>

## Make Your App Performant

In case of performance issues, follow this checklist to see if you can resolve them yourself, or at least provide a pre-analysis when requesting support.

Many performance issues are configuration-related. The configuration of OpenUI5 and/or your application may need to be adjusted to enable available performance features. Please always have a look at the OpenUI5 release notes and at [What's New in OpenUI5](What's_New_in_OpenUI5_99ac68a.md)

Follow this guide for a quick step-by-step performance check for your application:

1.  [Use the UI5 Support Assistant to check for known issues](Support_Assistant_57ccd7d.md)
2.  [Use Asynchronous Loading](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_AsyncLoading)
3.  [Make Use of Asynchronous Module Loading \(AMD Style\)](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_AsyncModuleLoading)
4.  [Use the `manifest.json` Descriptor File instead of the Bootstrap to define Dependencies](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ManifestJson)
5.  [Load OpenUI5 from the Content Delivery Network \(CDN\)](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_LoadFromCDN)
6.  [Ensure that all Resources are Available to Avoid 404 Errors](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_Resources404)
7.  [Use "manifest first" to load the Component](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ManifestFirst)
8.  [Ensure that Library Preloads are Enabled](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_LibraryPreloads)
9.  [Ensure that Application Resources are Loaded with a Component Preload](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ComponentPreload)
10. [Ensure the Routing is Configured to load Targets Asynchronously](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_RoutingConfigured)
11. [Check Network Requests](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_NetworkRequests)
12. [Migrate `jquery.sap.*` Modules to their Modularised Variants](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_MigrateJquery)
13. [Migrate Synchronous Variants of UI5 Factories to Asynchronous Variants](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_MigrateFactories)
14. [Use the OData V2 Model Preload](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ModelPreload) 
15. [Use OData V2 Metadata Caching](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_MetadataCaching)
16. [Check Lists and Tables](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ListsTables)
17. [Further Optimize your Code](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_OptimizeCode)

Blog: SAPUI5 Application Startup Performance - Troubleshooting

