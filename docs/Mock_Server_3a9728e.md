<!-- loio3a9728ec31f94ca18a7d543ce419d85d -->

| loio |
| -----|
| 3a9728ec31f94ca18a7d543ce419d85d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3a9728ec31f94ca18a7d543ce419d85d) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3a9728ec31f94ca18a7d543ce419d85d)</div>

## Mock Server

In this tutorial, we will explore some advanced features of the mock server.

If no OData service is available or you simply don’t want to depend on the OData backend connectivity for your development and tests, the mock server can mimic the OData back-end calls. It is designed to simulate an OData provider by intercepting the HTTP communication made to the server, and providing a fake output. All this is transparent to the data binding and usage of OData model.

In certain scenarios, using only the built-in OData simulation of the mock server is insufficient for completely server-independent tests. For example, if your application is using an OData feature that is not supported by the mock server, or if your application invokes a function import that depends on server specific implementation \(and thus is also not simulated generically\). We will demonstrate how to use function callbacks in order to change existing mock requests.

Additionally, we will demonstrate how to mock an additional request that is not simulated out of the box by the OpenUI5 mock server.

> Note:
> The tutorial describes how to use some advanced features of the mock server, disregarding the legal aspects of shipping mock data. Usually the mock data and mock server invocation is done in a test folder that is not shipped to customers. Be very careful that you don't ship mock data!
> 
> 

***

### Preview

 ![](loio55edd9fa2cc24f398a9373d6d497d3e4_HiRes.png) 

> Note:
> You don't have to do all tutorial steps sequentially, you can also jump directly to any step you want. Just download the code from the previous step, and start there.
> 
> You can view and download the files for all steps in the Demo Kit at [Mock Server](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.core.tutorial.mockserver/samples). Copy the code to your workspace and make sure that the application runs by calling the `webapp/index.html` file. Depending on your development environment you might have to adjust resource paths and configuration entries.
> 
> For more information check the following sections of the tutorials overview page \(see [Get Started: Setup and Tutorials](Get_Started_Setup_and_Tutorials_8b49fc1.md)\):
> 
> -   [Downloading Code for a Tutorial Step](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download)
> 
> -   [Adapting Code to Your Development Environment](Get_Started_Setup_and_Tutorials_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation)
> 
> 
> 

***

### Prerequisites

This tutorial assumes you have access to the SAP Web IDE either by having a trial account or a customer account. For more information, see [App Development Using SAP Web IDE](App_Development_Using_SAP_Web_IDE_13ced94.md).

You should also be familiar with the concepts explained in the [Walkthrough](Walkthrough_3da5f4b.md) tutorial and with the OData specification.

**Related information**  


[Mock Server](Mock_Server_69d3cbd.md)

