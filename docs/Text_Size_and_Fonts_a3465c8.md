<!-- loioa3465c8d71b449dba23d557cb2c413aa -->

| loio |
| -----|
| a3465c8d71b449dba23d557cb2c413aa |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a3465c8d71b449dba23d557cb2c413aa) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a3465c8d71b449dba23d557cb2c413aa)</div>

## Text Size and Fonts

The size of the text and the font choice greatly impact the visibility and readability of an application. Additionally, your application also has to still be usable at high zoom levels.

***

### Rules and Guidelines

As an application developer, you should always consider the fact that the application could be zoomed to 200%, and everything should still be visible. For that reason, any style that involves disabling zooming or setting fixed weight or height should be avoided. Properties that affect the zooming have to be set accordingly.

Here are some of the most common JavaScript properties that you should bear in mind:

-   `user-scalable`

-   `initial-scale`

-   `maximum-scale`

-   `minimum-scale`

-   `width`

-   `height`

-   `target-densitydpi`


> Note:
> Setting inappropriate values for these properties can completely disable the zooming of an application. Here is an example of such incorrect values:
> 
> ```
> <meta name="viewport" content="user-scalable=no, initial-scale=1, maximum-scale=1,
>  minimum-scale=1, width=device-width, height=device-height,
>  target-densitydpi=device-dpi" />
> ```
> 
> 

Additionally, you can also make zoom adjustments or disable zoom completely in CSS. For example:

```
zoom {
   zoom: 150%;
}
```

Or

```
#elementId {
   -ms-transform: scale(2,3); /* Internet Explorer 9 */
   -webkit-transform: scale(2,3); /* Safari */
   transform: scale(2,3);
}

html {
   -ms-content-zoom-limit-min: 1;
   -ms-content-zoom-limit-max: 1;
}

html {
   touch-action: none;
}

```

***

### Tips for Testing

Enlarge the application UI text by zooming up to 200%.

-   Is each text element and each image enlarged to double width and double height?

-   Is the text still readable \(no overlaps\)?

-   Are text alternatives for non-text content magnified in the same way?

-   Is the full content and functionality still available?

-   Does the layout still look OK?


