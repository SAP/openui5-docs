| loio |
| -----|
| 698f8c0a889f48d3a8b7fbcd26779be2 |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/698f8c0a889f48d3a8b7fbcd26779be2.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/698f8c0a889f48d3a8b7fbcd26779be2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/698f8c0a889f48d3a8b7fbcd26779be2)</div>
<!-- loio698f8c0a889f48d3a8b7fbcd26779be2 -->

## Pitfalls and Troubleshooting

Tips and tricks if OPA is not behaving or reacting the way you expect it to.

***

### Why can't OPA find the control I'm looking for?

OPA checks a lot of conditions before it passes a control to your matchers/actions/success functions. If your control does not match these conditions, you will never be able to set a breakpoint. For such instances, OPA logs a lot of information into the browser's console, if you turn on the OpenUI5 debug mode. You can either use the `sap-ui-debug=true` URL parameter or the OpenUI5 [Diagnostics](Diagnostics_.md#loio6ec18e80b0ce47f290bc2645b0cc86e6). The diagnostics may also be helpful to see the state of your UI.

After turning on the debug mode, you can have a look at the log and also filter it by looking for `opa` or `matchers`.

 ![](loio340d18e41c28469fbd14b6fe128ff89b_LowRes.jpg) 

A frequent cause of error are typos in the view name or control IDs. These are easily found by looking through the logs.

***

#### Multiple views with the same `viewName`

If there are multiple views with the same `viewName`, OPA5 may not find the exact control you are looking for.

As of version 1.62, there are a couple of ways to ensure a correct match:

-   `viewId` parameter is introduced. You can set it in `Opa5.extendConfig()`, `Opa5.waitFor()` and in page object definitions. `viewId` can be used standalone or in combination with `viewName`. If OPA5 finds multiple views with the same name, it will prompt you to add a view ID with the test failure message "Please provide `viewId` to locate the exact view.".

-   Views that are not rendered will not be used in OPA5 control search.


***

#### Control is not found when running the test on a different machine or in a suite

The size of the iFrame in which the application is loaded is as big as the browser window. It is scaled down to leave space for the QUnit info but the content is preserved the same as when run in full size. This means that regardless of the small iFrame, you shouldn't see any responsive change in the application's appearance.

If the test runs fine locally but control is not found on another machine, there is a chance that the other machine's screen is too small and triggers the responsive behaviour of some controls. For example, CI executors with smaller screens or when the test is part of a suite and the iFrame is placed inside a suite wrapper much smaller than the screen.

One way is to test for the responsive behavior and add conditional `waitFors` and test cases. Tests for different screens, such as phone and desktop, are better separated in different test files.

If you want to workaround the sizing issue and don't want to test responsive behavior, you can set a fixed size for the iFrame. The idea is to write the test for the small size which will most probably result in the central environment. You can use the `width` and `height` parameters of `iStartMyAppInAFrame` or the `opaFrameWidth` and `opaFrameHeight` URL parameters.

If either width or height is not defined, the default 100% of the window's body will be set, and later scaled down by 40%.

If either width or height is not defined, a default value is assigned. The default screen size is 1280x1024 px. The iFrame takes 60% of the screen size, which makes the default iFrame size to be 768x614.4 px.

***

### Sometimes my test fails, sometimes it doesn't

***

#### **Is it the startup that's failing?**

Maybe the app is loading too slowly for the OPA tests. If there's a local index file that does not contain the library dependencies your application needs, the OpenUI5 bootstrap is very slow. To fix this, add the dependencies you need in your application descriptor's `sap.ui.dependencies` namespace. If you do not have a descriptor, use the bootstrap option libs. For more information, see [Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md) and [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md) respectively.

***

#### **It's failing during the execution**

If this happens, your test is probably executing actions faster than it should. If you encounter a failure, look at the current state of the UI - in almost all cases an action could not be triggered or a JavaScript error occurred. This error should be included in the console logs. If an action could not be executed, please make sure you use the action parameter of OPA5's `waitFor` function. When using the success function for triggering actions, OPA5 does not check a lot of things.

Here are some examples that have occurred in known applications:

-   An application was using the `bindingContext` of a control in a press handler. OPA5 was way faster than a human user, so the HTTP-Request that was sometimes finished by the time OPA5 was executing the check, was sometimes still pending and so an exception was thrown. The test failed because OPA was trying to reach a page that could not be shown because of this error. This had to be fixed in the application coding.

-   When there was no action parameter available, a `ListItem` got rerendered while a press action was executed on it. Due to the rerendering, the `List` was not able to perform the click, meaning it was not executed and the test failed. This only happened on certain occasions, depending on the execution speed of the machine executing the test. This is now detected automatically when using actions.


***

### OPA5 is failing on a specific browser: what should i do?

***

#### **Am i comparing language-dependent texts and the browser has a different language?**

Check the logs to see if your matcher is failing because it's checking a text against a different language. If you want to always execute your tests with the same language, use the `sap-ui-language=` URL or bootstrap parameter.

***

#### **It is only Internet Explorer that's affected?**

If you are using an IFrame to launch your application, Internet Explorer is more strict when it comes to objects from removed IFrames. If you are using the OPA context to remember objects, then destroy your frame and then execute a function on the object, you will get a JavaScript exception. How do you avoid it? By only remembering values like strings or integers when destroying the frame, or by using the component startup in OPA5.

***

### OPA is not even starting and there's no logging either

If you require `sinon-qunit.js`, it overwrites the browser functions `setTimeout` and `setInterval`. OPA needs these functions and without them, the tests will not start. You can either set the `fakeTimers` to false in your test setup, or maybe consider not using sinon together with OPA.

```lang-js
module("Opatests", {
    beforeEach : function () {
        sinon.config.useFakeTimers = false;
    },
    afterEach : function () {
        sinon.config.useFakeTimers = true;
    }
});
```

**Related information**  


[Diagnostics](Diagnostics_.md#loio6ec18e80b0ce47f290bc2645b0cc86e6)

