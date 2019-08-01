<!-- loioa075ed88ef324261bca41813a6ac4a1c -->

| loio |
| -----|
| a075ed88ef324261bca41813a6ac4a1c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a075ed88ef324261bca41813a6ac4a1c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a075ed88ef324261bca41813a6ac4a1c)</div>

## Legacy jQuery.sap Replacement

Overview of the mapping of legacy APIs to the new APIs for the migration

The deprecation of the `jQuery.sap` API requires that it is replaced with the new API. The following list provides an overview of the required replacements.

***

***

#### Replacement With New Modules

To migrate the simple replacements, add the new module dependency and replace the call with the added argument name as shown in the following example:

> Note:
> ![](loio7d56a8eabb9e4426a7643e2f524015bd_LowRes.png)
> 
> 

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Old API Call</th>
			<th>New Module</th>
			<th>Replacement Type</th>
			<th>Replace with</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> `jQuery.sap.assert` </td>
			<td> `sap/base/assert` </td>
			<td>Simple replacement</td>
			<td> `assert` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.resources` </td>
			<td>`sap/base/i18n/ResourceBundle`</td>
			<td>Method changed</td>
			<td>`ResourceBundle.create`</td>
		</tr>
		<tr>
			<td> `jQuery.sap.log` </td>
			<td>`sap/base/Log`</td>
			<td>Simple replacement</td>
			<td> `Log` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.addLogListener` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.addLogListener` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.debug` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td>`Log.debug`</td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.error` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.error` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.fatal` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.fatal` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.getLevel` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.getLevel` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.getLog` </td>
			<td> `sap/base/Log` </td>
			<td>Method changed</td>
			<td> `Log.getLogEntries` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.getLogEntries` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.getLogEntries` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.getLogger` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.getLogger` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.info` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.info` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.isLoggable` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.isLoggable` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.Level` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.Level` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.logSupportInfo` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.logSupportInfo` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.removeLogListener` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.removeLogListener` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.trace` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.trace` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.log.warning` </td>
			<td> `sap/base/Log` </td>
			<td>Simple replacement</td>
			<td> `Log.warning` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.encodeCSS` </td>
			<td> `sap/base/security/encodeCSS` </td>
			<td>Simple replacement</td>
			<td> `encodeCSS` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.encodeJS` </td>
			<td> `sap/base/security/encodeJS` </td>
			<td>Simple replacement</td>
			<td> `encodeJS` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.encodeURL` </td>
			<td> `sap/base/security/encodeURL` </td>
			<td>Simple replacement</td>
			<td> `encodeURL` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.encodeURLParameters` </td>
			<td> `sap/base/security/encodeURLParameters` </td>
			<td>Simple replacement</td>
			<td> `encodeURLParameters` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.encodeHTML` </td>
			<td> `sap/base/security/encodeXML` </td>
			<td>Simple replacement</td>
			<td> `encodeXML` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.encodeXML` </td>
			<td> `sap/base/security/encodeXML` </td>
			<td>Simple replacement</td>
			<td> `encodeXML` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.addUrlWhitelist` </td>
			<td> `sap/base/security/URLWhiteList` </td>
			<td>Method changed</td>
			<td> `URLWhitelist.add` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.clearUrlWhitelist` </td>
			<td> `sap/base/security/URLWhiteList` </td>
			<td>Method changed</td>
			<td> `URLWhitelist.clear` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.getUrlWhitelist` </td>
			<td> `sap/base/security/URLWhiteList` </td>
			<td>Method changed</td>
			<td> `URLWhitelist.entries` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.removeUrlWhitelist` </td>
			<td> `sap/base/security/URLWhiteList` </td>
			<td>Method changed</td>
			<td> `URLWhitelist.delete` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.validateUrl` </td>
			<td> `sap/base/security/URLWhiteList` </td>
			<td>Method changed</td>
			<td> `URLWhitelist.validate` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.camelCase` </td>
			<td> `sap/base/strings/camelize` </td>
			<td>Simple replacement</td>
			<td> `camelize` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.charToUpperCase` </td>
			<td> `sap/base/strings/capitalize` </td>
			<td>Simple replacement</td>
			<td> `capitalize` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.escapeRegExp` </td>
			<td> `sap/base/strings/escapeRegExp` </td>
			<td>Simple replacement</td>
			<td>`escapeRegExp`</td>
		</tr>
		<tr>
			<td> `jQuery.sap.formatMessage` </td>
			<td> `sap/base/strings/formatMessage` </td>
			<td>Simple replacement</td>
			<td> `formatMessage` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.hashCode` </td>
			<td> `sap/base/strings/hash` </td>
			<td>Simple replacement</td>
			<td>`hash`</td>
		</tr>
		<tr>
			<td> `jQuery.sap.hyphen` </td>
			<td> `sap/base/strings/hyphenate` </td>
			<td>Simple replacement</td>
			<td> `hyphenate` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.unicode` `jQuery.sap.isStringNFC` </td>
			<td> `sap/base/strings/NormalizePolyfill` </td>
			<td>Simple replacement</td>
			<td>`NormalizePolyfill`</td>
		</tr>
		<tr>
			<td>-</td>
			<td>`sap/base/strings/toHex`</td>
			<td>-</td>
			<td>-</td>
		</tr>
		<tr>
			<td> `jQuery.sap.arraySymbolDiff` </td>
			<td> `sap/base/util/array/diff` </td>
			<td>Simple replacement</td>
			<td> `diff` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.unique` </td>
			<td> `sap/base/util/array/uniqueSort` </td>
			<td>Simple replacement</td>
			<td> `uniqueSort` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.equal` </td>
			<td> `sap/base/util/deepEqual` </td>
			<td>Simple replacement</td>
			<td> `deepEqual` </td>
		</tr>
		<tr>
			<td>-</td>
			<td> `sap/base/util/defineLazyProperty` </td>
			<td>-</td>
			<td>-</td>
		</tr>
		<tr>
			<td> `jQuery.sap.each` </td>
			<td> `sap/base/util/each` </td>
			<td>Simple replacement</td>
			<td> `each` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.forIn` </td>
			<td> `sap/base/util/each` </td>
			<td>Simple replacement</td>
			<td> `each` </td>
		</tr>
		<tr>
			<td>-</td>
			<td> `sap/base/util/includes` </td>
			<td>-</td>
			<td>-</td>
		</tr>
		<tr>
			<td> `jQuery.isPlainObject` </td>
			<td> `sap/base/util/isPlainObject` </td>
			<td>Simple replacement</td>
			<td> `isPlainObject` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.parseJS` </td>
			<td> `sap/base/util/JSTokenizer` </td>
			<td>Simple Replacement</td>
			<td> `JSTokenizer.parseJS` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.extend` </td>
			<td> `sap/base/util/merge` </td>
			<td>Complex Replacement</td>
			<td>Old: 

```
// Shallow
jQuery.sap.extend({}, sContent);

