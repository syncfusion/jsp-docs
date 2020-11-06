---
layout: post
title: Named Set
description: named set
platform: jsp
control: PivotTreeMap
documentation: ug
---

# Named sets

Named sets is a multidimensional expression (MDX) that returns a set of dimension members that can be created by combining cube data, arithmetic operators, numbers, and functions.

You can bind the named sets in the pivot tree map by setting it's unique name in the `fieldName` property in the row or column axis and `isNamedSets` Boolean property to true.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotTreeMap id="PivotTreeMap1">
<ej:pivotTreeMap-dataSource catalog="Adventure Works DW 2008 SE" cube="Adventure Works" data="//bi.syncfusion.com/olap/msmdpump.dll">
<ej:pivotTreeMap-dataSource-rowCollections>
<ej:pivotTreeMap-dataSource-rows fieldName="[Core Product Group]" isNamedSets="true"></ej:pivotTreeMap-dataSource-rows>
</ej:pivotTreeMap-dataSource-rowCollections>
<ej:pivotTreeMap-dataSource-columnCollections>
<ej:pivotTreeMap-dataSource-columns fieldName="[Customer].[Customer Geography]"></ej:pivotTreeMap-dataSource-columns>
</ej:pivotTreeMap-dataSource-columnCollections>
<ej:pivotTreeMap-dataSource-valueCollections>
<ej:pivotTreeMap-dataSource-values axis="columns">
<ej:pivotTreeMap-dataSource-values-measureCollections>
<ej:pivotTreeMap-dataSource-values-measure fieldName="[Measures].[Internet Sales Amount]"></ej:pivotTreeMap-dataSource-values-measure>
</ej:pivotTreeMap-dataSource-values-measureCollections>
</ej:pivotTreeMap-dataSource-values>
</ej:pivotTreeMap-dataSource-valueCollections>
</ej:pivotTreeMap-dataSource>
</ej:pivotTreeMap>
</div>
<script id="tooltipTemplate" type="application/jsrender">
	<div style="background:White; color:black; font-size:12px; font-weight:normal; border: 1px solid #4D4D4D; white-space: nowrap;border-radius: 2px; margin-right: 25px; min-width: 110px;padding-right: 5px; padding-left: 5px; padding-bottom: 2px ;width: auto; height: auto;">
		<div>Measure(s) : {{:~Measures(#data)}}</div><div>Row : {{:~Row(#data)}}</div><div>Column : {{:~Column(#data)}}</div><div>Value : {{:~Value(#data)}}</div>
	</div>
</script> 

{% endhighlight %}

![](NamedSets_images/namedset.png)

