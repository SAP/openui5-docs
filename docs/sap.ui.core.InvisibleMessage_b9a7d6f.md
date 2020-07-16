<!-- loiob9a7d6f607f049988797b68b65e60901 -->

| loio |
| -----|
| b9a7d6f607f049988797b68b65e60901 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b9a7d6f607f049988797b68b65e60901) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b9a7d6f607f049988797b68b65e60901)</div>

## sap.ui.core.InvisibleMessage

The Invisible Message class provides a way to grammatically expose dynamic content changes in a way that can be announced by screen readers.

This class is experimental and the API might be changed in future.

***

The `sap.ui.core.InvisibleMessage` enables developers to specify the message to be announced when something dynamically changes on the user interface. In this manner, the class allows control and application developers to improve the usability of the applications, by sending dedicated messages to the screen reader users.

***

<a name="loiob9a7d6f607f049988797b68b65e60901__section_v25_cwt_3mb"/>

### Usage

This class is a singleton. The class instance can be retrieved via the static method `sap.ui.core.InvisibleMessage.getInstance()`. The sap.ui.core.InvisibleMessage is designed to be used both internally in the controls logic and from the applications.

Using the service, you have to specify the message to be announced by the screen reader and the mode which will be inserted in the aria-live attribute via the `sap.ui.core.InvisibleMessage.announce(sText, sMode)` method. The possible modes to choose from are:

-   `sap.ui.core.InvisibleMessageMode.Polite` - Indicates that updates to the region should be presented at the next graceful opportunity, such as at the end of reading the current sentence, or when the user pauses typing.

-   `sap.ui.core.InvisibleMessageMode.Assertive` - Indicates that updates to the region have the highest priority and should be presented to the user immediately.


Keep in mind that according to the ARIA standard, the live regions should be presented on page load and should be empty. Thus, we recommend to instantiate `sap.ui.core.InvisibleMessage` via `sap.ui.core.InvisibleMessage.getInstance()` as early as possible in the application logic – with the Component initialization, with the main Controller initialization, after Core initialization, ect. Therefore the `sap.ui.core.InvisibleMessage` should be instantiated before the rest of the DOM tree \(controls\) get rendered, preferably in the `onBeforeRendering()`method of the control. Then, you should specify the text, that has to be announced by the screen reader, and the live region’s mode using the announce method.

