| loio |
| -----|
| d2f58695fce3476f92fdfc07c9e8f7c6 |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/d2f58695fce3476f92fdfc07c9e8f7c6.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d2f58695fce3476f92fdfc07c9e8f7c6) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d2f58695fce3476f92fdfc07c9e8f7c6)</div>
<!-- loiod2f58695fce3476f92fdfc07c9e8f7c6 -->

## App Initialization: What Happens When an App Is Started?

When a user starts an app \(in the SAP Fiori launchpad \(FLP\) or using an HTML page\), several steps will be performed in the background.

***

> Note:
> When a user closes the app, the `destroy` function of the component is called. All models and the router are destroyed. The router will take care of destroying the views.
> 
> If a controller has created resources that need to be destroyed explicitly, for example non-aggregated controls, the app developer has to use the `onExit` function of the controller to free up resources. For more information, see [Controller](Controller_121b8e6.md).
> 
> 

**Related information**  


[App Overview: The Basic Files of Your App](App_Overview_The_Basic_Files_of_Your_App_28b59ca.md)

