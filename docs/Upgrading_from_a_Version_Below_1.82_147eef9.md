<!-- loio147eef96aa5f4126ac99f10e25bac75e -->

| loio |
| -----|
| 147eef96aa5f4126ac99f10e25bac75e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/147eef96aa5f4126ac99f10e25bac75e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/147eef96aa5f4126ac99f10e25bac75e)</div>

## Upgrading from a Version Below 1.82

***

### New jQuery Version Included

With OpenUI5 version 1.82, the third-party library jQuery is upgraded from Version 2.2.3 to Version 3.5.1. Several measures have been implemented to make this new framework variant of jQuery as compatible to the previously contained version as feasible. In particular, we introduce a compatibility layer to ensure that most of your existing application or control code may not need adjustment. This could, however, introduce incompatibilites to the new jQuery version. **Please read the following information carefully** to understand any current and possible future impact.

***

#### Compatibility layer

With the major version upgrade from v2 to v3, jQuery has introduced a number of incompatible changes \(see the breaking changes in the [jQuery 3.0 Core Upgrade Guide](https://jquery.com/upgrade-guide/3.0/)\).

We evaluated each of those changes and classified them to see what needed to be fixed on the layers of framework, control and application. To minimize the migration effort required by application and control developers, we have introduced an additional compatibility layer on top of jQuery \(delivered as `sap/ui/thirdparty/jquery-compat.js`\).

This compatibility layer has the following properties:

-   It can be excluded by setting the `excludejquerycompat` configuration via:
    -   URL parameter \(case-sensitive\) `sap-ui-excludeJQueryCompat=true`

    -   Data attribute \(case-insensitive\) of the OpenUI5 bootstrap `data-sap-ui-excludejquerycompat="true"`
    -   Global configuration object before OpenUI5 boots up `window["sap-ui-config"]["excludejquerycompat"]=true`
-   It restores several APIs that have been incompatibly changed in jQuery v3 back to their old behavior in jQuery v2. Details on those changes can be found in the table below.

***

#### List of jQuery changes covered by OpenUI5 compatibility layer

The following table contains some important differences between jQuery v2.2.3 and jQuery v3.5.1. The rightmost column indicates whether such an incompatible change of jQuery v3 was "rolled back" to the original jQuery v2 behavior by our compatibility layer.

> Note:
> Though we aim to make sure that the jQuery APIs used by controls and applications stay compatible even after breaking changes by jQuery, we cannot guarantee a 100% compatibility rate.
> 
> 

|API \(and what has changed\)|jQuery v2|jQuery v3|jQuery v3 + Compat. Layer = jQuery v2|
|----------------------------|---------|---------|-------------------------------------|
| **`jQuery.fn.size()`** |function exists|removed|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|
| **`jQuery.fn.offset()`** must have at least one valid DOM element, otherwise it throws an error|doesn't throw error|throws an error|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|
| **`jQuery.fn.context`** when a jQuery object is created from a node \(like in our `oControl.$()` call\), it no longer has the `context` property set| `context` property exists| `context` property has been removed|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|
| **`jQuery.fn.andSelf()`** function was removed; jQuery proposes to use`jQuery.fn.addBack()` instead.|exists|removed|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|
| **`jQuery.fn.[width|height|outerWidth|outerHeight]`** return value type changed|returns integer|returns float|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|
| **`jQuery.fn.[width|height|outerWidth|outerHeight]`** in case of an empty jQuery element, the return value was changed from `null` to `undefined` |returns `null` \(can be automatically casted to 0 when compared to a number\)|returns `undefined` \(casted to `NaN`\)|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|
| **`jQuery.event.props`** and **`jQuery.event.fixHooks`** |exists|removed|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|
| **`jQuery.Deferred.then(function A() {})`** |Function `A` is called immediately within the same call stack|Function `A` is called after the current call stack is finished|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|
| **`jQuery.Deferred.[resolve|reject|notify]`** `this` context that is set by| `this` context is set to the promise of the `Deferred` object| `this` context is undefined|![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)|

***

#### List of unpatched jQuery incompatibilities

Some incompatible changes that are introduced with jQuery 3.5.1 aren't restored to the old behavior of jQuery 2.2.3 by our compatibility layer.This is because we consider them reasonable improvements, for which we don't see any negative impact from our evaluation with existing applications.

|API|jQuery v2|jQuery v3|
|---|---------|---------|
| **`jQuery.fn.[width|height]`** doesn't include the scrollbar width if there is one|includes the width or height of the scrollbar, if there is one|doesn't include the scrollbar width if there is one Use `jQuery.fn.[outerWidth|outerHeight]` instead. Also works in jQuery v2.|
| **`jQuery.animation`** |uses `setInterval()` |uses `requestAnimationFrame()`|
| **`jQuery.ajax`** for multiple response header values that have the same header name|only returns the first header value|merges multiple header values into a string, separated by ", "|
| **`jQuery(function A() {})`** callback is delayed even if the DOM ready event already occurred|function `A` is called immediately within the current call stack|function `A` is called after the current call stack has finished|
| **`jQuery.swap()`** |exists|*removed, because it's an undocumented internal method!*|
| **`jQuery.data`** in case the key contains a dash "-"|see [https://jquery.com/upgrade-guide/3.0/\#data](https://jquery.com/upgrade-guide/3.0/#data) |see [https://jquery.com/upgrade-guide/3.0/\#data](https://jquery.com/upgrade-guide/3.0/#data) |
| **`jQuery.fn.selector`** unreliable pseudo-selector has been removed|concatenates the selector property after further tree traversal calls, for example `jQuery.fn.filter` \(see [https://api.jquery.com/category/traversing/tree-traversal/](https://api.jquery.com/category/traversing/tree-traversal/)\)|according to jQuery documentation, it was never reliable and thus removed with 3.0: [https://api.jquery.com/selector/](https://api.jquery.com/selector/)|
| **`jQuery.easing.*`** see [https://jquery.com/upgrade-guide/3.0/\#deprecated-additional-easing-function-parameters](https://jquery.com/upgrade-guide/3.0/#deprecated-additional-easing-function-parameters) |function accepts multiple arguments|function accepts only one argument|

***

#### Known jQuery issues

At the time of writing, the following jQuery issues have been identified. They have been fixed in the jQuery variant `sap/ui/thirdparty/jquery.js`, shipped with OpenUI5 release 1.82 and later:

-   [jQuery Issue \#4382](https://github.com/jquery/jquery/issues/4382):

    Introduced with jQuery 3.4.0, this causes several tests to fail.

    The bug isn't fixed in the jQuery 3.x code line, but only in the master for an upcoming jQuery 4.x release \(see [this commit](https://github.com/jquery/jquery/commit/8a741376937dfacf9f82b2b88f93b239fe267435)\).

    At the time of writing, it's not clear whether and when the fix will be downported to the jQuery 3.x code line.

-   [jQuery Issue \#4417](https://github.com/jquery/jquery/issues/4417):

    At the time of writing, the bug is still open in jQuery's Github repository. Once the bug has been fixed, the in-place patch in our framework's jQuery variant will be deleted.

-   [jQuery Issue \#4431](https://github.com/jquery/jquery/issues/4431):

    jQuery wrongly calculates the offsetParent. The `offsetParent` property of `HTMLElement` returns a`<td>`, `<th>`, `<table>` ancestor even when the ancestor element has a `static` CSS position.

    The original implementation of `jQuery.fn.offsetParent` can handle this case correctly.


***

#### Remove the deprecated jQuery API from your code

You can activate an additional support rule with the [UI5 Support Assistant](Support_Assistant_57ccd7d.md). The rule `"Usage of deprecated jQuery API"` will show you warnings for all instances of deprecated jQuery v3 API usage.

Though these APIs are "only" deprecated and could still be used, the jQuery project will remove them with their next version jQuery 4.x.

> Note:
> To stay future-proof, we strongly recommend that you remove/refactor all your application and control code so as not to use any deprecated jQuery API anymore.
> 
> 

