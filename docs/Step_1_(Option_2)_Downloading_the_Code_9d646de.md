<!-- loio9d646de79e3a46ee8143a4b21b332e5e -->

| loio |
| -----|
| 9d646de79e3a46ee8143a4b21b332e5e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9d646de79e3a46ee8143a4b21b332e5e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9d646de79e3a46ee8143a4b21b332e5e)</div>

## Step 1 \(Option 2\): Downloading the Code

In this step, we set up the initial app without SAP Web IDE.

If you are working with another IDE or development environment than the SAP Web IDE, you can simply download the code from the *Samples* in the Demo Kit at [Worklist App - Step 1](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.worklist.01/preview) and skip the wizard steps described in the previous step of this tutorial. The code contains a preconfigured application project that can be used as a starting point to develop the worklist app. You can deploy the downloaded application to a \(local\) Web server and call the `webapp/test/mockServer.html` file in your browser manually to start the app.

To access the real service, you would need to set up a proxy service that connects your app project deployed on a Web server to the remote service. Due to the so called same-origin policy browsers deny AJAX requests to service endpoints in case the domain/subdomain, protocol, or port differ from the app’s domain/subdomain, protocol, or port. Cross-origin resource sharing \(CORS\) makes it possible to break out of these restrictions derived from the same-origin policy. With CORS the server and browser agree which cross-origin requests are allowed. Another way to bypass the same-origin policy is using a proxy on the same host of the app. To keep it simple, our app contains a test page to run the app with local mock data instead of retrieving the data from a real server hosted somewhere else. This way we won’t have any issues related to the same-origin policy of the browsers, as long as we run the app with our mock server.

> Note:
> The texts in the `i18n.properties` file are automatically generated based on the template Customizing \(OData entity set, entities, properties, and texts\). The result can be incorrect texts like "Enter an <Products\> name or a part of it." You should therefore revise the generated texts in the `i18n.properties` file.
> 
> 

**Related information**  


[Development Environment](Development_Environment_7bb04e0.md)

