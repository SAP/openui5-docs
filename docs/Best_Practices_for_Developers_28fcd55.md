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

