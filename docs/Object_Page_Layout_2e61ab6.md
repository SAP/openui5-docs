<!-- loio2e61ab6c68a2480eb666c1927a707658 -->

| loio |
| -----|
| 2e61ab6c68a2480eb666c1927a707658 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2e61ab6c68a2480eb666c1927a707658) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2e61ab6c68a2480eb666c1927a707658)</div>

## Object Page Layout

The `ObjectPageLayout` control provides a layout that allows apps to easily display information related to a business object.

***

<a name="loio2e61ab6c68a2480eb666c1927a707658__section_hby_mpx_mcb"/>

### Overview

The `ObjectPageLayout` layout is composed of a header \(title and content\), an optional anchor bar and block content wrapped in sections and subsections that structure the information.

   
  
`ObjectPageLayout` main structure<a name="loio2e61ab6c68a2480eb666c1927a707658__fig_lyy_3qx_mcb"/>

 ![](loio6b015871feac4b62a1111c73ba78c86f_HiRes.png "ObjectPageLayout main structure") 

***

<a name="loio2e61ab6c68a2480eb666c1927a707658__section_xy2_fsx_mcb"/>

### Header \(Title and Content\)

The `ObjectPageLayout`'s header consists of two parts: header title and header content.

The header title is the topmost part of the `ObjectPageLayout` that is always visible. Its main purpose is to display the name of the represented business object along with actions that the user can perform.

The header content scrolls along with the content of the page until it disappears \(collapsed header\). When scrolled back to the top it becomes visible again \(expanded header\). It contains all the additional information of the object.

Here is how the header title and header content are defined in both views:

XML view:

``` xml
<ObjectPageLayout id="ObjectPageLayout">

	 *HIGHLIGHT START*<headerTitle>*HIGHLIGHT END*
		<ObjectPageHeader objectTitle="John Smith">
			<actions>
				<ObjectPageHeaderActionButton icon="sap-icon://edit" text="Edit" />
				<ObjectPageHeaderActionButton icon="sap-icon://save" text="Save" />
			</actions>
		</ObjectPageHeader>
	*HIGHLIGHT START*</headerTitle>*HIGHLIGHT END*

	*HIGHLIGHT START*<headerContent>*HIGHLIGHT END*
		<m:Label text="Personal description"/>                                                
		<m:Text value="some KPI info"/>
	*HIGHLIGHT START*</headerContent>*HIGHLIGHT END*

</ObjectPageLayout>
```

JavaScript view:

``` js
// Create a header title, set the objectTitle property and add some action buttons
var oHeaderTitle = new sap.uxap.ObjectPageHeader();
oHeaderTitle.setObjectTitle("John Smith");
oHeaderTitle.addAction(new sap.uxap.ObjectPageHeaderActionButton({icon: "sap-icon://edit", text: "Edit"}));
oHeaderTitle.addAction(new sap.uxap.ObjectPageHeaderActionButton({icon: "sap-icon://save", text: "Save"}));
oObjectPage.setHeaderTitle(oHeaderTitle);

// Add arbitrary header content
oObjectPage.addHeaderContent(new sap.m.Label({text:"Personal description"}));
oObjectPage.addHeaderContent(new sap.m.Text({value:"some KPI info"}));
```

***

<a name="loio2e61ab6c68a2480eb666c1927a707658__section_hd5_ysx_mcb"/>

### Sections, Subsections, Blocks

The content of the page that appears below the header is composed of blocks structured into sections and subsections.

   
  
Blocks structured into sections and subsections<a name="loio2e61ab6c68a2480eb666c1927a707658__fig_gbq_lvx_mcb"/>

 ![](loio69eeaf31d2e3481fa479d8a42229b6ec_HiRes.png "Blocks structured into sections and subsections") 

The blocks hold the actual app content, while the purpose of the sections and subsections is to define grouping.

A subsection groups together a set of blocks \(under a common title\), while a section groups together a set of subsections \(under a common title\).

The grouping enables the control to automatically create an internal menu \(anchor bar\) that shows the titles of the sections and subsections as separate anchors. The user can select them to scroll to the respective section or subsection content.

Here are some examples of how sections are initialized in both views:

XML view:

``` xml
<ObjectPageLayout id="ObjectPageLayout" >
        *HIGHLIGHT START*<sections>*HIGHLIGHT END*
            <ObjectPageSection title="Payroll" >
                *HIGHLIGHT START*<subSections>*HIGHLIGHT END*
                    <ObjectPageSubSection title="sub payroll title">
                        *HIGHLIGHT START*<blocks>*HIGHLIGHT END*
                            <myNameSpace:myBlock/>
                            <myNameSpace:myBlock/>
                            <myNameSpace:myBlock/>
                        *HIGHLIGHT START*</blocks>*HIGHLIGHT END*
                    </ObjectPageSubSection>
                *HIGHLIGHT START*</subSections>*HIGHLIGHT END*
            </ObjectPageSection>
        *HIGHLIGHT START*</sections>*HIGHLIGHT END*
    </ObjectPageLayout>
```

JavaScript view:

