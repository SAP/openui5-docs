<!-- loiod4ac0edbc467483585d0c53a282505a5 -->

| loio |
| -----|
| d4ac0edbc467483585d0c53a282505a5 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d4ac0edbc467483585d0c53a282505a5) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d4ac0edbc467483585d0c53a282505a5)</div>

## exit\(\) Method

The `exit()` method is used to clean up resources and to deregister event handlers.

If the `exit()` method is implemented, OpenUI5 core invokes the method for each control instance when it is destroyed.

> Note:
> Any method in your inheriting control overrides methods with the same name in the superclass. If, for example, your control implements the `init()` method, the `init()` of the superclass will no longer be executed. The control is then no longer properly initialized and this typically causes an error. To avoid breaking the control, call the superclass method.
> 
> Consider also that the superclass might implement the method later on, or removes its own method implementation because it is not needed anymore. We recommend that you check for the existence of the superclass method before calling it:
> 
> ``` js
> 
> sap.ui.somelib.SomeControl.extend("my.OwnControl", {
>        ...
>        init: function() {
>              if (sap.ui.somelib.SomeControl.prototype.init) { // check whether superclass implements the method
>                     sap.ui.somelib.SomeControl.prototype.init.apply(this, arguments); // call the method with the original arguments
>              }
> 
>              //... do any further initialization of your subclass... 
>        } 
> ```
> 
> 

