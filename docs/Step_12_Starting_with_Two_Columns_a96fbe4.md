<!-- loioa96fbe44ae6544589a096041f99d38c2 -->

| loio |
| -----|
| a96fbe44ae6544589a096041f99d38c2 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a96fbe44ae6544589a096041f99d38c2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a96fbe44ae6544589a096041f99d38c2)</div>

## Step 12: Starting with Two Columns

In this step, we set up the app to start with an initial layout of two columns.

By default, the `FlexibleColumnLayout` starts off with one column. If your use case requires it, you can set the initial layout to start with two columns. The user can still navigate to a single-column layout by closing the detail page from the navigation actions or a three-column layout by selecting an item from the detail page.

***

<a name="loioa96fbe44ae6544589a096041f99d38c2__section_yfh_d31_12b"/>

### Preview

   
  
Initial layout with two columns<a name="loioa96fbe44ae6544589a096041f99d38c2__fig_zfh_d31_12b"/>

 ![](loio18a03a866de94ad7a488f776417c685b_HiRes.png "Initial layout with two columns") 

***

<a name="loioa96fbe44ae6544589a096041f99d38c2__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 12](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.12/preview).

``` js
		...
		getHelper: function () {
			return this._getFcl().then(function(oFCL) {
				var oSettings = {
					defaultTwoColumnLayoutType: fioriLibrary.LayoutType.TwoColumnsMidExpanded,
					defaultThreeColumnLayoutType: fioriLibrary.LayoutType.ThreeColumnsMidExpanded*HIGHLIGHT START*,
					initialColumnsCount: 2*HIGHLIGHT END*
				};
				return (FlexibleColumnLayoutSemanticHelper.getInstanceFor(oFCL, oSettings));
			 });
		},
		...
```

We set the `initialColumnsCount` parameter of the `getHelper` method to `2`.