``` js
var oSubSection1 = new sap.uxap.ObjectPageSubSection({title:"sub payroll title"});
    var oSection1 = new sap.uxap.ObjectPageSection({title:"Payroll"});
    oSection1.addSubSection(oSubSection1);
    oObjectPage.addSection(oSection1);
```

***

<a name="loio2e61ab6c68a2480eb666c1927a707658__section_olf_1cr_ncb"/>

### Layout Options

The `subSectionLayout` property provides information on how all the underlying subsections arrange the blocks within their internal grid. The default is set to `titleOnTop`, which arranges the blocks content in columns where the first column is below the section and subsection titles.

   
  
Blocks Content Arranged in Columns with Section and Subsection Titles Displayed on Top<a name="loio2e61ab6c68a2480eb666c1927a707658__fig_c2l_fcr_ncb"/>

 ![](loio80c15831d2f14649ab7e56f24b17a5b9_HiRes.png "Blocks Content Arranged in Columns with Section and Subsection Titles Displayed on
					Top") 

Additionally, a second layout named `titleOnLeft` arranges the blocks content from the second column, leaving the first one for section and subsection titles only.

   
  
Blocks Content Arranged in Columns with Section and Subsection Titles Displayed on the Left<a name="loio2e61ab6c68a2480eb666c1927a707658__fig_s45_fcr_ncb"/>

 ![](loio96bf1fad37a74191968095bdd71698d3_HiRes.png "Blocks Content Arranged in Columns with Section and Subsection Titles Displayed on the
					Left") 

Here is how this property is set in the XML view:

``` xml
<ObjectPageLayout id="ObjectPageLayout" *HIGHLIGHT START*subSectionLayout="titleOnTop"*HIGHLIGHT END*>
        <sections>
            <ObjectPageSection title="Payroll" >
                <subSections>
                    <ObjectPageSubSection title="sub payroll title">
                        <blocks>
                            <myNameSpace:myBlock/>
                            <myNameSpace:myBlock/>
                            <myNameSpace:myBlock/>
                        </blocks>
                    </ObjectPageSubSection>
                </subSections>
            </ObjectPageSection>
        </sections>
    </ObjectPageLayout>
```

The `moreBlocks` aggregation of `sap.uxap.ObjectPageSubSection` allows you to specify blocks to be displayed only after the user clicks the internally created *See more* button:

 ![](loio74c97287cab245018b4ad7dc364108ee_HiRes.png) 

The *See more* button is only displayed for subsections that contain one of the following:

-   Visible blocks in the `moreBlocks` aggregation

-   Visible `BlockBase` block that has the `showSubSectionMore` property set to `true`


***

<a name="loio2e61ab6c68a2480eb666c1927a707658__section_jzh_b2r_ncb"/>

### Additional Rules for Displaying Sections and Subsections

The following additional rules are internally applied to display the contents of the `ObjectPageLayout` correctly. Each rule is applied to the output of the preceding rule.

1.  If the subsection content is empty \(contains no blocks\), it is not displayed \(no anchor is displayed for that subsection in the anchor bar and no title is displayed in the page body\).

2.  If the section content is empty \(contains no subsections\), it is not displayed \(no anchor is displayed for that section in the anchor bar and no title is displayed in the page body\).

3.  If a section without a title contains only one subsection with a title, the section gets the title of the subsection \(`SectionTitle`=`SubsectionTitle` and `SubsectionTitle`=`NULL`\).

4.  If the `ObjectPageLayout` contains only one section, no anchor bar is displayed.

5.  If there are more than one section, the first one will not have a title.


***

<a name="loio2e61ab6c68a2480eb666c1927a707658__section_q1l_f2r_ncb"/>

### Lazy Loading

The lazy loading mechanism allows you to load data only when the blocks are inside or near the visible area on the screen. This way, you avoid sending too many requests from the start of the page loading.

If you want to use lazy loading, all your blocks must be based on `BlockBase`, otherwise they are loaded as normal OpenUI5 components.

Lazy loading is disabled by default. To enable it, set the `enableLazyLoading` property to `true`:

``` js
<ObjectPageLayout id="ObjectPageLayout" *HIGHLIGHT START*enableLazyLoading="true"*HIGHLIGHT END*>
```

The `ObjectPageLayout` control ensures that only the visible blocks and those adjacent to them have loaded their data, but not the entire page. As the user scrolls or navigates within the page, new data is requested as needed.

> Note:
> Setting `enableLazyLoading` to `true` after the `ObjectPageLayout` has been instantiated does not work, as all bindings will have been resolved by then.
> 
> 

**Related information**  


[Object Page Headers](Object_Page_Headers_d2ef009.md)

[Anchor Bar](Anchor_Bar_370b679.md)

[Object Page Blocks](Object_Page_Blocks_4527729.md)

[Creating Blocks](Creating_Blocks_2978f60.md)

[Object Page Scrolling](Object_Page_Scrolling_bc410e9.md)

[API Reference: `sap.uxap.ObjectPageLayout`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.ObjectPageLayout.html)

[API Reference: `sap.uxap.ObjectPageSection`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.ObjectPageSection.html)

[API Reference: `sap.uxap.ObjectPageSubSection`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.ObjectPageSubSection.html)

[API Reference: `sap.uxap.BlockBase`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.BlockBase.html)

