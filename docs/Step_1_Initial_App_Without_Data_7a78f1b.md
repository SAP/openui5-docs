<!-- loio7a78f1b707c248fd9ec53dcb5f10814c -->

| loio |
| -----|
| 7a78f1b707c248fd9ec53dcb5f10814c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7a78f1b707c248fd9ec53dcb5f10814c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7a78f1b707c248fd9ec53dcb5f10814c)</div>

## Step 1: Initial App Without Data

We start with a simple app scenario with a list of items bound to an OData V2 service. Since the OData V2 service is not available yet on a real server, we will use the mock server to simulate both data and data calls.

For this very simple tutorial app we will use an OData V2 service called `NerdMeetups` that lists meet-up groups according to location, date, topic, etc. The app will display a simple list populated by a function import call to display only upcoming meet-ups \(meet-ups with an event date greater to the current date\).

Additionally, a button will fetch the first three meet-ups \(using a custom URL parameter called `first`\). This exercise simply shows an app with no data retrieved from the back end. This can happen when the back end is down, or when the service is not implemented yet.

Usually you start the development of an app with local mock data first. This way you can continue implementing the application logic without depending on the back end readiness and connectivity.

***

### Preview

   
  
<a name="loio7a78f1b707c248fd9ec53dcb5f10814c__fig_wg3_bdq_st"/>The initial app

 ![](loio3a29b22e092e4bf8a549fa2931758673_HiRes.png "The initial app") 

***

### Coding

To set up your project for this tutorial, download the files for *Step 1* in the Demo Kit at [Mock Server - Step 1](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.mockserver.01/preview). Copy the code to your workspace and make sure that the application runs by calling the `webapp/test/mockServer.html` file.

Depending on your development environment you might have to adjust resource paths and configuration entries. The project structure and the files coming with this tutorial are explained in detail in the [Walkthrough](Walkthrough_3da5f4b.md) tutorial.

You should have the same files as displayed in the following figure:

   
  
<a name="loio7a78f1b707c248fd9ec53dcb5f10814c__fig_gsc_mld_tt"/>Folder structure with downloaded files

 ![](loio026a90809d1a4dc5a28e147bc77eb830_HiRes.png "Folder structure with downloaded files") 

**Parent topic:** [OData V2 Mock Server](OData_V2_Mock_Server_3a9728e.md "In this tutorial, we will explore some advanced features of the OData V2 mock server.")

**Previous:** [Step 2: Creating a Mock Server to Simulate Data](Step_2_Creating_a_Mock_Server_to_Simulate_Data_50897de.md "In this step, we use the OData V2 mock server to add data to our app without dependency to any remote server or system.")

