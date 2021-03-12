<!-- loio6322164936f047de941ec522b95d7b70 -->

| loio |
| -----|
| 6322164936f047de941ec522b95d7b70 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/6322164936f047de941ec522b95d7b70) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/6322164936f047de941ec522b95d7b70)</div>

## Hyphenation for Text Controls

OpenUI5 offers the possibility to hyphenate words in multiline texts when controls are in wrapping mode.

***

<a name="loio6322164936f047de941ec522b95d7b70__section_s33_lmb_ffb"/>

### Overview

The hyphenation feature is an intelligent wrapping capability for optimal visual rendering of multiline text. It is especially useful for longer text instances in any type of container.

It is enabled through the `wrappingType` property for the following controls:

-   `sap.m.Text`

-   `sap.m.Title`

-   `sap.m.Label`


***

<a name="loio6322164936f047de941ec522b95d7b70__section_dtc_x2m_3fb"/>

### Use Cases

***

#### Using the integrated hyphenation through the `wrappingType` property directly in the text controls

All three controls have a `wrapping` property that determines text wrapping. By default, it is set to `true` for the `sap.m.Text` control and to `false` for `sap.m.Label` and `sap.m.Title`. Setting the `wrapping` property of these controls to `true` allows you to use the `wrappingType` property which enables hyphenation. It's an `enum` property with two possible values:

-   `WrappingType.Normal` – The text wraps on several lines keeping the words in their entirety.
-   `WrappingType.Hyphenated` – The text wraps on several lines separating words into syllables and marking the syllabification with a hyphen.

Example:

``` js
new sap.m.Label({
  text: "Liquiditätspositionshierarchie Datenänderungsbelege",
  wrapping: true,
  wrappingType: sap.m.WrappingType.Hyphenated
});

```

***

#### Using the `sap.ui.core.hyphenation.Hyphenation` API

This class provides methods to evaluate the possibility of using browser-native hyphenation or to initialize and use a third-party hyphenation module. Using this API you can check if browser-native hyphenation is supported for a particular language.

If browser-native hyphenation is not supported, you can directly use this API to hyphenate texts. A third-party library named Hyphenopoly is used in that case.

As the `sap.ui.core.hyphenation.Hyphenation` class is a singleton, an instance should be acquired from the [`getInstance`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.hyphenation.Hyphenation/methods/getInstance) method.

Example:

``` js
var oHyphenationApi = sap.ui.core.hyphenation.Hyphenation.getInstance();
if (!oHyphenationApi.canUseNativeHyphenation("en")) {
  oHyphenationApi.initialize("en").then(function() {
    console.log(
      oHyphenationApi.hyphenate("An example text to hyphenate.", "en")
    );
  });
}
```

***

#### Manual control of hyphenation when third-party resources are loaded.

By default, the text controls load any required third-party resources at a later state which can lead to flickering of the first visible text control between its unhyphenated and hyphenated states. To prevent this, you can prepare the third-party library before rendering your app.

Example:

``` js
sap.ui.core.hyphenation.Hyphenation.getInstance()
  .initialize()
  .then(function() {
    // continue with application initialization/rendering
  });

```

***

<a name="loio6322164936f047de941ec522b95d7b70__section_ksz_fsb_ffb"/>

### How It Works for Text Controls

We’ve taken the following dynamic approach to hyphenation:

-   We use browser-native hyphenation when possible;
-   If browser hyphenation is not possible – we use a third-party tool called Hyphenopoly through the `sap.ui.core.hyphenation.Hyphenation` API.

Once you've set the control property to `WrappingType.Hyphenated`, the control instance checks dynamically whether the browser you’re using supports hyphenation. If yes, it enables the CSS hyphenation and lets the browser perform it. If it doesn’t, the process is redirected to a third-party tool and the hyphenation module is asynchronously loaded together with the specific resources per language. This is done through the `sap.ui.core.hyphenation.Hyphenation` API, which is responsible for loading all resources in an async mode and for the dynamic initialization of the third-party library with the language resources and some required configurations. It also caches the rules internally for future use.

When the framework makes the choice whether browser-native hyphenation or third-party hyphenation should be used, it logs a message in the console for more information about what was decided.

   
  
