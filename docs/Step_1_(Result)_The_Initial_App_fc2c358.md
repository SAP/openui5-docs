<!-- loiofc2c35880ccf4282a6baf8ab861bc10e -->

| loio |
| -----|
| fc2c35880ccf4282a6baf8ab861bc10e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/fc2c35880ccf4282a6baf8ab861bc10e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/fc2c35880ccf4282a6baf8ab861bc10e)</div>

## Step 1 \(Result\): The Initial App

With the generated code \(SAP Web IDE\) or the downloaded code from the Demo Kit, you have an initial app structure with the following content inside the `webapp` folder.

-   **Home Page** \(`webapp/view/Worklist.view.xml` file\)

    The home page of the app shows a table of products including the corresponding number of units in the stock. The title of the table shows how many items are available. A search field in the header toolbar of the table allows you to search for a product by name. Pressing a table row navigates the user to a new page that shows the details of the pressed product.

-   **Data**

    You can run the app with the real service or with the mock server serving mock data. In the `webapp/localService/mockserver.js` file, the mock server is configured. Using the mock server in this tutorial allows us to easily run the code even without network connection and without the need of having a remote server for our application data. To run the app with the mock server and its corresponding mock data the `/webapp/test/mockServer.html` file has to be called in the browser.

    The `webapp/localService/metadata.xml` file is used by the mock server to describe our OData service. In this step, the mock server will generate mock data based on this file. In a subsequent step the mock server will use our own custom mock data.

-   **Configuration of the App**

    In the `webapp/manifest.json` descriptor file, we configure our app. The descriptor file contains the following relevant sections:

    -   `sap.app`

        In this section we reference an `i18n.properties` file and use a special syntax to bind the texts for the title and description properties. In the `dataSources` section, we tell our app where to find our `mainService` OData service. As you might guess, the URI correlates to the `rootUri` of our mock server instance, which can be found in `webapp/localService/mockserver.js`. It is important that these two paths match to allow our mock server to provide the test data we defined above.

    -   `sap.ui5`

        In the `sap.ui5` section, we declare with the `rootView` parameter that our `mycompany.myapp.MyWorklistApp.view.App` view shall be loaded and used as the `rootView` for our app.

        Furthermore, we define two models to be automatically instantiated and bound to the component: an `i18n` model and a default model `""`. The latter references our `mainService` `dataSource`, which is declared in our `sap.app` section as an OData 2.0 data source. The `i18n` file can be found at `webapp/i18n/i18n.properties`. The `mainService` data source will be mocked by our mock server.

    > Note:
    > There is a `test.html` file in the `webapp` folder. This file serves as an easy entry point for developers to run and test the app in various ways during development. It contains links to the relevant files inside the `test` folder, which you can use to run with the Mock Server or to run unit tests and OPA tests.
    > 
    > 


**Related information**  


[App Templates: Kick Start Your App Development](App_Templates_Kick_Start_Your_App_Development_a460a73.md)

[Folder Structure: Where to Put Your Files](Folder_Structure_Where_to_Put_Your_Files_003f755.md)

