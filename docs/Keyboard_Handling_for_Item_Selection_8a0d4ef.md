<!-- loio8a0d4efa29d44ef39219c18d832012da -->

| loio |
| -----|
| 8a0d4efa29d44ef39219c18d832012da |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8a0d4efa29d44ef39219c18d832012da) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8a0d4efa29d44ef39219c18d832012da)</div>

## Keyboard Handling for Item Selection

The following keys and key combinations are used for selecting one or multiple items from a list.

***

### Single Selection

|Key combination|Behavior|
|---------------|--------|
|*SPACE*|If focus is on an item, select the item and deselect all others.|

***

### Multi Selection

|Key combination|Behavior|
|---------------|--------|
|*SPACE*|If focus is on an item, select the item and deselect all others.|
|*CTRLSPACE*|If focus is on an item, select the item in addition to an existing selection..|
|*SHIFTSPACE*|If focus is on an item, select all items from the previous selected item to the now focused item \(included\). Previous selection: all kinds of selection except *SHIFT**SPACE* selections|
|*SHIFTUP*|If focus is on an item, change selection state \(selected/ not selected\) to the item above.|
|*SHIFTDOWN*|If focus is on an item, change selection state \(selected/ not selected\) to the item below.|
|*CTRLA*|Selects all items which the user can reach in the current view by scrolling or paging. If all items are selected, deselect all items.|

