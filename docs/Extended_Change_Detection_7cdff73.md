<!-- loio7cdff73f308b4b10bdf7d83b7aba72e7 -->

| loio |
| -----|
| 7cdff73f308b4b10bdf7d83b7aba72e7 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7cdff73f308b4b10bdf7d83b7aba72e7) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7cdff73f308b4b10bdf7d83b7aba72e7)</div>

## Extended Change Detection

Extended change detection offers fine-grained information on the actual data changes. This can be used, for example, to only update the DOM when really necessary and avoid complete rerendering of a huge list whenever data is changed.

The binding base class already offers a `Change` event, which is fired whenever the bound data has been changed. This is sufficient for bindings like property and context binding. Since lists can contain a huge amount of data, you need more detailed information on the changes to avoid a complete rerendering of the whole list each time data has been changed on the UI.

***

<a name="loio7cdff73f308b4b10bdf7d83b7aba72e7__section_efm_hht_scb"/>

### Calculation of Differences

When extended change detection is enabled, an algorithm is executed to compare the last returned context array with the current context array and the differences is attached to the array of contexts as an additional property named `diff` whenever the `getContexts` method is called. The following results are possible:

-   There is no `diff` property on the context array

    The data was completely changed or a difference could not be calculated. In this case there is no possibility for fine-grained update, a complete recreation or rerendering is necessary.

-   The `diff` property returns an empty array

    The algorithm has been executed, but could not find any differences between the initial and the current state. This may occur if data within the list has been changed, but detection of updates have not been enabled for the extended change detection.

-   The `diff` property returns an array of different entries

    The difference has been calculated and can be used by the control or application to update dependent structures in a fine grained manner


The difference between the state when the list was initially loaded and the current state is provided to the control as an array that contains `insert` and `remove` entries that contain the actual changes.

> Note:
> | **Old State** | **New State** |
> | `["one", "two", "three", "four", "five"]` | `["one", "three", "four", "five", "six"]` |
> | **Difference** |
> | `[{index: 1, type: "delete"}, {index: 4, type: "insert}]` |
> 
> The algorithm is implemented in the utility method `jQuery.sap.arraySymbolDiff`, which tries to calculate the smallest possible difference for the transition from old to the new state. The indexes are calculated in a way that they are valid after all previous steps have been applied, so it can be used in a loop to update an existing array, without any additional index shift needed.
> 
> 

> Note:
> -   Extended change detection calculates the difference between the context arrays returned by calling `getContexts`. This means, it is completely independent from the `startIndex` and `length` parameters. Any additional call to `getContexts`, either by the app or the control itself, may trigger a difference calculation and may cause update problems. If you want to access the current context of a list binding, you should use `getCurrentContexts` in your app instead.
> 
> -   When a `ListBinding` is firing a `Refresh` event, the call to `getContexts` caused by this event is used to inform the `ListBinding` on the `startIndex` and `length` of entries requested by the control. No difference calculation is done on this specific call, as controls do not use the result of this call but instead wait for the data returned by the server.
> 
> 
> 

***

<a name="loio7cdff73f308b4b10bdf7d83b7aba72e7__section_a2g_vht_scb"/>

### Using Extended Change Detection in App Development

If a control you want to use in your app to visualize list entries supports extended change detection, you should make sure that each entity of your model has a unique key to improve performance.

-   For OData models, the unique keys are automatically provided.

-   For all other models \(like a JSON model\), you have to define the keys either by using a key property or by using a function that calculates the key in the binding info of their list binding as in the following example:

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> `key` property</th>
			<th> `key` function</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> ``` jsoControl.bindItems({
  path: "/listData",
  key: "id"
});
```
			</td>
			<td> ``` jsoControl.bindItems({
  path: "/listData",
  key: function(oContext) {
    return oContext.getProperty("user") + oContext.getProperty("timestamp"); 
  }
});
```
			</td>
		</tr>
	</tbody>
</table>


***

<a name="loio7cdff73f308b4b10bdf7d83b7aba72e7__section_w1g_5ht_scb"/>

### Using Extended Change Detection in Control Development

Extended change detection is disabled by default. If your control is meant to have only a few children like a toolbar with buttons, you should not activate extended change detection because a copy of the previous state would then always be kept unnecessarily in the binding.

With extended change detection the control uses specific `insert` and `remove` calls only for elements that need to be added or removed instead of recreating all elements of an aggregation or setting new binding contexts on all aggregated elements.

You activate extended change detection for your control by setting the `bUseExtendedChangeDetection` property either on the control prototype or a specific control instance. The `ManagedObject` class takes care of reading and applying the information about the differences to aggregations with the `enableExtendedChangeDetection` method. The method has the following parameters:

-   `bDetectUpdates`

    Defines whether data changes within the same entity should also be contained in the `diff`. This is especially relevant when a factory function is used to create child controls, so depending on the data a different control may be created by the same entity.

-   `vKey`

    Defines how a unique symbol for each row is calculated, which is then used for the calculation of differences. This can either be a property name \(in case the data already has something like a `key` property\) or a function that is able to calculate such a unique key from the entity data.


You also have to implement the specific aggregation modifier methods to avoid the rerendering of the complete UI and only to a fine-grained DOM update.

> Note:
> If your control has a custom `updateAggregation` method \(that means control takes care for updating the aggregation\) you have to make sure in your implementation that the difference information is interpreted and applied.
> 
> 

For more information, see the [API Reference: `sap.ui.base.ManagedObject.bindAggregation`](https://openui5.hana.ondemand.com/#/api/sap.ui.base.ManagedObject/methods/bindAggregation).

**Related information**  


[API Reference: `sap.ui.base.ManagedObject.bindAggregation`](https://openui5.hana.ondemand.com/#/api/sap.ui.base.ManagedObject/methods/bindAggregation)

[API Reference: `sap.ui.Model.ListBinding.getContexts`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.ListBinding/methods/getContexts)

