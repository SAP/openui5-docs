<!-- loio25ab54b0113c4914999c43d07d3b71fe -->

| loio |
| -----|
| 25ab54b0113c4914999c43d07d3b71fe |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/25ab54b0113c4914999c43d07d3b71fe) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/25ab54b0113c4914999c43d07d3b71fe)</div>

## Examples for Data Binding in Different View Types

Examples how complex syntax can be used for calculated fields in XML, HTML, and JS views.

***

<a name="loio25ab54b0113c4914999c43d07d3b71fe__section_yqd_24p_rcb"/>

### XML View \(Recommended\)

``` js

<mvc:View controllerName="testdata.complexsyntax" xmlns:core="sap.ui.core"
    xmlns:mvc="sap.ui.core.mvc" xmlns="sap.ui.commons" xmlns:table="sap.ui.table"
    xmlns:html="http://www.w3.org/1999/xhtml">
    <html:h2>
        <Label text="Hello Mr. {path:'/singleEntry/firstName', formatter:'.myFormatter'}, {/singleEntry/lastName}"></Label>
    </html:h2>
    <table:Table rows="{/table}">
        <table:columns>
            <table:Column>
                <Label text="Name"></Label>
                <table:template>
                    <TextField value="{path:'gender', formatter:'.myGenderFormatter'} {firstName}, {lastName}"></TextField>
                </table:template>
            </table:Column>
            <table:Column>
                <Label text="Birthday"></Label>
                <table:template>
                    <TextField value="{parts:[{path:'birthday/day'},{path:'birthday/month'},{path:'birthday/year'}], formatter:'my.globalFormatter'}"></TextField>
                </table:template>
            </table:Column>
        </table:columns>
    </table:Table>
    <html:h2>
        <Label text="A type test: {path:'/singleEntry/amount', type:'sap.ui.model.type.Float', formatOptions: { minFractionDigits: 1}} EUR"></Label>
    </html:h2>
</mvc:View>

```

***

<a name="loio25ab54b0113c4914999c43d07d3b71fe__section_fgl_f4p_rcb"/>

### HTML View

``` js

<template data-controller-name="testdata.complexsyntax">
    <div>
        <h2><div data-sap-ui-type="sap.ui.core.HTML" id="MyHTMLControl" data-content="<div>Hello Mr. {/singleEntry/firstName}, {/singleEntry/lastName}</div>"></div></h2>
        <div data-sap-ui-type="sap.ui.table.Table" id="MyTable" data-rows="{/table}">
            <div data-sap-ui-aggregation="columns">
                <div data-sap-ui-type="sap.ui.table.Column">
                    <div data-sap-ui-type="sap.ui.commons.Label" data-text="Name"></div>
                    <div data-sap-ui-aggregation="template">
                        <div data-sap-ui-type="sap.ui.commons.TextField" data-value="{firstName}, {lastName}"></div>
                    </div>
                </div>
                <div data-sap-ui-type="sap.ui.table.Column">
                    <div data-sap-ui-type="sap.ui.commons.Label" data-text="Birthday"></div>
                    <div data-sap-ui-aggregation="template">
                        <div data-sap-ui-type="sap.ui.commons.TextField" data-value="{parts:[{path:'birthday/day'},{path:'birthday/month'},{path:'birthday/year'}], formatter:'my.globalFormatter'}"></div>
                    </div>
                </div>
            </div>
        </div>
        <h2><div data-sap-ui-type="sap.ui.commons.Label" id="MyLabelType" data-text="A type test: {path:'/singleEntry/amount', type:'sap.ui.model.type.Float', formatOptions: { minFractionDigits: 1}} EUR"></div></h2>
    </div>
</template>

```

***

<a name="loio25ab54b0113c4914999c43d07d3b71fe__section_gqr_g4p_rcb"/>

### JS View

A JS view is not declarative view, but you may use the same syntax as in XML- and HTMLView, just do not forget to pass a controller instance as a parameter:

``` js

sap.ui.jsview("testdata.complexsyntax", {
    
    getControllerName: function() {
        return "testdata.complexsyntax";
    },

    /**
     * 
     * @param oController may be null
     * @returns {sap.ui.cre.Control}
     */
    createContent: function(oController) {
        var c = sap.ui.commons;
        var aControls = [];
        var oLabel = new c.Label({text:"Hello Mr. {path:'/singleEntry/firstName', formatter:'.myFormatter'}, {/singleEntry/lastName}"}, oController);
        aControls.push(oLabel);
        
        var oTable = new sap.ui.table.Table({rows:"{/table}"});
        var oColumn = new sap.ui.table.Column();
        var oLabel2 = new c.Label({text:"Name"});
        var oTextField = new c.TextField({value:"{path:'gender', formatter:'.myGenderFormatter'} {firstName}, {lastName}"}, oController);
        oColumn.setLabel(oLabel2);
        oColumn.setTemplate(oTextField);
        oTable.addColumn(oColumn);
        aControls.push(oTable);
        var oLabel2 = new c.Label({text:"{path:'/singleEntry/amount', type:'sap.ui.model.type.Float'}"});
        aControls.push(oLabel2);
        return aControls;
    }
});

```

