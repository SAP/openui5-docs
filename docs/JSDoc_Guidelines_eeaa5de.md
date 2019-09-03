<!-- loioeeaa5de14e5f4fc1ac796bc0c1ada5fb -->

| loio |
| -----|
| eeaa5de14e5f4fc1ac796bc0c1ada5fb |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/eeaa5de14e5f4fc1ac796bc0c1ada5fb) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/eeaa5de14e5f4fc1ac796bc0c1ada5fb)</div>

## JSDoc Guidelines

Provides an overview of guidelines for creating JSDoc documentation.

To document JavaScript coding, you can add documentation comments to the code. Based on these comments, the descriptions of the OpenUI5 entities are generated and shown in the *API Reference* of the Demo Kit. OpenUI5 uses the JSDoc3 toolkit, which resembles JavaDoc, to generate the descriptions. For an explanation of the available tags, see [http://usejsdoc.org](http://usejsdoc.org).

***

<a name="loioeeaa5de14e5f4fc1ac796bc0c1ada5fb__section_wjj_hys_l2b"/>

### Basics of JSDoc

Here are some general principles for writing comments:

-   Document the constructor with `@class`, `@author`, `@since`, and so on.

-   For subclasses, document the inheritance by using an `@extends` tag in their constructor doclet.

-   Document at least public and protected methods with JSDoc, mark them as `@public` or `@protected`.

    If you also document private methods with JSDoc, mark them as `@private`. This is currently the default in OpenUI5, but not in JSDoc, so it is safer to explicitly specify this. `@protected` is not clearly defined for a JavaScript environment. In OpenUI5, it denotes a method that is not meant to be used by applications. It might be used outside the relevant class or subclasses, but only in closely related classes.

    To specify explicit classes that are allowed to use a class or function, mark them as `@private` followed by `@ui5-restricted <modulenames>`, which will override the latter and make sure that the JSDoc cannot generate this content.

-   Document method parameters with type \(in curly braces\) and parameter name \(in square brackets if optional\).

-   Use `@namespace` for static helper classes that only provide static methods.


For an example of how to create a class, see [Example for Defining a Class](Example_for_Defining_a_Class_f6fba4c.md).

***

<a name="loioeeaa5de14e5f4fc1ac796bc0c1ada5fb__section_s55_3j2_p2b"/>

### Descriptions

A documentation comment should provide the following content:

-   Summary sentence at the beginning; the summary is reused, for example, for tooltips and in summaries in the *API Reference*

-   Background information required to understand the object

-   Special considerations that apply

-   Detailed description with additional information that does not repeat the self-explanatory API name or summary


> Note:
> Avoid implementation details and dependencies unless they are important for usage.
> 
> 

***

#### Dos and Don'ts

-   To avoid line wrapping, make sure that each line of the description has a similar length as the code. In the *API Reference*, the line breaks in a description are ignored, and it appears as a continuous text.

-   Use a period at the end of each summary sentence. The punctuation is required for JSDoc to identify the first sentence.

-   Don’t use a period inside a summary sentence. For example, don’t use “e.g.”, but write “for example” instead. Otherwise the summary sentence will be cut off.


> Note:
> You can create links to external sources. The source should comply with standard legal requirements. The required icons are added to the link as described in the Demo Kit under *Terms of Use* \> *Disclaimer*. For more information about creating links, see the explanations below \(@see and \{@link\}\).
> 
> 

***

#### Recommendations for Writing Descriptions

-   Don’t use exclamation marks.

-   Make sure you spell acronyms correctly, for example, ID, JSON, URL.

-   In the summary sentence, omit repetitive clauses like "This class" or "This method".

-   For actions, start directly with an appropriate verb in the third person: Adds, allocates, constructs, converts, deallocates, destroys, gets, provides, reads, removes, represents, returns, sets, saves, and so on.

    For methods, use the following verbs:

    |Type|Verb|
    |----|----|
    |Constructor|Constructs|
    |Boolean|Indicates \(whether\)|
    |Getter|Gets|
    |Setter|Sets|
    |Other|Adds/Removes/Creates/Releases/Other verb that applies|

-   For objects, use a noun phrase.

    Example: Base class for navigation


***

<a name="loioeeaa5de14e5f4fc1ac796bc0c1ada5fb__section_cfg_hvt_l2b"/>

### Inline and HTML Tags

You can use inline and HTML tags in your comments.

**Inline tags** can be placed anywhere in the comments. Inline tags are denoted by curly brackets and have the following syntax: \{@tagname comment\}.

**HTML tags** are used to format documentation comments. HTML tags have the standard HTML syntax: <tag\>...</tag\>.

The table provides an overview of the most common inline and HTML tags.

Inline and HTML Tags<a name="loioeeaa5de14e5f4fc1ac796bc0c1ada5fb__table_ezd_5yt_l2b"/>

|Tag|Use|Example|How to Use / Details|Type of Tag|
|---|---|-------|--------------------|-----------|
|\{@link\}|Links within API Reference| `{@link sap.ui.generic.app.navigation.service.NavError Error}` `{@link sap.ui.comp.smarttable.SmartTable#event:beforeRebindTable}` |To replace the path with a display text, use it like this: \{@link <path\> space <display text\>\}. You can also use `#myMethod` for links within a class or control to individual methods, for example. The leading hash will then be removed automatically. For other links, use the required syntax, for example, `#event:name`.|Inline|
|Empty line|Creates a paragraph| |Using <p\> is not necessary, since empty lines are used to define paragraphs.|HTML|
|<code\>…</code\>|Technical entities \(optional\)|the <code\>Button</code\> control| |
|<pre\>…</pre\>|Code samples| | |
|<ul\> <li\>…</li\> <li\>…</li\> </ul\>|Unordered lists| | |
|<ol\> <li\>…</li\> <li\>…</li\> </ol\>|Ordered lists| | |
|<strong\>… </strong\> or <b\>…</b\>|Bold font| | |
|<i\>…</i\>|Italics| | |
|&nbsp;|Non-breaking space| | |

***

<a name="loioeeaa5de14e5f4fc1ac796bc0c1ada5fb__section_agg_ncm_n2b"/>

### Block Tags

You can also use block tags in your comments.

**Block tags** can only be placed in the tag section below the comment. They are separated from the comment by an empty line \(recommended, but not a technical requirement\). Block tags have the following syntax: @tagname comment.

The table provides an overview of the most common block tags.

Block Tags<a name="loioeeaa5de14e5f4fc1ac796bc0c1ada5fb__table_krl_ffm_n2b"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Tag</th>
			<th>Use</th>
			<th>Example</th>
			<th>How to Use / Details</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>@param</td>
			<td>Adds parameters</td>
			<td> ``` js/**
 * ...
 * @param {string} statement The SQL statement to be prepared
 * ...
 */
```
			</td>
			<td>Begin description with a capital letter.</td>
			<td>@returns</td>
			<td>Adds return values</td>
			<td> `@returns {type1</td>
			<td>type2</td>
			<td>...} Description` </td>
			<td>Begin description with a capital letter.</td>
		</tr>
		<tr>
			<td>@throws</td>
			<td>Adds the description of an exception if an error occurs</td>
			<td> `@throws {type} Description` </td>
			<td>Begin description with a capital letter.</td>
		</tr>
		<tr>
			<td>@author</td>
			<td>Adds the name of the developer responsible for the code</td>
			<td> `@author Max Mustermann` </td>
			<td>This is an optional tag that is not displayed in JSDoc. If you need to use the version tag, use $\{version\} so you don't have to update this manually for each new version.</td>
		</tr>
		<tr>
			<td>@version</td>
			<td>Names the version for an entity</td>
			<td> `@version 14.1.2` </td>
		</tr>
		<tr>
			<td>@see</td>
			<td>Adds information \(for example, link to documentation or the SAP Fiori Design Guidelines\) in the header section of the *API Reference* </td>
			<td> `@see path` `@see free text` `@see {@link topic:bed8274140d04fc0b9bcb2db42d8bac2 Smart Table}` `@see {@link fiori:/flexible-column-layout/ Flexible Column Layout}` </td>
			<td>@see \{@link topic:loio <semantic control name\>\} provides a link to the documentation \(developer guide\). If there are several @see tags with documentation links, only the first one is shown in the header. The other ones are displayed under *Documentation Links* in the *Overview* section. For more generic topics that are not directly related to a class or control, use inline links.</td>
		</tr>
		<tr>
			<td>@since</td>
			<td>Adds the version in which an entity was first introduced</td>
			<td> `@since 1.30` </td>
			<td>Be as specific as possible \(without mentioning patch levels for new development\), since this information is useful even for internal purposes. For example, mention 1.27, even though this is not an external release.</td>
		</tr>
		<tr>
			<td>@deprecated</td>
			<td>Adds the version in which an entity was deprecated</td>
			<td> `@deprecated As of version 1.28, replaced by {@link class name}` </td>
			<td>Be as specific as possible \(without mentioning patch levels\), since this information is useful even for internal purposes. For example, mention 1.27, even though this is not an external release. Provide information about what replaces the deprecated entity.</td>
		</tr>
		<tr>
			<td>@experimental</td>
			<td>Classifies an entity that is not ready for production use yet, but available for testing purposes</td>
			<td> `@experimental As of version 1.56.0` </td>
		</tr>
		<tr>
			<td>@example</td>
			<td>Inserts a code sample after the comment</td>
			<td> ``` js/**
 * ...
 * @example
 * var id = myjob.schedules.add({
 *     description: "Added at runtime, run every 10 minutes",
 *     xscron: "* * * * * *\/10 0",
 *     parameter: {
 *         a: "c"
```
			</td>
			<td>The code sample is inserted automatically with <pre\>. It is always inserted right after the comment. To insert an example somewhere else, for example, in the middle of a comment, use <pre\>. You can add a header for the example by using <caption\>.</td>
	</tbody>
</table>

***

#### Tips for Using Block Tags

-   The order of the block tags is not mandatory from a technical perspective, but recommended to ensure consistency.

    For parameters, however, a fixed order is mandatory.

-   There are more tags available, such as `@class`or `@name`.


***

<a name="loioeeaa5de14e5f4fc1ac796bc0c1ada5fb__section_rh4_3yr_kgb"/>

### Links to API Documentation

To refer to another entity within the *API Reference*, you can use `{@link}` in combination with the reference types shown in the table below.

Reference Types within API Reference <a name="loioeeaa5de14e5f4fc1ac796bc0c1ada5fb__table_rkg_bds_kgb"/>

|Type of Reference|Description|Example|Comment|
|-----------------|-----------|-------|-------|
|<full.path.ClassName\>|Refers to a class, interface, enumeration, or namespace| `sap.ui.comp.smarttable.SmartTable` | |
|full.path.ClassName**\#**method|Refers to an instance method of a class| `sap.ui.comp.smarttable.SmartTable#getHeader` | `.prototype.` and \# are interchangeable|
|full.path.ClassName**.prototype.**method|Refers to an instance method of a class| | |
|full.path.ClassName**\#event:**name|Refers to an event fired by an instance of a class| `sap.ui.comp.smarttable.SmartTable#event:beforeRebindTable` | |
|full.path.ClassName**.**method|Refers to a static method \(or any other static property\)| | |
| `#method` |Refers to an instance method **within** a class| `#getHeader` |You can use this type of reference within an API that you are documenting, for example, within the `SmartTable` control documentation if you want to link to a method that belongs to the control itself.|
| `#.method` |Refers to a static method **within** a class| | |
| `#event:name` |Refers to an event **within** a class| | |

