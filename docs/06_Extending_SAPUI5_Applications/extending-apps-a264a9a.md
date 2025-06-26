<!-- loioa264a9abf98d4caabbf9b027bc1005d8 -->

# Extending Apps

You can adapt an OpenUI5 app to your specific requirements. For example, you can adapt or replace views, extend or replace controllers, or change language-specific texts.

The extension of OpenUI5 apps uses the component configuration. The extension information is stored in a specific area of the component configuration. It can be performed on a custom app that extends a delivered standard app. A replacement or extension of views and custom controllers can also be part of a custom app, but may not always be required. If no replacement and no custom controller exists, the custom app project only contains the component definition with the extension configuration. The standard app itself is not changed. The customized app becomes the start-up project and launches the standard app with the additional extension configuration.

For more information, see [Using Component Configuration](using-component-configuration-c264d66.md).

-   **[Using Component Configuration](using-component-configuration-c264d66.md "OpenUI5 supports the
			extension of a base controller by merging the delivered standard controller with a
			custom controller on JavaScript object level.")**  
OpenUI5 supports the extension of a base controller by merging the delivered standard controller with a custom controller on JavaScript object level.
-   **[Localized Texts for Extended Apps](localized-texts-for-extended-apps-2edc3f9.md "You can add custom localized text files that contain additional texts or texts that
		overwrite the original texts to the sap.ui.model.resource.ResourceModel
	")**  
You can add custom localized text files that contain additional texts or texts that overwrite the original texts to the `sap.ui.model.resource.ResourceModel` 
-   **[Caveats Regarding Stability Across Application Upgrades](caveats-regarding-stability-across-application-upgrades-aef3384.md "There are a few restrictions in the compatibility of custom applications that have to be
		considered when extending OpenUI5 standard applications.")**  
There are a few restrictions in the compatibility of custom applications that have to be considered when extending OpenUI5 standard applications.
-   **[Supportability](supportability-c44813d.md "In case of problems or errors in the custom application, several options exist that
		support you in resolving the issues.")**  
In case of problems or errors in the custom application, several options exist that support you in resolving the issues.

