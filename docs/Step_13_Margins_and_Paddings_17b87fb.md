<!-- loio17b87fbafb5a4474982760d2a3a73e69 -->

| loio |
| -----|
| 17b87fbafb5a4474982760d2a3a73e69 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/17b87fbafb5a4474982760d2a3a73e69) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/17b87fbafb5a4474982760d2a3a73e69)</div>

## Step 13: Margins and Paddings

Our app content is still glued to the corners of the letterbox. To fine-tune our layout, we can add margins and paddings to the controls that we added in the previous step.

Instead of manually adding CSS to the controls, we will use the standard classes provided by OpenUI5. These classes take care of consistent sizing steps, left-to-right support, and responsiveness.

***

### Preview

   
  
<a name="loio17b87fbafb5a4474982760d2a3a73e69__fig_r1j_pst_mr"/>The layout of the panel and its content now has margins and padding

 ![](loiodffe7aa1ab4c41fda3ac8d06af4479d1_HiRes.png "The layout of the panel and its content now has margins and padding") 

***

### Coding

You can view and download all files at [Walkthrough - Step 13](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.13/preview).

``` xml
<mvc:View
	controllerName="sap.ui.demo.walkthrough.controller.App"
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
							*HIGHLIGHT START*class="sapUiResponsiveMargin"
							width="auto"*HIGHLIGHT END*>
							<content>
								<Button
									text="{i18n>showHelloButtonText}"
									press=".onShowHello"
									*HIGHLIGHT START*class="sapUiSmallMarginEnd"*HIGHLIGHT END*/>
								<Input
									value="{/recipient/name}"
									valueLiveUpdate="true"
									width="60%"/>
								*HIGHLIGHT START*<Text
									text="Hello {/recipient/name}"
									class="sapUiSmallMargin"/>*HIGHLIGHT END*
							</content>
						</Panel>
					</content>
				</Page>
			</pages>
		</App>
	</Shell>
</mvc:View>
```

To layout the panel, we add the CSS class `sapUiResponsiveMargin` that will add some space around the panel. We have to set the width of the panel to `auto` since the margin would otherwise be added to the default width of 100% and exceed the page size.

If you decrease the screen size, then you can actually see that the margin also decreases. As the name suggests, the margin is responsive and adapts to the screen size of the device. Tablets will get a smaller margin and phones in portrait mode will not get a margin to save space on these small screens.

Margins can be added to all kinds of controls and are available in many different options. We can even add space between the button and the input field by adding class `sapUiSmallMarginEnd` to the button.

To format the output text individually, we remove the description from the input field and add a new `Text` control with the same value. Here we also use a small margin to align it with the other content. Similarly, we could add the standard padding classes to layout the inner parts of container controls such as our panel, but as it already brings a padding by default, this is not needed here.

***

### Conventions

-   Use the standard OpenUI5 CSS classes for the layout if possible.


**Parent topic:** [Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:** [Step 12: Shell Control as Container](Step_12_Shell_Control_as_Container_4df1d91.md "Now we use a shell control as container for our app and use it as our new root element. The shell takes care of visual adaptation of the application to the device’s screen size by introducing a so-called letterbox on desktop screens.")

**Previous:** [Step 14: Custom CSS and Theme Colors](Step_14_Custom_CSS_and_Theme_Colors_723f4b2.md "Sometimes we need to define some more fine-granular layouts and this is when we can use the flexibility of CSS by adding custom style classes to controls and style them as we like.")

**Related Information**  


[Using Predefined CSS Margin Classes](Using_Predefined_CSS_Margin_Classes_777168f.md "OpenUI5 gives you the option of adding spacing in between controls by adding a margin. A margin clears an area around its respective control, outside of its border.")

[Using Container Content Padding CSS Classes](Using_Container_Content_Padding_CSS_Classes_c71f6df.md "For many container controls in OpenUI5, such as a Dialog or a Page, you can define whether the container should have a padding within the content area. A padding clears the area between the container layout and the controls that are displayed in the content area.")

