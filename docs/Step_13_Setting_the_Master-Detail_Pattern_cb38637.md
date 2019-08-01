<!-- loiocb3863746ea14d3698a8b6cc2c62832d -->

| loio |
| -----|
| cb3863746ea14d3698a8b6cc2c62832d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/cb3863746ea14d3698a8b6cc2c62832d) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/cb3863746ea14d3698a8b6cc2c62832d)</div>

## Step 13: Setting the Master-Detail Pattern

In this step, we set up the app to follow the master-detail pattern.

Apps using the master-detail pattern operate with a layout divided into two separate areas - a master list area and a details area. The master list area displays the items available to the user and the details area displays the details for an item that is selected in the master list. If your use case requires it, you can set the `FlexibleColumnLayout` to use a maximum of two columns. For more information, see the [SAP Fiori Design Guidelines](https://experience.sap.com/fiori-design-web/flexible-column-layout/#two-columns-masterdetail-mode).

***

<a name="loiocb3863746ea14d3698a8b6cc2c62832d__section_yfh_d31_12b"/>

### Preview

   
  
Master-detail pattern with `FlexibleColumnLayout`<a name="loiocb3863746ea14d3698a8b6cc2c62832d__fig_zfh_d31_12b"/>

 ![](loio267d05fd0b294310b7bebdeda5f70e3b_HiRes.gif "Master-detail pattern with FlexibleColumnLayout") 

***

<a name="loiocb3863746ea14d3698a8b6cc2c62832d__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 13](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.13/preview).

``` js
		...
		getHelper: function () {
			return this._getFcl().then(function(oFCL) {
				var oSettings = {
					defaultTwoColumnLayoutType: fioriLibrary.LayoutType.TwoColumnsMidExpanded,
					defaultThreeColumnLayoutType: fioriLibrary.LayoutType.ThreeColumnsMidExpanded,
					initialColumnsCount: 2*HIGHLIGHT START*,
					maxColumnsCount: 2*HIGHLIGHT END*
				};
				return (FlexibleColumnLayoutSemanticHelper.getInstanceFor(oFCL, oSettings));
			 });
		},
		...
```

We set `maxColumnsCount` parameter of the `getHelper` method to `2`.

