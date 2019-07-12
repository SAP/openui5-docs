| loio |
| -----|
| f86dbe9d7f7d48dea5286003b1322165 |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/f86dbe9d7f7d48dea5286003b1322165.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f86dbe9d7f7d48dea5286003b1322165) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f86dbe9d7f7d48dea5286003b1322165)</div>
<!-- loiof86dbe9d7f7d48dea5286003b1322165 -->

## Image

Additional information on `sap.m.Image`

***

<a name="loiof86dbe9d7f7d48dea5286003b1322165__section_N10018_N10011_N10001"/>

### Supporting Different Pixel Densities

Some mobile devices, starting with iPhone4 and iPad3, have a display with a very high density of pixels \(four pixels where older models would only have one pixel\). They are called "retina displays" by Apple to suggest they are as crisp and clear as the eye can see. They use four physical pixels to display one logical CSS pixel, so images can be displayed much sharper when given twice as large as usually required because internally the device can use much more pixels to display all details of the image. Browsers on those displays do this automatically when images are scaled down.

So some devices support higher resolution images while others do not. We therefore recommend that OpenUI5 application developers provide image resources for all relevant densities to provide a very crisp and clear display of images on devices with "retina display".

The `sap.m.Image` control automatically chooses the right density, depending on the device on which it is displayed. If an image of a certain density is not available, the image control falls back to a default image, which should be provided as well.

> Note:
> The image control is also used implicitly by other controls, for example
> 
> -   Button
> -   Segmented Button
> -   Standard List Item
> 
> 

> Note:
> If you do not have higher resolution images you should set the `densityAware` property to false to avoid unnecessary roundtrips.
> 
> 

***

<a name="loiof86dbe9d7f7d48dea5286003b1322165__section_N10057_N10011_N10001"/>

### Example

Assume the following controls are displayed on a device with high-density screen \(`window.devicePixelRatio` is 2\):

```lang-js

new sap.m.Image({ 
	    densityAware: false, // tell the image control that there are no different optimized image variants
	    src : "first.png"   // therefore Image control will directly load first.png 
})

new sap.m.Image({ 
    	src : "second.png"    // Image control will first look for second@2.png, then fall back to second.png
})
```

The first image control has been told that there are no image files for the different densities, so it will directly load "first.png". This image looks as good as other images on retina displays.

The second image control will first attempt to load second@2.png which should be twice as large as the normal image and would be scaled down for display, so it looks absolutely crisp on retina displays. If this file does not exist, it will fall back to "second.png", but this fallback will cause an additional server request.

***

<a name="loiof86dbe9d7f7d48dea5286003b1322165__section_N10075_N10011_N10001"/>

### Naming Conventions

Density related images are loaded if you provide an image name with density awareness in following format is provided:

```
[imageName]@[densityValue].[extension]
```

Currently, we support the densities 1.5 and 2. The following example shows a set of images with different densities:

-   detail.png \(default\)
-   detail@1.5.png
-   detail@2.png

> Note:
> detail@0.75.png \(not supported any more, will use the standard image for such low density device\)
> 
> 

