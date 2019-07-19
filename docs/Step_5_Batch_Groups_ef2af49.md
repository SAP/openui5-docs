<!-- loioef2af4957fae469e9203e98006d3ee75 -->

| loio |
| -----|
| ef2af4957fae469e9203e98006d3ee75 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ef2af4957fae469e9203e98006d3ee75) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ef2af4957fae469e9203e98006d3ee75)</div>

## Step 5: Batch Groups

In this step, we have a closer look at batch groups. Batch groups are used to group multiple requests into one server request to improve the overall performance.

***

<a name="loioef2af4957fae469e9203e98006d3ee75__section_bt4_fxc_z1b"/>

### Preview

   
  
No visual change compared to the last step<a name="loioef2af4957fae469e9203e98006d3ee75__fig_klh_5kw_4cb"/>

 ![](loio3ac4fcc0ea714c7c9157b22cbca4db79_LowRes.png "No visual change compared to the last step") 

***

<a name="loioef2af4957fae469e9203e98006d3ee75__section_tsr_gxc_z1b"/>

### Coding

You can view and download all files at [OData V4 - Step 5](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.odatav4.05/preview).

***

<a name="loioef2af4957fae469e9203e98006d3ee75__section_pp2_mxc_z1b"/>

### webapp/manifest.json

``` json
...
				"": {
				"dataSource": "default",
				"settings": {
					"autoExpandSelect": true,
					"operationMode": "Server",
					*HIGHLIGHT START*"groupId": "$auto"*HIGHLIGHT END*,
					"synchronizationMode": "None"
				}
...
```

In the previous steps, batch processing was turned off, so that we could monitor the network traffic between our app and the service more easily. Now we turn on batch processing by changing the `groupID` to `$auto`. You can also just remove the line from the code as this is the default.

We now run the app and open the browser developer tools. On the *Console* tab, we clear all messages and choose the *Refresh* button.

> Note:
> Change the settings of the *Console* so that it only displays information messages, not warnings and errors, to make it easier to find the messages we're looking for.
> 
> 

We see that the request is now bundled: To read the user data, the app now sends a `POST` request instead of a `GET` request to the server. The URL of the `POST` request does not include the `path` to the data we want. Instead it ends with `$batch` that indicates that this is a batch request.

A `$batch` request uses multipart MIME to put several requests into one. This makes it harder to analyze when looking at the request in the browser developer tools. To overcome this issue, you can:

-   Switch the group ID to `$direct` temporarily by changing the source code or changing the default value in the debugger.

-   Copy the relevant part of the request or response from the developer tools to an editor and auto-format it as JSON to analyze it.


**Related information**  


[Batch Control](Batch_Control_74142a3.md)

[Performance Aspects](Performance_Aspects_5a0d286.md)

