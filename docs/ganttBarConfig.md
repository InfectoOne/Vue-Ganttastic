# ganttBarConfig type
The ganttBarConfig object allows customization of the bar objects and how they behave.

You can add new properties as you wish, but the following properties already exist, and will change how your bars behave.

## Properties
| Property | Type | Description |
| -------- | ---- | ----------- |
| `id` | string | An identifier for the bar |
| `label` | string? | The label for the bar. Can also be shown in the bar's tooltip if you set the `showLabelAsTooltipTitle` prop on the GGanttChart. Make sure to sanitize the value. |
| `subtitle` | string? | If set, this will be appended to the tooltip. Make sure to sanitize the value. |
| `html` | string? | Will render HTML immediately next to the label. Make sure to sanitize the value. |
| `hasHandles` | boolean? | Toggles the bars drag handles allowing user to adjust start and end times independently. |
| `immobile` | boolean? | Toggle an individual bar's ability to be dragged. Note that if an immobile bar is in a bundle with a mobile bar, dragging the mobile bar will also move the immobile bar. Immobile disables direct user interaction. |
| `bundle` | string? | Group bars together such that dragging any bar in the same bundle will also move all other bars in that bundle. |
| `pushOnOverlap` | boolean? | Prevents bars from overlapping each other by pushing other bars that would overlap out of the way. |
| `dragLimitLeft` | number? | |
| `dragLimitRight` | number? | |
| `style` | Object<CSSProperties> | The style for each bar. |
| `class` | string? | The class to be applied to each bar. |