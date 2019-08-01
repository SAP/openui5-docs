<!-- loio69d3cbd4150c4ffb884e788f7f60fd93 -->

| loio |
| -----|
| 69d3cbd4150c4ffb884e788f7f60fd93 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/69d3cbd4150c4ffb884e788f7f60fd93) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/69d3cbd4150c4ffb884e788f7f60fd93)</div>

## Mock Server

Mock server is a mocking framework for HTTP and HTTPS that is used to simplify integration testing and to decouple development teams by allowing to develop against a service that is not complete or unstable.

In OpenUI5, the mock server mimics OData backend calls. It simulates the OData provider and is completely client-based, meaning that no network connectivity to a remote host is required. It intercepts HTTP calls made to the server and provides a fake output to the client. All this is transparent to data binding and use of OData model and feels like a real server. No changes are required on the OData model.

The mock server provides mock services and also mock data. It supports randomly generated data based on the service metadata, as well as mock data provided in JSON files.

> Note:
> Mock Server only supports the JSON format for representing the resources it exposes, such as collections, entries, links, and so on.
> 
> 

**Related information**  


[sap.ui.core.util.MockServer](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.util.MockServer.html)

