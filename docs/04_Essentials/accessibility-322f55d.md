<!-- loio322f55d0cf1e4b459cc1911c899b7a5f -->

# Accessibility

Accessibility features are essential for the usability of each application and essential for users with disabilities. In an ongoing approach, OpenUI5 controls aim to comply with various accessibility standards such as screen reader support, high contrast theming, and keyboard handling.

OpenUI5 is constantly evolving and improving along the line of accessibility. SAP is including latest changes to accessibility regulations and industry standards into its guiding accessibility development policy and related accessibility testing procedures. We are continuously making improvements with every new version of the framework. Therefore, it's important, if you want to get the latest and greatest features and enhancements on the topic of accessibility, you should regularly update to the last available version.

The following topics provide important accessibility information related to OpenUI5 controls.

> ### Note:  
> This documentation describes standard accessibility functionality in OpenUI5. For specific information on accessibility in products based on OpenUI5, see the documentation for the respective product. **In case of conflict between the OpenUI5 documentation and the respective product documentation describing accessibility functionality, the respective product documentation shall prevail.** 
> 
> Note that accessibility for web applications also depends on the browser and the operating system used. For more information, see the [SAP Accessibility Status Documents](https://www.sap.com/about/company/diversity/accessibility.html#product-information) section.



<a name="loio322f55d0cf1e4b459cc1911c899b7a5f__section_q4h_rvw_3sb"/>

## Understanding Accessibility

Accessibility refers to the possibility for everyone, including and especially people who are differently-abled, to access and use information technology products. It is a guiding principle in OpenUI5 design and development processes and integral part of the framework.

Accessibility is incorporated at two levels: framework and application level. Many features are available on the framework level and provided to app developers out of the box, which ensures consistency across all products. Some features need to be added or adapted according to the app-specific context and need to be considered when developing your app.

Depending on your use case please refer to the corresponding accessibility chapter in the Developing Controls or Developing Apps sections in Demo Kit.



<a name="loio322f55d0cf1e4b459cc1911c899b7a5f__section_mfg_vvw_3sb"/>

## OpenUI5 Accessibility Building Blocks

-   Markup \(correct HTML\): When developing accessible applications, you need to pay attention to the correctness of the resulting HTML. Some vital accessibility features \(screen reader and keyboard support\) rely on a correct and meaningful structure of the application.

-   ARIA attribute: Accessible Rich Internet Applications \(ARIA\) is a set of attributes that define ways to make web content and applications more accessible to people with disabilities who use assistive technologies.
-   Keyboard handling: Keyboard handling enables users to access every UI element of the application with the keyboard.
-   Screen reader: A screen reader is a software application that identifies and interprets textual content on the UI. Developers need to know how the screen reader reads out the contents of the UI.
-   Contrast: The different colors shown on the UI need to have a good contrast to each other, in order to be easily distinguishable.
-   Resizing: Developers should always consider the fact that the application could be zoomed to 200%, and everything should still be visible.
-   APIs: The framework provides APIs to help app developers improve the accessibility in the context of their application.

**Related Information**  


[Accessibility in SAP Fiori](https://experience.sap.com/fiori-design-web/accessibility-in-sap-fiori/ "Accessibility in SAP Fiori")

[Accessibility in the Developing Apps Section](../05_Developing_Apps/accessibility-03b914b.md "Accessibility in the Developing Apps Section")

[Accessibility Aspects in the Developing Controls Section](../07_Developing_Controls/accessibility-aspects-694b356.md "Accessibility Aspects in the Developing Controls Section")

