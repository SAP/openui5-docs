<!-- loio91f15ad16f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f15ad16f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/91f15ad16f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f15ad16f4d1014b6dd926db0e91070)</div>

## Declarative Support: Events

The value of the event data attribute contains the name of a JavaScript function which will be used as callback once the event has been triggered.

The following code snippet gives an example how a change of `Input` results in an alert with its new value when the focus is lost:

```html
<script>
  function handleChange (oEvent) {
    alert (oEvent.getSource().getValue());
  }
</script>

<div data-sap-ui-type="sap.m.Input" data-value="Change me!" data-change="handleChange"></div>
```

Currently, OpenUI5 only supports to specify the name of a callback function. You can define callback functions within any class, see the following code example:

```html

<div data-sap-ui-type="sap.m.Input" data-value="Change me!" data-change= "my.company.MyClass.handleChange"></div>
```

