<!-- loio69d3cbd4150c4ffb884e788f7f60fd93 -->

| loio |
| -----|
| 69d3cbd4150c4ffb884e788f7f60fd93 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/69d3cbd4150c4ffb884e788f7f60fd93) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/69d3cbd4150c4ffb884e788f7f60fd93)</div>

## Mock Server

A mock server is a mocking framework for HTTP and HTTPS that is used to simplify integration testing and to decouple development teams by allowing to develop against a service that is incomplete or unstable.

***

<a name="loio69d3cbd4150c4ffb884e788f7f60fd93__section_vvl_t14_wnb"/>

### OData V2 Mock Server

The mock server included with OpenUI5 mimics OData V2 back-end calls. It simulates the OData provider and is completely client-based, meaning that no network connectivity to a remote host is required. It intercepts HTTP calls made to the server and provides a fake output to the client. All this is transparent to data binding and the use of an OData model and feels like a real server. No changes are required on the OData model.

The OData V2 mock server provides mock services and also mock data. It supports randomly generated data based on the service metadata as well as mock data provided in JSON files.

> Note:
> The mock server only supports the JSON format for representing the resources it exposes, such as collections, entries, links, and so on.
> 
> 

For more information on the OData V2 mock server, see the topics given below.

***

<a name="loio69d3cbd4150c4ffb884e788f7f60fd93__section_qlf_v14_wnb"/>

### OData V4 Mock Server

The mock server functionality for OData V4 is included with CAP Node.js. For more information, see [https://cap.cloud.sap/docs/get-started/grow-as-you-go\#with-mocks](https://cap.cloud.sap/docs/get-started/grow-as-you-go#with-mocks).

**Related information**  


[sap.ui.core.util.MockServer](https://openui5.hana.ondemand.com/#/api/sap.ui.core.util.MockServer)

