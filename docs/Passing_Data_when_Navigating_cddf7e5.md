<!-- loiocddf7e54277446a4a35c9fd9285da009 -->

| loio |
| -----|
| cddf7e54277446a4a35c9fd9285da009 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/cddf7e54277446a4a35c9fd9285da009) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/cddf7e54277446a4a35c9fd9285da009)</div>

## Passing Data when Navigating

When you use the `to(…)` and `back(…)` methods of the `NavContainer` to trigger navigation, you can also give an optional payload data object.

This object is then available in the page events, for example `beforeShow` and `afterShow`. You can also use this mechanism to decouple page implementations.

Example:

``` js

app.to("detailPage", {id:"42"}); // trigger navigation and hand over a data object
                                 // this data object could also be a binding context when dealing with data binding
...


// and where the detail page is implemented:
myDetailPage.addEventDelegate({
   onBeforeShow: function(evt) {
      var idToRetrieve = evt.data.id;
      // ...now retrieve the data element with the given ID and update the page UI
   }
});
```

When you navigate back to a page, it receives the original data object which has been given when you first navigated to the page, but you can also give an additional data object with the back navigation.

***

### API References

-   [sap.m.NavContainer](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.NavContainer.html)
-   [sap.m.NavContainerChild](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.NavContainerChild.html)

