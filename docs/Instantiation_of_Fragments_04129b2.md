<!-- loio04129b2798c447368f4c8922c3c33cd7 -->

| loio |
| -----|
| 04129b2798c447368f4c8922c3c33cd7 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/04129b2798c447368f4c8922c3c33cd7) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/04129b2798c447368f4c8922c3c33cd7)</div>

## Instantiation of Fragments

OpenUI5 provides the generic function `sap.ui.fragment()` to instantiate fragments.

Comparing fragments to views, there is one important difference: Fragments are no controls. While views are control instances which have their own HTML and their own set of properties and may contain other controls, fragments just consist of their content. Views contain their content controls, while fragments consist of their content controls.

For example, when a fragment containing a button is instantiated, the result is just this button.

The generic function `sap.ui.fragment()` can be called with either the name, the type, and optionally a controller, or with a configuration object and an optional controller. It either returns the root control contained in the fragment or an array of root controls, depending on the type of the fragment. This fragment type is usually known in advance. Therefore, a specific method for each fragment type can be used to programmatically instantiate a fragment. You find more information on the instantiation process in the respective topics linked in the related link section below.

The different methods used for the instantiation of a fragment have the following commonalities:

-   A fragment name must be given. This name must be resolvable to the fragment file URL by the OpenUI5 module loading mechanism. In case of JS fragments the name may also be defined inline.
-   A controller can be optionally given. Some fragments may require a controller and certain methods to be present in this controller.
-   An ID can be optionally given.

    If no ID is given, any control IDs specified in the fragment are used as is. The repeated use of a fragment can lead to duplicate IDs. One way to avoid that problem is to specify a unique fragment ID. For more information see [Unique IDs](Unique_IDs_5da591c.md). This ID will then be used as prefix for all controls in this fragment instance.


