<!-- loio0715706772ed43f389d2ab9b381ef8ec -->

| loio |
| -----|
| 0715706772ed43f389d2ab9b381ef8ec |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/0715706772ed43f389d2ab9b381ef8ec) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/0715706772ed43f389d2ab9b381ef8ec)</div>

## IDs in Declarative XML or HTML Fragments

If a fragment with a control ID is instantiated twice without giving an ID, a duplicate ID error occurs.

Given the following XML fragment example:

``` xml
<HBox xmlns="sap.m">
   <Button                    text="Hello World" />
   <Button id="btnInFragment" text="Hello World" />
</HBox>
```

The first button will always have a generated ID, as, for instance, `__button2`. This is regardless of how the fragment is instantiated or whether it resides inside a view.

The second button will either have the ID `btnInFragment`, in case the fragment is instantiated without giving an ID. This approach is easy to use, but implies the risk of ID collisions when instantiated multiple times:

``` js
sap.ui.htmlfragment("my.useful.UiPartZ"); // Button ID will not be prefixed
```

The other possible ID of the second button is `myFragment--btnInFragment`, in case the fragment is instantiated giving the ID `myFragment`. You should not rely on the exact syntax of this prefixing.

``` js
sap.ui.htmlfragment("myFragment", "my.useful.UiPartZ");
```

It is, however, possible that a containing view may add its prefix. For more information, see [IDs of Fragments in Views](IDs_of_Fragments_in_Views_f10bf70.md).

