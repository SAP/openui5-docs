<!-- loioe8e5af5b73b04b7bb93d90b90d1fb03f -->

| loio |
| -----|
| e8e5af5b73b04b7bb93d90b90d1fb03f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e8e5af5b73b04b7bb93d90b90d1fb03f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e8e5af5b73b04b7bb93d90b90d1fb03f)</div>

## Example of a Simple XML Composite Control

This section shows you an example of a simple XML composite control.

> Note:
> The code samples in this section reflect examples of possible use cases and might not always be suitable for your purposes. Therefore, we recommend that you do not copy and use them directly.
> 
> 

Here is an example of a simple XML composite control, with the following JS part:

``` js
sap.ui.define([
    'sap/ui/core/XMLComposite'], 
    function( XMLComposite ) {
    "use strict";
    var SimpleText = XMLComposite.extend("fragments.SimpleText", {
        metadata: {
            properties: {
                text: { type: "string", defaultValue: "Default Text"}
            }
        }
    });
    return SimpleText;
}, /* bExport= */true);
```

And here comes the visual part, the fragment definition XML file:

``` xml

<core:FragmentDefinition xmlns:m="sap.m" xmlns:core="sap.ui.core">
        <m:Text text="{$this>/text}" />
</core:FragmentDefinition>
```

There is no specific `renderer` method; the rendering is handled generically by the framework.

If you want to use this XML composite control, you can set up a page like this:

``` html

<!DOCTYPE HTML>
<html>
<head>
    .
    .
    .
    <script>
        sap.ui.require([
            "fragments/SimpleText"
        ], function(SimpleText) {
        var oSimpleText = new SimpleText({text : "Hello World"});
        oSimpleText.placeAt("content");
    });
    </script>
</head>
<body id="content" class="sapUiBody">
</body>
</html>
```

