| loio |
| -----|
| 85738e3ac3bb407d9e1cfeb8bb9268cb |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/85738e3ac3bb407d9e1cfeb8bb9268cb.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/85738e3ac3bb407d9e1cfeb8bb9268cb) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/85738e3ac3bb407d9e1cfeb8bb9268cb)</div>
<!-- loio85738e3ac3bb407d9e1cfeb8bb9268cb -->

## Normal Methods

Normal or public methods comprise all methods that do not belong to one of the special method types.

All methods are appended to the implementation object. Private methods are identified by a name starting with an underscore and must **not** be called from outside the control. The following code snippet is an example for the public method `divide` that calls the private helper method `_checkForZero` within the control:

```lang-js

  divide: function(x, y) {     // a public method of the Control

      if (this._checkForZero(y)) {

         throw new Error("Second parameter may not be zero");

      }

      return x / y;

   },



   _checkForZero: function(y) { // private helper method

      if (y === 0) {

         return true;

      }

      return false;

   }
```

