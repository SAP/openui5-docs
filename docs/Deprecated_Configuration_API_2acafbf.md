<!-- loio2acafbfcc2cb47e8aac6d2e32399af10 -->

| loio |
| -----|
| 2acafbfcc2cb47e8aac6d2e32399af10 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/2acafbfcc2cb47e8aac6d2e32399af10) | [demo kit latest release](https://sdk.openui5.org/topic/2acafbfcc2cb47e8aac6d2e32399af10)</div>

## Deprecated Configuration API

This page describes important aspects of the deprecation of the `sap.ui.core.Configuration` API facade. It shows a migration path away from the deprecated legacy APIs and towards their future-proof alternatives, provided the functionality is still meant for productive usage.

***

<a name="loio2acafbfcc2cb47e8aac6d2e32399af10__section_msd_jb4_rzb"/>

### Overview of Deprecated API Methods of `Configuration`

The following is an alphabetical list of API methods on `sap.ui.core.Configuration`. Meant as a compact and practical overview, it is derived from the [API Reference](https://sdk.openui5.org/api/sap.ui.core.Configuration), which may provide complementary information.


<table>
<tr>
<th valign="top">

Legacy API Method on Configuration

</th>
<th valign="top">

New Module

</th>
<th valign="top">

Replace With

</th>
</tr>
<tr>
<td valign="top">

`applySettings`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement.

This API method, which was typically used via `sap.ui.getCore().getConfiguration().applySettings()`, is superseded by different dedicated facade modules addressing the corresponding topics.It's therefore not possible to use a generic pattern to replace these calls.

Check the API documentation of `sap.ui.core.Configuration` and use the references below to find the correct replacement.

</td>
</tr>
<tr>
<td valign="top">

`getAccessibility`

</td>
<td valign="top">

[`sap/ui/core/ControlBehavior`](https://sdk.openui5.org/api/module:sap/ui/core/ControlBehavior) 

</td>
<td valign="top">

[`ControlBehavior.isAccessibilityEnabled()`](https://sdk.openui5.org/api/module:sap/ui/core/ControlBehavior%23methods/sap/ui/core/ControlBehavior.isAccessibilityEnabled) 

</td>
</tr>
<tr>
<td valign="top">

`getActiveTerminologies`

</td>
<td valign="top">

[`sap/base/i18n/Localization`](https://sdk.openui5.org/api/module:sap/base/i18n/Localization) 

</td>
<td valign="top">

[`Localization.getActiveTerminologies()`](https://sdk.openui5.org/api/module:sap/base/i18n/Localization%23methods/sap/base/i18n/Localization.getActiveTerminologies) 

</td>
</tr>
<tr>
<td valign="top">

`getAllowlistService`

</td>
<td valign="top">

[`sap/ui/security/Security`](https://sdk.openui5.org/api/module:sap/ui/security/Security) 

</td>
<td valign="top">

[`Security.getAllowlistService()`](https://sdk.openui5.org/api/module:sap/ui/security/Security%23methods/sap/ui/security/Security.getAllowlistService) 

</td>
</tr>
<tr>
<td valign="top">

`getAnimation`

</td>
<td valign="top">

[`sap/ui/core/ControlBehavior`](https://sdk.openui5.org/api/module:sap/ui/core/ControlBehavior) 

</td>
<td valign="top">

[`ControlBehavior.getAnimationMode()`](https://sdk.openui5.org/api/module:sap/ui/core/ControlBehavior%23methods/sap/ui/core/ControlBehavior.getAnimationMode) 

</td>
</tr>
<tr>
<td valign="top">

`getAnimationMode`

</td>
<td valign="top">

[`sap/ui/core/ControlBehavior`](https://sdk.openui5.org/api/module:sap/ui/core/ControlBehavior) 

</td>
<td valign="top">

[`ControlBehavior.getAnimationMode()`](https://sdk.openui5.org/api/module:sap/ui/core/ControlBehavior%23methods/sap/ui/core/ControlBehavior.getAnimationMode) 

</td>
</tr>
<tr>
<td valign="top">

`getAppCacheBuster`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getAppCacheBusterMode`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getApplication`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement. Use [`sap/ui/core/ComponentSupport`](https://sdk.openui5.org/api/module:sap/ui/core/ComponentSupport) instead. See also [Declarative API for Initial Components](Declarative_API_for_Initial_Components_82a0fce.md).

</td>
</tr>
<tr>
<td valign="top">

`getAutoAriaBodyRole`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getCalendarType`

</td>
<td valign="top">

[`sap/base/i18n/Formatting`](https://sdk.openui5.org/api/module:sap/base/i18n/Formatting) 

</td>
<td valign="top">

[`Formatting.getCalendarType()`](https://sdk.openui5.org/api/module:sap/base/i18n/Formatting%23methods/sap/base/i18n/Formatting.getCalendarType) 

</td>
</tr>
<tr>
<td valign="top">

`getCalendarWeekNumbering`

</td>
<td valign="top">

[`sap/base/i18n/Formatting`](https://sdk.openui5.org/api/module:sap/base/i18n/Formatting) 

</td>
<td valign="top">

[`Formatting.getCalendarWeekNumbering()`](https://sdk.openui5.org/api/module:sap/base/i18n/Formatting%23methods/sap/base/i18n/Formatting.getCalendarWeekNumbering) 

</td>
</tr>
<tr>
<td valign="top">

`getCompatibilityVersion`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getDebug`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getFileShareSupport`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getFiori2Adaptation`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getFlexibilityServices`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getFormatLocale`

</td>
<td valign="top">

[`sap/base/i18n/Formatting`](https://sdk.openui5.org/api/module:sap/base/i18n/Formatting) 

</td>
<td valign="top">

[`Formatting.getLanguageTag()`](https://sdk.openui5.org/api/module:sap/base/i18n/Formatting%23methods/sap/base/i18n/Formatting.getLanguageTag)

The new API returns an [`sap/base/i18n/LanguageTag`](https://sdk.openui5.org/api/module:sap/base/i18n/LanguageTag). There are two possibilities to replace the deprecated API calls using the new formatting API:

-   Either you replace the deprecated API by transforming the retrieved new `LanguageTag` into an [`sap/ui/core/Locale`](https://sdk.openui5.org/api/sap.ui.core.Locale). To do so, require `sap/ui/core/Locale` and pass the `LanguageTag` as a parameter to the `Locale` constructor.

-   Alternatively, you adjust the usage of the locale to the new `LanguageTag` API.

> ### Example:  
> ```
> // either transform LanguageTag into Locale and use as before
> sap.ui.require([
>     "sap/base/i18n/Formatting",
>     "sap/ui/core/Locale"
> ], (Formatting, Locale) => {
>     // Transform LanguageTag to Locale
>     const oFormatLocale = new Locale(Formatting.getLanguageTag());
>     const sFormatLanguage = oFormatLocale.getLanguage();
> });
>  
> // or adjust usage of Locale to LanguageTag API
> sap.ui.require([
>     "sap/base/i18n/Formatting"
> ], (Formatting) => {
>     const oFormatLanguageTag = Formatting.getLanguageTag();
>     const sFormatLanguage = oFormatLanguageTag.language;
> });
> ```



</td>
</tr>
<tr>
<td valign="top">

`getFormatSettings`

</td>
<td valign="top">

[`sap/base/i18n/Formatting`](https://sdk.openui5.org/api/module:sap/base/i18n/Formatting) 

</td>
<td valign="top">

[`Formatting`](https://sdk.openui5.org/api/module:sap/base/i18n/Formatting%23methods/Summary)

The `getFormatSettings` API is superseded by the `Formatting` facade itself.

> ### Example:  
> ```
> sap.ui.require([
>     "sap/base/i18n/Formatting",
>     "sap/base/i18n/date/CalendarType"
> ], (Formatting, CalendarType) => {
>     Formatting.setCalendarType(CalendarType.Islamic);
> });
> ```



</td>
</tr>
<tr>
<td valign="top">

`getFrameOptions`

</td>
<td valign="top">

[`sap/ui/security/Security`](https://sdk.openui5.org/api/module:sap/ui/security/Security) 

</td>
<td valign="top">

[`Security.getFrameOptions()`](https://sdk.openui5.org/api/module:sap/ui/security/Security%23methods/sap/ui/security/Security.getFrameOptions) 

</td>
</tr>
<tr>
<td valign="top">

`getInspect`

</td>
<td valign="top">

\-

</td>
<td valign="top">

Deprecated without replacement

</td>
</tr>
<tr>
<td valign="top">

`getLanguage`

</td>
<td valign="top">

[`sap/base/i18n/Localization`](https://sdk.openui5.org/api/module:sap/base/i18n/Localization) 

</td>
<td valign="top">

[`Localization.getLanguage()`](https://sdk.openui5.org/api/module:sap/base/i18n/Localization%23methods/sap/base/i18n/Localization.getLanguage) 

</td>
</tr>
<tr>
<td valign="top">

`getLanguageTag`

</td>
<td valign="top">

[`sap/base/i18n/Localization`](https://sdk.openui5.org/api/module:sap/base/i18n/Localization) 

</td>
<td valign="top">

`Localization.getLanguageTag().toString()` 

</td>
</tr>
</table>

