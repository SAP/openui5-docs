<!-- loio4a063b8250f24d0cbf7c689821df7199 -->

| loio |
| -----|
| 4a063b8250f24d0cbf7c689821df7199 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/4a063b8250f24d0cbf7c689821df7199) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/4a063b8250f24d0cbf7c689821df7199)</div>

## Step 17: Listen to Matched Events of Any Route

In the previous step, we have listened for bypassed events to detect possible technical issues with our app. In this step, we want to improve the analysis use case even more by listening to any matched event of the route. We could use this information to measure how the app is used and how frequently the pages are called. Many Web analytic tools track page hits this way. The collected information can be used, for example to improve our app and its usability.

***

### Preview

   
  
<a name="loio4a063b8250f24d0cbf7c689821df7199__fig_r1j_pst_mr"/>Console output for routes matched by listening to `routeMatched` events

 ![](loioea12aae79b3841fe927f8e57f2f73e3b_HiRes.png "Console output for  routes matched by listening to routeMatched
					events") 

***

### Coding

You can view and download all files in the *Samples* in the Demo Kit at [Routing and Navigation - Step 17](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.navigation.17/preview).

***

### webapp/controller/App.controller.js

``` js
sap.ui.define([
	"sap/ui/demo/nav/controller/BaseController",
	"sap/base/Log"
], function (BaseController, Log) {
	"use strict";
	return BaseController.extend("sap.ui.demo.nav.controller.App", {
		onInit: function () {
			// This is ONLY for being used within the tutorial.
			// The default log level of the current running environment may be higher than INFO,
			// in order to see the debug info in the console, the log level needs to be explicitly
			// set to INFO here.
			// But for application development, the log level doesn't need to be set again in the code.
			Log.setLevel(Log.Level.INFO);

			var oRouter = this.getRouter();
			oRouter.attachBypassed(function (oEvent) {
				var sHash = oEvent.getParameter("hash");
				// do something here, i.e. send logging data to the back end for analysis
				// telling what resource the user tried to access...
				Log.info("Sorry, but the hash '" + sHash + "' is invalid.", "The resource was not found.");
			});
			*HIGHLIGHT START*oRouter.attachRouteMatched(function (oEvent){
				var sRouteName = oEvent.getParameter("name");
				// do something, i.e. send usage statistics to back end
				// in order to improve our app and the user experience (Build-Measure-Learn cycle)
				Log.info("User accessed route " + sRouteName + ", timestamp = " + new Date().getTime());
			});*HIGHLIGHT END*
		}
	});
});
```

We extend the `App` controller again and listen to the `routeMatched` event. The `routeMatched` event is thrown for any route that matches to our route configuration in the descriptor file. In the event handler, we determine the name of the matched route from the event parameters and log it together with a time stamp. In an actual app, the information could be sent to a back-end system or an analytics server to find out more about the usage of your app.

Now you can access, for example, `webapp/index.html#/employees` while you have the console of the browser open. As you can see, there is a message logged for each navigation step that you do within the app.

**Parent topic:** [Navigation and Routing](Navigation_and_Routing_1b6dcd3.md "OpenUI5 comes with a powerful routing API that helps you control the state of your application efficiently. This tutorial will illustrate all major features and APIs related to navigation and routing in OpenUI5 apps by creating a simple and easy to understand mobile app. It represents a set of best practices for applying the navigation and routing features of OpenUI5 to your applications.")

**Next:** [Step 16: Handle Invalid Hashes by Listening to Bypassed Events](Step_16_Handle_Invalid_Hashes_by_Listening_to_Bypassed_Events_a7932a7.md "So far we have created many useful routes in our app. In the very early steps we have also made sure that a Not Found page is displayed in case the app was called with an invalid hash. Now, we proceed further and track invalid hashes to be able to detect and correct any invalid links or add new URL patterns that are often requested but not found. Therefore, we simply listen to the bypassed events")

