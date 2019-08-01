<!-- loio753b32617807462d9af483a437874b36 -->

| loio |
| -----|
| 753b32617807462d9af483a437874b36 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/753b32617807462d9af483a437874b36) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/753b32617807462d9af483a437874b36)</div>

## Development Conventions and Guidelines

To keep the OpenUI5 code readable and maintainable, development conventions and guidelines are introduced. We strongly recommend that you follow these guidelines even if you find them violated somewhere. For files that are consistently **not** following these rules and for which adhering to the rules would make the code worse, follow the local style. If you want to contribute your content to OpenUI5, you **have to** follow these conventions and guidelines.

> Note:
> This list is not complete.
> 
> 

***

### General Guidelines

The following list gives some general guidelines to be adhered to when developing content for OpenUI5:

-   Always consider the developers who **use** your control or code! Do not surprise them, but give them what they expect. And make it simple.

-   Use tabs, not spaces, for indentation; adhere to local standards in the file.

-   Use Unix line endings \(LF-only\).

    In Eclipse, this is configured in *Preferences* \> *General* \> *Workspace* \> *New Text File Line Delimiter*.

-   Text files must be UTF-8 encoded \(HANA\); only `*.properties` and `*.hdbtextbundle` files must be ISO8859-1 encoded as defined in the corresponding standard.

    This is the status quo. As this causes issues, it may be subject to change. In Eclipse, this is configured in *Preferences* \> *General* \> *Workspace* \> *Text File Encoding*.

-   An 80-character line length guideline does **not** exist.

-   Use comments; do **not** rephrase the code, but tell the reader what is **not** in the code. Describe why your code does what it does. Prefer line comments.


