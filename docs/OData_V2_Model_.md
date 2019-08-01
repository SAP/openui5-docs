<!-- loio6c47b2b39db9404582994070ec3d57a2 -->

| loio |
| -----|
| 6c47b2b39db9404582994070ec3d57a2 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/6c47b2b39db9404582994070ec3d57a2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/6c47b2b39db9404582994070ec3d57a2)</div>

## OData V2 Model

The OData V2 Model enables binding of controls to data from OData services.

The OData model is a server-side model, meaning that the data set is only available on the server and the client only knows the currently visible \(requested\) data. Operations, such as sorting and filtering, are done on the server. The client sends a request to the server and shows the returned data.

> Note:
> Requests to the back end are triggered by list bindings \(`ODataListBinding`\), context bindings \(`ODataContextBinding`\), and CRUD functions provided by the `ODataModel`. Property bindings \(`ODataPropertyBindings`\) do not trigger requests.
> 
> 

The OData model currently supports OData version 2.0.

The following two versions of the OData model are implemented: `sap.ui.model.odata.ODataModel` and `sap.ui.model.odata.v2.ODataModel`. The `v2.ODataModel` has an improved feature set and new features will only be implemented in this model. `sap.ui.model.odata.ODataModel` is deprecated. We recommend to only use `v2.ODataModel`.

The following table shows the supported features for both OData models:

|Feature| `sap.ui.model.odata.v2.ODataModel` | `sap.ui.model.odata.ODataModel` |
|-------|------------------------------------|---------------------------------|
|OData version support|2.0|2.0|
|JSON format|Yes \(default\)|Yes|
|XML format|Yes|Yes \(default\)|
|Support of two-way binding mode|Yes; for property changes only, not yet implemented for aggregations|Experimental; only properties of one entity can be changed at the same time|
|Default binding mode|One-way binding|One-way binding|
|Client-side sorting and filtering|Yes For more information, see [API Reference: sap.ui.model.odata.OperationMode](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.OperationMode.html). |No|
|$batch|Yes; all requests can be batched|Only manual batch requests are possible|
|Data cache in model|All data is cached in the model|Manually requested data is **not** cached|
|Automatic refresh|Yes \(default\)|Yes|
|Message handling|Yes, see [Error, Warning, and Info Messages](Error,_Warning,_and_Info_Messages_62b1481.md) |No|

> Note:
> Be aware of the Same-Origin-Policy security concept which prevents access to back ends on different domains or sites.
> 
> 

The requests to the service to fetch data are made automatically based on the data bindings that are defined for the controls.

**Related information**  


[API Reference: `sap.ui.model.odata.v2.ODataModel`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v2.ODataModel.html)

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio218afa0780da42fd982b72e992fb57d2__loio218afa0780da42fd982b72e992fb57d2"/>

<!-- loio218afa0780da42fd982b72e992fb57d2 -->

## Creating the Model Instance

One OData model instance can only cover one OData service. For accessing multiple services, you have to create multiple OData model instances.

The only mandatory parameter when creating an `ODataModel` instance is the service URL. It can be passed as first parameter or within the `mParameters` map to the constructor.

***

``` js
var oModel = new sap.ui.model.odata.v2.ODataModel("http://services.odata.org/Northwind/Northwind.svc/");
var oModel = new sap.ui.model.odata.v2.ODataModel({serviceUrl: "http://services.odata.org/Northwind/Northwind.svc"});
```

When creating an `ODataModel` instance, a request is sent to retrieve the service metadata:

```
http://services.odata.org/Northwind/Northwind.svc/$metadata
```

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio71a3ae02691147abaf6d78a553d50161__loio71a3ae02691147abaf6d78a553d50161"/>

<!-- loio71a3ae02691147abaf6d78a553d50161 -->

## Service Metadata

The service metadata is cached per service URL. Multiple OData models that are using the same service can share this metadata.

Only the first model instance triggers a `$metadata` request. A JSON representation of the service metadata can be accessed by calling the `getServiceMetadata()` method on an Odata model instance.

``` js

var oMetadata = oModel.getServiceMetadata();
```

> Note:
> In the `v2.ODataModel`, the service metadata is loaded asynchronously. It is not possible to load it synchronously. To get notified when the loading is finished, attach the `metadataLoaded` event.
> 
> 

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio82afe9152177428290cc9d5dbd90e245__loio82afe9152177428290cc9d5dbd90e245"/>

<!-- loio82afe9152177428290cc9d5dbd90e245 -->

## Adding Additional URL Parameters

For OData services, you can use URL parameters for configuration. OpenUI5 sets most URL parameters automatically, according to the respective binding.

For authentication tokens or general configuration options, for example, you can add additional arguments to the request URL. Some of the parameters must not be included in every request, but should only be added to specific list or context bindings, such as `$expand` or `$select`. For this, the binding methods provide the option to pass a map of parameters, which are then included in all requests for this specific binding. The OData model currently only supports `$expand` and `$select`.

There are different ways to add URL parameters to the requests:

-   Appending parameters to the service URL:

    ``` js
    var oModel = new sap.ui.model.odata.v2.ODataModel("http://myserver/MyService.svc/?myParam=value&myParam2=value");
    ```

    These parameters will be included in every request sent to the OData server.

-   Passing URL parameters with the `mparameters` map

    You can pass URL parameters that are used for `$metadata` requests only \(`metadataUrlParams`\) as well as URL parameters that are included only in data requests \(`serviceUrlParams`\). The parameters are passed as maps:

    ``` js
    var oModel = new sap.ui.model.odata.v2.ODataModel({ 
        serviceUrl: "http://services.odata.org/Northwind/Northwind.svc",    
        serviceUrlParams: {
            myParam: "value1",
            myParam2: "value2"
        },
        metadataUrlParams: {
            myParam: "value1",
            myParam2: "value2"
        }
    });
    ```


 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio7370a173015e49929e011d6ab6b4885c__loio7370a173015e49929e011d6ab6b4885c"/>

<!-- loio7370a173015e49929e011d6ab6b4885c -->

## Custom HTTP Headers

You can add custom headers which are sent with each request.

To do this, provide a map of headers to the OData model constructor or use the `setHeaders()` function:

-   Passing custom headers with the `mparameters` map

    ``` js
    var oModel = new sap.ui.model.odata.v2.ODataModel({
        headers: {
            "myHeader1" : "value1",
            "myHeader2" : "value2"
        }
    });
    ```

-   Setting custom headers globally on a model instance

    ``` js
    oModel.setHeaders({"myHeader1" : "value1", "myHeader2" : "value2"});
    ```

    > Note:
    > When you add custom headers, all previous custom headers are removed if not specified again in the headers map. Some headers are private, that is, they are set by the OData model internally and cannot be set:
    > 
    > ```
    > "accept"
    > "accept-language"
    > "maxdataserviceversion"
    > "dataserviceversion"
    > "x-csrf-token"
    > ```
    > 
    > For additional methods and parameters, see the [API Reference: sap.ui.model.odata.v2.ODataModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v2.ODataModel.html). 
    > 
    > 


 <a name="loio6c47b2b39db9404582994070ec3d57a2 loioc4be40ce21ff4d0485b1d8f8114f7426__loioc4be40ce21ff4d0485b1d8f8114f7426"/>

<!-- loioc4be40ce21ff4d0485b1d8f8114f7426 -->

## Addressing Entities: Binding Path Syntax

The binding path syntax for OData models matches the URL path relative to the service URL used in OData to access specific entities or entity sets.

