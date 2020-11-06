---
layout: post
title: Cell Editing | JSP | PivotGrid | Syncfusion
description: This document illustrates that how to enable cell editing feature through API in JSP PivotGrid control
platform: jsp
control: PivotGrid
documentation: ug
---

# Cell editing

I> This feature is applicable only for the relational data source.

Cell editing allows you to edit and alter the values in the pivot grid. The summary values will be recreated based on edited values. By selecting multiple cells (like in cell selection feature), you can edit multiple cells at the same time.
  
You can enable cell editing option in the pivot grid by setting the `enableCellEditing` property to true.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" enableCellEditing="true">
	//...
</ej:pivotGrid>
</div>

{% endhighlight %}

![Cell editing in JSP pivot grid control](Cell-Editing_images/celleditingclient.png)


