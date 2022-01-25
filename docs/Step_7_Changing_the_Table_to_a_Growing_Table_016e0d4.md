<!-- loio016e0d44f8ff47d2bdf4fdad9b7bf7cd -->

| loio |
| -----|
| 016e0d44f8ff47d2bdf4fdad9b7bf7cd |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/016e0d44f8ff47d2bdf4fdad9b7bf7cd) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/016e0d44f8ff47d2bdf4fdad9b7bf7cd)</div>

## Step 7: Changing the Table to a Growing Table

Let’s switch back to developing and add the missing feature for the test we implemented in the previous step. We will simply change the table to a growing table as this is a basic feature of the table. This will display a trigger at the end of the table that the user can click on to display more items.

***

### Preview

   
  
<a name="loio016e0d44f8ff47d2bdf4fdad9b7bf7cd__fig_r1j_pst_mr"/>The List of posts is now dynamically loading more items when we scroll to the end of the page

 ![](loio43d882b890714236901f5b067e34e81e_LowRes.png "The List of posts is now dynamically loading more items when we scroll to the
					end of the page") 

***

### Coding

You can view and download all files in the *Samples* in the Demo Kit at [Testing - Step 7](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.testing.07/preview).

***

### webapp/view/Worklist.view.xml

``` xml
<mvc:View …
	<semantic:FullscreenPage
		id="page"
		title="{i18n>worklistViewTitle}">
		<semantic:content>
			<Table
				id="table"
				*HIGHLIGHT START*growing="true"
*HIGHLIGHT END*
				width="auto"
				…
				>
			…
			</Table>
		</semantic:content>
		…
	</semantic:FullscreenPage>
</mvc:View>
```

We simply set the parameter `growing` to `true` to enable our feature. Now we can run the integration test that we just wrote in the previous step and it should not fail anymore. Similarly, if we run the app, we now see only 20 items initially. And if we choose the *More* button then three more items are loaded.

***

### Conventions

-   Use OPA tests for UI-related integration tests


**Parent topic:** [Testing](Testing_291c912.md "In this tutorial we will test application functionality with the testing tools that are delivered with OpenUI5. At different steps of this tutorial you will write tests using QUnit, OPA5, and the OData V2 mock server. Additionally, you will learn about testing strategies, Test Driven Development (TDD), and much more.")

**Next:** [Step 6: A First OPA Test](Step_6_A_First_OPA_Test_1b47457.md "A bulletin board may contain many posts. We expect to have a high data load once it is officially released. Then, there might be performance issues and long loading times if we display all entries at the same time. Therefore we will introduce a feature that limits the initial display to 20 items. The user can then click on a more button to view more items. As with the unit test, we start by writing an integration test for this feature and then add the application functionality later.")

**Previous:** [Step 8: Testing Navigation](Step_8_Testing_Navigation_10592af.md "So far, we have a list of posts on the home page of the app. But typically, a post comes with more details that should be displayed on a separate detail page. We call it the post page because it displays details of a post. In this step we will introduce a new journey to test the post page. We write tests that trigger typical navigation events with OPA. Testing navigation greatly helps in reducing manual testing efforts as it covers a lot of testing paths. It is good practice to cover every view of your application with at least one test, since OPA will check if an exception is thrown. In this way you can detect critical errors very fast.")

**Related Information**  


[Growing Feature for Table and List](Growing_Feature_for_Table_and_List_9164ba7.md "sap.m.ListBase provides growing-related properties, which can be used for tables and lists.")

[API Reference: `sap.m.Table`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.Table.html)

