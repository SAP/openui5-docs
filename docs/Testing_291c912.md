<!-- loio291c9121e6044ab381e0b51716f97f52 -->

| loio |
| -----|
| 291c9121e6044ab381e0b51716f97f52 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/291c9121e6044ab381e0b51716f97f52) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/291c9121e6044ab381e0b51716f97f52)</div>

## Testing

In this tutorial we will test application functionality with the testing tools that are delivered with OpenUI5. At different steps of this tutorial you will write tests using QUnit, OPA5, and the mock server. Additionally, you will learn about testing strategies, Test Driven Development \(TDD\), and much more.

For the application features that we add, we focus on writing clean and testable code with the goal of having good test coverage and a high quality app. We will create a simple full screen app that we will extend with more tests and features throughout the tutorial.

Imagine the following situation: You and your development team take over a bulletin board prototype that will be shipped as a product soon. A bulletin board typically consists of functionality to browse posts and add own offers to the board. However, the prototype only covers a minimum set of features and tests so far.

With this very minimalistic app as a starting point, we have a good foundation and we can inspect the most important testing functionality. Furthermore, we want to implement new features for the app that were requested by the product team using Test Driven Development and best practices for writing testable code and testing OpenUI5 apps.

So why do we do all this? Obviously, writing tests and testable code does not come without effort. Well, we want to ensure the implementation of a high quality app by having decent test coverage of our application logic. And we check that our code does not break by running the automated tests whenever we change something or when we upgrade to a newer version of the OpenUI5 framework or other external libraries. Additionally, we can find bugs proactively and do not need excessive manual testing anymore so the efforts definitely pay off. Also, when we decide to refactor something in the future, we can easily verify that the features of the app are still working as expected.

There are a lot more reasons and many small details that we will address throughout this tutorial. You can work yourself through the steps by applying the code deltas individually or by downloading the samples for each step and playing around with it.

***

### Preview

 ![](loio89001ea1e4ab4529b8d412ee683b9744_HiRes.png) 

***

### Prerequisites

In addition to the prerequisites that are presupposed for all our tutorials \(see [Prerequisites](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_prerequisites)\), you should also be familiar with the basics of JavaScript unit testing with QUnit. Have a look at the official QUnit documentation to make yourself familiar with basic testing knowledge. Steps 27 to 29 of the Walkthrough tutorial also cover the test setup in an app that is used throughout this tutorial.

If you want to automate the test execution using a test runner, you can set this up as described under [Test Automation](Test_Automation_.md#loioae448243822448d8ba04b4784f4b09a0).

***

> Note:
> You don't have to do all tutorial steps sequentially, you can also jump directly to any step you want. Just download the code from the previous step, and start there.
> 
> You can view and download the files for all steps in the Demo Kit at [Testing Apps](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.tutorial.testing/samples). Copy the code to your workspace and make sure that the application runs by calling the `webapp/test/test.html` file. Depending on your development environment you might have to adjust resource paths and configuration entries.
> 
> For more information check the following sections of the tutorials overview page \(see [Get Started: Setup and Tutorials](Get_Started_Setup_and_Tutorials_8b49fc1.md)\):
> 
> -   [Downloading Code for a Tutorial Step](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download)
> 
> -   [Adapting Code to Your Development Environment](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation)
> 
> 
> 

**Related information**  


[Testing](Testing_7cdee40.md)

[QUnit Home Page](https://qunitjs.com/)

