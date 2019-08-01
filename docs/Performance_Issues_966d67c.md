<!-- loio966d67c8cc5046419d1b35556cd9e447 -->

| loio |
| -----|
| 966d67c8cc5046419d1b35556cd9e447 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/966d67c8cc5046419d1b35556cd9e447) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/966d67c8cc5046419d1b35556cd9e447)</div>

## Performance Issues

This section lists some of the most important issues that should be avoided to improve performance in OpenUI5 applications.

***

<a name="loio966d67c8cc5046419d1b35556cd9e447__1"/>

### Don't use visibility for lazy instantiation

When an application has areas that are not visible initially, or if only one of multiple options is visible at a time, **do not** create all UI controls and set most of them to non-visible! If you do, OpenUI5 will instantiate and initialize all of those controls, which consumes unnecessary time and memory, even when they are not rendered. On top of this, the data binding will also be initialized, which may trigger back-end requests that are not needed at this stage. The impact is particularly big when the parts of the UI that are not visible initially are complex or numerous.

Please note that lazy loading of views can be achieved with routing. For more information, see [Routing and Navigation](Routing_and_Navigation_3d18f20.md) and [Step 10: Implement "Lazy Loading"](Step_10_Implement_Lazy_Loading_cdab0a1.md) of the Navigation and Routing tutorial.

> Note:
> An application needs to display a `Panel` containing a `Table` in **display mode**, but the user can switch to **edit mode** to modify data, in which case a different `Panel` needs to be shown. Especially when using XML views, it is tempting for application developers to specify two panels in the view XML and set the `Panel` with the editable table to `visible="false"`. The *Edit* button could then just toggle visibility of both panels.
> 
> 

The following XML view is easy to handle, but leads to suboptimal performance when the `editPanel` has a lot of content.

View:

``` xml
<mvc:View xmlns:mvc="sap.ui.core.mvc" xmlns="sap.m" controllerName="my.own.controller">
	<Page>
                        
		<Panel id="displayPanel" headerText="Display Data">
			<Table...>
		</Panel>
                        
		<!-- edit panel is initially hidden, but still instantiated -->
		<Panel id="editPanel" headerText="Edit Data" visible="false">
			<Table...> 
		</Panel>
                        
		<Button text="Edit" press="toEditMode"/>
	</Page>
</mvc:View>
```

Controller code:

``` js
toEditMode: function() {
	this.byId("displayPanel").setVisible(false);
	this.byId("editPanel").setVisible(true);
}
```

The following code is better in terms of initial performance because the second table is created lazily when the user switches to edit mode.

View:

``` xml
<mvc:View xmlns:mvc="sap.ui.core.mvc" xmlns="sap.m" controllerName="my.own.controller">
	<Page>
            
		<!—only the initially needed display panel -->
		<Panel id="displayPanel" headerText="Display Data">
			<Table...>
		</Panel>
      
		<Button text="Edit" press="toEditMode"/>
	</Page>
</mvc:View>
```

Additional fragment named `EditPanel.fragment.xml` for content that is initially hidden:

``` xml
<Panel xmlns="sap.m" id="editPanel" headerText="Edit Data" visible="false">
	<Table...>
</Panel>
```

Controller code:

``` js
toEditMode: function() {
	this.byId("displayPanel").setVisible(false);
                  
	var oEditPanel = this.byId("editPanel");
	if (!oEditPanel) { // load and instantiate the edit panel lazily
		// instantiate the Fragment:
		// giving the View ID as ID will prefix the IDs in the Fragment and allows using this.byId(…) in the Controller
		// giving “this” (the Controller) allows using controller methods from within the Fragment
		oEditPanel = sap.ui.xmlfragment(this.getView().getId(), "myApp.EditPanel", this); 
		this.byId("myPage").insertContent(oEditPanel, 0); // for sake of simplicity inserts at position 0
	}
	oEditPanel.setVisible(true);
}
```

In other scenarios, at the time of developing you may not know which UI part is displayed initially. In this case, you can define that the UI is empty \(showing none of the panels\) in the view definition, and the controller’s `onInit()` method decides which fragment to instantiate and display initially:

``` js
onInit: function() {
	var oPanel;
	if (bEditMode) { 
		oPanel = sap.ui.xmlfragment("myApp.EditPanel");
	} else {
		oPanel = sap.ui.xmlfragment("myApp.DisplayPanel");
	}
	this.byId("myPage").insertContent(oPanel, 0);
}
```

> Note:
> Although the example above shows an XML view and an XML fragment, the problem and the solution apply to all view types.
> 
> Please also note that this guideline is not set in stone: If the hidden UI elements are just small or few in number, using fragments would not help but add additional overhead instead. Having said that, creating several big tables and displaying only one of them is **not** a good idea. There is no definite rule where to draw the line, it depends on many factors like application size, number of libraries being loaded, and additional data requested by those hidden controls. If in doubt, you can test the performance using the performance tracing tools in the browser’s developer console with the controls in question being hidden, against them being removed.
> 
> 

See also: [Reusing UI Parts: Fragments](Reusing_UI_Parts_Fragments_36a5b13.md).

**Related information**  


[Performance: Speed Up Your App](Performance_Speed_Up_Your_App_408b40e.md)

