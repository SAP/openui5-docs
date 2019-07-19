<!-- loiof38c21c2f71e455e8d4a959522035a1f -->

| loio |
| -----|
| f38c21c2f71e455e8d4a959522035a1f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f38c21c2f71e455e8d4a959522035a1f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f38c21c2f71e455e8d4a959522035a1f)</div>

## ARIA Labeling

Proper labeling of all UI elements is needed in order to ensure the screen reader announces everything correctly. Here we describe the available options and how and when they should be used.

***

### Labeling

There are several options for labeling:

1.   `Label` element with `labelFor` attribute

    -   Single ID reference to the labeled control

    -   Reference is maintained on the label, not on the labeled control

    -   Multiple references are not possible

    > Note:
    > `<Label text="Product price" required="true" **labelFor="productPriceInput"**/>`
    > 
    > 

2.  The `aria-label` attribute

    -   Text is directly provided in the attribute, no extra HTML control needed

    -   Attribute is maintained on the labeled control

    -   Only indirect support for multiple texts

3.  The `aria-labelledBy` attribute

    -   Whitespace separated list of ID references to controls

    -   Attribute is maintained on the labeled control

    -   Explicitly designed for multiple references


> Note:
> The different options cannot be used in conjunction. There is a precedence rule, which determines how the labeling attributes are prioritized and read by the screen reader. As an application developer, you need to be aware of the order in which the labeling is read by your screen reader.
> 
> 

**Related information**  


[Best Practices for ARIA Labeling](Best_Practices_for_ARIA_Labeling_3169195.md)

