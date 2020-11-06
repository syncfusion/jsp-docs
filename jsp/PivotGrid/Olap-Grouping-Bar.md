---
layout: post
title: Grouping Bar
description: grouping bar
platform: jsp
control: PivotGrid
documentation: ug
---

# Grouping bar

## Initialization

Grouping bar allows you to dynamically alter the report by filter and remove operations in the pivot grid control. Based on the OLAP data source and report bound to the pivot grid control, the grouping bar will be automatically populated. You can enable this option in the pivot grid by setting the `enableGroupingBar` property to true.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" enableGroupingBar="true">
	//...
</ej:pivotGrid>
</div>

{% endhighlight %}

![](Grouping-Bar_images/OlapGroupingbar.png)

## Drag and drop

You can alter the report on fly through the drag and drop operation.

![](Grouping-Bar_images/GBar_Olap.png)

## Context menu

You can also alter the report by using the context menu.

![](Grouping-Bar_images/CMenu_Olap.png)

## Searching values

The search option available in the grouping bar allows you to search a specific value that should be filtered from the list of values in the filter pop-up window.

![](Grouping-Bar_images/OlapFilterIcon.png)

![](Grouping-Bar_images/olapclientsearching.png)

## Filtering values

The filtering option available in the grouping bar allows you to select a specific set of values that should be displayed in the pivot grid control. At least, one value should be present in checked state while filtering, otherwise, the OK button will be disabled.

![](Grouping-Bar_images/OlapFiltericon.png)

![](Grouping-Bar_images/OlapFiltering.png)

## Removing field

The remove option available in the grouping bar allows you to completely remove a specific field from the pivot grid control. The remove operation can be achieved by clicking the remove icon available in each field or by dragging and dropping the field out of the grouping bar region.

![](Grouping-Bar_images/OlapRemoveicon.png)

![](Grouping-Bar_images/OlapRemove.png) 

