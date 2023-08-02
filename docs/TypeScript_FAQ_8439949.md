<!-- loio8439949bbdc34141bd2b9194f91d42c2 -->

| loio |
| -----|
| 8439949bbdc34141bd2b9194f91d42c2 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/8439949bbdc34141bd2b9194f91d42c2) | [demo kit latest release](https://sdk.openui5.org/topic/8439949bbdc34141bd2b9194f91d42c2)</div>

## TypeScript FAQ

***

<a name="loio8439949bbdc34141bd2b9194f91d42c2__section_llg_15n_hyb"/>

### Contents

-   [What is TypeScript about?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__whatists)
-   [What is the overall approach for using TypeScript in UI5 applications?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__approach)
-   [How to set up a new UI5 app for TypeScript development?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__howto)
-   [How can I get an end-to-end hands-on impression of creating and developing a UI5 app in TypeScript?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__handson)
-   [How to convert an existing UI5 app to TypeScript?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__convert)
-   [How to develop custom controls in TypeScript?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__customcontrols)
-   [How to use third-party libraries from npm in UI5 apps?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__thirdpartylib)
-   [How to test in TypeScript?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__test)
-   [How to profit from TypeScript even when doing plain JavaScript development?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__profitfromts)
-   [What are the TypeScript projects and releases provided by the UI5 development team?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__tsandui5)
-   [Where to report issues?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__issues)
-   [Are the type definitions ready for productive use?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__productiveuse)
-   [Where can I find release notes or news about changes in the UI5 type definitions?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__releasenotes)
-   [What is the future roadmap for TypeScript in UI5?](TypeScript_FAQ_8439949.md#loio8439949bbdc34141bd2b9194f91d42c2__roadmap)

***

***

#### What is TypeScript about?

TypeScript is an extension of JavaScript that enhances it with type information, enabling error detection through type checking and providing code assistance in numerous supporting code editors \(such as code completion and inline documentation\). It's important to note that browsers cannot directly execute TypeScript; a transpilation step is required.

***

#### What is the overall approach for using TypeScript in UI5 applications?

We publish type definition files describing all the UI5 APIs and types. With the help of these definitions, the TypeScript tools can do their job and support writing UI5 apps in TypeScript.

***

#### How to set up a new UI5 app for TypeScript development?

By adding TypeScript and the UI5 type definitions as dev dependencies and setting up the transpilation step. The `ui5-typescript-helloworld` project can serve as copy template and provides a detailed step-by-step guide for setting up a TypeScript project.

***

#### How can I get an end-to-end hands-on impression of creating and developing a UI5 app in TypeScript?

You can follow the [`ui5-typescript-tutorial`](https://github.com/SAP-samples/ui5-typescript-tutorial) tutorial, starting from scratch using an app template, extending the resulting app, and also covering advanced topics later on, like control development and integrating third-party libraries from npm.

***

#### How to convert an existing UI5 app to TypeScript?

***

#### How to develop custom controls in TypeScript?

***

#### How to use third-party libraries from npm in UI5 apps?

Third-part libraries written for running in a browser environment can be easily used with very natural `npm install` and import `<moduleName>` from `dependencyName`, resulting in code completion for those libraries and automatic transpiling into UI5’s own AMD-like module format.

***

#### How to test in TypeScript?

***

#### How to profit from TypeScript even when doing plain JavaScript development?

***

#### What are the TypeScript projects and releases provided by the UI5 development team?

***

#### Where to report issues?

***

#### Are the type definitions ready for productive use?

They are ready for use since version 1.116.

***

#### Where can I find release notes or news about changes in the UI5 type definitions?

***

#### What is the future roadmap for TypeScript in UI5?

