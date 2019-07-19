<!-- loioa3e7cb6f671b4b839f37eb5f88429e41 -->

| loio |
| -----|
| a3e7cb6f671b4b839f37eb5f88429e41 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a3e7cb6f671b4b839f37eb5f88429e41) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a3e7cb6f671b4b839f37eb5f88429e41)</div>

## Step 8: OData Operations

Our OData service provides one OData operation: the `ResetDataSource` action. In this step, we add a button that resets all data changes we made during the tutorial to their original state using this action.

***

<a name="loioa3e7cb6f671b4b839f37eb5f88429e41__section_bt4_fxc_z1b"/>

### Preview

   
  
A *Restart Tutorial* button is added<a name="loioa3e7cb6f671b4b839f37eb5f88429e41__fig_ybl_pdx_4cb"/>

 ![](loioe518debe1cdc4fcd9f5a6cffd014fbfa_LowRes.png "A Restart Tutorial button is added") 

***

<a name="loioa3e7cb6f671b4b839f37eb5f88429e41__section_tsr_gxc_z1b"/>

### Coding

You can view and download all files at [OData V4 - Step 8](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.odatav4.08/preview).

***

<a name="loioa3e7cb6f671b4b839f37eb5f88429e41__section_pvc_fyc_z1b"/>

### webapp/controller/App.controller.js

``` js
...
		onResetChanges : function () {
			this.byId("peopleList").getBinding("items").resetChanges();
			this._setUIChanges();
		},

		*HIGHLIGHT START*onResetDataSource : function () {
			var oModel = this.getView().getModel(),
				oOperation = oModel.bindContext("/ResetDataSource(...)");

			oOperation.execute().then(function () {
					oModel.refresh();
					MessageToast.show(this._getText("sourceResetSuccessMessage"));
				}.bind(this), function (oError) {
					MessageBox.error(oError.message);
				}
			);
		},*HIGHLIGHT END*

		onSave : function () {
...

```

The `onResetDataSource` event handler calls the `ResetDataSource` action, which is an action of the *TripPin* OData service that resets the data of the service to its original state.

We call that action by first creating a deferred operation binding on the model. The `(…)` part of the binding syntax marks the binding as deferred. We use a deferred binding because we want to control when the action is executed. Since it is deferred, we need to explicitly call its `execute` method.

The execution is asynchronous, therefore the execute method returns a `Promise`. We attach simple success and error handlers to that `Promise` by calling its `then` method.

> Note:
> Many of the methods in the OData V4 API of OpenUI5 return a `Promise` to manage asynchronous processing
> 
> 

***

<a name="loioa3e7cb6f671b4b839f37eb5f88429e41__section_pp2_mxc_z1b"/>

### webapp/view/App.view.xml

``` xml
<mvc:View
	controllerName="sap.ui.core.tutorial.odatav4.controller.App"
	displayBlock="true"
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<Shell>
		<App busy="{appView>/busy}" class="sapUiSizeCompact">
			<pages>
				<Page title="{i18n>peoplePageTitle}">
*HIGHLIGHT START*					<headerContent>
						<Button
							id="resetChangesButton"
							text="{i18n>resetChangesButtonText}"
							enabled="{= !${appView>/hasUIChanges}}"
							press="onResetDataSource"
							type="Emphasized">
						</Button>
					</headerContent>*HIGHLIGHT END*
...
```

We add the **headerContent** aggregation to the **Page** and insert the new **Button**. We add the **onResetDataSource** event handler to the **press** event.

***

<a name="loioa3e7cb6f671b4b839f37eb5f88429e41__section_kl4_d1x_4cb"/>

### webapp/i18n/i18n.properties

``` prefs
...
# Toolbar
...
*HIGHLIGHT START*#XBUT: Button text for reset changes
resetChangesButtonText=Restart Tutorial*HIGHLIGHT END*
...
# Messages
...
*HIGHLIGHT START*#XMSG: Message for changes reverted
sourceResetSuccessMessage=All changes reverted back to start*HIGHLIGHT END*
```

We add the missing texts to the properties file.

***

And now we are done! We built a simple application with user data from an OData V4 service. We can display, edit, create, and delete users. And we use OData V4 features such as batch groups and automatic type detection.

**Related information**  


[Bindings](Bindings_54e0ddf.md)

[OData Operations](OData_Operations_b54f789.md)

