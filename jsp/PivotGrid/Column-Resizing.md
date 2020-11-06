---
layout: post
title:  Column Resizing | JSP | PivotGrid | Syncfusion
description: This document illustrates that how to enable column resizing feature and its customization through API in JSP PivotGrid control
platform: jsp
control: PivotGrid
documentation: ug
---

# Resizing column

Allows you to change the column width by holding and dragging the column border using the mouse pointer.

## Column width based on size

The `enableColumnResizing` property adjusts the width of each column based on size of the widget.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" enableColumnResizing="true">
	//...
</ej:pivotGrid>
</div>

{% endhighlight %}

## Column width based on text

The `resizeColumnsToFit` property automatically adjusts the width of each column based on the maximum content length available in the respective column.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" resizeColumnsToFit="true">
	//...
</ej:pivotGrid>
</div>

{% endhighlight %}

![Column resizing in JSP pivot grid control](Column-Resizing_images/columnresizing.png)