You access the data provided by the OData model according to the structure of the OData service as defined in the metadata of a service. URL parameters, such as filters, cannot be added to a binding path. A binding path can be absolute or relative. Absolute binding paths are resolved immediately. A relative path can only be resolved if it can be automatically converted into an absolute binding path. If, for example, a property is bound to a relative path and the parent control is then bound to an absolute path, the relative property path can e resolved to an absolute path.

***

The following binding samples within the `ODataModel` are taken from the Northwind demo service.

Absolute binding path \(starting with a slash \('/'\)\):

```
"/Customers"
"/Customers('ALFKI')/Address"
```

Relative binding paths that can be resolved with a context \(for example `"/Customer('ALFKI')"`\):

```
"CompanyName"
"Address"
"Orders"
```

Resolved to:

```
"/Customer('ALFKI')/CompanyName"
"/Customer('ALFKI')/Address"
"/Customer('ALFKI')/Orders"
```

Navigation properties, used to identify a single entity or a collection of entities:

```
"/Customers('ALFKI')/Orders"
"/Products(1)/Supplier"
```

For more information on addressing OData entries, see the URI conventions documentation on [http://www.odata.org](http://www.odata.org).

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loioadd47c3966dd40489e952bb4f5f74a7c__loioadd47c3966dd40489e952bb4f5f74a7c"/>

<!-- loioadd47c3966dd40489e952bb4f5f74a7c -->

## Accessing Data from an OData Model

The data requested from an OData service is cached in the OData model.

It can be accessed by the `getData()` and the `getProperty()` method, which returns the entity object or value. These methods do not request data from the backend, so you can only access already requested and cached entities:

``` js
oModel.getData("/Customer('ALFKI')");
oModel.getProperty("/Customer('ALFKI')/Address");
```

You can only access single entities and properties with these methods. To access entity sets, you can get the binding contexts of all read entities via a list binding. The values returned by these methods are copies of the data in the model, not references as in the JSONModel.

> Note:
> Do **not** modify objects or values inside the model manually; always use the provided API to change data in the model, or use two-way binding \(see *Two-way Binding* section below\).
> 
> 

> Note:
> The ODataModel uses the `$skip` and `$top` URL parameters for paging. It is possible that data is modified between two paging requests, for eample, entities can be added orremoved and this may lead to data inconsistencies.
> 
> 

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio4c4cd99af9b14e08bb72470cc7cabff4__loio4c4cd99af9b14e08bb72470cc7cabff4"/>

<!-- loio4c4cd99af9b14e08bb72470cc7cabff4 -->

## Creating Entities

To create entities for a specified entity set, call the `createEntry()` method. The method returns a context object that points to the newly created entity.

The application can bind against these objects and change the data by means of two-way binding. To store the entities in the OData backend, the application calls `submitChanges()`. To reset the changes, the application can call the `deleteCreatedEntry()` method.

The application can choose the properties that shall be included in the created object and can pass its own default values for these properties. Per default, all property values are empty, that is, undefined.

> Note:
> The entity set and the passed properties must exist in the metadata definition of the OData service.
> 
> ``` js
> // create an entry of the Products collection with the specified properties and values
> var oContext = oModel.createEntry("/Products", { properties: { ID:99, Name:"Product", Description:"new Product", ReleaseDate:new Date(), Price:"10.1", Rating:1} });
> // binding against this entity
> oForm.setBindingContext(oContext);
> // submit the changes (creates entity at the backend)
> oModel.submitChanges({success: mySuccessHandler, error: myErrorHandler});
> // delete the created entity
> oModel.deleteCreatedEntry(oContext);
> 
> ```
> 
> If created entities are submitted, the context is updated with the path returned from the creation request and the new data is imported into the model. So the context is still valid and points to the new created entity.
> 
> 

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loioff667e12b8714f3595e68f3e7c0e7a14__loioff667e12b8714f3595e68f3e7c0e7a14"/>

<!-- loioff667e12b8714f3595e68f3e7c0e7a14 -->

## CRUD Operations

The OData model allows manual CRUD \(create, read, update, delete\) operations on the OData service. If a manual operation returns data, the data is imported into the data cache of the OData model. All operations require a mandatory `sPath` parameter as well as an optional `mParameters` map.

***

The `create` and `update` methods also require a mandatory `oData` parameter for passing the created or changed data object. Each operation returns an object containing a function abort, which can be used to abort the request. If the request is aborted, the error handler is called. This ensures that the success or the error handler is executed for every request. It is also possible to pass additional header data, URL parameters, or an eTag.

-   Creating entities

    The `create` function triggers a `POST` request to an OData service which was specified at creation of the OData model. The application has to specify the entity set, in which the new entity and the entity data is to be created.

    ``` js
    var oData = {
        ProductId: 999,
        ProductName: "myProduct"
    }
    oModel.create("/Products", oData, {success: mySuccessHandler, error: myErrorHandler});
    ```

-   Reading entities

    The `read` function triggeres a `GET` request to a specified path. The path is retrieved from the OData service which was specified at creation of the OData model. The retrieved data is returned in the `success` callback handler function.

    ``` js
    oModel.read("/Products(999)", {success: mySuccessHandler, error: myErrorHandler});
    ```

-   Updating entities

    The `update` function triggers a `PUT`/`MERGE` request to an OData service which was specified at creation of the OData model. After a successful request to update the bindings in the model, the refresh is triggered automatically.

    ``` js
    
    var oData = {
        ProductId: 999,
        ProductName: "myProductUpdated"
    }
    oModel.update("/Products(999)", oData, {success: mySuccessHandler, error: myErrorHandler});
    ```

-   Deleting entities

    The `remove` function triggers a `DELETE` request to an OData service which was specified at creation of the OData model. The application has to specify the path to the entry which should be deleted.

    ``` js
    oModel.remove("/Products(999)", {success: mySuccessHandler, error: myErrorHandler});
    ```

-   Refresh after change

    The model provides a mechanism to automatically refresh bindings that depend on changed entities. If you carry out a `create`, `update` or `remove` function, the model identifies the bindings and triggers a refresh for these bindings. If the model runs in batch mode, the refresh requests are bundled together with the changes in the same batch request. You can disable the auto refresh by calling `setRefreshAfterChange(false)`. If the auto refresh is disabled, the application has to take care of refreshing the respective bindings.

    ``` js
    oModel.setRefreshAfterChange(false);
    ```


 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio94e302455f8044e79de759c86bb295a2__loio94e302455f8044e79de759c86bb295a2"/>

<!-- loio94e302455f8044e79de759c86bb295a2 -->

## Concurrency Control and ETags

OData uses HTTP ETags for optimistic concurrency control. The service must be configured to provide them. The ETag can be passed within the parameters map for every CRUD request. If no ETag is passed, the ETag of the cached entity is used, if it is loaded already.

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio30362c1cafd244dd86752e28993bbcdd__loio30362c1cafd244dd86752e28993bbcdd"/>

<!-- loio30362c1cafd244dd86752e28993bbcdd -->

## XSRF Token

To address cross-site request forgery, an OData service may require XSRF tokens for change requests by the client application. In this case, the client has to fetch a token from the server and send it with each change request to the server. The OData model fetches the XSRF token when reading the metadata and then automatically sends it with each write request header. If the token is no longer valid, a new token can be fetched by calling the `refreshSecurityToken` function on the OData model. The token is fetched with a request to the service root URL, which usually responds with the service document. To get a valid token, make sure that the response is **not** cached.

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio66a130fa4d10411b8fc90df00185554b__loio66a130fa4d10411b8fc90df00185554b"/>

<!-- loio66a130fa4d10411b8fc90df00185554b -->

## Refreshing the Model

The `refresh` function refreshes all data within an OData model. Each binding reloads its data from the server. For list or context bindings, a new request to the back end is triggered. If the XSRF token is no longer valid, it has to be fetched again with a `read` request to the service document. Data that has been imported via manual CRUD requests is **not** reloaded automatically.

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio8a6ae1d390534d05a560bf350af59c29__loio8a6ae1d390534d05a560bf350af59c29"/>

<!-- loio8a6ae1d390534d05a560bf350af59c29 -->

## Batch Processing

The `v2.ODataModel` supports batch processing \(`$batch`\) in two different ways:

-   Default: All requests in a thread are collected and bundled in batch requests, meaning that request is sent in a timeout immediately after the current call stack is finished. This includes all manual CRUD requests as well as requests triggered by a binding.

-   Deferred: The requests are stored and can be submitted with a manual `submitChanges()` call by the application. This also includes all manual CRUD requests as well as requests triggered by a binding.


The model cannot decide how to bundle the requests. For this, OpenUI5 provides the `groupId`. For each binding and each manual request, a `groupId` can be specified. All requests belonging to the same group are bundled into one batch request. Request without a `groupId` are bundled in the default batch group. You can use a `changeSetId` for changes. The same principle applies: Each change belonging to the same `changeSetId` is bundled into one `changeSet` in the batch request. Per default, all changes have their own `changeSet`. For more information, see the API reference.

You can use the `setDeferredGroups()` method to set a previously defined subset of groups to deferred.

> Note:
> The same is also valid for `setChangeGroups()` and `getChangeGroups()`.
> 
> 

All requests belonging to the `group` are then stored in a request queue. The deferred batch group must then be submitted manually by means of the `submitChanges()` method. If you do **not** specify a batch group ID when calling `submitChanges`, all deferred batch groups are submitted.

> Note:
> Set a subset of groups to deferred
> 
> ``` js
> var oModel = new sap.ui.model.odata.v2.ODataModel(myServiceUrl);
> ```
> 
> Pass the `groupId` to a binding:
> 
> ``` js
> {path:"/myEntities", parameters: {groupId: "myId"}}
> ```
> 
> Set the `groupId` to deferred:
> 
> 1.  Get the list of deferred groups:
> 
>     ``` js
>     var aDeferredGroups = oModel.getDeferredGroups();
>     ```
> 
> 2.  Append your `groupId` to the list:
> 
>     ``` js
>     aDeferredGroups=aDeferredGroups.concat(["myId"]);
>     ```
> 
> 3.  Set all groups to deferred:
> 
>     ``` js
>     oModel.setDeferredGroups(aDeferredGroups);
>     ```
> 
> 
> Submit all deferred groups:
> 
> ``` js
> oModel.submitChanges({aDeferredGroups, success: mySuccessHandler, error: myErrorHandler});
> ```
> 
> 

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio42b3ca19a47d49a3b4ba5f34ca0d1f7e__loio42b3ca19a47d49a3b4ba5f34ca0d1f7e"/>

<!-- loio42b3ca19a47d49a3b4ba5f34ca0d1f7e -->

## Two-Way Binding

The `v2.ODataModel` enables two-way binding. Per default, all changes are collected in a batch group called "changes" which is set to deferred.

To submit the changes, use `submitChanges()`. The data changes are made on a data copy. This enables you to reset the changes without sending a new request to the backend to fetch the old data again. With `resetChanges()` you can reset all changes. You can also reset only specific entities by calling `resetChanges` with an array of entity paths.

> Note:
> Filtering and sorting is not possible if two-way changes are present as this would cause inconsistent data on the UI. Therefore, before you carry out sorting or filtering, you have to submit or reset the changes.
> 
> 

You can collect the changes for different entities or types in different batch groups. To configure this, use the `setChangeGroups()` method of the model:

``` js
var oModel = new sap.ui.model.odata.v2.ODataModel(myServiceUrl);
oModel.setDeferredGroups(["myGroupId", "myGroupId2"]);
oModel.setChangeGroups({
    "EntityTypeName": {
        groupId: "myGroupId",  
        [changeSetId: "ID",]
        [single: true/false,]
    }
)};
oModel.submitChanges({groupId: "myGroupId", success: mySuccessHandler, error: myErrorHandler});
```

To collect the changes for all entity types in the same batch group, use '\*’ as `EntityType`. If the change is not set to deferred, the changes are sent to the backend immediately. By setting the `single` parameter for `changeSet` to true or false, you define if each change results in its own change set \(`true`\) or if all changes are collected in one change set \(`false`\). The model only takes care of the `changeSetId` if `single` is set to `false`.

> Note:
> The first change of an entity defines the order in the change set.
> 
> 

**Example**

Reset changes:

``` js
var oModel = new sap.ui.model.odata.v2.ODataModel(myServiceUrl);
//do a change
oModel.setProperty("/myEntity(0)", oValue);

//reset the change
oModel.resetChanges(["/myEntity(0)"]);
```

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loiobf1fc3b4c9ab4bbc845a3f0e0940c004__loiobf1fc3b4c9ab4bbc845a3f0e0940c004"/>

<!-- loiobf1fc3b4c9ab4bbc845a3f0e0940c004 -->

## Binding-specific Parameters

The OData protocol specifies different URL parameters.

***

You can use these parameters in bindings in addition to the parameters described above:

-   Expand parameter

    The `expand` parameter allows the application to read associated entities with their navigation properties:

    ``` js
    oControl.bindElement("/Category(1)", {expand: "Products"}); 
    
    oTable.bindRows({
        path: "/Products",
        parameters: {expand: "Category"}
    });
    ```

    In this example, all products of `"Category(1)"` are embedded inline in the server response and loaded in one request. The category for all `"Products"` is embedded inline in the response for each product.

-   Select parameter

    The `select` parameter allows the application to define a subset of properties that is read when requesting an entity.

    ``` js
    oControl.bindElement("/Category(1)", {expand: "Products", select: "Name,ID,Products"}); 
    
    oTable.bindRows({
        path: "/Products",
        parameters: {select: "Name,Category"}
    });
    ```

    In this example, the properties `Name`, `ID` and `ofCategory(1)` as well as all properties of the embedded products are returned. The properties `Name` and `Category` are included for each product. The `Category` property contains a link to the related category entry.

-   Custom query options

    You can use custom query options as input parameters for service operations. When creating the list binding, specify these custom parameter as follows:

    ``` js
    oTable.bindRows({
            path: "/Products", 
            parameters: {
            custom: {
                param1: "value1",
                param2: "value2"
            }
        },
        template: rowTemplate
    });
    ```

    If you use `bindElement`, you can specify custom parameters as follows:

    ``` js
    oTextField.bindElement("/GetProducts", {
        custom: {
            "price" : "500"
        }
    });
    ```


 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__loio62149734b5c24507868e722fe87a75db"/>

<!-- loio62149734b5c24507868e722fe87a75db -->

## Optimizing Dependent Bindings

The ODataModel V2 supports a flag called "preliminaryContext". With this option set to true, the ODataModel is able to bundle the OData calls for dependent bindings together into fewer $batch requests.

***

<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__section_mjn_51f_zbb"/>

### Introduction

Two bindings are considered "dependent" if one cannot be resolved without the other being resolved first, for example a relative binding cannot be resolved without a resolved absolute binding.

If the `preliminaryContext` option is set to `false`, each binding will be resolved once its preceding binding has been resolved or if it is an absolute binding itself.

The `preliminaryContext` option can also be activated/deactivated per binding instance. This overwrites the default value set on the ODataModel instance.

***

<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__section_svw_z1f_zbb"/>

### Settings and Usage

***

#### ODataModel v2

The constructor parameter is named **preliminaryContext** \(type Boolean\) and has the following properties:

-   Default value is `false`.

-   It is used by the `ContextBinding` as a default value for `createPreliminaryContext` if not given in the constructor. For examples on its usage see "ContextBinding".

-   It is used by the `ContextBinding` as a default value for `usePreliminaryContext` if not given in the constructor. For examples on its usage see "ContextBinding"..


***

#### ODataListBinding v2

The constructor parameter is named **usePreliminaryContext** \(type Boolean\) and has the following properties:

-   Default value is `false`, as it is derived from the ODataModel's default.

-   If set to true:

    -   The `ODataListBinding`accepts preliminary contexts \(for example. in a `setContext()` call\).

    -   The `ODataListBinding` fires a change event with `ChangeReason.Context`, if the binding is updated and a preliminary context was set.


***

#### ODataContextBinding

The `ODataContextBinding` supports two different parameters:

-   `usePreliminaryContext` \(same as a ODataListBinding v2\)

-   `createPreliminaryContext`

    -   If the binding cannot be resolved, it still creates a preliminary binding context, which can be used by other subordinate dependent bindings, which have set the `usePreliminaryContext` option to `true`.

    -   A change event with `ChangeReason.Context` is fired once the data is loaded for the currently preliminary `Context` instance. Afterwards, the existing `Context` instance is not considered "preliminary" anymore.


***

<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__section_wr4_fhf_zbb"/>

### Relationship Between Binding and Model Settings

***

#### Default Behavior

To describe the preliminary context feature in more detail, we first have to look at the default Model/Binding behavior. Let's look at the simple example in the following graphic.

   
  
Simple Binding Example<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__fig_h54_vhf_zbb"/>

 ![](loioe2fe691bea0f4181b6d835c11c92e9ba_LowRes.png "Simple Binding Example") 

Without using preliminary contexts, **Binding 1** resolves only after **Binding 0** is resolved.

For example, if **Binding 1** is a relative `ODataListBinding` on a `Table` control, its OData request will only be sent, once the data for the absolute **Binding 0** is available, for example by using an Element binding on a `Panel` control.

This leads to two subsequent OData requests, one for **Binding 0** and afterwards one for **Binding 1**, as shown in the following table:

Simple Example: Binding Resolution<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__table_xww_51z_zbb"/>

|Request Number|Content|
|--------------|-------|
|1| `GET Products(1)` |
|2| `GET Products(1)/Supplier` |

Now let's look at a more complex example.

   
  
Complex Binding Example<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__fig_j4y_3bz_zbb"/>

 ![](loio410269787de249dc8b573954dd0adc86_LowRes.png "Complex Binding Example") 

In this example we add another binding, which will be resolved once **Binding 0** and **Binding 1** are resolved. This leads to the following three individual `$batch` requests:

Complex Example: Binding Resolution<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__table_ssr_ddz_zbb"/>

|Request Number|Content|
|--------------|-------|
|1| `GET Products(1)` |
|2| `GET Products(1)/Supplier` |
|3| `GET Suppliers(1)/Products` |

***

#### Optimized Behavior

Let's look at the same simple example but with some optimizations.

   
  
Simple Binding Example - Optimized<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__fig_nym_hgz_zbb"/>

 ![](loio57a4d12d4e5d41ecb74298a55b60d0fb_LowRes.png "Simple Binding Example - Optimized") 

Here **Binding 1** uses the preliminary context created by **Binding 0**, and thus the request URL can directly be resolved.

This now leads to only a single `$batch` request:

Simple Example: Binding Resolution Optimized<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__table_mwj_pgz_zbb"/>

|Request Number|Content|
|--------------|-------|
|1| `GET Products(1)` `GET Products(1)/Supplier` |

In this example **Binding 1** has set its `usePreliminaryContext` flag to `true`, and thus accepts preliminary contexts to be set.

> Note:
> If either `createPreliminaryContext` or `usePreliminaryContext` is set to `false`, the default behavior is active.
> 
> 

Now let's see how this works in the complex example.

   
  
Complex Binding Example - Optimized<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__fig_yv1_fhz_zbb"/>

 ![](loioe02b1d8006634769b0094215622c626d_LowRes.png "Complex Binding Example - Optimized") 

In this example we added another binding to the scenario. **Binding 2** is again a relative binding, which can only resolve once **Binding 1** is resolved. **Binding 1** behaves just as before.

In this case the single, generated request looks like this:

Complex Example: Binding Resolution Optimized<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__table_ihd_nhz_zbb"/>

|Request Number|Content|
|--------------|-------|
|1| `GET Products(1)` `GET Products(1)/Supplier` `GET Products(1)/Supplier/Products` |

***

#### Results and Conclusion

Notice how the **Products** list of the **Supplier** is referenced through the entity **Products\(1\)**.This is a result of bundling all data requests into one single `$batch` request, without waiting for the **Products\(1\)** entity and its associated **Supplier** entity to be loaded.

As opposed to the default behavior, we do not require to have the **Products\(1\)** and **Supplier** entities loaded before sending the data request for the Supplier's **Products.Supplier**.So in this case we use a data path based on **Products\(1\)** and not the **ID** of the Supplier. You can compare that to the default behavior of the complex example described above.

> Note:
> What would happen if one binding in the above chain does not set the `usePreliminaryContext` or the `createPreliminaryContext` option to true?
> 
> For example, if **Binding 2** sets its `usePreliminaryContext` option to `false`, the resolution chain is broken and we have a mixed scenario. Here one part is loaded optimized in one `$batch`, and the second part is loaded in a separate `$batch`:
> 
> Complex Example: Binding Resolution Optimized<a name="loio6c47b2b39db9404582994070ec3d57a2 loio62149734b5c24507868e722fe87a75db__table_zr4_m3z_zbb"/>
> 
> |Request Number|Content|
> |--------------|-------|
> |1| `GET Products(1)` `GET Products(1)/Supplier` |
> |2| `GET Products(1)/Supplier/Products` |
> 
> 

> Note:
> With the `$expand` query option you can load all associated entities of another entity. In the previous examples we requested the **Product** list of a certain **Supplier** via a separate request. When using a `$expand` query instead, you could request the same information within one single request:
> 
> `GET Products(1)?$expand=Supplier/Products`
> 
> Even though you now also achieved to have less requests, using `$expand` has a couple of drawbacks. These can be circumvented by using the preliminary context feature, which does not have these limitations.
> 
> In OData V2, with a `$expand` you cannot use additional filters and sorters for the expanded entries. In addition, the `$expand` option always loads **ALL** associated entities, so paging with `$skip` or `$top` is also not possible. Using the preliminary context feature, you get multiple sub-requests in a single `$batch`, yet you can easily include additional filters and sorters on the related subordinate entries.
> 
> 

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio6cb8d585ed594ee4b447b5b560f292a4__loio6cb8d585ed594ee4b447b5b560f292a4"/>

<!-- loio6cb8d585ed594ee4b447b5b560f292a4 -->

## Function Import

The `ODataModel` supports the invoking of function imports or actions by the `callFunction` method.

``` xml
oModel.callFunction("/GetProductsByRating",{method:"GET", urlParameters:{"rating":3}, success:fnSuccess, error: fnError})
```

If the `callFunction` request is deferred, it can be submitted via the `submitChangesmethod`.

> Note:
> Only "IN" parameters of function imports are currently supported.
> 
> 

***

<a name="loio6c47b2b39db9404582994070ec3d57a2 loio6cb8d585ed594ee4b447b5b560f292a4__section_qwk_mtz_xbb"/>

### Binding of Function Import Parameters

OData Model V2 supports the binding against function import parameters. This is similar to the `createEntry` method which supports binding against entity properties. The `callFunction` method returns a request handle that has a `promise`. This `promise` is resolved when the context to which it is bound is created successfully or is rejected if not:

``` xml
var oHandle = oModel.callFunction("/GetProductsByRating", {urlParameters: {rating:3}});
oHandle.contextCreated().then(function(oContext) {
      oView.setBindingContext(oContext);
});
```

If the function import returns result data, then the result data can be accessed and bound against in the `$result` property using the context:

``` xml
<form:SimpleForm>
   <core:Title text="Parameters" />
   <Label text="Rating" />
   <Input value="{rating}" />
   <Button text="Submit" press=".submit" />
   <core:Title text="Result" />
   <List items="{$result}">
    <StandardListItem title="{Name}" />
   </List>
</form:SimpleForm>
```

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loioc40fc72612754bad877f374bdeb0f893__loioc40fc72612754bad877f374bdeb0f893"/>

<!-- loioc40fc72612754bad877f374bdeb0f893 -->

## Language

OpenUI5 uses the concept of a "current language" \(see [Identifying the Language Code / Locale](Identifying_the_Language_Code__Locale_91f21f1.md)\). This language is automatically propagated to the OData service by the OData V2 model. For this reason, applications must not hard code the language themselves, e.g. they must not specify the `"sap-language"` URL parameter as a custom query option.

 <a name="loio6c47b2b39db9404582994070ec3d57a2 loio341823349ed04df1813197f2a0d71db2__loio341823349ed04df1813197f2a0d71db2"/>

<!-- loio341823349ed04df1813197f2a0d71db2 -->

## Meta Model for OData V2

The implementation `sap.ui.model.odata.ODataMetaModel` offers a unified access to both OData Version 2.0 metadata and Version 4.0 annotations.

It uses the existing `sap.ui.model.odata.ODataMetadata` as a foundation and merges the OData Version 4.0 annotations from the existing `sap.ui.model.odata.ODataAnnotations` directly into the corresponding entity or property.

You can get an instance of `sap.ui.model.odata.ODataMetaModel` from an instance of `sap.ui.model.odata.v2.ODataModel`, see [XML Templating](XML_Templating_5ee619f.md).

***

### Basic Structure

The basic structure of `sap.ui.model.odata.ODataMetadata` is shown in the following code snippet. It shows you how the most important elements of the entity model are nested. Each of these elements \(except *association set end*\) can have `extensions`, that is, XML attribute values from some namespace. The code snippets below show how these extensions are stored and processed.

```
"dataServices": {
    "schema": [{
      "association": [{
        "end": []
      }],
      "complexType": [{
        "property": []
      }],
      "entityContainer": [{
        "associationSet": [{
          "end": []
        }],
        "entitySet": [],
        "functionImport": [{
          "parameter": []
        }]
      }],
      "entityType": [{
        "property": [],
        "navigationProperty": []
      }]
    }]
  }
}
```

The following code snippet gives a closer look and has more properties:

```
{
  "version": "1.0",
  "dataServices": {
    "dataServiceVersion": "2.0",
    "schema": [{
      "namespace": "GWSAMPLE_BASIC",
      "entityType": [{
        "name": "BusinessPartner",
        "key": {
          "propertyRef": [{
            "name": "BusinessPartnerID"
          }]
        },
        "property": [{
          "name": "BusinessPartnerID",
          "type": "Edm.String",
          "nullable": "false",
          "maxLength": "10"
        }],
        "navigationProperty": [{
          "name": "ToSalesOrders",
          "relationship": "GWSAMPLE_BASIC.Assoc_BusinessPartner_SalesOrders",
          "fromRole": "FromRole_Assoc_BusinessPartner_SalesOrders",
          "toRole": "ToRole_Assoc_BusinessPartner_SalesOrders"
        }]
      }],
      "complexType": [{
        "name": "CT_Address",
        "property": [{
          "name": "City",
          "type": "Edm.String",
          "maxLength": "40"
        }]
      }],
      "association": [{
        "name": "Assoc_BusinessPartner_SalesOrders",
        "end": [{
          "type": "GWSAMPLE_BASIC.BusinessPartner",
          "multiplicity": "1",
          "role": "FromRole_Assoc_BusinessPartner_SalesOrders"
        }, {
          "type": "GWSAMPLE_BASIC.SalesOrder",
          "multiplicity": "*",
          "role": "ToRole_Assoc_BusinessPartner_SalesOrders"
        }],
        "referentialConstraint": {
          "principal": {
            "role": "FromRole_Assoc_BusinessPartner_SalesOrders",
            "propertyRef": [{
              "name": "BusinessPartnerID"
            }]
          },
          "dependent": {
            "role": "ToRole_Assoc_BusinessPartner_SalesOrders",
            "propertyRef": [{
              "name": "CustomerID"
            }]
          }
        }
      }],
      "entityContainer": [{
        "name": "GWSAMPLE_BASIC_Entities", 
        "isDefaultEntityContainer": "true",
        "entitySet": [{
          "name": "BusinessPartnerSet",
          "entityType": "GWSAMPLE_BASIC.BusinessPartner"
        }],
        "associationSet": [{
          "name": "Assoc_BusinessPartner_SalesOrders_AssocS",
          "association": "GWSAMPLE_BASIC.Assoc_BusinessPartner_SalesOrders",
          "end": [{
            "entitySet": "BusinessPartnerSet",
            "role": "FromRole_Assoc_BusinessPartner_SalesOrders"
          }, {
            "entitySet": "SalesOrderSet",
            "role": "ToRole_Assoc_BusinessPartner_SalesOrders"
          }]
        }],
        "functionImport": [{
          "name": "SalesOrder_Confirm",
          "returnType": "GWSAMPLE_BASIC.SalesOrder",
          "entitySet": "SalesOrderSet",
          "httpMethod": "POST",
          "parameter": [{
            "name": "SalesOrderID",
            "type": "Edm.String",
            "mode": "In",
            "maxLength": "10"
          }]
        }]
      }]
    }]
  }}
```

***

### Accessing Objects and Properties

The objects in the OData meta model are arranged in arrays. `/dataServices/schema`, for example, is an array of schemas where each schema has an `entityType` property with an array of entity types, and so on. So, `/dataServices/schema/0/entityType/16` can be the path to the entity type with name "Order" in the schema with namespace "MySchema".

However, these paths are not stable: If an entity type with lower index is removed from the schema, the path to "Order" changes to `/dataServices/schema/0/entityType/15`. To avoid problems with changing indexes, `getObject` and `getProperty` support XPath-like queries for the indexes. Each index can be replaced by a query in square brackets. You can, for example, address the schema by using the path `/dataServices/schema/[${namespace}==='MySchema']` or address the entity by using the path `/dataServices/schema/[${namespace}==='MySchema']/entityType/[${name}==='Order'`\].

