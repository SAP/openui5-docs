<!-- loio45ac9f19d9414b30b121c6e00f57433c -->

| loio |
| -----|
| 45ac9f19d9414b30b121c6e00f57433c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/45ac9f19d9414b30b121c6e00f57433c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/45ac9f19d9414b30b121c6e00f57433c)</div>

## Behavior-driven Development with Gherkin

With behavior-driven development \(BDD\), you as a developer start with a user story that defines the business value that the developed app should have. Next, you write a test that verifies the new functionality \(this test initially fails\). Finally, you write the needed functionality and your test passes. Gherkin is a test framework that supports this approach.

At first, as you are learning BDD, it will take a long time to implement new tests. Resist the temptation to abandon automated testing. The most important software development phase for successful software is the maintenance phase. Automated tests are the best way to ensure an effective maintenance phase, and help ensure that the code quality remains high over time.

It's true that when you first try automated testing it might take a long time, but even this first attempt will be worthwhile and pay dividends later. In your future projects, when you implement your tests much faster, your initial investment in learning how to do integration testing will really pay off.

One good way to ensure that you get the most value for your investment of time into automated testing is to ensure that you test the right things. Integration testing is best for testing the main path of the major business scenarios. These are what are called "face-saving tests", in the sense that you will lose face if you try to deliver the software when these major business scenarios are failing. Hence, integration tests are a great way to do a quick and painless smoke test every time you commit a change to your software, to ensure that you haven't broken anything important.

Since writing integration tests can be time-consuming, it's better to use unit testing to test all of the nuances and failure cases of your software. Unit tests are cheap and easy to write, and are better suited to achieving full test coverage for the software.

***

### Gherkin

Gherkin is written in JavaScript and is fully compatible with OpenUI5, OPA, and QUnit. It is based on the “cucumber” tool.

The advantages of using Gherkin are:

-   You write executable specifications that are easy to understand and that allow the easy generation of integration tests.

-   Product specification and documentation are **always up to date**; they evolve during the development project.

-   Single source of truth: Reduce communication errors across your development team, because the product owner, developers, and testers are all working from the same specification.

-   Maximize the business value you get out of the time spent writing tests, and keep your focus on the customer and their requirements.


The Gherkin library contains the following parts:

-   Feature file

    Software specification written in Gherkin syntax. Feature files are human-readable specifications that are also machine-readable. Features are composed of **test scenarios**, which are themselves composed of **test steps**.

    ```nocode
    Feature: Wearing sunscreen stops skin cancer
    
      Scenario: Apply sunscreen
        Given the sun is dangerous
        When I apply sunscreen
        Then I protect my skin
    ```

-   Steps file

    Translates the feature file into something a computer can understand and execute. The steps file also contains the tests to be executed to ensure that the software behaves according to its specification. The main elements of a steps file are called **step definitions**.

    ``` js
    this.register(/^I protect my skin$/i, function() {
      this.assert.assertEqual(this.mySkin, 'protected');
    });
    ```

-   Test harness

    Stitches together the feature file and steps file and executes runtime tests on the result using a test framework such as QUnit.

-   `DataTableUtils`

    Convenience library for handling data tables and string normalization.


-   **[Feature Files](Feature_Files_9113397.md " Feature files are human-readable specifications that are also machine-readable.")**  
 Feature files are human-readable specifications that are also machine-readable.
-   **[Basic Example How to Use Gherkin](Basic_Example_How_to_Use_Gherkin_4b0c519.md "Like test-driven development (TDD), behavior-driven development (BDD) with Gherkin encourages us to write more tests because you do it right from
		the beginning. Having more tests makes it cheaper and easier to maintain the code over time. Let's dive into the specifics using following an
		example.")**  
Like test-driven development \(TDD\), behavior-driven development \(BDD\) with Gherkin encourages us to write more tests because you do it right from the beginning. Having more tests makes it cheaper and easier to maintain the code over time. Let's dive into the specifics using following an example.
-   **[Gherkin and OPA Page Objects](Gherkin_and_OPA_Page_Objects_c689cd8.md "Gherkin is compatible with the concept of OPA5 page objects.")**  
Gherkin is compatible with the concept of OPA5 page objects.
-   **[Code Coverage](Code_Coverage_20737a4.md "It can be handy to calculate the code coverage of your integration tests, for example, to figure out whether you forgot to test something or to
		provide statistics on your test quality.")**  
It can be handy to calculate the code coverage of your integration tests, for example, to figure out whether you forgot to test something or to provide statistics on your test quality.
-   **[Logging](Logging_ebcf60c.md "During tesing with Gherkin, errors are logged to the test execution Web page. ")**  
During tesing with Gherkin, errors are logged to the test execution Web page.
-   **[Frequently Asked Questions](Frequently_Asked_Questions_02ef39f.md "")**  


**Related Information**  


[cucumber Home Page](https://cucumber.io/)

[Gherkin documentation on Github](https://github.com/cucumber/cucumber/wiki/Gherkin)

