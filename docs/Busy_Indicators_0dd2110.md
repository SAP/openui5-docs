<!-- loio0dd211065c714c0d8a35cecb5fea8557 -->

| loio |
| -----|
| 0dd211065c714c0d8a35cecb5fea8557 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/0dd211065c714c0d8a35cecb5fea8557) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/0dd211065c714c0d8a35cecb5fea8557)</div>

## Busy Indicators

You use busy indicators to inform users that something is going on in the background, for example, some data is being fetched from the back end and the user has to wait. As long as the busy indicator is shown, either all or a specific part of the UI is blocked, and no user interaction is possible.

Whenever busy indication is triggered, the default delay until the busy indicator is displayed on the UI is 1000 ms \(1 second\). If this delay were not in place, the busy indicator would always be displayed, even if there is no negotiable waiting time.

You can choose between the following busy indicators, depending on your use case:

-   `sap.ui.core.BusyIndicator`

-   `sap.m.BusyDialog`

-   `sap.m.BusyIndicator`


***

### Blocking the Whole UI

You can use the `sap.ui.core.BusyIndicator` busy indicator to block the whole UI. You can set the delay in ms by specifying the number:

``` js
sap.ui.core.BusyIndicator.show(*HIGHLIGHT START*<number>*HIGHLIGHT END*);
```

To release the UI again, the busy indication must be hidden again. This function call hides the busy indication immediately:

``` js
sap.ui.core.BusyIndicator.hide();
```

[API Reference: `sap.ui.core.BusyIndicator`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.BusyIndicator.html)

***

### Busy Indication with Dialog

With the `sap.m.BusyDialog` busy indicator, you can block the whole UI like you do with `sap.ui.core.BusyIndicator`, but you can also show a dialog box. In this dialog box, you can also include a *Cancel* button that users can choose to stop the activity that's running in the background.

[API Reference: `sap.m.BusyDialog`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.BusyDialog.html)

[API Overview and Samples: `sap.m.BusyDialog`](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.BusyDialog/samples)

***

### Busy Indication on Control Level

The `sap.m.BusyIndicator` busy indicator blocks specific UI areas that are defined by a control. For example, if a table in a complex UI is loading, only the table is blocked - the user can still carry on working with the rest of the UI.

If a control is set to busy, the complete control will be covered with a block layer, so no mouse events or keyboard interaction with the control are possible. If keyboard navigation is being used to step through the controls, controls that are set to `busy` are skipped and the focus jumps to the next control.

Here's how to do it:

``` js
	var oInput = new sap.m.Input({
		value:'Hello World'
	});
...
	*HIGHLIGHT START*oInput.setBusy(true);*HIGHLIGHT END*

```

The following code shows how you define the default state of a control as `busy` so that it will be displayed as busy when it has been rendered:

``` js
	var oInput = new sap.m.Input({
		value:'Hello World',
		*HIGHLIGHT START*busy: true
*HIGHLIGHT END*
	});

```

To release the control's busy state again, the same API can be used. This has to be done by the application after some data has been loaded, for example with the following command:

``` js
oMyListBox.setBusy(false);
```

To change the default delay of the local busy indicator, use:

``` js
oMyListBox.setBusyIndicatorDelay(*HIGHLIGHT START*<number>*HIGHLIGHT END*);
```

[API Reference: `sap.m.BusyIndicator`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.BusyIndicator.html)

[API Overview and Samples: `sap.m.BusyIndicator`](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.BusyIndicator/samples)

[API Overview and Samples: `sap.ui.core.Control`](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.core.Control/samples)

