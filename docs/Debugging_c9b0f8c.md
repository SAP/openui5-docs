<!-- loioc9b0f8cca852443f9b8d3bf8ba5626ab -->

| loio |
| -----|
| c9b0f8cca852443f9b8d3bf8ba5626ab |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/c9b0f8cca852443f9b8d3bf8ba5626ab) | [demo kit latest release](https://sdk.openui5.org/topic/c9b0f8cca852443f9b8d3bf8ba5626ab)</div>

## Debugging

When developing apps, searching for bugs is an inevitable part of the process. To analyze an issue, you can use the developer tools of your browser and built-in OpenUI5 tools. In this section, we give an overview of the OpenUI5 tools you can use when debugging. To learn more about the developer tools of your browser, check the documentation of the browser.

 <a name="loio1ed4b5f9f18848b1badee9b72d4ac261"/>

<!-- loio1ed4b5f9f18848b1badee9b72d4ac261 -->

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

<a name="loioc57cb1c50c584fb1930d8da5f709b3ba"/>

<!-- loioc57cb1c50c584fb1930d8da5f709b3ba -->

### Switching the OpenUI5 Version

***

Open the *Diagnostics* window with the shortcut [CTRL\] + [SHIFT\] + [ALT\] + [S\].

At the top of the *Debugging* view, you can configure a custom URL from which the application should load OpenUI5 the next time that the app opens.

Either select a known OpenUI5 installation from the dropdown box, or enter a different URL that points to the `sap-ui-core.js` file within a complete OpenUI5 runtime.

Once you have entered the URL, press *Activate Reboot URL*. When you then reload the application page, the application loads OpenUI5 from the alternative URL. This only happens for the next single reboot; after that, OpenUI5 is loaded again from the standard URL referenced within the app.

This feature can be used to test an application against a newer or older version of OpenUI5 as part of compatibility testing, or for verifying a bug fix or regression.

![](images/loio64d3bfdd0f784ae68030208523452899_LowRes.png)

 <a name="loio9d57287c155741e7ad15f42736605ffa"/>

<!-- loio9d57287c155741e7ad15f42736605ffa -->

### Setting Breakpoints

Breakpoints are helpful when you debug the event handling of an OpenUI5 object. You can either set breakpoints in the developer tools of your browser, or use the *Diagnostics* window.

For more information, see [Diagnostics](Diagnostics_6ec18e8.md#loio6ec18e80b0ce47f290bc2645b0cc86e6).

 <a name="loio549150aa11cf432780c1801a6e2dc3c4"/>

<!-- loio549150aa11cf432780c1801a6e2dc3c4 -->

### Breakpoints on the Class Level

In the *Debugging* section of the *Diagnostics* window, you can set breakpoints on the class level.

1.  Open the *Debugging* view of the *Diagnostics* window.

2.  Select a class from the dropdown list or enter the name of the class and choose *Add Class*.

    The selected class is now visible below the dropdown list.

    The number next to the method name shows the number of methods that belong to the class and the number of methods for which a breakpoint is set.

3.  Select the class. On the right side of the view, you can now select methods of the selected class from a dropdown list.

4.  From the dropdown list, select the method for which you want to set the breakpoint and choose *Add breakpoint*.

    The selected methods are listed below the dropdown list.

5.  Open the developer tools of your browser. Whenever the selected methods are called for any instance of the selected control, the code execution is paused in the debugger.

    ![](images/loiof54ea7bfedff4501959df91b53697579_LowRes.png)

    In the call stack you find the method for which you set a breakpoint.

    ![](images/loio862249d44d7c478cb7be1abb033115bd_LowRes.png)

6.  To remove a breakpoint, select the red x.


 <a name="loiob691c4e7e970484991007a4e30fcd6d0"/>

<!-- loiob691c4e7e970484991007a4e30fcd6d0 -->

### Breakpoints on the Object Level

In the *Control Tree* of the *Diagnostics* window, you can set breakpoints on the object level.

1.  Open the *Control Tree* view of the *Diagnostics* window.

2.  Select a control in the tree.

    You can also press and hold [Ctrl\] + [Shift\] + [Alt\] and select a control in your app to select it in the tree.

3.  Select the *Breakpoints* tab on the right.

4.  From the dropdown list, select the method for which you want to set the breakpoint and choose *Add breakpoint*.

    The selected methods are listed below the dropdown list.

5.  Open the developer tools of your browser. Whenever the selected methods are called for any instance on the control, the code execution is paused in the debugger.

    ![](images/loioecd173835d854d65877e2be9ebc1f08f_LowRes.png)

6.  To remove a breakpoint, select the red x.


