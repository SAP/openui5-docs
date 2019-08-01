<!-- loioeaeea19a991d46f29e6d8d8827317d0e -->

| loio |
| -----|
| eaeea19a991d46f29e6d8d8827317d0e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/eaeea19a991d46f29e6d8d8827317d0e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/eaeea19a991d46f29e6d8d8827317d0e)</div>

## Guidelines and Best Practices

There are some general guidelines for writing succinct and meaningful rules to ensure high quality, consistency and better usability of the reported issues.

***

<a name="loioeaeea19a991d46f29e6d8d8827317d0e__section_sws_qkx_d1b"/>

### Rule Property Values

The following table contains guidelines and examples on how to set the rule property values.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Field</th>
			<th>Guidelines / Explanation</th>
			<th>Example / Clarification</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>ID</td>
			<td>

 -   CamelCase
 -   Start with small caps
			</td>
			<td>*hardcodedTextValues*</td>
			<td>Async</td>
			<td>Defines if the rule check function will contain asynchronous operations. It can be true or false. The default value is false.</td>
			<td>Make sure you use the resolve function in your rule check function as a 4th parameter.</td>
		</tr>
		<tr>
			<td>Audiences</td>
			<td>

 -   Control - rule is relevant for control developers
 -   Internal - rule is relevant for an SAP internal developer

 -   Application - rule is relevant for app developers
			</td>
			<td>Choose one.</td>
			<td>Categories</td>
			<td>A list of categories checked that show which aspects of the application are affected by the rule. Examples:

 -   Performance
 -   Model Bindings

 -   Memory
			</td>
			<td>Choose one or more, or add your own.</td>
			<td>Min version</td>
			<td>The minimum OpenUI5 version required so that the rule can produce valid results. The Support Assistant considers applicable rules according to their `minversion` value. If you have rules in your custom library, keep in mind that the rule `minversion` will still be compared against the underlying OpenUI5 version. If you are not aware of the version, you can put in the `minversion` field "\*", "-" or whitespace \(" "\) to make sure these rules are executed.</td>
			<td>for example, 1.44 for OpenUI5 version comparison or "\*", "-", or whitespace \(" "\) to avoid version filtering.</td>
		</tr>
		<tr>
			<td>Max version</td>
			<td>The maximum OpenUI5 version required to run the rule.</td>
			<td>\(currently not taken into account\)</td>
		</tr>
		<tr>
			<td>Title</td>
			<td>

 -   As short as possible, as descriptive as possible.
 -   \(Where applicable\) - **<Control Name \(no namespace\)\>:** Description of issue

 -   Sentence case.
			</td>
			<td>*Page: invalid background design property*</td>
			<td>Description</td>
			<td>

 -   Briefly explain what the rule does/checks.
 -   Ideally one sentence. No period.

 -   Avoid explaining how to fix the issue.
			</td>
			<td>*Dialogs with content should have ariaLabelledBy association set*</td>
			<td>Resolution</td>
			<td>

 -   Explain how to fix the issue.
 -   Use imperative.

 -   Ideally one sentence. No period.

 -   Could be left out if it is trivial and already explained in the Description.
			</td>
			<td>*Set property upperCase to false or add icons to IconTabFilters*</td>
			<td>Details</td>
			<td>

 -   Contains technical details on a rule that was triggered for a specific element.
 -   References specific errors and should not be a resolution hint.
			</td>
			<td>*Element\{0\} has no icon but its parent Element\{1\} has property upperCase set to true.*</td>
			<td>URLs</td>
			<td>

 -   Ideally every rule should point to a topic or document in the DevGuide, API Reference, Samples, or SAP Fiori Design Guidelines.
 -   Use the following text values when referring to specific parts of the documentation:

     -   Developer Guide - **Documentation: <Title of topic\>**

     -   API Reference - **API Reference: <Name of control + path to method/property\>**

     -   SAP Fiori Guidelines - **SAP Fiori Guidelines: <Name of control\>**

     -   External Link - no description text, just a URL
			</td>
			<td>

 -   *Documentation: Element Binding* -   *API Reference: ComboBox \#getSelectedItem*
 -   *SAP Fiori Design Guidelines: RadioButton*
			</td>
		</tr>
		<tr>
			<td>Check function</td>
			<td>Check function code</td>
			<td> `function (issueManager, oCoreFacade, oScope) { ... }` </td>
		</tr>
	</tbody>
</table>

***

<a name="loioeaeea19a991d46f29e6d8d8827317d0e__section_qpw_fn5_tz"/>

### Check Function Guidelines

Here are some general guidelines that you should consider when creating a new rule:

-   **Create very specific rules**

    It is important that the rules are as specific as possible. Avoid too generic or unspecific rules that would produce excessive number of issues difficult to digest or follow up. The rules should focus on one issue and provide a resolution for it.

-   **Reduce the number of issues generated**

    Do not overload the user with a large number of issues. When appropriate, produce one issue where multiple texts are concatenated with `\n` delimiter.

-   **Write clear descriptions and resolutions**

    Use the guidelines in [Create a Ruleset for a Library](Create_a_Ruleset_for_a_Library_b5a5135.md)


