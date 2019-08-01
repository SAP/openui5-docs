<!-- loioa428d4128f22435693a65223fe6d8ff2 -->

| loio |
| -----|
| a428d4128f22435693a65223fe6d8ff2 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a428d4128f22435693a65223fe6d8ff2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a428d4128f22435693a65223fe6d8ff2)</div>

## Using Mock Data

Mock Data can be used when you start the development of an app as well as for testing and problem solving when the data service is not available or it requires effort to set up data services.

To switch to mock mode, set the URL parameter `responderOn` to `true`. We recommend to provide one check for this parameter in the app in a central place, for example in the `model.Config` object in the `model` folder.

```
jQuery.sap.declare("model.Config");

model.Config = {};

(function () {
    
    // The "reponder" URL parameter defines if the app shall run with mock data
    var responderOn = jQuery.sap.getUriParameters().get("responderOn");
    
    // set the flag for later usage
    model.Config.isMock = ("true" === responderOn);
}
)();

```

To run your app with mock data, you can use the mock server. The mock server intercepts HTTP calls to the server and produces a faked output to the client. This is transparent to your data binding and the use of OData model and feels like a real server. You start the mock server when you intialize your app as follows:

```
sap.ui.app.Application.extend("Application", {
    
    init : function () {
        
        ...
        
        // start mock server
        if (model.Config.isMock) {
            jQuery.sap.require("sap.ui.core.util.MockServer");
            var oMockServer = new sap.ui.core.util.MockServer({
                rootUri: model.Config.getServiceUrl();
            });
            oMockServer.simulate("model/metadata.xml", "model/");
            oMockServer.start();
        }

```

The mock server needs a metadata XML file that describes the data structure of your service. You can obtain this by opening the OData service root URL in a browser with the suffix "$metadata" appended. Copy the resulting XML file into the model folder of your application.

Remove any kind of link that points to internal servers.

The following two options for providing mock data exist:

-   Provide your own mock data

    You can provide JSON files as test data for the mock server to produce the output. Put all files into the model folder. To avoid a "not found" error messages of the mock server, provide JSON files for each entity of the service. Otherwise, the mock server will log those error messages to the console and create empty data sets for the entities lacking a respective JSON data file. This is all right, in case you do not want to load mock data for those entities. The mock server can also generate mock data for those entities by passing a parameter to the simulate function.

-   Mock server generates the mock data

    The mock server can produce random mock data based on the service metadata it simulates. This can be done easily by providing the path to the metadata fil and omitting the second parameter of the simulate function. However, this option does not provide data that matches your business scenario.


