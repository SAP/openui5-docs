<!-- loio8439949bbdc34141bd2b9194f91d42c2 -->

| loio |
| -----|
| 8439949bbdc34141bd2b9194f91d42c2 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/8439949bbdc34141bd2b9194f91d42c2) | [demo kit latest release](https://sdk.openui5.org/topic/8439949bbdc34141bd2b9194f91d42c2)</div>

## TypeScript FAQ

Frequently asked questions regarding TypeScript in OpenUI5.

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_obw_l5f_myb"/>

### What is TypeScript about?

TypeScript is an extension of JavaScript that enhances it with type information, enabling error detection through type checking and providing code assistance in numerous supporting code editors \(such as code completion and inline documentation\). It's important to note that browsers cannot directly execute TypeScript; a transpilation step is required.

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_slg_v5f_myb"/>

### What is the overall approach for using TypeScript in OpenUI5 applications?

We publish type definition files describing all the OpenUI5 APIs and types. With the help of these definitions, the TypeScript tools can do their job and support writing OpenUI5 apps in TypeScript.

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_awv_z5f_myb"/>

### How to set up a new OpenUI5 app for TypeScript development?

For detailed information on developing applications with OpenUI5, see [Developing Apps](Developing_Apps_23cfd95.md). To write OpenUI5 apps in TypeScript and take advantage of its benefits, you also need to add TypeScript and the OpenUI5 type definitions as dev dependencies. Additionally, you must set up the TypeScript transpilation step. The [`ui5-typescript-helloworld`](https://github.com/SAP-samples/ui5-typescript-helloworld/blob/main/step-by-step.md) project can serve as copy template and provides a detailed step-by-step guide for setting up a TypeScript project.

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_rhs_fvf_myb"/>

### How can I get an end-to-end hands-on impression of creating and developing a OpenUI5 app in TypeScript?

You can follow the [`ui5-typescript`](https://github.com/SAP-samples/ui5-typescript-tutorial) tutorial, starting from scratch using an app template, extending the resulting app, and also covering advanced topics later on, like control development and integrating third-party libraries from npm.

To start even faster, see one of the following app templates:

-   [`generator-ui5-ts-app`](https://github.com/ui5-community/generator-ui5-ts-app): A plain app template that contains one view and basic routing setup and is explained in this blog post: [Getting Started with TypeScript for UI5 Application Development](https://blogs.sap.com/2021/07/01/getting-started-with-typescript-for-ui5-application-development/).

-   [`generator-ui5-ts-app-fcl`](https://github.com/ui5-community/generator-ui5-ts-app-fcl): A more comprehensive template including a FlexibleColumnLayout and allowing OData service and entity configuration within the wizard.

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_zvl_5wf_myb"/>

### How to test in TypeScript?

You can check the `testing` branch of the [`ui5-typescript-helloworld`](https://github.com/SAP-samples/ui5-typescript-helloworld/tree/testing) sample app.

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_prp_pwf_myb"/>

### How to develop custom controls in TypeScript?

Check the [TypeScript Guidelines](TypeScript_Guidelines_192397d.md).

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_bbj_bxf_myb"/>

### How to profit from TypeScript even when doing plain JavaScript development?

Check the `js-with-typescript-support` branch of the [`ui5-cap-event-app`](https://github.com/SAP-samples/ui5-cap-event-app/blob/js-with-typescript-support/README.md) sample app. It explains how to add TypeScript-based benefits to an existing JavaScript app without actually switching to TypeScript development.

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_ahv_j1g_myb"/>

### Are the type definitions ready for productive use?

They are ready for use since version 1.116.

***

