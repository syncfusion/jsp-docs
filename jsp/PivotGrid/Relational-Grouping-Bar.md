---
layout: post
title: Grouping Bar | JSP | PivotGrid | Syncfusion
description: This document illustrates that how to enable grouping bar feature and its functionalities in JSP PivotGrid control with relational mode
platform: jsp
control: PivotGrid
documentation: ug
---

# Grouping bar

## Initialization

Grouping bar allows you to dynamically alter the report by filter, sort, and  remove operations in the pivot grid control. Based on the relational data source and report bound to the pivot grid control, the grouping bar will be automatically populated. You can enable this option in the pivot grid by setting the `enableGroupingBar` property to true.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" enableGroupingBar="true">
	//...
</ej:pivotGrid>
</div>

{% endhighlight %}

![Grouping bar support in JSP pivot grid control with relational client mode](Grouping-Bar_images/realtionalclientGB.png)

## Drag and drop

You can alter the report on fly through the drag and drop operation.

![Drag and drop in JSP pivot grid control](Grouping-Bar_images/GBar_Rel.png)

## Context menu

You can alter the report by using the context menu.

![Context menu in JSP pivot grid control](Grouping-Bar_images/CMenu_Rel.png)

## Searching values

The search option available in the grouping bar allows you to search a specific value that should be filtered from the list of values in the filter pop-up window.

![Member editor dialog in JSP pivot grid control](Grouping-Bar_images/filter.png)

![Searching in JSP pivot grid control](Grouping-Bar_images/groupingbar-search.png)

## Filtering values

The filtering option available in the grouping bar allows you to select a specific set of values that should be displayed in the pivot grid control. At least, one value should be present in checked state while filtering, otherwise, the OK button will be disabled.

![Member editor in JSP pivot grid control](Grouping-Bar_images/FILTER.png)

![Filtering in JSP pivot grid control](Grouping-Bar_images/FILTER1.png)

## Sorting values

The sorting option available in the grouping bar allows you to arrange headers in the ascending or descending order. This option is applicable for fields available only in the row and column region. By default, headers are sorted in the ascending order. In the sorting indicator, up arrow denotes the ascending order and down arrow denotes the descending order.

![Sorting icon in JSP pivot grid control](Grouping-Bar_images/sort.png)

![Sorted results in JSP pivot grid control](Grouping-Bar_images/sort-grid.png)

## Removing field

The remove option available in the grouping bar allows you to completely remove a specific field from the pivot grid control. The remove operation can be achieved by clicking remove icon available in each field or by dragging and dropping field out of the grouping bar region.

![Remove icon in JSP pivot grid control](Grouping-Bar_images/remove.png)

![Removed items in JSP pivot grid control](Grouping-Bar_images/remove-grid.png) 

