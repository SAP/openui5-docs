<!-- loio5cb1169c748b4da58a9c981fb0b491c7 -->

| loio |
| -----|
| 5cb1169c748b4da58a9c981fb0b491c7 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5cb1169c748b4da58a9c981fb0b491c7) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5cb1169c748b4da58a9c981fb0b491c7)</div>

## Busy Indication

The Worklist app implements a busy indication concept as specified by the SAP Fiori Design Guidelines.

Calling the app will result in the following:

-   Only initially a global busy indicator is displayed that overlays the whole app until the metadata of the service is loaded.

-   A local busy indicator is displayed on the worklist table or on the page of the object view while the data from the service is loading.

-   When controls are loading additional data or getting refreshed, a local busy indication is displayed automatically.


By default, the busy indicator delay is set to one second for all controls. This would first show the UI for a second, then show a busy indication until the data is loaded. To avoid this behavior initially and show the busy indicator immediately without delay the following concept is implemented in the app: The `busyIndicatorDelay` and `busy` properties of certain controls \(`AppView`, `Table` on the *Worklist* page, `FullScreenPage` on the *Object* page\) are bound to the local view model and manipulated in the controllers of the app. The delay is initially set to "0" for displaying the busy indicator immediately, and reset to the previous value after the initial loading is done.

> Note:
> You can find more information about busy indicators, busy states, and busy handling in general in the [SAP Fiori Design Guidelines](https://experience.sap.com/fiori-design/).
> 
> 

