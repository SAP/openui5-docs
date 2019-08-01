<!-- loiod04a6d41480c4396af16b5d2b25509ec -->

| loio |
| -----|
| d04a6d41480c4396af16b5d2b25509ec |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d04a6d41480c4396af16b5d2b25509ec) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d04a6d41480c4396af16b5d2b25509ec)</div>

## Whitelist Service

SAPUI5 supports the configuration of a central whitelist service.

`frameOptions` uses the whitelist service to determine whether the application should run in the parent origin or not. The whitelist service call uses the parent origin as URI parameter \(URL encoded\) as follows:

```
GET url/to/whitelist/service?parentOrigin=https://parent.domain.com
```

The service responds to the request with a valid JSON:

``` js

{
    "version" : "1.0",
    "active"  : true | false,                   // defines if entry is active (if not, framing will be allowed per default)
    "origin"  : "<same as passed to service>",
    "framing" : true | false                    // if active, describes if framing should be allowed (see FrameOptions)
}
```

**Related information**  


[Frame Options](Frame_Options_62d9c4d.md)

[Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md)

