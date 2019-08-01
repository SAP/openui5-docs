<!-- loio3459c372aaaa4c31ab87bb0e174adcc3 -->

| loio |
| -----|
| 3459c372aaaa4c31ab87bb0e174adcc3 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3459c372aaaa4c31ab87bb0e174adcc3) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3459c372aaaa4c31ab87bb0e174adcc3)</div>

## OData Features Supported by Mock Server

List of OData version 2.0 features supported or not supported by the mock server

The mock server only supports the JSON format for representing the resources it exposes, such as collections, entries, and links.

> Note:
> The mock server doesn’t support more than one draft service in an application.
> 
> 

The following table lists the OData features that are supported by the mock server.

Supported OData Features<a name="loio3459c372aaaa4c31ab87bb0e174adcc3__table_h31_lzq_qv"/>

|Feature|Status|
|-------|------|
|CRUD calls|Supported|
|Navigations|Supported|
| **Query String options:** |
|- Orderby System Query Option \(`$orderby`\)|Supported|
|- Top System Query Option \(`$top`\)|Supported|
|- Skip System Query Option \(`$skip`\)|Supported|
|- Filter System Query Option \(`$filter`\)|Supported; `eq`, `ne`, `gt`, `lt`, `ge`, `le`, `substringof`, `startswith`, `endswith`, `and`, `or` |
|- Expand System Query Option \(`$expand`\)|Supported|
|- Select System Query Option \(`$select`\)|Supported|
|- Inlinecount System Query Option \(`$inlinecount`\)|Supported|
|- Format System Query Option \(`$format`\)|Supported; only JSON format is allowed|
|Batch processing|Supported|
|Multiple services|Supported; we recommend to create one Mock Server instance per service|
|Update via `MERGE`/`PATCH` |Supported|
|ETag handling|Supported|

The following table lists the OData features that are **not** supported by the mock server.

Unsupported OData Features<a name="loio3459c372aaaa4c31ab87bb0e174adcc3__table_ymm_pzq_qv"/>

|Feature|Status|
|-------|------|
|Service operations \(function imports\)|Unsupported, but can be extended|
|Annotations|Unsupported|
|Getting individual properties of an entity \(`$value`\)|Unsupported|
| `Edm.DateTime` keys|Unsupported|
| `Edm.DateTime` values|All dates have to be either before 2017 or after; you cannot use mixed values|
| `metadata.xml` with properties from `datetimeoffset` |Unsupported|
|Key of type `Edm.Boolean` |Unsupported|
|Key of type `Edm.Int64` |Unsupported|
| `$links` and `#AddressingLinksBetweenEntries` |Unsupported For more information see [Addressing Links between Entries](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/#AddressingLinksBetweenEntries) and [Referencing Requests in a Change Set](http://www.odata.org/documentation/odata-version-2-0/batch-processing/#ReferencingRequestsInAChangeSet) on [http://www.odata.org/](http://www.odata.org/).|
|Multiple navigation properties|Unsupported|
|Response in byte array format|Unsupported|
|Combination of the system queries `$select` and `$expand` in draft OData services|Unsupported|
|Filter query string operator \(`$filter`\) with one of the functions `substringof(string po, string p1)`, `endswith(string p0, string p1)` or `startswith(string p0, string p1)` |Does not support input strings \(`p0` or `p1`\) containing a comma `,`.|
|Key values containing a comma|Unsupported|
|System query option `$expand` with multiple multi-level navigation properties with the same root navigation property|Unsupported|
|Filter query `$filter` on fields from type `edm.datetime` |Unsupported|

