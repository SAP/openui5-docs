<!-- loio5826c0c2e47c4507ba0eeb26332c33a2 -->

| loio |
| -----|
| 5826c0c2e47c4507ba0eeb26332c33a2 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/5826c0c2e47c4507ba0eeb26332c33a2) | [demo kit latest release](https://sdk.openui5.org/topic/5826c0c2e47c4507ba0eeb26332c33a2)</div>

## Step 13: Margins and Paddings \(TypeScript\)

Our app content is still glued to the corners of the letterbox. To fine-tune our layout, we can add margins and paddings to the controls that we added in the previous step.

Instead of manually adding CSS to the controls, we will use the standard classes provided by OpenUI5. These classes take care of consistent sizing steps, left-to-right support, and responsiveness.

***

### Preview

  
  
**The layout of the panel and its content now has margins and padding**

![](images/loio0becf3ee81f5486a864e3b39ba036402_LowRes.png "The layout of the panel and its content now has margins and padding")

***

<a name="loio5826c0c2e47c4507ba0eeb26332c33a2__section_wl1_jq2_syb"/>

### Coding

You can view all files at [OpenUI5 TypeScript Walkthrough - Step 13: Margins and Paddings](https://github.com/sap-samples/ui5-typescript-walkthrough/tree/main/steps/13) and [download the solution as a zip file](https://sap-samples.github.io/ui5-typescript-walkthrough/ui5-typescript-walkthrough-step-13.zip).

***

<a name="loio5826c0c2e47c4507ba0eeb26332c33a2__section_xl1_jq2_syb"/>

### webapp/view/App.view.xml

To layout the panel, we add the CSS class `sapUiResponsiveMargin` that will add some space around the panel. We have to set the width of the panel to `auto` since the margin would otherwise be added to the default width of 100% and exceed the page size.

If you decrease the screen size, then you can actually see that the margin also decreases. As the name suggests, the margin is responsive and adapts to the screen size of the device. Tablets will get a smaller margin and phones in portrait mode will not get a margin to save space on these small screens.

Margins can be added to all kinds of controls and are available in many different options. We can even add space between the button and the input field by adding class `sapUiSmallMarginEnd` to the button.

To format the output text individually, we remove the description from the input field and add a new `Text` control with the same value. Here we also use a small margin to align it with the other content. Similarly, we could add the standard padding classes to layout the inner parts of container controls such as our panel, but as it already brings a padding by default, this is not needed here.

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
							headerText="{i18n>helloPanelTitle}"
							class="sapUiResponsiveMargin"
							width="auto">
							<content>
								<Button
									text="{i18n>showHelloButtonText}"
									press=".onShowHello"
									class="sapUiSmallMarginEnd"/>
								<Input
									value="{/recipient/name}"
									valueLiveUpdate="true"
									width="60%"/>
								<Text
									text="Hello {/recipient/name}"
									class="sapUiSmallMargin"/>
							</content>
						</Panel>
					</content>
				</Page>
			</pages>
		</App>
	</Shell>
</mvc:View>
```

***

### Conventions

-   Use the standard OpenUI5 CSS classes for the layout if possible.


**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 12: Shell Control as Container \(TypeScript\)](Step_12_Shell_Control_as_Container_TypeScript_4af44cb.md "Now we use a shell control as container for our app and use it as our new root element. The shell takes care of visual adaptation of the application to the device's screen size by introducing a so-called letterbox on desktop screens.")

**Previous:**[Step 14: Custom CSS and Theme Colors \(TypeScript\)](Step_14_Custom_CSS_and_Theme_Colors_TypeScript_4cc841e.md "Sometimes we need to define some more fine-granular layouts and this is when we can use the flexibility of CSS by adding custom style classes to controls and style them as we like.")

**Related Information**  


[Using Predefined CSS Margin Classes](Using_Predefined_CSS_Margin_Classes_777168f.md "OpenUI5 gives you the option of adding spacing in between controls by adding a margin. A margin clears an area around its respective control, outside of its border.")

[Using Container Content Padding CSS Classes](Using_Container_Content_Padding_CSS_Classes_c71f6df.md "For many container controls in OpenUI5, such as a Dialog or a Page, you can define whether the container should have a padding within the content area. A padding clears the area between the container layout and the controls that are displayed in the content area.")

