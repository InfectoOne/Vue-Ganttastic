# API: GGanttRow
Represents a single row of the chart. It is meant to be a child component of `g-gantt-chart`.  

## Props
| Prop        | Type    | Default | Description                  |
|-------------|---------|---------|------------------------------|
| `label`     |`string?`| `""`    | Text that is floating in the upper left corner of the row.
| `bars`      |`GanttBarObject[]`|  | Array of objects, each representing a bar in this row. Any JavaScript/TypeScript object with a nested `ganttBarConfig` object with a unique `id` string property is compatible. The objects must also contain two properties which represent the start and end datetime of the bar. The names of those properties must be passed  to the `bar-start` and `bar-end` props of the `g-gantt-chart` parent.
| `highlight-on-hover` | `boolean?` | `false` | Used for toggling a background color transition effect on mouse hover.
| `disableDragging` | `boolean?` | `false` | Used to disable dragging on a per-row basis. You can still disable dragging on a per-bar basis by setting `immobile` in the `GanttBarConfig` object of your bar object. Note that bar bundles ignore the immobile flag. If you drag an immobile bar in a bundle, the dragging will be prevented. If you drag a mobile bar in the same bundle, the immobile bars will also move. You can disable dragging entirely by setting `disableDragging` at the Chart level.
  
## Custom Events
| Event name                 | Event data                                                 |
|----------------------------|------------------------------------------------------------|
| `drop`                     | `{ e: MouseEvent, datetime: string}`                       |


## Slots
| Slot name                  | Slot data             | Description                             |
|----------------------------|-----------------------| ----------------------------------------|
| `label`           |   | Used for modifying the text that is floating in the upper left corner of the row. |
| `bar-label`        |  `{bar: GanttBarObject}` | Used for modifying the text in a bar. |