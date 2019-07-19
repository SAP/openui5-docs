<!-- loio5a0d286c5606424b8e0d663c87445733 -->

| loio |
| -----|
| 5a0d286c5606424b8e0d663c87445733 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5a0d286c5606424b8e0d663c87445733) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5a0d286c5606424b8e0d663c87445733)</div>

## Performance Aspects

The OData V4 model offers the features described below which influence performance.

***

### `odata.metadata=minimal`

The OData V4 model uses an `odata.metadata=minimal` header in its requests to reduce the amount of data that is sent from server to client. For more information, see section "3.1.1 odata.metadata=minimal" in the [OData JSON Format Version 4.0](http://docs.oasis-open.org/odata/odata-json-format/v4.0/os/odata-json-format-v4.0-os.html) specification.

***

### `$expand` and `$select`

An application can either specify `$expand` and `$select` parameters to read all data to be displayed in one request, or create bindings dynamically to load only part of the data with one request per binding. The application needs to decide whether to have less roundtrips with a bigger payload or more roundtrips with smaller payload.

To reduce payload, applications should only select properties that are needed using `$select` \(see the code sample in the [Parameters](Parameters_1ab4f62.md) topic\). Besides the properties needed on the UI, the binding must select key properties to support features such as read requests sent from a child binding, write requests, or bound operations on the respective entity.

***

### Batching Requests or Not

By default, the OData V4 model collects all requests made to the OData service in a batch request to reduce the number of roundtrips. The disadvantage of a batch request is that it cannot be cached by the browser. If some of the requests \(e.g. value help requests\) are "cacheable", it is a good idea to request these resources directly and use the browser cache to improve the performance of the application. In such cases, use the `$direct` group as described in the section [Batch Control](Batch_Control_74142a3.md).

***

### Binding Caches

Absolute bindings and also relative bindings, which fulfill certain conditions, have a cache that is used for their data. Once data is read, all value requests \(e.g. those made by dependent relative bindings\) are served by this cached data. `ODataListBinding` additionally supports paging. For more information about this, see [Bindings](Bindings_54e0ddf.md).

Calling `refresh` on an absolute binding clears its cache as well as the caches of its relative child bindings. Calling `refresh` on the model refreshes all bindings that have been created by that model.

> Note:
> Relative bindings have an own cache store cache by context. When you change the context of the relative binding and then switch back to the previous context, the latter context change will not lead to a data request as the cache holding this data is reused. This is useful for master-detail scenarios where selection in the master leads to setting the corresponding context in the relative binding for the detail. Entries in the master that have already been selected won't lead to a data request.
> 
> **Note:** For the above mechanism to work, you must not recreate a relative binding as you then lose the cache for the previously selected contexts. Keep the binding and just set its context.
> 
> 

***

<a name="loio5a0d286c5606424b8e0d663c87445733__section_uhx_xn4_cdb"/>

### Early requests for metadata and security token

The requests for the service's root `$metadata` document and annotation files and for the security token may be on the "critical execution path": By default, these requests are sent lazily when the OpenUI5 application starts, for example. only when the corresponding information is needed. This delays application startup until these requests have returned.

If you construct the model with parameter **earlyRequests**, the requests are sent as early as possible and application startup performance may improve.

> Note:
> Modern browsers typically can process up to six parallel requests. Therefore it strongly depends on the number of requests sent initially by the application, if and how much the performance improves.
> 
> 

> Note:
> The default value for `earlyRequests` is false in OpenUI5 version 1.54. It may, however, change to true in later releases: Do not rely on the default value and explicitly set it to false to ensure the requests are not sent early.
> 
> 

**Related information**  


[OData JSON Format Version 4.0](http://docs.oasis-open.org/odata/odata-json-format/v4.0/os/odata-json-format-v4.0-os.html)

[Bindings](Bindings_54e0ddf.md)

[Batch Control](Batch_Control_74142a3.md)

