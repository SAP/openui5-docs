<!-- loio086c41c2441946219384197a6c82072b -->

| loio |
| -----|
| 086c41c2441946219384197a6c82072b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/086c41c2441946219384197a6c82072b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/086c41c2441946219384197a6c82072b)</div>

## Colors and Theming

Theming is an important aspect for an OpenUI5 application. The different colors shown on the UI need to have a good contrast to each other in order to be easily distinguishable.

***

### General Recommendations

Different people perceive and interpret colors in different ways, which is something you must take into account when developing your applications. High-contrast themes are already available for all OpenUI5 controls.

-   Applications need to provide the user with an option to switch themes.

    -   If the application runs in the SAP Fiori launchpad, this is covered automatically.


-   There are two possible ways to change the theme:

    -   With the URL parameter `sap-ui-theme`

        ```
        sap-ui-theme=sap_belize_hcb
        ```

        and

        ```
        sap-ui-theme=sap_belize_hcw
        ```

    -   From the API using the core method `applyTheme`

        ```
        sap.ui.getCore().applyTheme(“sap_belize_hcb”);
        ```

        or

        ```
        sap.ui.getCore().applyTheme(“sap_belize_hcw”);
        ```


-   You should avoid writing custom CSS. If you do need custom CSS for some reason, check to make sure everything is working fine on all available themes.

-   If a new theme is created, the color contrast between the elements should be checked. People with visual impairments and people using the application under less than ideal circumstances \(bad monitor, sunlight hitting the screen, window reflections\) may not be able to read the text easily if the contrast levels are insufficient. Specialized tools can help you to measure the color contrast.


***

### DOs and DON'Ts

***

#### DOs

-   Use predefined CSS parameters in your CSS. You can find them in the following files within the OpenUI5 library:

    -   `resources/sap/m/themes/base/library-parameters.json`

    -   `resources/sap/m/themes/sap_hcb/library-parameters.json`


-   Use `REM`/`EM` instead of `PX` as a unit.

-   Use the flexible layout concept in CSS.

-   Use media-queries when flexible layouts do not meet UX expectations.

-   Don't forget the Retina display. You need to provide 2 versions for an icon \(`icon.png` and `icon@2x.png`\).


***

#### DON'Ts

-   Define a custom color.

-   Define a custom font family.

-   Set fixed width/height \(except for some exceptions like images\).

-   Define writing-modes \(left-to-right or right-to-left\), as this is handled by the OpenUI5 control itself.


***

### Tips for Testing

Check the color contrasts.

-   Take a screenshot, put it into an image tool and convert it to black and white

    -   Are there screen elements, lines or texts that are disappearing?

    -   Check the color contrast for elements that disappear.


-   If time allows, check all contrasts of all elements.


