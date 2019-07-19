<!-- loiob59f13d3586c4196b28e92683e9dff19 -->

| loio |
| -----|
| b59f13d3586c4196b28e92683e9dff19 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b59f13d3586c4196b28e92683e9dff19) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b59f13d3586c4196b28e92683e9dff19)</div>

## Keyboard Handling for Basic Navigation

The following keys and key combinations are used for navigation between controls within an application.

***

### Standard Navigation

Navigation between controls is done using the *TAB* key. *TAB* moves the focus from one control to the next one inside the application. The tab order is defined by the placement of the control within the DOM tree, therefore apps have a large influence on it.

> Note:
> Controls are in the tab order, if they are interactive, enabled and visible. This includes read-only controls. Disabled or hidden controls are taken out of the tab order. Non-interactive controls \(for example, layout container\) can never be reached with *TAB*.
> 
> 

|Key combination|Behavior|
|---------------|--------|
|*TAB*|Forward Navigation: On enter, move focus to the control.On leave, move focus to the next control in the application.|
|* SHIFT TAB *|Backward Navigation: On enter, move focus to the control.On leave, move focus to the previous control in the tab order.|

***

### Group Navigation

Controls which are adjacent within the application can be grouped. Within a group, *F6* skips all controls of the group and moves the focus to the first control in the application within the **next** group. * SHIFT F6 * moves the focus to the first control of the **previous** group.

|Key combination|Behavior|
|---------------|--------|
|*F6*|Forward Navigation: Move focus to the next control in the tab order after the group|
|* SHIFT F6 *|Backward Navigation: Move focus to the previous control in the tab order before the group|

