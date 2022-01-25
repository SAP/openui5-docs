<!-- loioebcf60c3b0e24c348b88603bbb8eb16c -->

| loio |
| -----|
| ebcf60c3b0e24c348b88603bbb8eb16c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ebcf60c3b0e24c348b88603bbb8eb16c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ebcf60c3b0e24c348b88603bbb8eb16c)</div>

## Logging

During tesing with Gherkin, errors are logged to the test execution Web page.

Most error messages are sufficient to figure out what has gone wrong, for example, if an OPA5 `waitFor` call is failing. Gherkin also logs information to the JavaScript console with the prefix `[GHERKIN]` at priority `INFO`.

> ### Note:  
> If at test execution time you don't see the logs, then OpenUI5 might not be logging down to this level.
> 
> Check the bootstrap in the HTML file:
> 
> ``` html
> <!DOCTYPE html>
> <html>
>   <head>
>     <meta charset="utf-8">
>     <title>Using Gherkin with OPA5</title>
> 
>     <script
>       id="sap-ui-bootstrap"
>       src="https://openui5nightly.hana.ondemand.com/resources/sap-ui-core.js"
>       data-sap-ui-resourceroots='{"GherkinWithOPA5": "./"}'
>       **data-sap-ui-loglevel="INFO"**>
>     </script>
> ```

***

Here are some examples of Gherkin console logs:

-   `[GHERKIN] Running feature: 'Feature: Clicking Buttons Is a Life Saving Activity'`

-   `[GHERKIN] Running scenario: 'Scenario: Click a button, save a life!'`

-   `[GHERKIN] Running step: text='I see Alice' regex='/^I see (.*?)$/i'`


These logs are particularly helpful for telling you which regular expression \(the `regex` attribute from step definition in a steps file\) was matched with a particular feature file test step \(the `text` attribute\). This can help you search for the relevant regular expression among your step definitions \(when your test code is large\), and could also help with troubleshooting if an unexpected regular expression is being matched.

