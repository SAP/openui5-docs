<!-- loio0635156f3950494885ca314a13e15e29 -->

## Enabling the Automatic Header Adaptation in the Manifest

Application developers can enable automatic adaptation of their existing applications from the `manifest.json` file \(also known as descriptor for applications, components and libraries\).



### The Automatic Header Adaptation

OpenUI5 offers an adapter mechanism to let existing apps automatically adjust their header layout according to the SAP Fiori design guidelines.

> ### Note:  
> The screenshots in this topic are mockups and are used to visually outline the adaptations. The final apps will look somewhat different.

  
  
**Header of a fullscreen application**

![](images/loiod78b4f43624842a894908bbcf9c8dd20_HiRes.png "Header of a fullscreen application")

The complete adaptation of a fullscreen app to SAP Fiori design guidelines consists of five main steps:

1.  Remove the app-specific header bar. The header is made transparent and collapsed if there is no content in it after the adaptation.

2.  Display the title in the center of the SAP Fiori launchpad header.

3.  Move the action buttons from the app header to the header content area below the SAP Fiori launchpad header.

4.  Move the *Back* button from the app-specific header to the SAP Fiori launchpad header.

5.  Drill-down hierarchy levels can be added to the dropdown menu adjacent to the FLP title.


> ### Note:  
> These adaptations are primarily valid only for **fullscreen** apps. Other floorplans, like List-Detail, are affected differently and the adaptation there will not be the same.



### Enabling the Adaptation in the Manifest

You can override the adapter default behavior for a single application by adding an entry in the manifest in the `sap.ui5/config` section. Setting `sapFiori2Adaptation` to **true** enables the full functionality of the Adapter.

```
"config": {
            ...
            "sapFiori2Adaptation": true,
            ...
}

```

Alternatively, you can use five fine-grained settings to enable only some of the adaptations. In the following example, you can see how to trigger transparent headers \(`style` attribute\) and title propagation to SAP Fiori launchpad \(`title` attribute\). The other adaptations are not applied.

```
"config": {
            ...
            "sapFiori2Adaptation": {
                  "style": true,       
                  "collapse": false,   
                  "title": true,       
                  "back": false,       
                  "hierarchy": false   
            },
            ...
}

```

In the list below, you can see what each of the settings enables.

-   `style` - Triggers header transparency

-   `collapse` - Triggers collapsing of the header when empty

-   `title` - Triggers moving the header to SAP Fiori launchpad

-   `back` - Triggers the *Back* button visibility in the app

-   `hierarchy` - Triggers propagation of the hierarchy to SAP Fiori launchpad


> ### Note:  
> In rare cases, this automatic adaptation of the header area may not work, due to the application structure or other reasons. In this case the headers will still appear in the old design, but the apps will continue to be usable.

Some old SAP Fiori applications do not have a manifest yet. If you consider the effort to provide proper manifests for all applications as too high, there is a second way to do this configuration. This alternative configuration is done in the `metadata` section of <code><b>Component.js</b></code> \(the app's root component\), which also has a `config` section. The configuration options can be done there in the same manner.

> ### Note:  
> If both the metadata and manifest are configured, and contradict each other, the configuration in **manifest.json** is applied.

