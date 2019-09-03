<!-- loioae448243822448d8ba04b4784f4b09a0 -->

| loio |
| -----|
| ae448243822448d8ba04b4784f4b09a0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ae448243822448d8ba04b4784f4b09a0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ae448243822448d8ba04b4784f4b09a0)</div>

## Test Automation

To make sure that the code is always tested thoroughly before it is included in a productive app, you should use a test runner that automates tests. The test runner can be included in your project setup so that it is called whenever code changes are submitted.

In the following section, we describe the setup with *Karma*, but you can of course choose a different solution.

*Karma* uses plugins to add support for various framworks. For OpenUI5, you can use the `karma-ui5` plugin that helps with testing OpenUI5 projects.

**Related information**  


[Continuous Integration: Ensure Code Quality](Continuous_Integration_Ensure_Code_Quality__fe7a158.md)

[*Karma* Home Page](https://karma-runner.github.io/)

[`karma-ui5` on GitHub](https://help.sap.com/viewer/disclaimer-for-links?q=https%3A%2F%2Fgithub.com%2FSAP%2Fkarma-openui5)

 <a name="loioae448243822448d8ba04b4784f4b09a0 loioa182676ed3714bd5b4f011eb29076f6c__loioa182676ed3714bd5b4f011eb29076f6c"/>

<!-- loioa182676ed3714bd5b4f011eb29076f6c -->

## Installing Karma for Automated Testing

Initial setup of the application testing environment with Karma.

***

You have installed *Node.js* in version 8.5 or higher and *npm*.

1.  Install *Karma* globally via *npm* so that you can run *Karma* by typing the `karma` command in your command-line interface \(CLI\).

    For more information, see the [Karma Installation Guide on GitHub](http://karma-runner.github.io/1.0/intro/installation.html).

    Use the following command:

    ```nocode
    npm install --global karma-cli
    ```

2.  Create a `package.json` file.

    -   If you already have an *npm* project, you can skip this step.

    -   If not, use the following command:

```nocode
npm init --yes
```

3.  Install *Karma* locally in your working directory.

    Use the following command:

    ```nocode
    npm install --save-dev karma
    ```

4.  Install the *Karma UI5 plugin* locally on your working directory.

    Use the following command:

    ```nocode
    npm install --save-dev karma-ui5
    ```

5.  Install the *Karma Chrome Launcher* locally in your working directory.

    Use the following command:

    ```nocode
    npm install --save-dev karma-chrome-launcher
    ```

    In this example, we use Google Chrome as browser. You can find an overview of availabler browser launchers by searching for packages with the keywords `karma-launcher` on the *npm* home page.

6.  Create a `karma.conf.js` file in your working directory with the following content:

    ``` js
    module.exports = function(config) {
      config.set({
    
        frameworks: ["ui5"],
    
        ui5: {
          url: "https://<<server\>\>:<<port\>\>"
        },
     
        browsers: ["Chrome"]
        
        });
      });
    ```

    Adapt the URL \(`<server\\\>:<port\\\>` to the OpenUI5 resources according to your installation. You can also use OpenUI5 from a content delivery network, see [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

    > Note:
    > The OpenUI5 plugin uses sensible defaults to detect your type of project and the relevant folders. If you have a project with a different structure, you need to add some more configuration options. For more information, see the [Karma UI5 documentation](https://github.com/SAP/karma-ui5#about) on GitHub.
    > 
    > 

7.  You can now run the tests with the following command:

    ```nocode
    karma start
    ```


**Related information**  


[*Karma* Home Page](https://karma-runner.github.io/)

[*Node.js* Home Page](http://nodejs.org/)

[*npm* Home Page](https://www.npmjs.com/)

[karma-ui5 on GitHub](https://github.com/SAP/karma-openui5)

 <a name="loioae448243822448d8ba04b4784f4b09a0 loio8c27b0ab239242c69f181208c9b8fb1d__loio8c27b0ab239242c69f181208c9b8fb1d"/>

<!-- loio8c27b0ab239242c69f181208c9b8fb1d -->

## Continuous Integration With Headless Chrome

For running tests in CI scenarios, such as Travis CI in GitHub, Headless Chrome needs to be used. Headless Chrome is a Chromium Browser without GUI \(in a headless environment\).

You can use Headless Chrome standalone, but also with Karma. To launch Karma with Headless Chrome, you need to add the following changes to the karma config.

1.  Add `karma-chrome-launcher` to the project dev dependencies.

    ```
    npm install -D karma-chrome-launcher
    ```

    > Note:
    > This is only required, if Chrome is **not** used as browser, that means, it was not defined during karma initialization. In some cases, for example for running tests in a docker container, we recommend to add puppeteer as dependency which includes the latest Chrome version. For more details, see the karma-chrome-launcher repository on GitHub.
    > 
    > 

2.  Define the browser environment for running karma. For this, update the `config` object in `karma.conf.js` as follows:

    ``` js
    module.exports = function(config) {
      config.set({
        [...]
        browsers: ['ChromeHeadless'],
        singleRun: true
        [...]
      })
    }
    ```

    > Note:
    > Make sure to set the `singleRun` flag to `true`. Otherwise, the script ends up in watch mode, listening for file changes.
    > 
    > 


You can launch karma also with a specific config file. It might make sense, for example, to define a config file \(default: `karma.conf.js`\) for the local environment, and one config file, for example `karma-ci.conf.js` for the CI scenario. To launch karma with a different config file, add the file name as third parameter as follows:

``` js
karma start karma-ci.conf.js
```

 <a name="loioae448243822448d8ba04b4784f4b09a0 loio1851a066b0e34d84ae00f887445239e5__loio1851a066b0e34d84ae00f887445239e5"/>

<!-- loio1851a066b0e34d84ae00f887445239e5 -->

## Code Coverage with Istanbul and OPA5

To measure the code coverage, you can use the *Istanbul Code Coverage* plugin for *Karma*. Since the *Istanbul* plugin cannot retrieve results from within iFrames, you may run into problems if you use OPA5 tests.

To get correct code coverage results for OPA5 tests, you need to execute them inside the component containers instead of iFrames. This will also speed up the execution time of your OPA5 tests.

> Note:
> With component containers, you lose the isolation of your single tests. Also, the `index.html` file of your app is no longer executed \(only the `Component.js` file is needed\).
> 
> 

To execute the tests inside a component container, replace `iStartMyAppInAFrame()` with `iStartMyUIComponent()` and `iTeardownMyAppFrame()` with `iTeardownMyApp()` in all your OPA5 tests.

> Note:
> Currently, this does not work for apps that are created for the SAP Fiori launchpad \(FLP\).
> 
> 

For more information, see the [API Reference: `sap.ui.test.Opa5`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.test.Opa5.html).

**Related information**  


[*Istanbul Code Coverage* Home Page](https://istanbul.js.org/)

