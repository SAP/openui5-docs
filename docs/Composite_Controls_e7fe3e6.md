<!-- loioe7fe3e60481240518d7e9e25ea7eaa6f -->

| loio |
| -----|
| e7fe3e60481240518d7e9e25ea7eaa6f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e7fe3e60481240518d7e9e25ea7eaa6f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e7fe3e60481240518d7e9e25ea7eaa6f)</div>

## Composite Controls

Composite OpenUI5 controls, like Wizard or Semantic Page, are read based on the specific behavior of their parts. Still these controls require additional ARIA labels to correctly separate the areas within the control. Here are some examples:

-   Wizard Navigation Area - needs to be marked as a `navigation` landmark

-   Dynamic Side Content - needs to be marked as a `complementary` landmark


When creating new composite controls, you need to make sure to properly assign your controls to regions and label these regions correctly.

***

### sap.m.Page Custom Landmarks

The `sap.m.Page` control is used in a lot of applications. As a container control it has three distinct regions that hold content - header, content area and footer. There is also an additional role for the whole page. Each of these areas needs to have a clearly defined ARIA role that explains what the region does. The ARIA roles for all these regions can be set to custom values using the properties of `sap.m.PageAccessibleLandmarkInfo`. Possible values for these roles are stored in the `AccessibleLandmarkRole` enumeration. In the example below you can see how this is done in the `landmarkInfo` property of `sap.m.Page`.

```
<App>
	<Page title="Hello World" height="100%">
		<headerContent>
			<Title text="Just Page" />
		</headerContent>
		<subHeader>
			<Bar>
				<contentLeft>
					<Text text="Text in content left bar subheader "/>
				</contentLeft>
			</Bar>
		</subHeader>
		<footer>
			<Bar>
				<contentLeft>
					<Text text="Text in content left bar footer "/>
				</contentLeft>
			</Bar>
		</footer>
		<content>
			<Text text="Text in page content"/>
		</content>
		<landmarkInfo>
			
			<PageAccessibleLandmarkInfo 
				rootRole="Region" 
				rootLabel="Root Label"
				contentRole="Region"
				contentLabel="Content Label"
				footerRole="Region"
				footerLabel="Footer Label"
				headerRole="Region"
				headerLabel="Header Label"
				subHeaderRole="Region"
				subHeaderLabel="SubHeader Label" />
		</landmarkInfo>
	</Page>
</App>
```

