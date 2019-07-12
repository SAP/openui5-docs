| loio |
| -----|
| 08d220676c1c4de38fa8bbc515e2477f |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/08d220676c1c4de38fa8bbc515e2477f.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/08d220676c1c4de38fa8bbc515e2477f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/08d220676c1c4de38fa8bbc515e2477f)</div>
<!-- loio08d220676c1c4de38fa8bbc515e2477f -->

## HTML Fragments

HTML fragments have a similar syntax as HTML views, but without the `<template>` tag.

You can define a simple HTML fragment like this:

```lang-html

<div data-sap-ui-type="sap.m.Button" data-press="doSomething" data-text="Hello
        World"></div>
```

The fragment is stored as `…/my/useful/UiPartZ.fragment.html` and referenced as `Fragment my.useful.UiPartZ`. HTML fragments cannot specify a controller to be instantiated. They can use a controller for binding event handler methods, but only if the code instantiating them passes a controller.

