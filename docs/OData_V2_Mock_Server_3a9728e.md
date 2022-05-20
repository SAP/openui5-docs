<!-- loio3a9728ec31f94ca18a7d543ce419d85d -->

| loio |
| -----|
| 3a9728ec31f94ca18a7d543ce419d85d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/3a9728ec31f94ca18a7d543ce419d85d) | [demo kit latest release](https://sdk.openui5.org/topic/3a9728ec31f94ca18a7d543ce419d85d)</div>

## OData V2 Mock Server

In this tutorial, we will explore some advanced features of the OData V2 mock server.

If no OData V2 service is available or you simply don’t want to depend on the OData back-end connectivity for your development and tests, the mock server can mimic the OData V2 back-end calls. It is designed to simulate an OData V2 provider by intercepting the HTTP communication made to the server, and providing a fake output. All this is transparent to the data binding and usage of the OData V2 model.

In certain scenarios, using only the built-in OData V2 simulation of the mock server is insufficient for completely server-independent tests. For example, if your application is using an OData feature that is not supported by the mock server, or if your application invokes a function import that depends on a server specific implementation \(and thus is also not simulated generically\). We will demonstrate how to use function callbacks in order to change existing mock requests.

Additionally, we will demonstrate how to mock an additional request that is not simulated out of the box by the OpenUI5 OData V2 mock server.

> ### Caution:  
> The tutorial describes how to use some advanced features of the mock server, disregarding the legal aspects of shipping mock data. Usually the mock data and mock server invocation is done in a test folder that is not shipped to customers. Be very careful that you don't ship mock data!

***

### Preview

 ![](images/loio55edd9fa2cc24f398a9373d6d497d3e4_HiRes.png) 

> ### Tip:  
> You don't have to do all tutorial steps sequentially, you can also jump directly to any step you want. Just download the code from the previous step, and start there.
> 
> You can view and download the files for all steps in the Demo Kit at [Mock Server](https://sdk.openui5.org/entity/sap.ui.core.tutorial.mockserver). Copy the code to your workspace and make sure that the application runs by calling the `webapp/index.html` file. Depending on your development environment you might have to adjust resource paths and configuration entries.
> 
> For more information check the following sections of the tutorials overview page \(see [Get Started: Setup, Tutorials, and Demo Apps](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md)\):
> 
> -   [Downloading Code for a Tutorial Step](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download)
> 
> -   [Adapting Code to Your Development Environment](Get_Started_Setup_Tutorials_and_Demo_Apps_8b49fc1.md#loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation)

***

### Prerequisites

This tutorial assumes you have access to the SAP Business Application Studio. For more information, see [App Development Using SAP Business Application Studio](App_Development_Using_SAP_Business_Application_Studio_6bbad66.md).

You should also be familiar with the concepts explained in the [Walkthrough](Walkthrough_3da5f4b.md) tutorial and with the OData specification.

1.  [Step 1: Initial App Without Data](Step_1_Initial_App_Without_Data_7a78f1b.md "We start with a simple app scenario with a list of items bound to an OData V2
		service. Since the OData V2 service is not available yet on a real server, we will use the
		mock server to simulate both data and data calls. ")  
We start with a simple app scenario with a list of items bound to an OData V2 service. Since the OData V2 service is not available yet on a real server, we will use the mock server to simulate both data and data calls.
2.  [Step 2: Creating a Mock Server to Simulate Data](Step_2_Creating_a_Mock_Server_to_Simulate_Data_50897de.md "In this step, we use the OData V2 mock server to add data to our app without
		dependency to any remote server or system.")  
In this step, we use the OData V2 mock server to add data to our app without dependency to any remote server or system.
3.  [Step 3: Handling Custom URL Parameters](Step_3_Handling_Custom_URL_Parameters_46c1ca4.md "In this step, we add the functionality to interpret URL parameters in our local mock
		server configuration.")  
In this step, we add the functionality to interpret URL parameters in our local mock server configuration.
4.  [Step 4: Calling a Function Import](Step_4_Calling_a_Function_Import_95e5b87.md "We only want to display the upcoming meetings and hide the meetings happened in the
		past in our app. By using a function import that calculates these items on the back end we
		do not need to do the calculation on the client. The OData V2 mock server will be instructed
		to do the calculation locally for testing purposes.")  
We only want to display the upcoming meetings and hide the meetings happened in the past in our app. By using a function import that calculates these items on the back end we do not need to do the calculation on the client. The OData V2 mock server will be instructed to do the calculation locally for testing purposes.

**Related Information**  


[Mock Server](Mock_Server_69d3cbd.md "A mock server mimics one or more back-end services. It is used to simplify integration testing and to decouple UI development from service development. By using a mock server you can develop and test the UI even if the service in the back end is incomplete or unstable.")

