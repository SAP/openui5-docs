<!-- loio2696ab50faad458f9b4027ec2f9b884d -->

| loio |
| -----|
| 2696ab50faad458f9b4027ec2f9b884d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/2696ab50faad458f9b4027ec2f9b884d) | [demo kit latest release](https://sdk.openui5.org/topic/2696ab50faad458f9b4027ec2f9b884d)</div>

## Integration Testing with One Page Acceptance Tests \(OPA5\)

OPA5 is an API for OpenUI5 controls. It hides asynchronicity and eases access to OpenUI5 elements. This makes OPA especially helpful for testing user interactions, integration with OpenUI5, navigation, and data binding.

The OPA5 library is JavaScript-based. This means that you can write your tests in the same language in which your app is written. This has the following advantages:

-   Quick and easy access to JavaScript functions

-   Easy ramp-up as it can be used with any JavaScript unit test framework, such as QUnit or Jasmine

-   Using the same runtime enables debugging

-   Good OpenUI5 integration

-   Feedback within seconds makes it possible to execute tests directly after a change

-   Asynchronicity is handled with polling instead of timeouts, which makes it faster

-   Enables test-driven development \(TDD\)


Developers write OPA tests during app development. The test-driven development \(TDD\) results in less fragile tests, because the app is better isolated and supports less fragile APIs for testing:

-   It follows the arrange act assert pattern \(corresponds to given when then\), which improves readability and understanding of the test cases.

-   It is easy to run on mobile devices as no plugins/apps are needed; you can as easily just run it in the browser.

-   Saves time for the developer as regressions decrease


In short: Writing acceptance tests with OPA5 is very easy – Give it a try!

***

### Restrictions of OPA5

Note the following restrictions of OPA:

-   Screen capturing
-   Testing across more than one page
-   Remote test execution
-   End-to-end tests are not recommended with OPA due to authentication issues and fragility of test data

-   **[Getting Started with OPA5](Getting_Started_with_OPA5_22f175e.md "The following section explains step-by-step how to easily write tests for OpenUI5 apps.")**  
The following section explains step-by-step how to easily write tests for OpenUI5 apps.
-   **[Cookbook for OPA5](Cookbook_for_OPA5_ce4b180.md "Advanced topics and best practices for OPA tests.")**  
Advanced topics and best practices for OPA tests.
-   **[Retrieving Controls](Retrieving_Controls_21aeff6.md "Common use cases for retrieving controls")**  
Common use cases for retrieving controls
-   **[Structuring OPA Tests With Page Objects](Structuring_OPA_Tests_With_Page_Objects_f2f843d.md "The page object design pattern supports UI-based tests with improved readability,
        fostering the don't repeat yourself (DRY) principle of software
        development that is aimed at reducing repetition of any kind of information.")**  
The page object design pattern supports UI-based tests with improved readability, fostering the *don't repeat yourself* \(DRY\) principle of software development that is aimed at reducing repetition of any kind of information.
-   **[Using the autoWait Parameter](Using_the_autoWait_Parameter_fb487ef.md "Configuring OPA to use autoWait parameter for all statements
		improves test stability and reduces the number of waitFor
		statements.")**  
Configuring OPA to use `autoWait` parameter for all statements improves test stability and reduces the number of `waitFor` statements.
-   **[Extensions for OPA5](Extensions_for_OPA5_9c22d2a.md "Extend OPA capabilities with custom extensions.")**  
Extend OPA capabilities with custom extensions.
-   **[Test Libraries for OPA5](Test_Libraries_for_OPA5_a88a5e5.md "Test libraries are a means of collaboration between app developers and reusable
		content providers.")**  
Test libraries are a means of collaboration between app developers and reusable content providers.
-   **[Simulating User Interactions on Controls](Simulating_User_Interactions_on_Controls_8615a0b.md "OPA5 has a built-in actions parameter that can be used for simulating events. If you use
        an action, OPA5 makes sure that the UI is in a state that allows the action to be
        executed.")**  
OPA5 has a built-in actions parameter that can be used for simulating events. If you use an action, OPA5 makes sure that the UI is in a state that allows the action to be executed.
-   **[Using OpaBuilder](Using_OpaBuilder_952e2c7.md "Write tests by leveraging the builder pattern to create OPA5 descriptors.")**  
Write tests by leveraging the builder pattern to create OPA5 descriptors.
-   **[Pitfalls and Troubleshooting](Pitfalls_and_Troubleshooting_698f8c0.md "Tips and tricks if OPA isn't behaving or reacting the way you expect it to.")**  
Tips and tricks if OPA isn't behaving or reacting the way you expect it to.

**Related Information**  


[Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md "Browser and platform support for the OpenUI5 libraries on iOS, Android, macOS, and Windows platforms.")

