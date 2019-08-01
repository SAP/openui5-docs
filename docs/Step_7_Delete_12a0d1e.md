<!-- loio12a0d1ef150a42ef81e9f07fe6407018 -->

| loio |
| -----|
| 12a0d1ef150a42ef81e9f07fe6407018 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/12a0d1ef150a42ef81e9f07fe6407018) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/12a0d1ef150a42ef81e9f07fe6407018)</div>

## Step 7: Delete

In this step, we make it possible to delete user data.

***

<a name="loio12a0d1ef150a42ef81e9f07fe6407018__section_bt4_fxc_z1b"/>

### Preview

   
  
A new *Delete User* button is added<a name="loio12a0d1ef150a42ef81e9f07fe6407018__fig_m3r_hbx_4cb"/>

 ![](loio32509f45ef8549998c73af49b8cfaa01_LowRes.png "A new Delete User button is added") 

***

<a name="loio12a0d1ef150a42ef81e9f07fe6407018__section_tsr_gxc_z1b"/>

### Coding

You can view and download all files at [OData V4 - Step 7](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.odatav4.07/preview).

***

<a name="loio12a0d1ef150a42ef81e9f07fe6407018__section_pvc_fyc_z1b"/>

### webapp/App.controller.js

```
		*HIGHLIGHT START*onDelete : function () {
			var oSelected = this.byId("peopleList").getSelectedItem();

			if (oSelected) {
				oSelected.getBindingContext().delete("$auto").then(function () {
					MessageToast.show(this._getText("deletionSuccessMessage"));
				}.bind(this), function (oError) {
					MessageBox.error(oError.message);
				});
			}
		},*HIGHLIGHT END*
```

We add the `onDelete` event handler to the controller. In the event handler, we check whether an item is selected in the table and if so, the related data is deleted from the model. To do that, we retrieve the binding context of the selection and call its `delete` method.

We explicitly set the update group ID for the deletion to **$auto** to make sure that the request to the service is sent immediately as a batch request. Otherwise the `delete` function would apply the deferred batch processing that we defined for the table’s list binding event though, `delete` does not currently support deferred batch processing.

***

<a name="loio12a0d1ef150a42ef81e9f07fe6407018__section_pp2_mxc_z1b"/>

### webapp/App.view.xml

```
<mvc:View
	controllerName="sap.ui.core.tutorial.odatav4.controller.App"
	displayBlock="true"
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<Shell>
		<App busy="{appView>/busy}" class="sapUiSizeCompact">
			<pages>
				<Page title="{i18n>peoplePageTitle}">
					<content>
						<Table
							id="peopleList"
							growing="true"
							growingThreshold="10"
							items="{
								path: '/People',
								parameters: {
									$count: true,
									$$updateGroupId : 'peopleGroup'
								}
							}"
*HIGHLIGHT START*							mode="SingleSelectLeft">*HIGHLIGHT END*
							<headerToolbar>
								<OverflowToolbar>
									<content>
										<ToolbarSpacer/>
										<SearchField
										.../>
										<Button
										.../>
*HIGHLIGHT START*										<Button
											id="deleteUserButton"
											icon="sap-icon://delete"
											tooltip="{i18n>deleteButtonText}"
											press=".onDelete">
											<layoutData>
												<OverflowToolbarLayoutData priority="NeverOverflow"/>
											</layoutData>
										</Button>*HIGHLIGHT END*
										<Button
										.../>
										<Button
										...>
									</content>
								</OverflowToolbar>
							</headerToolbar>
							<columns>
								...
							</columns>
							<items>
								...
							</items>
						</Table>
					</content>
					<footer>
						...
					</footer>
				</Page>
			</pages>
		</App>
	</Shell>
</mvc:View>
```

We change the `mode` of the table to `SingleSelectLeft` to make it possible to select a row.

We add the *Delete* button to the toolbar. With the `OverflowToolbarLayoutData priority="NeverOverflow"` parameter, we make sure that the button is always visible.

***

<a name="loio12a0d1ef150a42ef81e9f07fe6407018__section_kl4_d1x_4cb"/>

### webapp/i18n/i18n.properties

``` prefs
...
# Toolbar
...
*HIGHLIGHT START*#XBUT: Button text for delete user
deleteButtonText=Delete User*HIGHLIGHT END*
...
# Messages
...
*HIGHLIGHT START*#XMSG: Message for user deleted
deletionSuccessMessage=User deleted*HIGHLIGHT END*
...
```

We add the missing texts to the properties file.

**Related information**  


[Deleting an Entity](Deleting_an_Entity_2613ebc.md)

