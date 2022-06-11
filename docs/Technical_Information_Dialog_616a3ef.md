<!-- loio616a3ef07f554e20a3adf749c11f64e9 -->

| loio |
| -----|
| 616a3ef07f554e20a3adf749c11f64e9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/616a3ef07f554e20a3adf749c11f64e9) | [demo kit latest release](https://sdk.openui5.org/topic/616a3ef07f554e20a3adf749c11f64e9)</div>

## Technical Information Dialog

The *Technical Information* dialog shows details of the OpenUI5 version currently being used in an app built with OpenUI5. You can use the *Technical Information* dialog to enable debug resources and open additional support tools to debug your app.

To open the technical information dialog from within a supported desktop browser, use the following [shortcut](Keyboard_Shortcuts_for_OpenUI5_Tools_154844c.md):

  [Ctrl\] + [Shift\] + [Alt\] / [Option\] + [P\] 

![](images/loio8bf9780408674588af6d33eb6cebadab_LowRes.png)

The dialog contains the following information:

-   The version number of the currently loaded OpenUI5 distribution that represent the core libraries of the framework and its build timestamp

    For more information, see [Versioning and Maintenance of OpenUI5](Versioning_and_Maintenance_of_OpenUI5_91f0214.md) and [SAPUI5 vs. OpenUI5](SAPUI5_vs_OpenUI5_5982a97.md)

-   The **user agent** that is used for detecting the device's capabilities and device adaption

-   The root **URL** of the currently loaded app


You can download the technical information, so that you can attach it to a ticket for example, by clicking *Copy*.

 <a name="copyda1306a437244116b156c4428b3c5b5f"/>

<!-- copyda1306a437244116b156c4428b3c5b5f -->

### Loading Debug Sources

For performance reasons, the OpenUI5 files are loaded in a minified version, this means that all possible variable names are shortened and comments are removed. This makes debugging harder because the code is less readable.

For debugging, you first have to load the *Debug Sources*. You have the following options:

-   URL parameter `sap-ui-debug=true`

-   Select the *Use Debug Sources* in the *Technical Information Dialog*

    For more information, see [Technical Information Dialog](Technical_Information_Dialog_616a3ef.md#loio616a3ef07f554e20a3adf749c11f64e9).


If you only want to load the debug sources for **specific packages**, you have the following options:

-   Add the module names to the `sap-ui-debug` URL parameter, separated by a comma. For example, `sap-ui-debug=sap/ui/core/Core.js,sap/m/InputType.js` loads the debug sources for the `sap.ui.core.Core` and `sap.m.InputType` libraries.

-   Choose the *Select specific modules* link in the *Technical Information Dialog*.

    For more information, see [Technical Information Dialog](Technical_Information_Dialog_616a3ef.md#loio616a3ef07f554e20a3adf749c11f64e9).


After reloading the page, in the *Network* tab of the browser’s developer tools you can see that the controls and framework assets are now loaded individually and have a `-dbg` suffix. These are the source code files that include comments, the uncompressed code of the app, and the OpenUI5 artifacts.

Choose  [Ctrl\] + [O\]  \(Windows\) or  [Command\] + [O\]  \(macOS\) and type the name of an OpenUI5 artifact to view its source code in debug mode.

> ### Note:  
> Turning on debug sources also increases the log level. For more information, see [Logging and Tracing](Logging_and_Tracing_9f4d62c.md).
> 
> To improve performance, you must deactivate the debug sources once you're done with debugging.

 <a name="loiob5dcf47c7d4a4228ab40d77f835648e3"/>

<!-- loiob5dcf47c7d4a4228ab40d77f835648e3 -->

### Technical Information Dialog on Mobile Devices

On mobile devices, the *Technical Information* dialog provides some additional features.

***

-   *Configurations \(bootstrap\)* - Displays a list of bootstrap parameters.
-   *Configurations \(computed\)* - Displays a list of computed parameters.
-   *URI parameters* - Displays the variables passed from the URI query string.
-   *End-to-End Trace* - A function that traces communication to a different part of the app.
-   *Loaded Libraries* - Displays a list of the currently loaded libraries.
-   *Loaded Modules* - Displays a collapsible list of the currently loaded modules.

<a name="loiob5dcf47c7d4a4228ab40d77f835648e3__table_mr1_wbn_tv"/>Technical Information Dialog on Mobile Devices


<table>
<tr>
<td valign="top">

![Technical Information in Mobile App](images/loiof11a08225adf4264a9ec9cbc2daad467_LowRes.jpg)



</td>
<td valign="top">

![Technical Information in Mobile App](images/loiod1e10c1bbf3d4983b8c2e39db7dbcdb0_LowRes.jpg)



</td>
</tr>
<tr>
<td valign="top">

![Technical Information in Mobile App](images/loioca7ba5f050484b99bede25b6c720ce30_LowRes.jpg)



</td>
<td valign="top">

![Technical Information in Mobile App](images/loiofc573fe3283d4e6da322a54e70bda756_LowRes.jpg)



</td>
</tr>
</table>

***

#### Accessing the Technical Information Dialog on Mobile Devices

To open the *Technical Information* dialog on your mobile device, proceed as follows:

1.  Press two fingers on a noninteractive screen area \(for example, a blank area\) for at least 3 seconds.
2.  Tap with a third finger while holding the other two on the screen.

> ### Restriction:  
> -   The *Technical Information* dialog can only be opened on mobile devices that support multi-touch.

  
  
<a name="loiob5dcf47c7d4a4228ab40d77f835648e3__fig_rlq_rlj_b1b"/>Gesture for opening the technical information dialog

![](images/loiodf42057180444e1ca483af61049f0555_LowRes.png "Gesture for opening the technical information dialog")

***

#### Using the End-to-End \(E2E\) Trace Function

The *E2E Trace* is used to create an XML file that traces the communication to a different part of your app.

To start the *E2E Trace*, proceed as follows:

1.  Select the detail level from the *Trace Level* dropdown list.
2.  Choose *Start*.
3.  Navigate to a different part of the application.

As a result, a dialog box opens indicating that your transaction has finished. Choose *OK* to continue running the current trace. Choose *Cancel* to stop the trace and display the result in a new window.

After stopping the trace, you can view the result and \(optionally\) upload it to a server by entering a `host name` and a `port number`, and then choosing *Submit*.

> ### Note:  
> The result of the last completed trace is also visible in the *XML Output* field when you open the *Technical Information* dialog again.

