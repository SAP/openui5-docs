<!-- loio28fcd55b04654977b63dacbee0552712 -->

| loio |
| -----|
| 28fcd55b04654977b63dacbee0552712 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/28fcd55b04654977b63dacbee0552712) | [demo kit latest release](https://sdk.openui5.org/topic/28fcd55b04654977b63dacbee0552712)</div>

## Best Practices for Developers

This page aims to be a good starting point for you to ensure your code bases, i.e. your OpenUI5 applications and libraries, do not become legacy but are ready for the future.

***

<a name="loio28fcd55b04654977b63dacbee0552712__section_kg5_3nj_rzb"/>

### Alignment for Future-Proof Code

The OpenUI5 framework keeps evolving, for instance to benefit from newer features in web browsers \(such as ECMAScript support\) or to account for their end of maintenance \(such as the end of IE11 support\). There are many substantial steps of an ongoing journey towards future major framework versions and continuous improvements.

Therefore, it is crucial that you continue to apply best practices. To support your activities, the documentation is frequently being updated in many places. This page is to collect fundamental information and to offer practical guidance, and it will evolve over time.

***

<a name="loio28fcd55b04654977b63dacbee0552712__section_z2p_zqm_21c"/>

### Best Practices for Legacy-Free Code

> ### Note:  
> The following information is a preliminary yet practical collection of best practices to ensure legacy-free OpenUI5 development. It is being improved continuously to reflect our latest recommendations. It will be further enhanced to both help transform existing code bases and provide guidance for creating new code.

***

#### Goals

The main objectives when migrating existing code or keeping it up to date with framework best practices are:

-   **No sync loading of code**

    for compliance with our Content Security Policy; for more information, see [Make Your App CSP Compliant](Make_Your_App_CSP_Compliant_1f81a09.md)

-   **No sync loading of data**

    to avoid deprecation warnings of web browsers regarding sync XHR

-   **No use of global names**

    to avoid pollution of the global namespace and conflicts with other code on the page

-   **No use legacy APIs**

    to reduce the API surface for easier usage and maintenance


***

#### Prerequisites

Before attempting to migrate or upgrade to a higher OpenUI5 version, make sure that your development does **not** use any undocumented internal framework resources, and double check that all compatibility guidelines have been followed, such as those mentioned in [Upgrading](Upgrading_9638e4f.md).

***

#### Deprecated APIs

In general, **you must not use deprecated APIs** anymore. Deprecated APIs can be found in the [API Reference](https://sdk.openui5.org/api/deprecated), in the [What's New Viewer](https://help.sap.com/whats-new/67f60363b57f4ac0b23efd17fa192d60?Type=Deleted%3BDeprecated), and in the reports by our [Support Assistant](Support_Assistant_57ccd7d.md).

Also, see any relevant warnings and errors logged to the browser's dev console during runtime. You might need to increase the `sap-ui-log-level`; for more information, see [Logging and Tracing](Logging_and_Tracing_9f4d62c.md).

Some APIs may only be partially deprecated, for instance:

-   [`sap/ui/core/theming/Parameters.get`](https://sdk.openui5.org/api/sap.ui.core.theming.Parameters%23methods/sap.ui.core.theming.Parameters.get) : Passing a non-object `vName` \(deprecated sinceOpenUI5 version 1.92 and 1.94\).

-   [`sap/ui/model/json/JSONModel#loadData`](https://sdk.openui5.org/api/sap.ui.model.json.JSONModel%23methods/loadData) : Using the `bAsync` and `bCache` flags \(deprecated sinceOpenUI5 version 1.107\).

-   [`sap/ui/model/odata/v2/ODataModel#createEntry`](https://sdk.openui5.org/api/sap.ui.model.odata.v2.ODataModel%23methods/createEntry) : Passing an array to `mProperties.properties` \(deprecated sinceOpenUI5 version 1.120\).


**Additional Information:**

-   [Don't Use Deprecated or Experimental Features](Don_t_Use_Deprecated_or_Experimental_Features_a8bd1a8.md)
-   [Use Only Public APIs](Use_Only_Public_APIs_b0d5fe2.md)
-   [Adapting to the Modularization of the Core](Adapting_to_the_Modularization_of_the_Core_b8fdf0c.md)
-   [Legacy jQuery.sap Replacement](Legacy_jQuery_sap_Replacement_a075ed8.md)
-   [Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md)

***

<a name="loio28fcd55b04654977b63dacbee0552712__section_tqd_z1n_21c"/>

### App Development

In the following we'll focus on crucial aspects of app development, specifically on asynchronous loading and best practices around Components, Controllers, Views, Fragments, and Models.

***

#### Asynchronous Loading

-   Use asynchronous loading for views, fragments, and components to enhance performance.
-   Implement the `sap.ui.core.IAsyncContentCreation` interface on component level to enable async component creation.
-   Load libraries via the new asynchronous APIs in advance before accessing code. Ensure that dependent librares are preloaded through the `manifest.json` in the `sap.ui5/dependencies/libs` section if not already maintained there.

**Additional Information:**

-   [Use Asynchronous Loading](Use_Asynchronous_Loading_676b636.md)
-   [Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md)
-   [Performance Checklist](Performance_Checklist_9c6400e.md)
-   [Load Only What You Really Need](Load_Only_What_You_Really_Need_e8fca3e.md)
-   [Performance: Speed Up Your App](Performance_Speed_Up_Your_App_408b40e.md)

***

#### OpenUI5 Object Creation

***

<a name="loio28fcd55b04654977b63dacbee0552712__section_gzy_knj_rzb"/>

### Some Important Best Practices

The following are some of the most relevant best practices you should get familiar with and apply for a future-proof code base:

[Don't Use Deprecated or Experimental Features](Don_t_Use_Deprecated_or_Experimental_Features_a8bd1a8.md)

[Use Only Public APIs](Use_Only_Public_APIs_b0d5fe2.md)

[Use the MVC Concept](Use_the_MVC_Concept_07afcf4.md)

[Keep Your Views Short and Simple](Keep_Your_Views_Short_and_Simple_b0d7db7.md)

[Use Stable IDs](Use_Stable_IDs_79e910e.md)

[Performance Checklist](Performance_Checklist_9c6400e.md)

[Make Your App CSP Compliant](Make_Your_App_CSP_Compliant_1f81a09.md)

[Use Asynchronous Loading](Use_Asynchronous_Loading_676b636.md)

[Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md)

[Load Only What You Really Need](Load_Only_What_You_Really_Need_e8fca3e.md)

[Best Practices for Loading Modules](Best_Practices_for_Loading_Modules_00737d6.md)

[Adapting to the Modularization of the Core](Adapting_to_the_Modularization_of_the_Core_b8fdf0c.md)

[Legacy jQuery.sap Replacement](Legacy_jQuery_sap_Replacement_a075ed8.md)

[Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md)

-   **[Don't Use Deprecated or Experimental Features](Don_t_Use_Deprecated_or_Experimental_Features_a8bd1a8.md "To keep your apps future proof and up to date with the latest improvements, you should
		only use artifacts (such as features, APIs, themes, etc.) that are still actively
		developed.")**  
To keep your apps future proof and up to date with the latest improvements, you should only use artifacts \(such as features, APIs, themes, etc.\) that are still actively developed.
-   **[Load Only What You Really Need](Load_Only_What_You_Really_Need_e8fca3e.md "The amount of resources and data that your app loads will directly affect the performance of your app. You should declare all dependencies
		and remove unused libraries and classes from your code.")**  
The amount of resources and data that your app loads will directly affect the performance of your app. You should declare all dependencies and remove unused libraries and classes from your code.
-   **[Use the MVC Concept](Use_the_MVC_Concept_07afcf4.md "MVC (Model-View-Controller) is a concept for structuring your software. It makes it easier to maintain and to extend your
		apps.")**  
MVC \(Model-View-Controller\) is a concept for structuring your software. It makes it easier to maintain and to extend your apps.
-   **[Keep Your Views Short and Simple](Keep_Your_Views_Short_and_Simple_b0d7db7.md "The view part of your app reflects what users can see and interact with. You should use a suitable set of UI controls that match your
		scenario and keep things simple.")**  
The view part of your app reflects what users can see and interact with. You should use a suitable set of UI controls that match your scenario and keep things simple.
-   **[Use Stable IDs](Use_Stable_IDs_79e910e.md "If you keep the IDs of controls, elements, and components stable, you can be sure that other OpenUI5 features will be able to identify them correctly during
		processing.")**  
If you keep the IDs of controls, elements, and components stable, you can be sure that other OpenUI5 features will be able to identify them correctly during processing.
-   **[Make Your App CSP Compliant](Make_Your_App_CSP_Compliant_1f81a09.md "CSP stands for Content Security Policy and is a security standard to prevent cross-site scripting or other code injection
		attacks.")**  
CSP stands for Content Security Policy and is a security standard to prevent cross-site scripting or other code injection attacks.
-   **[Use Asynchronous Loading](Use_Asynchronous_Loading_676b636.md "Asynchronous loading is the way to go: It makes your applications a lot faster and, through that, better to use.")**  
Asynchronous loading is the way to go: It makes your applications a lot faster and, through that, better to use.
-   **[Use Only Public APIs](Use_Only_Public_APIs_b0d5fe2.md "OpenUI5 APIs are classified into different types. Only APIs of type
			public should be used by application developers.")**  
OpenUI5 APIs are classified into different types. Only APIs of type `public` should be used by application developers.
-   **[Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md "Find a collection of information that helps you to find out if your application is ready
		for asynchronous loading.")**  
Find a collection of information that helps you to find out if your application is ready for asynchronous loading.
-   **[Performance Checklist](Performance_Checklist_9c6400e.md "Follow these steps to apply performance best practices to your application.")**  
Follow these steps to apply performance best practices to your application.