The syntax inside the square brackets corresponds to the expression binding syntax. The query is executed for each object in the array until the result is true \(truthy\) for the first time. This object is then chosen. To embed such a path into an expression binding, use a complex binding syntax: `${path:'...'}`. Example: `{:= ${path:'target>extensions/[${name} === \'semantics\']/value'} === 'email'}`

Each of these queries is self-contained. The query can refer to properties of the current candidate via a relative path, for example `${name}`, but it **cannot** refer to variables such as `${meta>}` that are available in XML templating at that point.

***

### Extensions

`extensions` array and transformed from objects into simple properties with an `sap:` prefix added to their name, see line number 8 in the following code snippet.

> Note:
> As this happens in addition, the following example shows both representations. By this, the respective annotations can be addressed via a simple relative path instead of searching an array.
> 
> 

```
1  {
2    "name": "BusinessPartnerID",
3    "extensions": [{
4      "name": "label",
5      "value": "Bus. Part. ID",
6      "namespace": "http://www.sap.com/Protocols/SAPData"
7    }],
8    "sap:label": "Bus. Part. ID"
9  }
```

***

### OData v4 Annotations

Each element of the entity model \(except *association set end*\) can be annotated. These annotations from the existing `sap.ui.model.odata.ODataAnnotations` are merged directly into the corresponding element. The following code snippet shows how the structure from the existing `sap.ui.model.odata.ODataMetadata`, as explained above and including extensions and constraints such as `nullable` or `maxLength`, is fleshed out with lifted v2 annotations and inlined v4 annotations, such as `Org.OData.Measures.V1.Unit` or `com.sap.vocabularies.UI.v1.Identification`. If you want to navigate the structure, for example for XML templating, it is important to understand this structure.

