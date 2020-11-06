---
layout: post
title: Advanced Filtering and Soritng | JSP | PivotGrid | Syncfusion
description: This document illustrates that how to define advance filtering and sorting with respective to the modes in JSP PivotGrid control
platform: jsp
control: PivotGrid
documentation: ug
---

# Advanced filtering and sorting

It allows to filter and sort the field members in the pivot grid.

You can enable the Advanced Filtering and Sorting option in the pivot grid by setting the `enableAdvancedFilter` property to true.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" enableAdvancedFilter="true" enableGroupingBar="true">
	//...
</ej:pivotGrid>
</div>

{% endhighlight %}

## Sorting

Sorting provides an option to sort the members of a field either in the ascending or descending order.

![Sorting options in JSP pivot grid control](AdvanceFiltering_images/sorting.png)

## Label filtering

Label filtering provides an option to filter the members of a field purely based on their caption. 

![Label filtering options in JSP pivot grid control](AdvanceFiltering_images/filtering.png)

![Label filter dialog in JSP pivot grid control](AdvanceFiltering_images/filtering_dialog.png)


## Value filtering

Value filtering provides an option to filter the members based on total values of the appropriate measure between members of the level.

![Value filtering options in JSP pivot grid control](AdvanceFiltering_images/valuefilter.png)

![Value filter dialog in JSP pivot grid control](AdvanceFiltering_images/valuefilter_dialog.png)
