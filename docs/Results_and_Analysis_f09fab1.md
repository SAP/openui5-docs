<!-- loiof09fab15373b4735a36cbc3cace0c1f4 -->

| loio |
| -----|
| f09fab15373b4735a36cbc3cace0c1f4 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/f09fab15373b4735a36cbc3cace0c1f4) | [demo kit latest release](https://sdk.openui5.org/topic/f09fab15373b4735a36cbc3cace0c1f4)</div>

## Results and Analysis

After an analysis run, you can view a list of all triggered rules, their description, resolution steps, and a control tree with highlighted problematic elements.

***

Below you can see an example of how the results are displayed.

   
  
<a name="loiof09fab15373b4735a36cbc3cace0c1f4__fig_j14_3k1_k1b"/>Support Assistant Issues View

 ![](images/loio78c90c54cda34b0091c96424bba7a55e_HiRes.png "Support Assistant Issues View") 

***

### Issues List

The left side shows a list of the triggered rules sorted by severity \(High, Medium, Low\). You can use the dropdown menus to filter on *Severity*, *Category*, or *Audience*. You can clear your filtering by choosing *Clear Filtering* \(![](images/loio4a0cf3bc3f7244549cf95901077aa6ae_HiRes.png)\).

Selecting *Report* generates an HTML report with the current set of rules and scope. You can view it in a new tab or download it as a `.ZIP` file.

***

### Issue Details

The middle part shows a detailed view of the selected rule. It contains the following:

-   Description - general description of the rule

-   Resolution - steps to resolve the issue

-   URLs - useful links \(for example, API Reference or Documentation\)

-   Severity - the severity of the identified issue

-   Element ClassName and ID - the namespace of the element


***

### Element Tree

The right side shows the element tree of the application. The root of the tree is called `<WEBPAGE>`. All rules that are not specific for a given control are mapped to this element. If these rules are triggered, the resulting issues will be mapped to the `<WEBPAGE>` element.

-   Hovering on an element in the tree highlights it in the application \(if it is visible\).

-   Selecting an element with issues in the element tree loads those issues in the issues list.

-   The table in the issues list shows all other elements that have triggered the same rule. The list also shows you the severity of each issue.


   
  
<a name="loiof09fab15373b4735a36cbc3cace0c1f4__fig_dhm_lk1_k1b"/>Support Assistant DOM Tree

 ![](images/loio4c280d1c4c5f40359f72f5f7ec22b982_HiRes.png "Support Assistant DOM Tree") 

