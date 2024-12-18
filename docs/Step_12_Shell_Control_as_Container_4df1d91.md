<!-- loio4df1d914e52d4b1aa0805eb01522537e -->

| loio |
| -----|
| 4df1d914e52d4b1aa0805eb01522537e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/4df1d914e52d4b1aa0805eb01522537e) | [demo kit latest release](https://sdk.openui5.org/topic/4df1d914e52d4b1aa0805eb01522537e)</div>

## Step 12: Shell Control as Container

Now we use a shell control as container for our app and use it as our new root element. The shell takes care of visual adaptation of the application to the device's screen size by introducing a so-called letterbox on desktop screens.

***

### Preview

  
  
**The app is now run in a shell that limits the app width**

![The graphic has an explanatory text.](images/loioa1f1b53df7bb4f74958cdf56904c4af4_LowRes.png "The app is now run in a shell that limits the app width")

***

<a name="loio4df1d914e52d4b1aa0805eb01522537e__section_qsr_xp2_syb"/>

### Coding

You can view and download all files at [Walkthrough - Step 12](https://sdk.openui5.org/entity/sap.m.tutorial.walkthrough/sample/sap.m.tutorial.walkthrough.12).

***

<a name="loio4df1d914e52d4b1aa0805eb01522537e__section_rsr_xp2_syb"/>

### webapp/view/App.view.xml

```xml
<mvc:View
	controllerName="ui5.walkthrough.controller.App"
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc"
	displayBlock="true">
	<Shell>
		<App>
			<pages>
				<Page title="{i18n>homePageTitle}">
					<content>
						<Panel
							headerText="{i18n>helloPanelTitle}">
							<content>
								<Button
									text="{i18n>showHelloButtonText}"
									press=".onShowHello"/>
								<Input
									value="{/recipient/name}"
									description="Hello {/recipient/name}"
									valueLiveUpdate="true"
									width="60%"/>
							</content>
						</Panel>
					</content>
				</Page>
			</pages>
		</App>
	</Shell>
</mvc:View>
```

The shell control is now the outermost control of our app and automatically displays a so-called letterbox, if the screen size is larger than a certain width.

> ### Note:  
> We don't add the `Shell` control to the declarative UI definition in the XML view if apps run in an external shell, like the SAP Fiori launchpad that already has a shell around the component UI.

There are further options to customize the shell, like setting a custom background image or color and setting a custom logo. Check the related API reference for more details.

**Parent topic:**[Walkthrough Tutorial \(JavaScript\)](Walkthrough_Tutorial_JavaScript_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:**[Step 11: Pages and Panels](Step_11_Pages_and_Panels_3b9d9f8.md "After all the work on the app structure it's time to improve the look of our app. We will use two controls from the sap.m library to add a bit more &quot;bling&quot; to our UI. You will also learn about control aggregations in this step.")

**Previous:**[Step 13: Margins and Paddings](Step_13_Margins_and_Paddings_17b87fb.md "Our app content is still glued to the corners of the letterbox. To fine-tune our layout, we can add margins and paddings to the controls that we added in the previous step.")

**Related Information**  


[API Reference: `sap.m.Shell`](https://sdk.openui5.org/api/sap.m.Shell)

