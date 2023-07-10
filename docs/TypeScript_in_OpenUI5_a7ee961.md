<!-- loioa7ee9617bc794b6fad21e4df38e31128 -->

| loio |
| -----|
| a7ee9617bc794b6fad21e4df38e31128 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/a7ee9617bc794b6fad21e4df38e31128) | [demo kit latest release](https://sdk.openui5.org/topic/a7ee9617bc794b6fad21e4df38e31128)</div>

## TypeScript in OpenUI5

TypeScript is an extension of JavaScript that adds type information to the language. It helps developers catch errors early through type checking and by providing code assist in supporting code editors, for example through code completion and inline documentation.

The types can be seen as a complementary addition to improve your development experience and help you write applications in modern JavaScript. You may always remove them from your app again in case of any issues. Browsers can’t execute TypeScript directly; it needs to be transpiled to JavaScript, which can then be executed as usual.

***

<a name="loioa7ee9617bc794b6fad21e4df38e31128__section_wg2_31v_4xb"/>

### Delivery of the OpenUI5 Type Information

When writing TypeScript code, the type information can be scattered across the code. But you can also create separate type definition files for existing JavaScript libraries. For OpenUI5, we provide separate definition files that describe the OpenUI5 APIs and types. With the help of these definitions, you can write OpenUI5 apps in TypeScript and enjoy all the benefits that come with it.

OpenUI5 type definitions are provided via npm under the name `@openui5/types` \(published directly by the OpenUI5 development team\) and `@types/openui5` \(maintained in the DefinitelyTyped infrastructure\).

Providing the type definitions as a separate package allows you to retain an older version of the types while upgrading the UI5 runtime, which is one of the options to mitigate incompatible changes of the types. For more information, see our [compatibility statement](TypeScript_in_OpenUI5_a7ee961.md#loioa7ee9617bc794b6fad21e4df38e31128__section_CSTD).

***

<a name="loioa7ee9617bc794b6fad21e4df38e31128__section_CSTD"/>

### Compatibility Statement for the OpenUI5 Type Definitions

We encourage you to use UI5 with TypeScript for an improved development efficiency and experience. TypeScript itself keeps evolving, and we try to further improve the UI5 type definitions, so there could be potential incompatible changes between versions of the type definitions. However, such incompatibilities would only affect the **compilation** of your code but will not cause **runtime** issues in your application. Plus, there are various ways to easily deal with them: You can, for example, simply keep using the previous version of the UI5 type definitions together with an updated UI5 runtime. For more information, see *Breaking changes* below.

Known incompatibilities will be communicated in the [UI5-TypeScript release notes](https://sap.github.io/ui5-typescript/releasenotes.html).

***

#### Breaking changes

UI5 with TypeScript is in its final stage of stability, so please go ahead and use it! However, breaking changes can still occur. Possible reasons are:

-   Fixes in the API documentation that cause TS compiler errors,
-   Changes in TypeScript itself,
-   A significant improvement of a type definition that can only be achieved with a breaking change,
-   A bug.

For more information, see [here](https://sap.github.io/ui5-typescript/beta-statement.html#why-will-there-still-be-breaking-changes-even-after-the-type-definitions-have-left-beta-stage).

To mitigate breaking changes, you have several options. You can find the full list here: [How to mitigate breaking changes?](https://sap.github.io/ui5-typescript/beta-statement.html#how-to-mitigate-breaking-changes-within-as-well-as-after-beta-phase)

***

#### Combining TypeScript versions and type definition releases

See [What is the plan regarding different TypeScript versions? Which ones will each type definition release be compatible with?](https://sap.github.io/ui5-typescript/beta-statement.html#what-is-the-plan-regarding-different-typescript-versions-which-ones-will-each-type-definition-release-be-compatible-with)

***

#### Further information

-   Documentation and resources: [UI5 & TypeScript](https://sap.github.io/ui5-typescript/)
-   Tutorial: [Learn App Development in UI5 and TypeScript](https://github.com/SAP-samples/ui5-typescript-tutorial)

npm Packages \(check the individual packages for licensing information\):

-   [UI5 type signatures on npm](https://www.npmjs.com/package/@sapui5/ts-types-esm)
-   [Babel preset UI5 transformer on npm](https://www.npmjs.com/package/babel-preset-transform-ui5) to transform ES modules and classes to classic UI5 code

