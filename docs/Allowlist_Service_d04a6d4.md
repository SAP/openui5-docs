<!-- loiod04a6d41480c4396af16b5d2b25509ec -->

| loio |
| -----|
| d04a6d41480c4396af16b5d2b25509ec |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/d04a6d41480c4396af16b5d2b25509ec) | [demo kit latest release](https://sdk.openui5.org/topic/d04a6d41480c4396af16b5d2b25509ec)</div>

## Allowlist Service

SAPUI5 supports the configuration of a central allowlist service.

`frameOptions` uses the allowlist service to determine whether the application should run in the parent origin or not. The allowlist service call uses the parent origin as URI parameter \(URL encoded\) as follows:

```
GET url/to/allowlist/service?parentOrigin=https://parent.domain.com
```

The service responds to the request with a valid JSON:

```js

{
    "version" : "1.0",
    "active"  : true | false,                   // defines if entry is active (if not, framing will be allowed per default)
    "origin"  : "<same as passed to service>",
    "framing" : true | false                    // if active, describes if framing should be allowed (see FrameOptions)
}
```

**Related Information**  


[Frame Options](Frame_Options_62d9c4d.md "The frame-options configuration of OpenUI5 is a client-side feature that is used to prevent security vulnerabilities like clickjacking, that is, situations where a user could be misled to use the targeted application unintentionally.")

[Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md "The following tables show available configuration options.")

