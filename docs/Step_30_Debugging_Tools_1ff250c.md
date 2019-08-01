<!-- loio1ff250c2038849f5991209f7e6c36f1f -->

| loio |
| -----|
| 1ff250c2038849f5991209f7e6c36f1f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1ff250c2038849f5991209f7e6c36f1f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1ff250c2038849f5991209f7e6c36f1f)</div>

## Step 30: Debugging Tools

Even though we have added a basic test coverage in the previous steps, it seems like we accidentally broke our app, because it does not display prices to our invoices anymore. We need to debug the issue and fix it before someone finds out.

Luckily, OpenUI5 provides a couple of debugging tools that we can use within the app to check the application logic and the developer tools of modern browsers are also quite good. We will now check for the root cause.

***

<a name="loio1ff250c2038849f5991209f7e6c36f1f__section_chj_s5x_31b"/>

### Preview

   
  
The diagnostics window<a name="loio1ff250c2038849f5991209f7e6c36f1f__fig_r1j_pst_mr"/>

 ![](loioc4e83f0e553c4314a1f24e13972e20df_HiRes.png "The diagnostics window") 

***

<a name="loio1ff250c2038849f5991209f7e6c36f1f__section_dhj_s5x_31b"/>

### Coding

You can view and download all files at [Walkthrough - Step 30](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.30/preview).

``` xml
<mvc:View
		controllerName="sap.ui.demo.walkthrough.controller.InvoiceList"
		xmlns="sap.m"
		xmlns:mvc="sap.ui.core.mvc">
	<List
			id="invoiceList"
			class="sapUiResponsiveMargin"
			width="auto"
			items="{
			path : 'invoice>/Invoices',
			sorter : {
				path : 'ShipperName',
				group : true
			}
		}">
		<headerToolbar>
			<Toolbar>
				<Title text="{i18n>invoiceListTitle}"/>
				<ToolbarSpacer/>
				<SearchField width="50%" search=".onFilterInvoices"/>
			</Toolbar>
		</headerToolbar>
		<items>
			<ObjectListItem
					title="{invoice>Quantity} x {invoice>ProductName}"
					number="{
					parts: [{path: 'invoice>*HIGHLIGHT START*ExTendedPrice'*HIGHLIGHT END*}, {path: 'view>/currency'}],
					type: 'sap.ui.model.type.Currency',
					formatOptions: {
						showMeasure: false
					}
				}"
				numberUnit="{view>/currency}"
					numberState="{=	${invoice>ExtendedPrice} > 50 ? 'Error' : 'Success' }">
				<attributes>
					<ObjectAttribute text="{
						path: 'invoice>Status',
						formatter: '.formatter.statusText'
					}"/>
				</attributes>
			</ObjectListItem>
		</items>
	</List>
</mvc:View>
```

We introduced a typo in the binding of the number attribute to simulate a frequent error; instead of using `'invoice>ExtendedPrice'` we use `'invoice>Ex**T**endedPrice'`. Now we call the app and notice that the price is actually missing. By pressing * CTRL ALT SHIFT S * we open the OpenUI5 support diagnostics tool and check the app.

> Note:
> If you use the Google Chrome browser, you can install the *UI5 Inspector* plugin. With this plugin, you can easily debug your - or OpenUI5-based apps. For more information, see [UI5 Inspector](UI5_Inspector_b24e724.md).
> 
> 

Besides technical information about the app and a trace that is similar to the developer tools console of the browser, there is a really handy tool for checking such errors in this dialog. Open the tab *Control Tree* by clicking on the expand symbol on the right.

A hierarchical tree of OpenUI5 controls is shown on the left and the properties of the selected control are displayed on the right. If we now select the first `ObjectListItem` control of the tree and go to the *Binding Infos* tab on the right, we can actually see that the binding path of the number attribute is marked as invalid. We can now correct the error in the view and the price should appear in the list of invoices again.

Sometimes errors are not as easy to spot and you actually need to debug the JavaScript code with the tools of the browser. For performance reasons, the OpenUI5 files are shipped in a minified version, this means that all possible variable names are shortened and comments are removed.

This makes debugging harder because the code is a lot less readable. You can load the debug sources by adding the URL parameter `sap-ui-debug=true` or by pressing * CTRL ALT SHIFT P * and select *Use Debug Sources* in the dialog box that is displayed. After reloading the page, you can see in the *Network* tab of the browser’s developer tools that now a lot of files with the `–dbg` suffix are loaded. These are the source code files that include comments and the uncompressed code of the app and the OpenUI5 artifacts.

   
  
Technical information dialog <a name="loio1ff250c2038849f5991209f7e6c36f1f__fig_vfz_xgf_yr"/>

 ![](loio8bf9780408674588af6d33eb6cebadab_LowRes.png "Technical information dialog ") 

For a more detailed explanation of the OpenUI5 support tools, go through the [Troubleshooting](Troubleshooting_5661952.md) tutorial.

If you're stuck and need help for some development task, you can also post a question in the OpenUI5-related forums, for example in the [SAP Community](https://www.sap.com/community/topic/ui5.html) or on [Stack Overflow](https://stackoverflow.com/search?q=sapui5).

***

<a name="loio1ff250c2038849f5991209f7e6c36f1f__section_lvc_gkw_31b"/>

### Conventions

-   As per OpenUI5 convention uncompressed source files end with `*-dbg.js`


**Related information**  


[Debugging](Debugging_.md#loioc9b0f8cca852443f9b8d3bf8ba5626ab)

[Diagnostics](Diagnostics_.md#loio6ec18e80b0ce47f290bc2645b0cc86e6)

[Technical Information Dialog](Technical_Information_Dialog_.md#loio616a3ef07f554e20a3adf749c11f64e9)

