<!-- loio147eef96aa5f4126ac99f10e25bac75e -->

| loio |
| -----|
| 147eef96aa5f4126ac99f10e25bac75e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/147eef96aa5f4126ac99f10e25bac75e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/147eef96aa5f4126ac99f10e25bac75e)</div>

## Upgrading from a Version Below 1.82

***

### New jQuery Version Included

With OpenUI5 1.82, the third-party library jQuery is upgraded from jQuery 2.2.3 to jQuery 3.5.1. Several measures have been implemented to make this new framework variant of jQuery as compatible to the previously contained version as feasible. In particular, we introduce a compatibility layer to ensure that most of your existing application or control code may not need adjustment. This could, however, introduce incompatibilites to the new jQuery version. **Please read the following information carefully** to understand any current and possible future impact.

***

#### Compatibility layer

With the major version upgrade from jQuery 2.x to jQuery 3.x, a number of incompatible changes have been introduced \(see the breaking changes in the [jQuery 3.0 Core Upgrade Guide](https://jquery.com/upgrade-guide/3.0/)\).

We evaluated each of those changes and classified them to see what needed to be fixed on the layers of framework, control and application. To minimize the migration effort required by application and control developers, we have introduced an additional compatibility layer on top of jQuery \(delivered as `sap/ui/thirdparty/jquery-compat.js`\).

-   It can be excluded by setting the `excludeJQueryCompat` configuration via:
    -   URL parameter \(case-sensitive\): `sap-ui-excludeJQueryCompat=true`

    -   Data attribute of the OpenUI5 bootstrap \(case-insensitive\): `data-sap-ui-excludejquerycompat="true"`
    -   Global configuration object before OpenUI5 boots up \(case-sensitive\): `window["sap-ui-config"]["excludejQueryCompat"]=true`
-   It restores several APIs that have been incompatibly changed in jQuery 3.x back to their old behavior in jQuery 2.x. Details on those changes can be found in the table below.

***

#### List of jQuery changes covered by OpenUI5 compatibility layer

The following table contains some important differences between jQuery 2.2.3 and jQuery 3.5.1. The rightmost column indicates whether such an incompatible change of jQuery 3.x was "rolled back" to the original jQuery 2.x behavior by our compatibility layer.

> ### Note:  
> Though we aim to make sure that the jQuery APIs used by controls and applications stay compatible even after breaking changes by jQuery, we cannot guarantee a 100% compatibility rate.

|API \(and what has changed\)

|jQuery 2.x

|jQuery 3.x

|jQuery 3.x + Compat. Layer = jQuery 2.x

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>------------------------------</th>
			<th>------------</th>
			<th>------------</th>
			<th>-----------------------------------------</th>
		</tr>
	</thead>
	<tbody>

			<td>function exists
			</td>
			<td>removed
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
		<tr>
			<td>**`jQuery.fn.offset()`**
must have at least one valid DOM element, otherwise it throws an error
			</td>
			<td>doesn't throw error
			</td>
			<td>throws an error
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
		<tr>
			<td>**`jQuery.fn.context`**
when a jQuery object is created from a node \(like in our `oControl.$()` call\), it no longer has the `context` property set
			</td>
			<td> `context` property exists
			</td>
			<td> `context` property has been removed
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
		<tr>
			<td>**`jQuery.fn.andSelf()`**
function was removed; jQuery proposes to use`jQuery.fn.addBack()` instead.
			</td>
			<td>exists
			</td>
			<td>removed
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
		<tr>
			<td>**`jQuery.fn.[width</td>
			<td>height</td>
			<td>outerWidth</td>
			<td>outerHeight]`**
return value type changed
			</td>
			<td>returns integer
			</td>
			<td>returns float
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
		<tr>
			<td>**`jQuery.fn.[width</td>
			<td>height</td>
			<td>outerWidth</td>
			<td>outerHeight]`**
in case of an empty jQuery element, the return value was changed from `null` to `undefined`
			</td>
			<td>returns `null` \(can be automatically cast to 0 when compared to a number\)
			</td>
			<td>returns `undefined` \(cast to `NaN`\)
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
		<tr>
			<td> **`jQuery.event.props`** and **`jQuery.event.fixHooks`** 
			</td>
			<td>exist
			</td>
			<td>removed
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
		<tr>
			<td> **`jQuery.Deferred.then(function A() {})`** 
			</td>
			<td>Function `A` is called immediately within the same call stack
			</td>
			<td>Function `A` is called after the current call stack is finished
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
		<tr>
			<td>**`jQuery.Deferred.[resolve</td>
			<td>reject</td>
			<td>notify]`**
`this` context that is set by
			</td>
			<td> `this` context is set to the promise of the `Deferred` object
			</td>
			<td> `this` context is undefined
			</td>
			<td>

![YES](loio3929e469c7824eb0a69206aeac69f257_LowRes.png)
			</td>
		</tr>
	</tbody>
</table>

***

#### List of unpatched jQuery incompatibilities

Some incompatible changes that are introduced with jQuery 3.5.1 aren't restored to the old behavior of jQuery 2.2.3 by our compatibility layer. This is because we consider them reasonable improvements, for which we don't see any negative impact from our evaluation with existing applications.

|API

|jQuery 2.x

|jQuery 3.x

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>-----</th>
			<th>------------</th>
			<th>------------</th>
		</tr>
	</thead>
	<tbody>

doesn't include the scrollbar width if there is one

			<td>includes the width or height of the scrollbar, if there is one
			</td>
			<td>doesn't include the scrollbar width if there is one
			</td>
			<td>Use `jQuery.fn.[outerWidth</td>
outerHeight]` instead. Also works in jQuery 2.x
			</td>
		</tr>
		<tr>
			<td> **`jQuery.animation`** 
			</td>
			<td>uses `setInterval()` 
			</td>
			<td>uses `requestAnimationFrame()`
			</td>
		</tr>
		<tr>
			<td>**`jQuery.ajax`**
for multiple response header values that have the same header name
			</td>
			<td>only returns the first header value
			</td>
			<td>merges multiple header values into a string, separated by ", "
			</td>
		</tr>
		<tr>
			<td>**`jQuery(function A() {})`**
callback is delayed even if the `DOM Ready` event already occurred
			</td>
			<td>Function `A` is called immediately within the current call stack
			</td>
			<td>Function `A` is called after the current call stack has finished
			</td>
		</tr>
		<tr>
			<td> **`jQuery.swap()`** 
			</td>
			<td>exists
			</td>
			<td>*removed, because it's an undocumented internal method!*
			</td>
		</tr>
		<tr>
			<td>**`jQuery.data`**
in case the key contains a dash "-"
			</td>
			<td>see [https://jquery.com/upgrade-guide/3.0/\#data](https://jquery.com/upgrade-guide/3.0/#data) 
			</td>
			<td>see [https://jquery.com/upgrade-guide/3.0/\#data](https://jquery.com/upgrade-guide/3.0/#data) 
			</td>
		</tr>
		<tr>
			<td>**`jQuery.fn.selector`**
unreliable pseudo-selector has been removed
			</td>
			<td>concatenates the selector property after further tree traversal calls, for example `jQuery.fn.filter` \(see [https://api.jquery.com/category/traversing/tree-traversal/](https://api.jquery.com/category/traversing/tree-traversal/)\)
			</td>
			<td>according to jQuery documentation, it was never reliable and thus removed with 3.0: [https://api.jquery.com/selector/](https://api.jquery.com/selector/)
			</td>
		</tr>
		<tr>
			<td>**`jQuery.easing.*`**
see [https://jquery.com/upgrade-guide/3.0/\#deprecated-additional-easing-function-parameters](https://jquery.com/upgrade-guide/3.0/#deprecated-additional-easing-function-parameters)
			</td>
			<td>function accepts multiple arguments
			</td>
			<td>function accepts only one argument
			</td>
		</tr>
		<tr>
			<td>**`jQuery.fn.[append</td>
			<td>prepend]`**
[jQuery Issue \#3976](https://github.com/jquery/jquery/issues/3976)

see also the table below
			</td>
			<td>automatically add a `<tbody>` element to a `<table>` element, if none is present
			</td>
			<td>adding elements to a table does **not** create an additional `<tbody>` element
			</td>
		</tr>
		<tr>
			<td>**`jQuery.fn.[after</td>
			<td>append</td>
			<td>before</td>
			<td>html</td>
			<td>prepend</td>
			<td>replaceWith]`**
**`jQuery.parseHTML`**

[jQuery Pull Request \#4642](https://github.com/jquery/jquery/pull/4642)

see also the table below
			</td>
			<td>some jQuery APIs in certain contexts call the `htmlPrefilter()` method, which replaces self-closing HTML tags with properly closed HTML elements \(e.g. <div/\> is replaced by <div\></div\>\)
			</td>
			<td>the `htmlPrefilter()` method returns the passed string unmodified
			</td>
		</tr>
	</tbody>
</table>

***

#### Changes in behavior for OpenUI5 versions above 1.81

Due to the above-mentioned jQuery incompatibilities, OpenUI5 behaves differently in certain cases after the jQuery update.

The following table describes these behavior changes and gives recommendations how to handle them:

|Changed Behavior

|in OpenUI5 < 1.82

|in OpenUI5 \>= 1.82

|Recommendation

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>------------------</th>
			<th>-------------------</th>
			<th>---------------------</th>
			<th>----------------</th>
		</tr>
	</thead>
	<tbody>

see also the table above

			<td>OpenUI5 Controls using a string-based rendering approach in their renderer modules implicitly use jQuery APIs to create the DOM elements.
Whenever you flush a `<tr>` element into a `<table>` element without an already existing `<tbody>` element, the UI5 Core RenderManager implicitly creates a `<tbody>` element.
			</td>
			<td>flushing a `<tr>` element into a `<table>` element from within a string-based OpenUI5 control renderer does **not** automatically create a `<tbody>` element
			</td>
			<td>If your application or control code depends on a `<tbody>` element being present in the DOM, you should add it manually to your rendering code and your CSS styling rules.
Adding the `<tbody>` element in this way is backward-compatible to older OpenUI5 and jQuery versions.
			</td>
		</tr>
		<tr>
			<td>**Self-Closing HTML Tags**
see also the table above
			</td>
			<td>OpenUI5 uses a UI5-specific jQuery 2.2.3 variant. Formerly, its internal `htmlPrefilter()` method used to replace self-closing HTML tags with properly closed HTML elements \(e.g. <div/\> was replaced by <div\></div\>\).
Since jQuery 3.5.0, this replacement is no longer done. Instead, the browser will automatically close the self-closing HTML element based on the DOM hierarchy, which could very likely occur at the wrong place. The custom jQuery 2.2.3 variant used in OpenUI5 also implements this change, because self-closing HTML tags for non-void HTML elements are not valid in HTML5.

The updated jQuery 2.2.3 variant is contained in the following OpenUI5 versions:

 -   1.38.47 or higher

 -   1.52.43 or higher

 -   1.60.28 or higher

 -   1.71.20 or higher

 -   1.78.4 or higher

 -   1.80.1 or higher

 -   1.81.0 or higher
			</td>
			<td>jQuery no longer closes self-closing tags for non-void HTML elements in the `htmlPrefilter()` method. Instead, the browser will automatically close the self-closing HTML element based on the DOM hierarchy, which could very likely occur at the wrong place.
			</td>
			<td>You should properly close non-void HTML elements. For detailed instructions for identifying affected code and fixing it, see [these instructions]().
Properly closing non-void HTML elements in this way is backward-compatible to older OpenUI5 and jQuery versions.
			</td>
		</tr>
	</tbody>
</table>

***

#### Known jQuery issues

At the time of writing, the following jQuery issues have been identified. They have been fixed in the jQuery variant `sap/ui/thirdparty/jquery.js` shipped with OpenUI5 1.82 and later:

-   [jQuery Issue \#4382: Bug with focus\(\) method in a specific case in 3.4.0](https://github.com/jquery/jquery/issues/4382).

    Introduced with jQuery 3.4.0, this causes several tests to fail.

    The bug isn't fixed in the jQuery 3.x code line, but only in the master for an upcoming jQuery 4.x release \(see [this commit](https://github.com/jquery/jquery/commit/8a741376937dfacf9f82b2b88f93b239fe267435)\).

    At the time of writing, it's not clear whether and when the fix will be downported to the jQuery 3.x code line.

-   [jQuery Issue \#4417: Exception when element is removed on blur](https://github.com/jquery/jquery/issues/4417).

    At the time of writing, the bug is still open in jQuery's Github repository. Once the bug has been fixed, the in-place patch in our framework's jQuery variant will be deleted.

-   [jQuery Issue \#4431: Position\(\) calculated incorrectly for elements inside a table](https://github.com/jquery/jquery/issues/4431).

    jQuery wrongly calculates the offsetParent. The `offsetParent` property of `HTMLElement` returns a`<td>`, `<th>`, `<table>` ancestor even when the ancestor element has a `static` CSS position.

    The original implementation of `jQuery.fn.offsetParent` can handle this case correctly.


***

#### Remove the deprecated jQuery API from your code

You can activate an additional support rule with the [UI5 Support Assistant](Support_Assistant_57ccd7d.md). The rule `"Usage of deprecated jQuery API"` will show you warnings for all instances of deprecated jQuery 3.x API usage.

Though these APIs are "only" deprecated and could still be used, the jQuery project will remove them with their next version jQuery 4.x

> ### Note:  
> To stay future-proof, we strongly recommend that you remove/refactor all your application and control code so as not to use any deprecated jQuery API anymore.