ODataMetaModel JSON Format:

``` js

"dataServices" : {
    "schema" : [{
        "namespace" : "GWSAMPLE_BASIC",
        "entityType" : [{
            "name" : "Product",
            "property" : [{
                "name" : "ProductID",
                "type" : "Edm.String",
                "nullable" : "false",
                "maxLength" : "10"
            }, {
                "name" : "SupplierName",
                "type" : "Edm.String",
                "maxLength" : "80",
                "extensions" : [{
                  "name" : "label",
                  "value" : "Company Name",
                  "namespace" : "http://www.sap.com/Protocols/SAPData"
                }, {
                  "name" : "creatable",
                  "value" : "false",
                  "namespace" : "http://www.sap.com/Protocols/SAPData"
                }, {
                  "name" : "updatable",
                  "value" : "false",
                  "namespace" : "http://www.sap.com/Protocols/SAPData"
                }],
                "sap:label" : "Company Name",
                "sap:creatable" : "false",
                "sap:updatable" : "false"
                "Org.OData.Core.V1.Computed" : {
                    "Bool" : "true"
                }
            }, {
                "name" : "WeightMeasure",
                "type" : "Edm.Decimal",
                "precision" : "13",
                "scale" : "3",
                "Org.OData.Measures.V1.Unit" : {
                    "Path" : "WeightUnit"
                }
            }, {
                "name" : "WeightUnit",
                "type" : "Edm.String",
                "maxLength" : "3"
            }],
            "com.sap.vocabularies.UI.v1.DataPoint" : {
                "Value" : {
                    "Path" : "WeightMeasure",
                    "EdmType" : "Edm.Decimal"
                }
            },
            "com.sap.vocabularies.UI.v1.Identification" : [{
                "Value" : {"Path" : "ProductID"}
            }, {
                "Value" : {"Path" : "SupplierName"}
            }, {
                "Value" : {"Path" : "WeightMeasure"}
            }]
        }]
    }]
}
```

