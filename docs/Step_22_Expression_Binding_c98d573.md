<!-- loioc98d57347ba444c6945f596584d2db45 -->

| loio |
| -----|
| c98d57347ba444c6945f596584d2db45 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c98d57347ba444c6945f596584d2db45) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c98d57347ba444c6945f596584d2db45)</div>

## Step 22: Expression Binding

Sometimes the predefined types of OpenUI5 are not flexible enough and you want to do a simple calculation or formatting in the view - that is where expressions are really helpful. We use them to format our price according to the current number in the data model.

***

### Preview

   
  
The price is now formatted according to its number<a name="loioc98d57347ba444c6945f596584d2db45__fig_r1j_pst_mr"/>

 ![](loio2ff81a7fea204f69913e33c2545bfb39_HiRes.png "The price is now formatted according to its number") 

***

### Coding

You can view and download all files at [Walkthrough - Step 22](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.22/preview).

``` xml
<mvc:View
controllerName="sap.ui.demo.walkthrough.controller.InvoiceList"
xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <List
      headerText="{i18n>invoiceListTitle}"
      class="sapUiResponsiveMargin"
      width="auto"
      items="{invoice>/Invoices}" >
      <items>
         <ObjectListItem
            title="{invoice>Quantity} x {invoice>ProductName}"
            number="{
		parts: [{path: 'invoice>ExtendedPrice'}, {path: 'view>/currency'}],
		type: 'sap.ui.model.type.Currency',
		formatOptions: {
			showMeasure: false
		}
		}"
		numberUnit="{view>/currency}"
        	*HIGHLIGHT START*numberState="{= ${invoice>ExtendedPrice} > 50 ? 'Error' : 'Success' }"*HIGHLIGHT END*/>
      </items>
   </List>
</mvc:View>
```

We add the property `numberState` in our declarative view and introduce a new binding syntax that starts with `=` inside the brackets. This symbol is used to initiate a new binding syntax, it's called an expression and can do simple calculation logic like the ternary operator shown here.

The condition of the operator is a value from our data model. A model binding inside an expression binding has to be escaped with the `$` sign as you can see in the code. We set the state to `'Error'`\(the number will appear in red\) if the price is higher than 50 and to `‘Success’` \(the number will appear in green\) otherwise.

Expressions are limited to a particular set of operations that help formatting the data such as Math expression, comparisons, and such. You can lookup the possible operations in the documentation.

***

### Conventions

-   Only use expression binding for trivial calculations.


**Related information**  


[Expression Binding](Expression_Binding_daf6852.md)

