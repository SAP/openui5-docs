<!-- loio2c5c84d207d246bc9f733f29df1ff892 -->

## Working with Multiple Targets

If you want to navigate to multiple targets with the same hash, you can either assign multiple targets to a route, or define a parent for the target.



### Multiple Targets for the Same Route

In the routing configuration, you can add multiple targets for the same route.

All target view or component instances are created and loaded in the order that they appear in the target option of a route when the pattern is matched.

If you add multiple targets to a route, this builds a connection between the targets on the route level only. The targets can still be displayed separately if needed. Use this approach when the connection between the targets is only needed in some routes, but not always.



### Parent Relationship

You can also define a parent for a target in the target definition. For the parent, you also create an entry in the `targets` configuration, but you don't have to create a corresponding route.

Whenever a target has a parent, an instance of the parent is always created before an instance of the target is created.

A parent relationship between targets tightly couples the two targets together. The parent target is always displayed before the child target is displayed. The child target can't be displayed without first displaying the parent target. This approach is mainly used when the view in the child target is added to an aggregation of the view in the parent target.

> ### Note:  
> There is also a `parent` property for the `route`. This property is only used when its parent exists in a parent component of the current component \(see [Enabling Routing in Nested Components](enabling-routing-in-nested-components-fb19f50.md)\). For all other types of parent-child relationships, either use multiple targets or a parent relationship in targets.



## Example

In the following example, the relationship between the views `employeeOverviewTop` and `employeeOverviewContent` is established by assigning both to the same route.

The relationship between the target `employeeOverview` and `employeeOverviewTop` \(`employeeOverviewContent` respectively\) is a parent relationship.

```js

"routing": {
  "config": {
    path: "sap.ui.demo.nav.view.employee.overview",
    [...]
  },
  "routes": [{
    "pattern": "employees/overview",
    "name": "employeeOverview",
    "target": ["employeeOverviewTop", "employeeOverviewContent"]
  }],
  "targets": {
    "employeeOverview": {
      "type": "View",
      "name": "EmployeeOverview",
      "level": 2,
      "controlId": "app",
      "controlAggregation": "content"
    },
    "employeeOverviewTop": {
      "parent": "employeeOverview",
      "type": "View",
      "name": "EmployeeOverviewTop",
      "controlId": "EmployeeOverviewParent",
      "controlAggregation": "content"
    },
    "employeeOverviewContent": {
      "parent": "employeeOverview",
      "type": "View",
      "name": "EmployeeOverviewContent",
      "controlId": "EmployeeOverviewParent",
      "controlAggregation": "content"
    }
  }
```

For more information, see the tutorial [Step 11: Assign Multiple Targets](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/b01840ec42ef48e6bfd2bc12612f501f.html "In this step, we will add a new button to the home page to illustrate the usage of multiple targets for a route. When the button is pressed, a new page opens that contains two parts: a header part at the top and a content part. The content part displays a table of employees that can be sorted and searched. We will use the array notation in the routing configuration to assign multiple targets to a route - a feature that we have not yet introduced.") :arrow_upper_right:.