***

<a name="loio6c47b2b39db9404582994070ec3d57a2 loio341823349ed04df1813197f2a0d71db2__Enhancement"/>

### Enhancement of the OData Meta Model

In addition to the easy access to the SAP-specific OData annotations, such as `sap:label`, corresponding vocabulary-based annotations are mixed in if they are not yet defined in the OData Version 4.0 annotations of the existing `sap.ui.model.odata.ODataAnnotations`.

> Note:
> Annotation terms are not merged, but replaced as a whole \("PUT" semantics\). If the same annotation term with the same target is also contained in an annotation file, the complete OData V4 annotation converted from the OData V2 annotation is replaced by the one contained in the annotation file for the specified target. Converted annotations never use a qualifier and are only overwritten by the same annotation term without a qualifier.
> 
> 

The following tables show the transformations that are implemented with version 1.30 of OpenUI5 \(variatons of this are marked accordingly\). In the examples shown below, `AnyPath` is a path expression as defined in the [OData Version 4.0 specification](http://docs.oasis-open.org/odata/odata/v4.0/os/part3-csdl/odata-v4.0-os-part3-csdl.html), section 14.5.12.

Transformations defined at `EntitySet`:

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>OData V2 SAP Extension</th>
			<th>Resulting OData V4 Annotation</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```
sap:creatable = "false"

```
			</td>
			<td> 

```
"Org.OData.Capabilities.V1.InsertRestrictions": { "Insertable" : { "Bool" : "false" } }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:deletable = "false"

```
			</td>
			<td> 

```
"Org.OData.Capabilities.V1.DeleteRestrictions": { "Deletable" : { "Bool" : "false" } }

```

 > Note:
 > If both, `sap:deletable` and `sap:deletable-path` are given, the service is broken and it is handled as `sap:deletable="false"`.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:deletable-path = "AnyPath"
```
			</td>
			<td> Where `AnyPath` is a path expression that identifies a Boolean property in the context of the entity type of the entity set. The value of this property indicates whether the entity can be deleted or not.</td>
 

```
"Org.OData.Capabilities.V1.DeleteRestrictions": { "Deletable" : { "Path" : "AnyPath" } }
```

 > Note:
 > If both, `sap:deletable` and `sap:deletable-path` are given, the service is broken and it is handled as `sap:deletable="false"`.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:label = "foo"
```
			</td>
			<td> Where `foo` is any text.</td>
 

```
"com.sap.vocabularies.Common.v1.Label": {"String" : "foo" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:pageable = "false"

```
			</td>
			<td> 

```
"Org.OData.Capabilities.V1.SkipSupported": {"Bool" : "false" },
"Org.OData.Capabilities.V1.TopSupported": {"Bool" : "false" }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:requires-filter = "true"

```
			</td>
			<td> 

```
"Org.OData.Capabilities.V1.FilterRestrictions": { "RequiresFilter" : { "Bool" : "true" } }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:searchable = "false"

```
			</td>
			<td> Alternatively, do not use the `sap:searchable` annotation.</td>
 

```
"Org.OData.Capabilities.V1.SearchRestrictions": { "Searchable" : { "Bool" : "false" } }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:topable = "false"

```
			</td>
			<td> 

```
"Org.OData.Capabilities.V1.TopSupported": {"Bool" : "false" }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:updatable = "false"

```
			</td>
			<td> 

```
"Org.OData.Capabilities.V1.UpdateRestrictions": { "Updatable" : { "Bool" : "false" } }

```

 > Note:
 > If both, `sap:updatable` and `sap:updatable-path` are given, the service is broken and it is handled as `sap:updatable="false"`.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:updatable-path = "AnyPath"
```
			</td>
			<td> Where `AnyPath` is a path expression that identifies a Boolean property in the context of the entity type of the entity set. The value of this property indicates whether the entity can be updated or not.</td>
 

```
"Org.OData.Capabilities.V1.UpdateRestrictions": { "Updatable" : { "Path" : "AnyPath" } }
```

 > Note:
 > If both, `sap:updatable` and `sap:updatable-path` are given, the service is broken and it is handled as `sap:updatable="false"`.
			</td>
		</tr>
	</tbody>
</table>

Transformations defined at `Property`:

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>OData V2 SAP Extension</th>
			<th>Resulting OData V4 Annotation</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```
sap:label = "foo"
```
			</td>
			<td> Where `foo` is any text.</td>
 

```
"com.sap.vocabularies.Common.v1.Label": {"String" : "foo" }
```

 > Note:
 > The resulting annotation is added at different places, not to the `Property`.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:creatable = "true" 
```

 and ```
sap:updatable = "false"
```
			</td>
			<td> 

```
"Org.OData.Core.V1.Immutable": { "Bool" : "true" }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:creatable = "false"
```

 and ```
sap:updatable = "false"
```
			</td>
			<td> 

```
"Org.OData.Core.V1.Computed": { "Bool" : "true"}

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:display-format = "NonNegative"
```

 > Note:
 > `NonNegative` indicates that only non-negative numeric values are provided and persisted, other input leads to errors; intended for `Edm.String` fields that are internally stored as `NUMC`.
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsDigitSequence": { "Bool" : "true" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:display-format = "UpperCase"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsUpperCase": { "Bool" : "true" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:field-control = "AnyPath"
```
			</td>
			<td> Where `AnyPath` is a path expression that identifies a property containing a numeric value that controls visibility..</td>
 

```
"com.sap.vocabularies.Common.v1.FieldControl": { "Path" : "AnyPath" }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:filterable = "false"
```
			</td>
			<td> 

```
"Org.OData.Capabilities.V1.FilterRestrictions":
{ "NonFilterableProperties" : [
{ "PropertyPath" : "PropA " },
{ "PropertyPath" : "PropC " }] }
```

 For example, if `sap:filterable` is set to `false` for properties `PropA` and `PropC`.

 > Note:
 > The resulting annotation is added to the `EntitySet`, not to the `Property`.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:filter-restriction="multi-value"
```
			</td>
			<td> For example, at a `BusinessPartnerID` property of a `BusinessPartner` type.</td>
 

```
"com.sap.vocabularies.Common.v1.FilterExpressionRestrictions":
[{ "Property" : { "PropertyPath" : "BusinessPartnerID" },
"AllowedExpressions" : { "EnumMember":
"com.sap.vocabularies.Common.v1.FilterExpressionType/MultiValue" } }]
```

 At the corresponding entity set, for example, `BusinessPartnerSet.multi-value` is mapped to `MultiValue`, `single-value` is mapped to `SingleValue`, and `interval` is mapped to `SingleInterval`.

 > Note:
 > The resulting annotation is added to the `EntitySet`, not to the `Property`.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:heading = "foo"
```
			</td>
			<td> Where `foo` is any text.</td>
 

```
"com.sap.vocabularies.Common.v1.Heading": { "String" : "foo" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:precision = "AnyPath"

```
			</td>
			<td> Where `AnyPath` is a path expression that identifies a property in the context of the entity type containing the number of significant decimal places for a numeric value.</td>
 

```
"Org.OData.Measures.V1.Scale": { "Path" : "AnyPath" }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:quickinfo = "foo"
```
			</td>
			<td> Where `foo` is any text.</td>
 

```
"com.sap.vocabularies.Common.v1.QuickInfo": { "String" : "foo" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:required-in-filter = "true"

```
			</td>
			<td>If `sap:required-in-filter` is set to `TRUE` for the `PropA` and `PropC` properties: 

```
"Org.OData.Capabilities.V1.FilterRestrictions": {
"RequiredProperties" : [
{ "PropertyPath" : "PropA " },
 { "PropertyPath" : "PropC " }] }
```

 > Note:
 > The resulting annotation is added to the `EntitySet`, not to the `Property`.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:sortable = "false"
```
			</td>
			<td>If `sap:sortable` is set to `FALSE` for the `PropA` and `PropC` properties: 

```
"Org.OData.Capabilities.V1.SortRestrictions": {
"NonSortableProperties" : [ 
{ "PropertyPath" : "PropA " }, 
{ "PropertyPath" : "PropC " }]}
```

 > Note:
 > The resulting annotation is added to the `EntitySet`, not to the `Property`.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:text = "AnyPath"
```
			</td>
			<td> Where `AnyPath` is a path expression that identifies a property in the context of the entity type containing a human-readable text for the value of this property.</td>
 

```
"com.sap.vocabularies.Common.v1.Text":{ "Path" : "AnyPath" }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:unit="WeightUnit"
```

 or ```
sap:unit="CurrencyCode"
```
			</td>
			<td> Where `WeightUnit` and `CurrencyCode` are names of properties in the same entity and `WeightUnit` points to a property with `sap-semantics:unit-of-measure` and `CurrencyCode`points to a property with `sap-semantics:currency-code`.</td>
 

```
"Org.OData.Measures.V1.Unit": { "Path" : "WeightUnit" }
```

 or ```
"Org.OData.Measures.V1.ISOCurrency": { "Path" : "CurrencyCode" }

```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:visible="false"
```
			</td>
			<td> 

```
"com.sap.vocabularies.UI.v1.Hidden" : { "Bool" : "true" }
```

 Deprecated as of SAPUI5 1.44: ```
"com.sap.vocabularies.Common.v1.FieldControl": { "EnumMember" :
"com.sap.vocabularies.Common.v1.FieldControlType/Hidden" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:aggregation-role="dimension"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Analytics.v1.Dimension" : { "Bool" : "true" }
```

 > Note:
 > Implemented with version 1.46.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:aggregation-role="measure"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Analytics.v1.Measure" : { "Bool" : "true" }
```

 > Note:
 > Implemented with version 1.46.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics="year"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsCalendarYear" : {"Bool" : "true"}
```

 > Note:
 > Implemented with version 1.50.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics="yearmonth"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsCalendarYearMonth" : {"Bool" : "true"}
```

 > Note:
 > Implemented with version 1.50.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics="yearmonthday"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsCalendarDate" : {"Bool" : "true"}
```

 > Note:
 > Implemented with version 1.50.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = url
```
			</td>
			<td> 

```
"Org.OData.Core.V1.IsURL" : { "Bool" : "true" }

```

 > Note:
 > Implemented with version 1.52.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics="yearquarter"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsCalendarYearQuarter" : {"Bool" : "true"}
```

 > Note:
 > Implemented with version 1.54.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics="yearweek"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsCalendarYearWeek" : {"Bool" : "true"}
```

 > Note:
 > Implemented with version 1.54.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics="fiscalyear"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsFiscalYear" : {"Bool" : "true"}
```

 > Note:
 > Implemented with version 1.54.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics="fiscalyearperiod"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Common.v1.IsFiscalYearPeriod" : {"Bool" : "true"}
```

 > Note:
 > Implemented with version 1.54.
			</td>
		</tr>
	</tbody>
</table>

Transformations defined at `NavigationProperty`:

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>OData V2 SAP Extension</th>
			<th>Resulting OData V4 Annotation</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```

 For example, if `sap:filterable` is set to `false` for properties `PropA` and `PropC` > Note:
> The resulting annotation is added to the `EntitySet`, *HIGHLIGHT START*not*HIGHLIGHT END* to the `NavigationProperty`.
> 
> 

 > Note:
> Implemented with version 1.42.
> 
> 

 > Note:
> Deprecated with version 1.54. See entry below.
> 
> 

 |
| ```

 > Note:
 > Implemented with version 1.42.

 > Note:
 > Deprecated with version 1.54. See entry below.
			</td>
		</tr>
		<tr>
			<td> 

```
sap:filterable = "false"
```
			</td>
			<td> 
```

 For example, if `sap:filterable` is set to false for navigation properties `NavPropA` and `NavPropB`. > Note:
> The resulting annotation is added to the `EntitySet`, *HIGHLIGHT START*not*HIGHLIGHT END* to the `NavigationProperty`.
> 
> 

 > Note:
> Implemented with version 1.54.
> 
> 

 |
| ```
```

 For example, if `sap:filterable` is set to false for navigation properties `NavPropA` and `NavPropB`.

 > Note:
 > The resulting annotation is added to the `EntitySet`, **not** to the `NavigationProperty`.

 > Note:
 > Implemented with version 1.54.
			</td>
		</tr>
		<tr>
```

 For example, if `sap:creatable` is set to `false` for navigation properties `NavPropA` and `NavPropC` > Note:
> The resulting annotation is added to the `EntitySet`, *HIGHLIGHT START*not*HIGHLIGHT END* to the `NavigationProperty`.
> 
> 

 > Note:
> If `sap:creatable` and `sap:creatable-path` are given, the service is broken and it is handled as `sap:creatable="false"`.
> 
> 

 > Note:
> Implemented with version 1.42.
> 
> 

 |
| ```
 For example, if `sap:creatable` is set to `false` for navigation properties `NavPropA` and `NavPropC`

 > Note:
 > The resulting annotation is added to the `EntitySet`, **not** to the `NavigationProperty`.

 > Note:
 > If `sap:creatable` and `sap:creatable-path` are given, the service is broken and it is handled as `sap:creatable="false"`.

 > Note:
 > Implemented with version 1.42.
			</td>
		</tr>
		<tr>
			<td> 

```
```

 > Note:
> The resulting annotation is added to the `EntitySet`, *HIGHLIGHT START*not*HIGHLIGHT END* to the `NavigationProperty`.
> 
> 

 > Note:
> If `sap:creatable` and `sap:creatable-path` are given, the service is broken and it is handled as `sap:creatable="false"`.
> 
> 

 > Note:
> Implemented with version 1.42.
> 
> 

 |

Transformations defined at `Schema`:

|OData V2 SAP Extension|Resulting OData V4 Annotation|
|----------------------|-----------------------------|
| ```
 > If `sap:creatable` and `sap:creatable-path` are given, the service is broken and it is handled as `sap:creatable="false"`.

 > Note:
 > Implemented with version 1.42.
			</td>
		</tr>
	</tbody>
</table>

Transformations defined at `Schema`:

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>OData V2 SAP Extension</th>
			<th>Resulting OData V4 Annotation</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```
schema-version="foo"
```
			</td>
			<td> 

```
"@Org.Odata.Core.V1.SchemaVersion" : "foo"
```

 > Note:
 > Implemented with version 1.54.
			</td>
		</tr>
	</tbody>
</table>

Depending on the value of the `sap:semantics` annotation, different vocabulary-based annotations are generated. The following transformations are implemented and defined at `property`. In the examples of the resulting JSON at the "defined at" object, `PROPERTY` is a placeholder for the name of the property at which the `sap:semantics` annotation is defined.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>OData V2 SAP Extension</th>
			<th>Resulting OData V4 Annotation</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```
sap:semantics = "currency-code"
```
			</td>
			<td>see `sap:unit` above</td>
			<td> 

```
sap:semantics = "unit-of-measure"
```
			</td>
			<td>see `sap:unit` above</td>
			<td> 

```
sap:semantics = "name"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "fn" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "givenname"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "n" : { "given" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "middlename"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "n" : { "additional" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "familyname"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "n" : { "surname" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "nickname"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "nickname" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "honorific"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "n" : { "prefix" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "suffix"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "n" : { "suffix" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "note"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "note" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "photo"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "photo" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "city"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "adr" : { "locality" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "street"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "adr" : { "street" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "country"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "adr" : { "country" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "region"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "adr" : { "region" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "zip"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "adr" : { "code" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "pobox"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "adr" : { "pobox" : { "Path" : "PROPERTY" } } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "org"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "org" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "org-unit"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "orgunit" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "org-role"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "role" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "title"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "title" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "bday"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Contact" : { "bday" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "dtstart"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "dtstart" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "dtend"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "dtend" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "duration"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "duration" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "class"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "class" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "status"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "status" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "transp"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "transp" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "fbtype"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "fbtype" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "wholeday"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "wholeday" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "location"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Event" : { "location" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "due"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Task" : { "due" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "completed"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Task" : { "completed" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "percent-complete"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Task" : { "percentcomplete" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "priority"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Task" : { "priority" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "from"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Message" : { "from" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "sender"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Message" : { "sender" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "subject"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Message" : { "subject" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "body"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Message" : { "body" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "received"
```
			</td>
			<td> 

```
"com.sap.vocabularies.Communication.v1.Message" : { "received" : { "Path" : "PROPERTY" } }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "tel"
```
			</td>
			<td>At the `EntityType` or `ComplexType`: 

```
"com.sap.vocabularies.Communication.v1.Contact" : { 
"tel" : [{
"uri" : { "Path" : "ATTRIBUTE" }
}]}
```

 Where `ATTRIBUTE` is the name of the annotated attribute of an `EntityType` or `ComplexType`. At `Property`: ```
"com.sap.vocabularies.Communication.v1.IsPhoneNumber" : { "Bool" : "true" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "tel";type=cell,work
```
			</td>
			<td>At the `EntityType` or `ComplexType`: 

```
"com.sap.vocabularies.Communication.v1.Contact" : { 
"tel" : [{
"type" : {
"EnumMember": "com.sap.vocabularies.Communication.v1.PhoneType/cell"
+ " com.sap.vocabularies.Communication.v1.PhoneType/work"
},
"uri" : { "Path" : "ATTRIBUTE" }
}]}
```

 Where `ATTRIBUTE` is the name of the annotated attribute of an `EntityType` or `ComplexType`. At `Property`: ```
"com.sap.vocabularies.Communication.v1.IsPhoneNumber" : { "Bool" : "true" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "email"
```
			</td>
			<td>At the `EntityType` or `ComplexType`: 

```
"com.sap.vocabularies.Communication.v1.Contact" : { 
"address" : [{
"uri" : { "Path" : "ATTRIBUTE" }
}]}
```

 Where `ATTRIBUTE` is the name of the annotated attribute of an `EntityType` or `ComplexType`. At `Property`: ```
"com.sap.vocabularies.Communication.v1.IsEmailAddress" : { "Bool" : "true" }
```
			</td>
		</tr>
		<tr>
			<td> 

```
sap:semantics = "email";type=work,pref
```
			</td>
			<td>At the `EntityType` or `ComplexType`: 

```
"com.sap.vocabularies.Communication.v1.Contact" : { 
"email" : [{
"address" : { "Path" : "ATTRIBUTE" },
"type" : {
"EnumMember" : "com.sap.vocabularies.Communication.v1.ContactInformationType/work"
+ "com.sap.vocabularies.Communication.v1.ContactInformationType/preferred"
}
}]}
```

 Where `ATTRIBUTE` is the name of the annotated attribute of an `EntityType` or `ComplexType`. At `Property`: ```
"com.sap.vocabularies.Communication.v1.IsEmailAddress" : { "Bool" : "true" }
```
			</td>
		</tr>
	</tbody>
</table>

**Related information**  


[XML Templating](XML_Templating_5ee619f.md)

[OData V2 Model](OData_V2_Model_.md#loio6c47b2b39db9404582994070ec3d57a2)

[Class `sap.ui.model.odata.ODataMetaModel`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.ODataMetaModel.html)

