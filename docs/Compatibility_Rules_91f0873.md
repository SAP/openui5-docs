<!-- loio91f087396f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f087396f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f087396f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f087396f4d1014b6dd926db0e91070)</div>

## Compatibility Rules

The following sections describe what SAP can change in major, minor, and patch releases. Always consider these rules when developing apps, features, or controls with or for OpenUI5.

> ### Caution:  
> As an app developer, **never** do the following:
> 
> -   Never manipulate HTML/CSS via JavaScript \(`domRef.className = "someCSSClass";`\) or directly via CSS, for example. Always follow our recommendations under [CSS Styling Issues](CSS_Styling_Issues_9d87f92.md).
> 
> -   Never use or override "private" functions that are not part of the [API Reference](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.html). Private functions are typically \(but not always\) prefixed with a preceding "\_". Always double-check the API Reference, private functions are not listed there.

***

<a name="loio91f087396f4d1014b6dd926db0e91070__section_4BED038D0A7E4237BE7AD473862AA281"/>

### API Evolution

Unless otherwise mentioned, the word "API" in this section refers to "public API", meaning functions, classes, namespaces, controls along with their declared properties, aggregations, and so on. The sole definition of the public API is the  [API Reference](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.html), which is included in the OpenUI5 Demo Kit. Features that are **not** mentioned there are **not** part of the API.

The following rules apply for introducing new APIs or making incompatible changes to existing APIs:

**Major release** \(**x**.yy.zz\): A new major version can introduce new APIs or make incompatible changes to existing APIs.

**Minor release** \(x.**yy**.zz\): A new minor version can introduce new APIs but must not contain incompatible changes to **any** APIs.

**Patch release** \(x.yy.**zz**\): A new patch version only contains fixes to the existing implementation, but does not usually contain new features or incompatible API changes.

> ### Note:  
> Exceptions to these rules are possible, but only in very urgent cases such as security issues. Such exceptions are documented in the [Change Log](https://openui5.hana.ondemand.com/#releasenotes.html).

***

<a name="loio91f087396f4d1014b6dd926db0e91070__section_N10074_N10013_N10001"/>

### Compatible Changes

The following changes to existing APIs are compatible and can be done anytime:

-   Adding new libraries, controls, classes, properties, functions, or namespaces

-   Generalizing properties, that is moving properties up in the inheritance hierarchy

-   Adding new values to enumeration types; this means that when dealing with `enum` properties, always be prepared to accept new values, for example, by implementing a `"default"` or `"otherwise"` path when reacting on `enum` values.


***

<a name="loio91f087396f4d1014b6dd926db0e91070__section_N1009A_N10013_N10001"/>

### Incompatible Changes

The following is not part of the public API and may **change in patch and minor releases**:

-   Open source libraries \(see [Third-Party Open Source Libraries](Compatibility_Rules_91f0873.md#loio91f087396f4d1014b6dd926db0e91070__Open_Source)\)

-   Log messages


The following changes to existing APIs are incompatible, but **can be done in a new major release**:

-   Renaming an API \(library, namespace, function, property, control, events, and so on\)

-   Removing support for parameters

-   Removing support for configuration entries

-   Reducing the visibility of an API; this does not break JavaScript applications, but changes the contract

-   Removing or reordering parameters in an API signature

-   Reducing the accepted value range, for example, parameter of a function

-   Broadening the value range of a return value \(or property\). Exception: enumerations

-   Moving JavaScript artifacts \(namespaces, functions, classes\) between modules

-   Replacing asserts with precondition checks

-   Moving properties \(and so on\) down in the inheritance hierarchy

-   Changing the name of `enum` values

-   Changing defaults \(properties, function parameters\)

-   Renaming or removing files


***

### Inheritance

Inheriting from OpenUI5 objects \(e.g. by calling `sap.ui.extend` on an existing control to add custom functionality\) may endanger the updatability of your code.

When overriding an OpenUI5 lifecycle method \(such as `init`, `exit`, `onBeforeRendering`, and `onAfterRendering`\), you must make sure that the super class implementation is called, for example like this:

```
MyClass.prototype.onAfterRendering = function() {
  SuperClass.prototype.onAfterRendering.apply(this);

  // do your additional stuff AFTER calling super class
}
```

SAP might add, remove, or change the internal implementation of the parent class at any time. Especially, you should not rely on the following functionality:

-   Internal structures and methods that are not part of the public API

-   Any internal logic and behavior of the object that is not reflected in the public API

-   The parent hierarchy of objects especially for composites where the API parent differs from the real parent \(e.g. parent object \> internal object \> child object\). For more information, see [API Reference: `sap.ui.base.ManagedObject`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.base.ManagedObject.html). 

-   All rendering functionality of a control, including the HTML structure and CSS classes

-   Naming collisions with OpenUI5 structures and methods. OpenUI5 might introduce new API or internal structures at a later point in time that collide with your implementation. To avoid collisions, a custom prefix may be applied. Don't use namespaces starting with `sap.m.*` or `sap.ui.*` in your app.


We recommend that you test inherited classes very carefully after updating OpenUI5 to make sure that the extended functionality is still working as expected.

***

### Deprecation

If possible and appropriate, we mark old artifacts as deprecated and create new artifacts, instead of making incompatible changes. A deprecation comment in the corresponding API documentation, and perhaps also a log entry in the implementation, explain why and when an artifact has been deprecated and include tips on how to achieve the same results without using deprecated functionality.

***

<a name="loio91f087396f4d1014b6dd926db0e91070__experimental"/>

### Experimental API

Some features or controls delivered with the current OpenUI5 version are flagged as "experimental". These experimental features and controls are not part of the released scope of the delivered OpenUI5 version. Do not use experimental features or controls in a productive environment, or with data that has not been sufficiently backed up.

Experimental features and controls can be changed or deleted at any time without notice, and without a formal deprecation process. They may also be incompatible to changes provided in an upgrade.

***

<a name="loio91f087396f4d1014b6dd926db0e91070__Open_Source"/>

### Third-Party Open Source Libraries

OpenUI5 contains and uses several third-party open source libraries, such as `jQuery`. These libraries can also be used by applications and/or custom control libraries, but the OpenUI5 compatibility rules described in this document do not apply to these third-party libraries.

If you want to use the third-party open source libraries included in OpenUI5, note the following restrictions:

-   SAP decides which versions and modules of the used libraries are provided.

-   SAP can upgrade to a higher version of the used libraries even within a patch release.

-   For important reasons such as security, OpenUI5 can stop providing a library at any time.

-   The third-party libraries are provided "as is". Extensions, adaptations, and support are not performed or provided by SAP.


> ### Note:  
> Do not use different versions of these libraries as this might lead to unforeseen side effects..

For a list of the third-party open source software used in OpenUI5, choose *More Information* → *About* and select the *Included Third-Party Software* link.

**Related Information**  


[Versioning and Maintenance of OpenUI5](Versioning_and_Maintenance_of_OpenUI5_91f0214.md "Versioning and maintenance strategy for OpenUI5.")

[API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui)

