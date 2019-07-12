| loio |
| -----|
| 7e245247aef949ac84785c56deb8baac |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/7e245247aef949ac84785c56deb8baac.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7e245247aef949ac84785c56deb8baac) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7e245247aef949ac84785c56deb8baac)</div>
<!-- loio7e245247aef949ac84785c56deb8baac -->

## Integrating Item Navigation

To integrate the item navigation in your control, apply the delegate in the `onAfterRendering` hook of your control.

```lang-js

sap.ui.commons.ListBox.prototype.onAfterRendering = function () {
        //Collect the dom references of the items
        var oFocusRef = this.getDomRef(),
                 aRows = oFocusRef.getElementsByTagName("TR"),
                 aDomRefs = [];
        for (var i=0;i<aRows.length;i++) {
                 aDomRefs.push(aRows[i].firstChild);
        }
        //initialize the delegate and apply it to the control (only once)
         if (!this.oItemNavigation) {
                  this.oItemNavigation = new sap.ui.core.delegate.ItemNavigation();
                  this.addDelegate(this.oItemNavigation);
        }

       // After each rendering the delegate needs to be initialized as well.

       //set the root dom node that surrounds the items
         this.oItemNavigation.setRootDomRef(oFocusRef);

       //set the array of dom nodes representing the items.
         this.oItemNavigation.setItemDomRefs(aDomRefs);

       //turn of the cycling
        this.oItemNavigation.setCycling(false);

       //set the selected index
        this.oItemNavigation.setSelectedIndex(this.getSelectedIndex());

      //set the page size
       this.oItemNavigation.setPageSize(this.getVisibleItems()); };
```

After the control is destroyed, ensure that the delegate is correctly removed. Otherwise, memory will leak because DOM nodes are still referenced by the delegate.

```lang-js

sap.m.List.prototype.destroy = function() {
                   if (this.oItemNavigation) {
                            this.removeDelegate(this.oItemNavigation);
                            this.oItemNavigation.destroy();
                   }
 }; 
```

