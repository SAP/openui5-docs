| loio |
| -----|
| 6ec0a7e1d3c64412a673b7dabe28c02b |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/6ec0a7e1d3c64412a673b7dabe28c02b.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/6ec0a7e1d3c64412a673b7dabe28c02b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/6ec0a7e1d3c64412a673b7dabe28c02b)</div>
<!-- loio6ec0a7e1d3c64412a673b7dabe28c02b -->

## Events Fired Centrally by the App or the NavContainer

When `NavContainer.to(…)` or `NavContainer.back(…)` are called, the `NavContainer` triggers events and the application can register for this events. The `navigate` event is fired before the transition animation starts, and the `afterNavigate` event is fired when the animation has been completed.

The events contain a lot of information about the page that is left and the target page of the navigation, as well as what kind of navigation is happening.

Example:

```lang-js

app.attachNavigate(function(evt) {
   var isBack = !evt.getParameter("isTo"); // there are several types of back animation, but we want the general direction only
   alert("Navigating " + (isBack ? "back " : "") + " to page " + evt.getParameter("toId"));
});
```

***

### API References

-   [event:afterNavigate](https://openui5.hana.ondemand.com/#/api/sap.m.NavContainer/events/afterNavigate)
-   [event:navigate](https://openui5.hana.ondemand.com/#/api/sap.m.NavContainer/events/navigate)

