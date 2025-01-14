---
title: Sticky Columns
page_title: jQuery Grid Documentation - Sticky Columns
description: "Get started with the jQuery Grid by Kendo UI supporting sticky columns that are scrollable, yet, visible at all times while the user scrolls the Grid horizontally."
slug: sticky_columns_kendoui_grid_widget
position: 3
---

# Sticky Columns

Sticky columns enable you to display specific columns at all times while the user scrolls the Grid horizontally. This specific column will be scrollable as well, however, it will fix its position to the left/right when it reaches left/right Grid border.

To configure a column as sticky simply set the `sticky` boolean setting of the corresponding column to `true`.

```
columns: [{
    field: "OrderID",
    title: "Order ID",
    sticky: true,
    width: 150
    }]
```

For a runnable example, refer to the demo on [implementing sticky columns in the Grid](https://demos.telerik.com/kendo-ui/grid/sticky-columns).


The following Grid configuration ensures that it will be possible to scroll columns horizontally to make the feature work. If there is not enough horizontal space for the scrollbar, it will not appear.
* Enable [scrolling](/controls/grid/scrolling/overview).
* [Stick columns initially](/api/javascript/ui/grid/configuration/columns.sticky) or [enable the stickable property](/api/javascript/ui/grid/configuration/columns.stickable) so users can stick column on the fly.
* Set a Grid height.
* Set explicit pixel widths to all columns to allow the Grid to adjust the layout of the sticky and non-sticky columns.
* Make sure that the Grid is not [initialized inside a hidden container](/controls/grid/appearance/hidden-containers).

The [JavaScript API of the Grid](/api/javascript/ui/grid) allows you to stick and unstick columns on the fly. However, this is possible only if the stickable configuration is enabled during initialization. If a certain column needs to be open for the users to change its position to sticky/non-sticky this must be specified in the column declaration.
```
columns: [{
    field: "OrderID",
    title: "Order ID",
    sticky: true,
    stickable: true,
    width: 150
    }]
```

## KB Articles on Grid Columns

* [Find Out More in the Knowledge Base](/knowledge-base)

## Known Limitations

* The sticky columns are not supported in Microsoft Internet Explorer. It is a browser limitation due to unsupported gutters.
* Sticky columns cannot work together with [column virtualization](https://demos.telerik.com/kendo-ui/grid/column-virtualization).
* A column cannot be both sticky and [locked](https://demos.telerik.com/kendo-ui/grid/frozen-columns). If it is defined like this, it will be locked and the sticky property will be ignored.
* Grid scrolling must be enabled.
* The header of the first column in a grouped Grid cannot be sticky.
* The autogenerated expand/collapse columns used by hierarchy and grouping cannot be sticky.
* [Row template](https://demos.telerik.com/kendo-ui/grid/rowtemplate) and [detail template](https://demos.telerik.com/kendo-ui/grid/detailtemplate) are not supported together with sticky columns. 
* If [multi-column headers](https://demos.telerik.com/kendo-ui/grid/multicolumnheaders) are used, only a column at the topmost level can be sticky. When the Grid uses Multi-column headers - the "Set Column Position" menu will not be visible.
* If the width of the Grid changes through JavaScript or resizing the page after the Grid is created, you have to call the [`resize` method](https://docs.telerik.com/kendo-ui/api/javascript/kendo/methods/resize) to recalculate the sticky styles.

## See Also

* [Implementing Sticky Columns in the Grid (Demo)](https://demos.telerik.com/kendo-ui/grid/sticky-columns)
* [Knowledge Base](/knowledge-base)
* [JavaScript API Reference of the Grid](/api/javascript/ui/grid)
