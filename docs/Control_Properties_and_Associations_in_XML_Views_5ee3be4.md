<!-- loio5ee3be4727864bb08b991414e0428e38 -->

| loio |
| -----|
| 5ee3be4727864bb08b991414e0428e38 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5ee3be4727864bb08b991414e0428e38) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5ee3be4727864bb08b991414e0428e38)</div>

## Control Properties and Associations in XML Views

***

### Properties

Property values for controls in XML views are specified as attributes of the XML element tag of the control. The name of the attribute corresponds to the name of the property in the API reference, for example, the property `text` of a the `sap.m.Text` control is specified as `text=”*value*”`.

> ### Note:  
> Escape characters that have a special meaning in XML \(like `<`, or `&`\) when they occur in a property value. Use XML entities instead \(like `&lt;` instead of a `<`, or `&amp;` instead of `&`\).

Attributes in XML views use the same binding syntax as constructors of controls. For example, `“{customerName}”` is used to bind a property against the model property with name `“customerName”`.

**Example:** `sap.m.Text` with plain text:

``` xml
<Text text="My Text"/>
```

**Example:** `sap.m.Text` with text provided by a binding:

``` xml
<Text text="{customerName}"/>
```

**Example:** `sap.m.Text` with escaped special characters:

``` xml
<Text text="&lt;div&gt;My HTML Text&lt;/div&gt;"/>
```

> ### Note:  
> Properties of type `function` can be specified similar to [event handlers in XML views](Handling_Events_in_XML_Views_b0fb4de.md). However, the legacy syntax of function names without dots is not supported.

***

### Associations

-   Associations of **cardinality `1`**: Define the ID of the associated element in an attribute that has the same name as the association in the XML view.

    **Example:** `sap.m.Select` with preselected item with ID **item2** :

    ``` xml
    <Select selectedItem="item2">
        <items>
            <core:Item id="item1" key="article_1" text="Article 1" />
            <core:Item id="item2" key="article_2" text="Article 2" />
            <core:Item id="item3" key="article_3" text="Article 3" />
        </items>
    </Select>
    ```

-   Associations of **cardinality `0..n`**: You can define multiple IDs separated by a blank.

    **Example:** `sap.m.MultiComboBox` with preselected items **item2** and **item3**:

    ``` xml
    <MultiComboBox selectedItems="item2 item3">
        <items>
            <core:Item id="item1" key="article_1" text="Article 1" />
            <core:Item id="item2" key="article_2" text="Article 2" />
            <core:Item id="item3" key="article_3" text="Article 3" />
        </items>
    </MultiComboBox>
    ```


