<!-- loiobafc6867041644a9b596370e48a106ee -->

| loio |
| -----|
| bafc6867041644a9b596370e48a106ee |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/bafc6867041644a9b596370e48a106ee) | [demo kit latest release](https://sdk.openui5.org/topic/bafc6867041644a9b596370e48a106ee)</div>

## Product Standards and Acceptance Criteria

To be of high quality and usable in mission-critical business software, OpenUI5 needs to fulfill specific product standards and acceptance criteria. While these are not directly related to code conventions, the most important standards and criteria are mentioned here, because new code needs to fulfill these requirements.

General product standards and acceptance criteria:

-   Browser support, see [Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md)

-   Security \(such as output encoding to prevent XSS attacks\)

-   Performance needs to be in focus

-   Automated tests, such as QUnit

-   Proper API documentation

-   Translation: All texts that are visible on the UI must be enabled for translation.

    Do **not** provide the translations, but only provide a raw english version in the `messagebundle.properties` file.

    Make sure that you annotate the strings properly for translation. For more information, see [Annotations in Translation Files](Annotations_in_Translation_Files_8310398.md).

-   Adhere to the compatibility rules, see [Compatibility Rules](Compatibility_Rules_91f0873.md).

-   Make sure that any Open Source libraries \(or parts of them\) that you use are officially approved before you add them to OpenUI5. Do **not** add any code you "found" somewhere.


Additional product standard and acceptance criteria for controls:

-   Screenreader support \(ARIA\)

-   Keyboard navigation support

-   Required themes; what themes are required depends on the library, but always includes the High Contrast theme for accessibility

-   Right-to-left support

-   Example page in the *Samples* in the Demo Kit


-   **[Annotations in Translation Files](Annotations_in_Translation_Files_8310398.md "All strings for translation have to be annotated to provide more context for
		translation. An annotation consists of an &quot;X/Y&quot; text type classification, an optional length
		restriction, and a freetext explanation how the string is used on the UI.")**  
All strings for translation have to be annotated to provide more context for translation. An annotation consists of an "X/Y" text type classification, an optional length restriction, and a freetext explanation how the string is used on the UI.

