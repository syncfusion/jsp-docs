---
layout: post
title: Multi-level Labels
description: multilevellabels
platform: jsp
control: PivotChart
documentation: ug
---

# Multi-level labels

Multi-level labels allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the expander present in the pivot chart.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 enableMultiLevelLabels="true">
		//...
		<ej:pivotChart-commonSeriesOptions type="column"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}


## Relational

![](MultiLevelLabels_images/relational.png)

## OLAP

![](MultiLevelLabels_images/olap.png)

