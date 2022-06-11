<!-- loiocb3863746ea14d3698a8b6cc2c62832d -->

| loio |
| -----|
| cb3863746ea14d3698a8b6cc2c62832d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/cb3863746ea14d3698a8b6cc2c62832d) | [demo kit latest release](https://sdk.openui5.org/topic/cb3863746ea14d3698a8b6cc2c62832d)</div>

## Step 13: Setting the Master-Detail Pattern

In this step, we set up the app to follow the master-detail pattern.

Apps using the master-detail pattern operate with a layout divided into two separate areas - a master list area and a details area. The master list area displays the items available to the user and the details area displays the details for an item that is selected in the master list. If your use case requires it, you can set the `FlexibleColumnLayout` to use a maximum of two columns. For more information, see the [SAP Fiori Design Guidelines](https://experience.sap.com/fiori-design-web/flexible-column-layout/#two-columns-masterdetail-mode).

***

<a name="loiocb3863746ea14d3698a8b6cc2c62832d__section_yfh_d31_12b"/>

### Preview

   
  
<a name="loiocb3863746ea14d3698a8b6cc2c62832d__fig_zfh_d31_12b"/>Master-detail pattern with `FlexibleColumnLayout`

 ![](images/loio267d05fd0b294310b7bebdeda5f70e3b_HiRes.gif "Master-detail pattern with FlexibleColumnLayout") 

***

<a name="loiocb3863746ea14d3698a8b6cc2c62832d__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [Flexible Column Layout App - Step 13](https://sdk.openui5.org/sample/sap.f.tutorial.fiori2.13/preview).

***

<a name="loiocb3863746ea14d3698a8b6cc2c62832d__section_b2w_gqj_l4b"/>

### webapp/Component.js \[MODIFY\]

```js
		...
		getHelper: function () {
			return this._getFcl().then(function(oFCL) {
				var oSettings = {
					defaultTwoColumnLayoutType: fioriLibrary.LayoutType.TwoColumnsMidExpanded,
					defaultThreeColumnLayoutType: fioriLibrary.LayoutType.ThreeColumnsMidExpanded,
					initialColumnsCount: 2,
					maxColumnsCount: 2
				};
				return (FlexibleColumnLayoutSemanticHelper.getInstanceFor(oFCL, oSettings));
			 });
		},
		...
```

We set `maxColumnsCount` parameter of the `getHelper` method to `2`.

**Parent topic:** [Flexible Column Layout App](Flexible_Column_Layout_App_c4de2df.md "In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the SAP Fiori design guidelines.")

**Next:** [Step 12: Starting with Two Columns](Step_12_Starting_with_Two_Columns_a96fbe4.md "In this step, we set up the app to start with an initial layout of two columns.")

