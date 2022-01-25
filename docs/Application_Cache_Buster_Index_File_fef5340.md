<!-- loiofef5340250134900843a23329c90097b -->

| loio |
| -----|
| fef5340250134900843a23329c90097b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/fef5340250134900843a23329c90097b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/fef5340250134900843a23329c90097b)</div>

## Application Cache Buster: Index File

The index file includes all files that should use the cache buster.

Unlike the cache buster mechanism for runtime resources, the application files have an own timestamp for each file. Thus, the application provides the index file `sap-ui-cachebuster-info.json`. The index file looks as follows:

``` js

{
  "mvc/MyMVC.view.js": "20120907134005",
  "mvc/MyMVC.controller.js": "20120907134005",
  "mvc/MyMVC.view2.js": "20120906113301",
  "mvc/MyMVC.controller2.js": "20120906113023"
}
```

