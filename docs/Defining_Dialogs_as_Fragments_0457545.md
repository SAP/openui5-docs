<!-- loio04575456e15e426d81054805990c7a53 -->

| loio |
| -----|
| 04575456e15e426d81054805990c7a53 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/04575456e15e426d81054805990c7a53) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/04575456e15e426d81054805990c7a53)</div>

## Defining Dialogs as Fragments

You can use fragments for the definition of dialogs.

***

To use fragments for defining popups, just let the root control of the fragment be a dialog or similar control.

The following shows an XML fragment dialog example:

``` xml
<Dialog xmlns="sap.m" title="XML Fragment Dialog">
    <TextView text="{/dialogText}" />
    <buttons>
        <Button text="Close" press="closeDialog"/>
    </buttons>
</Dialog>
```

Other fragment types are used the same way to define, for instance, a dialog as fragment.

For example, in JS fragments, the `createContent()` method returns a dialog control:

``` js

sap.ui.jsfragment("testdata.fragments.JSFragmentDialog", {
    createContent: function(oController) {
     var oDialog = new sap.m.Dialog({
            title: "JavaScript Fragment Dialog",
            content: [
                new sap.m.Input({
                    text: "{/dialogText}"
                })
            ],
            buttons: [
                new sap.m.Button({
                    text: "Close",
                    press: function(){
                        oDialog.close();
                    }
                })
            ]
        return oDialog;
    }
});
```

