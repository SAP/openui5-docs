<!-- loio9b5bdd8931194e88b22faf8537099073 -->

| loio |
| -----|
| 9b5bdd8931194e88b22faf8537099073 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9b5bdd8931194e88b22faf8537099073) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9b5bdd8931194e88b22faf8537099073)</div>

## Displaying a Specific Range of Records in a Control

It is possible to display only a specific range of records when using a list binding. The necessary properties can be set in the binding information.

***

Use the `length` and `startIndex` properties of the `oBindingInfo` parameter of the [`sap.ui.base.ManagedObject#bindAggregation`](https://openui5.hana.ondemand.com/#/api/sap.ui.base.ManagedObject/methods/bindAggregation) method if you wish to display only a specific range of your records. Your XML view will then look as shown in the following example. The resulting table will display the three notes with the lowest `Rank`.

``` xml
<Table 
    items="{
        path: '/Notes',
        sorter: { path: 'Rank' },
        length: 3
}">
    <columns>
        <Column>
            <Text text="Note" />
        </Column>
    </columns>
    <items>
        <ColumnListItem>
            <cells>
                <Text text="{Note}" />
            </cells>
        </ColumnListItem>
    </items>
</Table>

```

