<!-- loiob229914587444025be986d81dcc77303 -->

| loio |
| -----|
| b229914587444025be986d81dcc77303 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b229914587444025be986d81dcc77303) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b229914587444025be986d81dcc77303)</div>

## Descriptor for Libraries

The descriptor for libraries contains a subset of the attributes in the descriptor for applications and components.

|manifest.json|.library|Available for SAPUI5 dist libraries?|Comment|
|-------------|--------|------------------------------------|-------|
| `sap.app/id` | `name` |x| |
| `sap.app/type` |-|x|Generated with value `library` |
| `sap.app/embeds` |-|x|Generated|
| `sap.app/i18n` | `appData/manifest/i18n` | |New in `.library` |
| `sap.app/applicationVersion/version` | `version` |x| |
| `sap.app/title` | `title` |x|Text symbol syntax with leading curly brackets \(`{{`\) and trailing curly brackets \(`}}`\); new in `.library` |
| `sap.app/description` | `documentation` |x|Text symbol syntax with leading curly brackets \(`{{`\) and trailing curly brackets \(`}}`\)|
| `sap.app/ach` | `appData/ownership/component` |x| |
| `sap.app/openSourceComponents` | `appData/manifest/openSourceComponents` | |New in `.library` |
| `sap.app/resources` |-|x|Generated with value `resources.json` |
| `sap.app/offline` | `appData/manifest/offline` |x|New in `.library` |
| `sap.app/sourceTemplate` | `appData/manifest/sourceTemplate` | |New in `.library`, to be filled by SAP Web IDE only|
| `sap.ui/technology` |-|x|Generated with value `UI5` |
| `sap.ui/deviceTypes` | `appData/manifest/deviceTypes` | |New in `.library` |
| `sap.ui/supportedThemes` |-|x|Generated and merged|
| `sap.ui5/dependencies/minUI5Version` |-|x|Generated|
| `sap.ui5/dependencies/libs` | `dependencies` |x| |
| `sap.ui5/contentDensities` | `appData/manifest/contentDensities` | |New in `.library` |
| `sap.platform.abap/uri` | `appData/manifest/sap.platform.abap/uri` | |New in `.library` |
| `sap.platform.hcp/uri` | `appData/manifest/sap.platform.hcp/uri` | |New in `.library` |
| `sap.fiori/registrationIds` | `appData/manifest/sap.fiori/registrationId` | |New in `.library` |
| `sap.fiori/archeType` | `appData/manifest/sap.fiori/archeType` | |New in `.library` |

**Related information**  


[Creating a Descriptor File for Existing Apps](Creating_a_Descriptor_File_for_Existing_Apps_3a9baba.md)

