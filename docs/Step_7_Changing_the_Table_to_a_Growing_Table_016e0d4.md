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

   
  
The List of posts is now dynamically loading more items when we scroll to the end of the page<a name="loio016e0d44f8ff47d2bdf4fdad9b7bf7cd__fig_r1j_pst_mr"/>

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


**Related information**  


[Growing Feature for Table and List](Growing_Feature_for_Table_and_List_9164ba7.md)

[API Reference: `sap.m.Table`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.Table.html)

