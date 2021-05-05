<!-- loioe3038209d0e94f4487531956a60ef457 -->

| loio |
| -----|
| e3038209d0e94f4487531956a60ef457 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e3038209d0e94f4487531956a60ef457) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e3038209d0e94f4487531956a60ef457)</div>

## Keyboard Handling

Keyboard handling enables users to access every UI element of the application with the keyboard and is therefore tightly connected to accessibility. Additionally, this aspect is coupled to the screen reader functionality.

***

### General Recommendations

**Accessibility of UI elements**

Make sure that all available features of the application can be accessed by using only the keyboard - [TAB\], arrows, [ENTER\], and [SPACE\]. The user should be able to activate the functionality of **all** active elements.

**Tab order and reading order**

> ### Example:  
> When you have to select a country and city from select boxes, the country should be focused first and after that the city.

***

### Tips for Testing

Start the application and put away your mouse.

-   Can you reach every active screen element just by using the keyboard?

    -   Is this true also for dynamically created texts or control elements?

-   Can you navigate within control elements \(for example, list, table, tabstrip\) using arrow keys?

-   Can you also navigate away from each UI element using the keyboard?

-   Does the visible focus follow the exact keyboard commands? Is it always identifiable and in the visible area?

-   Can you execute all actions? \(Compare with what you can do with the mouse\)