//Deep
jQuery.sap.extend(true, {}, sContent)
```

 New: ```
//Shallow
Object.assign({}, sContent);

//Deep
merge({}, sContent);
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.now` </td>
			<td> `sap/base/util/now` </td>
			<td>Simple Replacement</td>
			<td> `now` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.getObject` </td>
			<td> `sap/base/util/ObjectPath` </td>
			<td>Complex Replacement</td>
			<td> 

```
ObjectPath.get("some.object.path", "someProperty");
```

 If the object path does not exist, the method doesn't create it anymore. If the path needs to be create it has do be done separately: ```
ObjectPath.create("some.object.path", window.myLib);
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.setObject` </td>
			<td> `sap/base/util/ObjectPath` </td>
			<td>Complex Replacement</td>
			<td> 

```
ObjectPath.set("some.object.path", "myValue", window.myLib);
```

 The object path is created if it does not exist.</td>
		</tr>
		<tr>
			<td> `jQuery.sap.properties` </td>
			<td> `sap/base/util/Properties` </td>
			<td>Method changed</td>
			<td> `Properties.create` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.uid` </td>
			<td> `sap/base/util/uid` </td>
			<td>Simple Replacement</td>
			<td> `uid` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.getUriParameters` </td>
			<td> `sap/base/util/UriParameters` </td>
			<td>Changed to class for instantiation</td>
			<td> 

```
var oUriParameters = new UriParameters(window.location.href);
oUriParameters.get("sap-ui-debug");
```
			</td>
		</tr>
		<tr>
			<td>-</td>
			<td> `sap/base/util/values` </td>
			<td>Simple Replacement</td>
			<td>-</td>
		</tr>
		<tr>
			<td> `jQuery.sap.Version` </td>
			<td> `sap/base/util/Version` </td>
			<td>Simple Replacement</td>
			<td> `Version` </td>
		</tr>
		<tr>
			<td>-</td>
			<td> `sap/ui/core/support/HotKeys` </td>
			<td>-</td>
			<td>-</td>
		</tr>
		<tr>
			<td> `jQuery.sap.syncStyleClass` </td>
			<td> `sap/ui/core/syncStyleClass` </td>
			<td>Simple Replacement</td>
			<td> `syncStyleClass` </td>
		</tr>
		<tr>
			<td> `jQuery.device.is.android_phone` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.android && Device.system.phone
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.device.is.android_tablet` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.android && Device.system.tablet
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.device.is.desktop` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.system.desktop
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.device.is.ipad` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.ios && Device.system.ipad
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.device.is.iphone` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.ios && Device.system.phone
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.device.is.landscape` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.orientation.landscape
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.device.is.phone` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.system.phone
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.device.is.portrait` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.orientation.portrait
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.device.is.tablet` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.system.tablet
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.Android` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.name === "Android"
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.bb` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.name === "bb"
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.fVersion` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.version
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.iOS` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.name === "iOS"
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.linux` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.name === "linux"
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.mac` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.name === "mac"
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.os` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.name
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.version` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.versionStr
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.win` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.name === "win"
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.os.winphone` </td>
			<td> `sap/ui/Device` </td>
			<td>Complex Replacement</td>
			<td> 

```
Device.os.name === "winphone"
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.containsOrEquals` </td>
			<td> `sap/ui/dom/containsOrEquals` </td>
			<td>Simple Replacement</td>
			<td> `containsOrEquals` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.denormalizeScrollBeginRTL` </td>
			<td> `sap/ui/dom/denormalizeScrollBeginRTL` </td>
			<td>Simple Replacement</td>
			<td> `denormalizeScrollBeginRTL` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.denormalizeScrollLeftRTL` </td>
			<td> `sap/ui/dom/denormalizeScrollLeftRTL` </td>
			<td>Simple Replacement</td>
			<td> `denormalizeScrollLeftRTL` </td>
		</tr>
		<tr>
			<td>-</td>
			<td> `sap/ui/dom/getComputedStyleFix` </td>
			<td>-</td>
			<td>-</td>
		</tr>
		<tr>
			<td> `jQuery.sap.ownerWindow` </td>
			<td> `sap/ui/dom/getOwnerWindow` </td>
			<td>Simple Replacement</td>
			<td> `getOwnerWindow` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.scrollbarSize` </td>
			<td> `sap/ui/dom/getScrollbarSize` </td>
			<td>Simple Replacement</td>
			<td> `getScrollbarSize` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.includeScript` </td>
			<td> `sap/ui/dom/includeScript` </td>
			<td>Simple Replacement</td>
			<td> `includeScript` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.includeStylesheet` </td>
			<td> `sap/ui/dom/includeStylesheet` </td>
			<td>Simple Replacement</td>
			<td> `includeStylesheet` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.replaceDOM` </td>
			<td> `sap/ui/dom/patch` </td>
			<td>Simple Replacement</td>
			<td> `patch` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.pxToRem` </td>
			<td> `sap/ui/dom/units/Rem` </td>
			<td>Simple Replacement</td>
			<td> `Rem.fromPx` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.remToPx` </td>
			<td> `sap/ui/dom/units/Rem` </td>
			<td>Simple Replacement</td>
			<td> `Rem.toPx` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.checkMouseEnterOrLeave` </td>
			<td> `sap/ui/events/checkMouseEnterOrLeave` </td>
			<td>Simple Replacement</td>
			<td> `checkMouseEnterOrLeave` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.bindAnyEvent` </td>
			<td> `sap/ui/events/ControlEvents` </td>
			<td>Simple Replacement</td>
			<td> `bindAnyEvent` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.ControlEvents` </td>
			<td> `sap/ui/events/ControlEvents` </td>
			<td>Simple Replacement</td>
			<td> `events` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.unbindAnyEvent` </td>
			<td> `sap/ui/events/ControlEvents` </td>
			<td>Simple Replacement</td>
			<td> `unbindAnyEvent` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.handleF6GroupNavigation` </td>
			<td> `sap/ui/events/F6Navigation` </td>
			<td>Simple Replacement</td>
			<td> `handleF6GroupNavigation` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.isMouseEventDelayed` </td>
			<td> `sap/ui/events/isMouseEventDelayed` </td>
			<td>Simple Replacement</td>
			<td> `isMouseEventDelayed` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.isSpecialKey` </td>
			<td> `sap/ui/events/isSpecialKey` </td>
			<td>Simple Replacement</td>
			<td> `isSpecialKey` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.touchEventMode` </td>
			<td> `sap/ui/events/jquery/EventSimulation` </td>
			<td>Simple Replacement</td>
			<td> `touchEventMode` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.keycodes` </td>
			<td> `sap/ui/events/KeyCodes` </td>
			<td>Simple Replacement</td>
			<td> `KeyCodes` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.PseudoEvents` </td>
			<td> `sap/ui/events/PseudoEvents` </td>
			<td>Simple Replacement</td>
			<td> `PseudoEvents` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.disableTouchToMouseHandling` </td>
			<td> `sap/ui/events/TouchToMouseMapping` </td>
			<td>Simple Replacement</td>
			<td> `disableTouchToMouseHandling` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.registerModulePath` </td>
			<td>-</td>
			<td>Complex Replacement</td>
			<td> 

```
sap.ui.loader.config({paths:{"myPath": "some/path"}});
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.registerResourcePath` </td>
			<td>-</td>
			<td>Complex Replacement</td>
			<td> 

```
sap.ui.loader.config({paths:{"myPath": "some/path"}});
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.add` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.add` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.average` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.average` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.clear` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.clear` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.end` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.end` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.filterMeasurements` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.filterMeasurements` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.getActive` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.getActive` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.getAllMeasurements` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.getAllMeasurements` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.getMeasurement` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.getMeasurement` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.pause` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.pause` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.registerMethod` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.registerMethod` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.remove` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.remove` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.resume` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.resume` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.setActive` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.setActive` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.start` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.start` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.unregisterAllMethods` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.unregisterAllMethods` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.unregisterMethod` </td>
			<td> `sap/ui/performance/Measurement` </td>
			<td>Simple Replacement</td>
			<td> `Measurement.unregisterMethod` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.fesr.getActive` </td>
			<td> `sap/ui/performance/trace/FESR` </td>
			<td>Simple Replacement</td>
			<td> `FESR.getActive` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.fesr.setActive` </td>
			<td> `sap/ui/performance/trace/FESR` </td>
			<td>Simple Replacement</td>
			<td> `FESR.setActive` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.fesr.addBusyDuration` </td>
			<td> `sap/ui/performance/trace/Interaction` </td>
			<td>Simple Replacement</td>
			<td> `Interaction.addBusyDuration` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.interaction.*` </td>
			<td> `sap/ui/performance/trace/Interaction` </td>
			<td>Method changed</td>
			<td> `Interaction.*` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.clearInteractionMeasurements` </td>
			<td> `sap/ui/performance/trace/Interaction` </td>
			<td>Method changed</td>
			<td> `Interaction.clear` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.endInteraction` </td>
			<td> `sap/ui/performance/trace/Interaction` </td>
			<td>Method changed</td>
			<td> `Interaction.end` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.filterInteractionMeasurements` </td>
			<td> `sap/ui/performance/trace/Interaction` </td>
			<td>Method changed</td>
			<td> `Interaction.filter` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.getAllInteractionMeasurements` </td>
			<td> `sap/ui/performance/trace/Interaction` </td>
			<td>Method changed</td>
			<td> `Interaction.getAll` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.getPendingInteractionMeasurement` </td>
			<td> `sap/ui/performance/trace/Interaction` </td>
			<td>Method changed</td>
			<td> `Interaction.getPending` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.measure.startInteraction` </td>
			<td> `sap/ui/performance/trace/Interaction` </td>
			<td>Method changed</td>
			<td> `Interaction.start` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.fesr.getCurrentTransactionId` </td>
			<td> `sap/ui/performance/trace/Passport` </td>
			<td>Method changed</td>
			<td> `Passport.getTransactionId` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.fesr.getRootId` </td>
			<td> `sap/ui/performance/trace/Passport` </td>
			<td>Method changed</td>
			<td> `Passport.getRootId` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.passport.*` </td>
			<td> `sap/ui/performance/trace/Passport` </td>
			<td>Simple replacement</td>
			<td> `Passport.*` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.getModulePath` </td>
			<td>-</td>
			<td>Complex replacement</td>
			<td> 

```
sap.ui.require.toUrl("some/path/to/module.js");
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.getResourcePath` </td>
			<td>-</td>
			<td>Complex replacement</td>
			<td> 

```
sap.ui.require.toUrl("some/path/to/resource.json");
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.FrameOptions` </td>
			<td> `sap/ui/security/FrameOptions` </td>
			<td>Simple replacement</td>
			<td> `FrameOptions` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.act` </td>
			<td> `sap/ui/util/ActivityDetection` </td>
			<td>Simple replacement</td>
			<td> `ActivityDetection` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.initMobile` </td>
			<td> `sap/ui/util/Mobile` </td>
			<td>Method changed</td>
			<td> `Mobile.init` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.setIcons` </td>
			<td> `sap/ui/util/Mobile` </td>
			<td>Simple replacement</td>
			<td> `Mobile.setIcons` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.setMobileWebAppCapable` </td>
			<td> `sap/ui/util/Mobile` </td>
			<td>Simple replacement</td>
			<td> `Mobile.setWebAppCabable` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.storage` </td>
			<td> `sap/ui/util/Storage` </td>
			<td>Method changed</td>
			<td> `Storage` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.storage.Type.*` </td>
			<td> `sap/ui/util/Storage` </td>
			<td>Simple replacement</td>
			<td> `Storage.Type` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.getParseError` </td>
			<td> `sap/ui/util/XMLHelper` </td>
			<td>Simple replacement</td>
			<td> `Helper.getParseError` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.parseXML` </td>
			<td> `sap/ui/util/XMLHelper` </td>
			<td>Method changed</td>
			<td> `Helper.parse` </td>
		</tr>
		<tr>
			<td> `jQuery.sap.serializeXML` </td>
			<td> `sap/ui/util/XMLHelper` </td>
			<td>Method changed</td>
			<td> `Helper.serialize` </td>
		</tr>
	</tbody>
</table>

***

#### Replacement with Native Browser APIs

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Old API Call</th>
			<th>New Native Replacement</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>`jQuery.device.is.standalone`</td>
			<td> 

```
window.navigator.standalone
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.inArray`</td>
			<td> 

```
var b = (aElements ? Array.prototype.indexOf.call(aElements, 4) : -1);
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.isArray`</td>
			<td> 

```
Array.isArray
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.sap.clearDelayedCall`</td>
			<td> 

```
window.clearTimout
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.sap.clearIntervalCall`</td>
			<td> 

```
window.clearInterval
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.sap.delayedCall`</td>
			<td> 

```
window.setTimeout
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.sap.domById`</td>
			<td> 

```
window.document.getElementById
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.sap.endsWith`</td>
			<td> 

```
sMyString.endsWith("abc")
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.sap.endsWithIgnoreCase`</td>
			<td> 

```
sMyString.toLowerCase().endsWith(sMyOtherString.toLowerCase())
```
			</td>
		</tr>
		<tr>
			<td>`jQuery.sap.getter`</td>
			<td> 

```
function(value) { return function() { return value; }; }(myValue);
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.intervalCall` </td>
			<td> 

```
window.setInterval
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.isEqualNode` </td>
			<td> 

```
Node.isEqualNode
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.newObject` </td>
			<td> 

```
Object.create
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.padLeft` </td>
			<td> 

```
"a".padStart(110, "0");
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.padRight` </td>
			<td> 

```
"a".padEnd(110, "0");
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.resources.isBundle` </td>
			<td> 

```
instanceof
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.startsWith` </td>
			<td> 

```
sMyString.startsWith("abc");
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.sap.startsWithIgnoreCase` </td>
			<td> 

```
sMyString.toLowerCase().startsWith(sMyOtherString.toLowerCase())
```
			</td>
		</tr>
		<tr>
			<td> `jQuery.support.retina` </td>
			<td> 

```
window.devicePixelRatio >= 2
```
			</td>
		</tr>
	</tbody>
</table>

***

#### jQuery Extensions Dependencies

jQuery extensions have been extracted into different modules. If the jQuery extension is required, it needs to be added to the module dependencies.

> Note:
> Change from the global dependencies to adding the module dependencies to the jQuery extensions:
> 
> ![](loioff6352e35e6a4b9a9c16ee3c1fa4d740_LowRes.png)
> 
> 

|jQuery Call|Old Module|New Module|
|-----------|----------|----------|
| `jQuery.*` | `jQuery.sap.global` | `sap/ui/thirdparty/jquery` |
| `jQuery.position` | `jQuery.sap.global` | `sap/ui/thirdparty/jqueryui/jquery-ui-position` |
| `jQuery.fn.control` | `jquery.sap.ui` | `sap/ui/dom/jquery/control` |
| `jQuery.fn.addLabelledBy` | `jquery.sap.dom` | `sap/ui/dom/jquery/Aria` |
| `jQuery.fn.removeLabelledBy` | `jquery.sap.dom` | `sap/ui/dom/jquery/Aria` |
| `jQuery.fn.addDescribedBy` | `jquery.sap.dom` | `sap/ui/dom/jquery/Aria` |
| `jQuery.fn.removeDescribedBy` | `jquery.sap.dom` | `sap/ui/dom/jquery/Aria` |
| `jQuery.fn.cursorPos` | `jquery.sap.dom` | `sap/ui/dom/jquery/cursorPos` |
| `jQuery.fn.firstFocusableDomRef` | `jquery.sap.dom` | `sap/ui/dom/jquery/Focusable` |
| `jQuery.fn.lastFocusableDomRef` | `jquery.sap.dom` | `sap/ui/dom/jquery/Focusable` |
| `jQuery.fn.getSelectedText` | `jquery.sap.dom` | `sap/ui/dom/jquery/getSelectedText` |
| `jQuery.fn.hasTabIndex` | `jquery.sap.dom` | `sap/ui/dom/jquery/hasTabIndex` |
| `jQuery.fn.parentByAttribute` | `jquery.sap.dom` | `sap/ui/dom/jquery/parentByAttribute` |
| `jQuery.fn.rect` | `jquery.sap.dom` | `sap/ui/dom/jquery/rect` |
| `jQuery.fn.rectContains` | `jquery.sap.dom` | `sap/ui/dom/jquery/rectContains` |
| `jQuery.fn.scrollLeftRTL` | `jquery.sap.dom` | `sap/ui/dom/jquery/scrollLeftRTL` |
| `jQuery.fn.scrollRightRTL` | `jquery.sap.dom` | `sap/ui/dom/jquery/scrollRightRTL` |
| `jQuery.fn.enableSelection` | `jquery.sap.dom` | `sap/ui/dom/jquery/Selection` |
| `jQuery.fn.disableSelection` | `jquery.sap.dom` | `sap/ui/dom/jquery/Selection` |
| `:sapTabbable, :focusable, :sapFocusable` | `jquery.sap.dom` | `sap/ui/dom/jquery/Selectors` |
| `jQuery.fn.selectText` | `jquery.sap.dom` | `sap/ui/dom/jquery/selectText` |
| `jQuery.fn.zIndex` | `jquery.sap.dom` | `sap/ui/dom/jquery/zIndex` |

