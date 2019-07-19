<!-- loio3d85d5eec1594be0a71236d5e61f89aa -->

| loio |
| -----|
| 3d85d5eec1594be0a71236d5e61f89aa |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3d85d5eec1594be0a71236d5e61f89aa) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3d85d5eec1594be0a71236d5e61f89aa)</div>

## XML View Cache

To be able to speed up processing times of XML views that make heavy use of the preprocessor feature, you can use the view cache to store its processed XML source. Then according network requests for the source and all preprocessor runs that modify the XML source are skipped and the source is taken from the cache.

To make sure that the cache always contains the latest view data, the cache has to be invalidated whenever the data changes that is needed for preprocessing. When the cache is invalidated, all resources are processed again and the cache gets filled with new data.

> Note:
> Parts of this feature are currently still experimental. For more information, see [API Reference: `sap.ui.xmlview`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.xmlview). 
> 
> 

The following data changes are handled automatically by OpenUI5:

-   OpenUI5 version changes

-   Descriptor file \(`manifest.json`\)

-   Locale \(for each locale one cached resource is being created\)


> Note:
> For each additional component that may have an influence on the preprocessing results of the view source, like OData metadata, you have to implement the invalidation by adding additional keys to the cache configuration.
> 
> 

***

### Prerequisites

This feature is only enabled for the following browsers:

-   Google Chrome as of version 49 for desktop

-   Internet Explorer as of version 11 for desktop


The XML view has to be loaded asynchronously.

***

### Cache Configuration

If you want to keep things simple, you can use the following cache configuration:

``` xml
var sCalculatedCacheKey = oKeyProvider.getCacheKey();
sap.ui.xmlview({
	async: true,
	id: "cacheableView",
	viewName: "my.cacheableView",
	cache: {
		// one key is mandatory
		keys:[sCalculatedCacheKey]
	}
});
```

If you want to pass on multiple keys, for example strings or promises that resolve with a string, you use the following syntax:

``` xml
var pCalculatedCacheKey = oKeyProvider1.getCacheKeyPromise();
var sAnotherKey = oKeyProvider2.getCacheKey(); 
sap.ui.xmlview({
	async: true,
	id: "cacheableView",
	viewName: "my.cacheableView",
	cache: {
		keys: [
		// several key providers, at least one
		pCalculatedCacheKeyPromise,
		sAnotherKey
		]
	}
});
```

***

<a name="loio3d85d5eec1594be0a71236d5e61f89aa__ViewCache_Preprocessor"/>

### Preprocessor Integration

If you want to implement a preprocessor that has influence on the creation of views, for example, by changing the XML code, you can use function `getCacheKey`. With this function, the view can find out whether the preprocessor triggers changes that invalidate the cache. The function returns a cache key or a promise that resolves a cache key. For more information, see [API Reference: `sap.ui.core.mvc.View.Preprocessor`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.mvc.View.Preprocessor.html). 

``` xml
// Example preprocessor implementation
sap.ui.define(['jquery.sap.global', 'sap/ui/base/Object'],
	function(jQuery, BaseObject) {
		'use strict';

		var TestPreprocessor = BaseObject.extend("smy.TestPreprocessor", {});

		TestPreprocessor.process = function(vSource, sCaller, mSettings) {
			return doSomething(vSource));
		};

		TestPreprocessor.getCacheKey = function(oViewInfo) {
			return sCacheKey;
		};

		return TestPreprocessor;

	}, /* bExport= */ true);
```

**Related information**  


[API Reference: `sap.ui.xmlview`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.xmlview)

[Preprocessing XML Views](Preprocessing_XML_Views_48b81b9.md)

