<!-- loio9c6400eb7dc145b78e94a81e6e390780 -->

| loio |
| -----|
| 9c6400eb7dc145b78e94a81e6e390780 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/9c6400eb7dc145b78e94a81e6e390780) | [demo kit latest release](https://sdk.openui5.org/topic/9c6400eb7dc145b78e94a81e6e390780)</div>

## Performance Checklist

Follow these steps to apply performance best practices to your application.

In addition to applying best practices, always stay up to date with the framework, for instance via the OpenUI5  [Release Notes](https://sdk.openui5.org/releasenotes.html) and the [What's New in OpenUI5](What_s_New_in_OpenUI5_99ac68a.md).

1.  [Use the UI5 Support Assistant to Check for Known Issues](Support_Assistant_57ccd7d.md)
2.   [Enable Asynchronous Loading in the Bootstrap](Use_Asynchronous_Loading_676b636.md#loio676b636446c94eada183b1218a824717__section_EALB)
3.  [Make Use of the `sap.ui.core.IAsyncContentCreation` Interface](Use_Asynchronous_Loading_676b636.md#loio676b636446c94eada183b1218a824717__section_AsyncInterface) or [Ensure the Root View and Routing are Configured to Load Targets Asynchronously](Use_Asynchronous_Loading_676b636.md#loio676b636446c94eada183b1218a824717__section_RootViewRoutingConfiguration)
4.  [Make Use of Asynchronous Module Loading \(AMD Style\)](Use_Asynchronous_Loading_676b636.md#loio676b636446c94eada183b1218a824717__section_AsyncModuleLoading)
5.  [Use `manifest.json` instead of the Bootstrap to define Dependencies](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ManifestJson)
6.  [Load OpenUI5 from the Content Delivery Network \(CDN\)](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_LoadFromCDN)
7.  [Ensure that all Resources are Properly Configured to Avoid 404 Errors](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_Resources404)
8.  [Use "manifest first" to load the Component](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ManifestFirst)
9.  [Ensure that Library Preloads are Enabled](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_LibraryPreloads)
10. [Ensure that Application Resources are Loaded as Component Preload](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ComponentPreload)
11. [Check Network Requests](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_NetworkRequests)
12. [Migrate `jquery.sap.*` Modules to their Modularised Variants](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_MigrateJquery)
13. [Migrate Synchronous Variants of UI5 Factories to Asynchronous Variants](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_MigrateFactories)
14. [Use the OData V2 Model Preload](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ModelPreload) 
15. [Use OData Metadata Caching](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_MetadataCaching)
16. [Use a `$select` Query when Binding an Aggregation](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_useSelectQuery)
17. [Limit the Loading of Data over the Network](Performance_Issues_966d67c.md#loio966d67c8cc5046419d1b35556cd9e447__section_LLAOD)
18. [Check Lists and Tables](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_ListsTables)
19. [Further Optimize your Code](Performance_Speed_Up_Your_App_408b40e.md#loio408b40efed3c416681e1bd8cdd8910d4__section_OptimizeCode)