<a name="loio6322164936f047de941ec522b95d7b70__fig_ilz_gch_hfb"/>Hyphenation Workflow

 ![](loio6992c16573754505aa2e008859207b91_LowRes.png "Hyphenation Workflow") 

***

<a name="loio6322164936f047de941ec522b95d7b70__section_b4v_3rr_kfb"/>

### Supported Languages

> Caution:  
> Note that as the hyphenation feature uses third-party and browser-native tools, we are not responsible for any grammatical incorrectness or inconsistencies of the hyphenation. Also, the variety of supported languages is outside the scope of our control and may be subject to future changes.

OpenUI5 provides hyphenation through the `hyphens` CSS property or the third-party tool Hyphenopoly.

The following table provides a list of languages supported by the third-party tool Hyphenopoly \(version 2.4.0\). Texts in all other languages are hyphenated only if the used browser supports the `hyphens` CSS property for the specified language.

|Language

|Code

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>----------</th>
			<th>------</th>
		</tr>
	</thead>
	<tbody>

			<td>bg
			</td>
		</tr>
		<tr>
			<td>Catalan
			</td>
			<td>ca
			</td>
		</tr>
		<tr>
			<td>Croatian
			</td>
			<td>hr
			</td>
		</tr>
		<tr>
			<td>Danish
			</td>
			<td>da
			</td>
		</tr>
		<tr>
			<td>Dutch
			</td>
			<td>nl
			</td>
		</tr>
		<tr>
			<td>English \(US\)
			</td>
			<td>en
			</td>
		</tr>
		<tr>
			<td>Estonian
			</td>
			<td>et
			</td>
		</tr>
		<tr>
			<td>Finnish
			</td>
			<td>fi
			</td>
		</tr>
		<tr>
			<td>French \(FR\)
			</td>
			<td>fr
			</td>
		</tr>
		<tr>
			<td>German
			</td>
			<td>de
			</td>
		</tr>
		<tr>
			<td>Greek
			</td>
			<td>el
			</td>
		</tr>
		<tr>
			<td>Hindi
			</td>
			<td>hi
			</td>
		</tr>
		<tr>
			<td>Hungarian
			</td>
			<td>hu
			</td>
		</tr>
		<tr>
			<td>Italian
			</td>
			<td>it
			</td>
		</tr>
		<tr>
			<td>Lithuanian
			</td>
			<td>lt
			</td>
		</tr>
		<tr>
			<td>Norwegian
			</td>
			<td>no
			</td>
		</tr>
		<tr>
			<td>Portuguese \(BR\)
			</td>
			<td>pt
			</td>
		</tr>
		<tr>
			<td>Russian
			</td>
			<td>ru
			</td>
		</tr>
		<tr>
			<td>Slovenian
			</td>
			<td>sl
			</td>
		</tr>
		<tr>
			<td>Spanish \(ES\)
			</td>
			<td>es
			</td>
		</tr>
		<tr>
			<td>Swedish
			</td>
			<td>sv
			</td>
		</tr>
		<tr>
			<td>Thai
			</td>
			<td>th
			</td>
		</tr>
		<tr>
			<td>Turkish
			</td>
			<td>tr
			</td>
		</tr>
		<tr>
			<td>Ukrainian
			</td>
			<td>uk
			</td>
		</tr>
	</tbody>
</table>

**Related Information**  


[API Reference: sap.m.Text](https://openui5.hana.ondemand.com/#/api/sap.m.Text)

[API Reference: sap.m.Title](https://openui5.hana.ondemand.com/#/api/sap.m.Title)

[API Reference: sap.m.Label](https://openui5.hana.ondemand.com/#/api/sap.m.Label)

[API Reference: sap.m.WrappingType](https://openui5.hana.ondemand.com/#/api/sap.m.WrappingType)

[API Reference: sap.ui.core.hyphenation.Hyphenation](https://openui5.hana.ondemand.com/#/api/sap.ui.core.hyphenation.Hyphenation)

[Hyphenopoly on GitHub](https://github.com/mnater/Hyphenopoly)

[`hyphens` CSS property and browser compatibility on MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens#Browser_compatibility)

