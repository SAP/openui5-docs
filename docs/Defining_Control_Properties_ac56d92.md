<!-- loioac56d92162ed47ff858fdf1ce26c18c4 -->

| loio |
| -----|
| ac56d92162ed47ff858fdf1ce26c18c4 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ac56d92162ed47ff858fdf1ce26c18c4) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ac56d92162ed47ff858fdf1ce26c18c4)</div>

## Defining Control Properties

Control properties are defined as follows:

``` js
properties: {
   "title" : "string",                         // a simple string property, default value is undefined
   "buttonText" : {defaultValue: "Search"},    // when no type is given, the type is string
   "showLogoutButton" : {type : "boolean", defaultValue : true},   // a boolean property where a default value is given
   "width" : {type : "sap.ui.core.CSSSize", defaultValue : "50px"} // a CSS size property where a default value is given
}
```

After the property is defined, the control automatically has the `setShowLogoutButton` and `getShowLogoutButton` methods for storing data. It is possible to assign custom definitions to these methods by overriding them and calling the generic property methods `setProperty` and `getProperty`:

``` js
MyControl.prototype.setShowLogoutButton = function(show) {
	// …here anything in addition to the default handling can be done…
	// then do the default handling:
	this.setProperty("showLogoutButton", show); // this validates and stores the new value
	return this; // return "this" to allow method chaining
};

```

***

### Allowed Property Types

Built-in Types<a name="loioac56d92162ed47ff858fdf1ce26c18c4__table_gkp_kb2_2y"/>

|Type|Description|
|----|-----------|
| `boolean` |Can either be `true` or `false`. Properties of that type should not be set to `undefined` or `null`. The default value is `false`.|
| `int` |JavaScript primitive values of type `number` and that don’t have a fractional part. To keep the implementation efficient, the constraint is not enforced. Declaring a property as type `int` is rather for information reasons. The corresponding object expects any given value to be an integer value. The default value of the type is the number `0`.|
| `float` |JavaScript primitive values of type `number` that can have a fractional part. It is named `float` instead of `number` to differentiate it from type `int` . The default value is the number `0`.|
| `string` |JavaScript string literal \(`typeof value === ‚string’`\) or a `String` object \(`value instanceof String`\). The default value is an empty string.|
| `object` |Plain JavaScript object \(an object whose constructor is `Object`\). Most of the time, other objects are accepted as well, but deserializers \(e.g. for XML views\) will try to convert the object from or to a JSON string. The default value is `null`. Don't mix this type up with the `any` type! \(Sorry, we maybe should have named it „`serializable`“ or „`JSON`“ or something like that, to make this more clear...\).|
| `any` |Any valid Javascript value \(including primitives, objects, functions, regular expressions, and native objects\). The support in serialized formats is quite limited. Valid JSON strings will be deserialized to an object. The default value is `null`.|
| `function` |Can be any JavaScript function. Note that properties of this type currently can't be used in serialized formats like XMLViews. If an XMLView needs to set a value for a control property of type function, it has to set the value in its controller code \(e.g. in the `onInit` hook\).|

Derived Types<a name="loioac56d92162ed47ff858fdf1ce26c18c4__table_lbg_fc2_2y"/>

|Category|Description|
|--------|-----------|
|regular expression \(RegExp\)|Derived from the built-in type `string`. Restricted subtypes that limit their valid values to strings that match a given regular expression. `RegExp` types can only be defined by calling the `DataType.createType()` method. Example:

```
var fooType = DataType.createType('foo', {
    isValid : function(vValue) {
        return /^(foo(bar)?)$/.test(vValue);
    }
}, DataType.getType('string'));

```

 If `mSettings` contains an implementation for `isValid`, then the validity check of the newly created type will first execute the check of the base type and then call the given `isValid` function. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.base.DataType.html). |
|enumeration \(enum\)|Derived from the built-in type `string`. Restricted subtypes can be derived that limit their valid values to a fixed set of values \(enumeration\). An `enum` type is defined through an object literal whose keys represent the allowed values. Restrictions:

-   The value for each key must be a string literal, equal to the key itself.

-   Renamings or aliases are not supported and only keys and values of type `string` are supported.


This was an early design decision in OpenUI5 and framework code relies on it. That code might fail for enumerations that don’t obey these restrictions.

 To reference an `enum` type in a property definition, its global name must be used \(like `sap.m.ValueColor` in the example below\). . Example: ``` js
/**
* Enumeration of possible value color settings.
*
* @enum {string}
* @public
*/
sap.m.ValueColor = {

	/**
	* Neutral value color.
	* @public
	*/
	Neutral : "Neutral",

	[…]
};

```

 |
|array| You don't have to define array types before using an array. From each valid type above, an array type with one or more dimensions can be derived by simply appending a pair of square brackets \(`[]`\) for each dimension, for example:

-   `int[]` is a one-dimensional array of integers

-   `int[][]` is a two-dimensional array of integers \(or more precisely an array of integer arrays\)


The type of an element in an array is called the component type \(`int` in the first example, `int[]` in the second\).

 The `DataType` object for an array type has a method `getComponentType` to retrieve the component `type`. For non-array types, this method returns `null`. The default value for any array type is the empty array.|

***

### Runtime Behavior and API of Property Types

At runtime, each type is represented as instance of the class `DataType` \(`sap/ui/base/DataType.js`\). A type can be looked up by its name by calling `DataType.getType(name)`. The framework treats all values for the above types as if they would be atomic. Changes inside a value \(e.g. changing the property of a value of type `object` or adding, removing, or changing members of an array\) are not detected by the framework and might lead to unexpected results. Instead, any change should be applied by setting a new \(or modified\) value with a call like `setText`, `setCaption`, `setColor`.

**Related information**  


[API Reference: `sap.ui.base.DataType`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.base.DataType.html)

