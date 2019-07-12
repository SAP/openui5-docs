| loio |
| -----|
| 559f60eaf71b47bb9f11a07622880f7c |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/559f60eaf71b47bb9f11a07622880f7c.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/559f60eaf71b47bb9f11a07622880f7c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/559f60eaf71b47bb9f11a07622880f7c)</div>
<!-- loio559f60eaf71b47bb9f11a07622880f7c -->

## Filter Search

The popover and dialog displayed by `FacetFilter` contain an `sap.m.SearchField` control. This enables the user to search for specific items in the list.

`FacetFilterList` internally handles the `search` and `liveChange` events by filtering the underlying data model: The search only works when the `FacetFilterList` items aggregation is bound to a model.

If you enable the `liveSearch` property of the `FacetFilter` control, keep the performance in mind as this will result in a backend request for each search character typed by the user.

