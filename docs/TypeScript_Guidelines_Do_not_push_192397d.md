<!-- loio192397d3cb954d4e986bcdc525c5205c -->

| loio |
| -----|
| 192397d3cb954d4e986bcdc525c5205c |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/192397d3cb954d4e986bcdc525c5205c) | [demo kit latest release](https://sdk.openui5.org/topic/192397d3cb954d4e986bcdc525c5205c)</div>

## TypeScript Guidelines \(Do not push\)

Provides an overview how to develop OpenUI5 control libraries in TypeScript.

***

<a name="loio192397d3cb954d4e986bcdc525c5205c__section_brg_5pj_gxb"/>

### Why TypeScript?

TypeScript is a superset of JavaScipt that extends its capabilities by adding optional static types, which can help developers catch errors during the development process, enable better tooling and code refactoring, and improve code readability and maintainability.

OpenUI5 publishes type definition files describing all the OpenUI5 APIs and types.

***

<a name="loio192397d3cb954d4e986bcdc525c5205c__section_mdl_gyq_3xb"/>

### Developing Custom Controls in TypeScript

There is [documentation](https://github.com/SAP-samples/ui5-typescript-helloworld/blob/custom-controls/README.md) and sample code in the [custom-controls branch of the Hello World application](https://github.com/SAP-samples/ui5-typescript-helloworld/tree/custom-controls), which explains how you can implement custom controls in TypeScript within OpenUI5 applications. It makes use of a [tool for generating TypeScript interfaces for the control API](https://github.com/SAP/ui5-typescript/tree/main/packages/ts-interface-generator), which has been [released via npm](https://www.npmjs.com/package/@ui5/ts-interface-generator) in alpha state. There is also a sample project that demonstrates how flull-fledged [control libraries can be developed in TypeScript](https://github.com/SAP-samples/ui5-typescript-control-library).
