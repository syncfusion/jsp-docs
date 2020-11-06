---
layout: post
title: Named Set
description: named set
platform: jsp
control: PivotGrid
documentation: ug
---

# Named set

The named set is a multidimensional expression (MDX) that returns a set of dimension members that can be created by combining cube data, arithmetic operators, numbers, and functions.

You can bind the named sets in the pivot grid by setting it's unique name in the `fieldName` property in the row or column axis and `isNamedSets` Boolean property to true.

{% highlight html %}

<ej:pivotGrid id="PivotGrid1">
<ej:pivotGrid-dataSource catalog="Adventure Works DW 2008 SE" cube="Adventure Works" data="//bi.syncfusion.com/olap/msmdpump.dll">
<ej:pivotGrid-dataSource-rows>
<ej:pivotGrid-dataSource-row fieldName="[Date].[Fiscal]"></ej:pivotGrid-dataSource-row>
</ej:pivotGrid-dataSource-rows>
<ej:pivotGrid-dataSource-columns>
<ej:pivotGrid-dataSource-column fieldName="[Core Product Group]" isNamedSets="true"></ej:pivotGrid-dataSource-column>
</ej:pivotGrid-dataSource-columns>
<ej:pivotGrid-dataSource-values>
<ej:pivotGrid-dataSource-value axis="columns">
<ej:pivotGrid-dataSource-value-measures>
<ej:pivotGrid-dataSource-value-measure fieldName="[Measures].[Internet Sales Amount]"></ej:pivotGrid-dataSource-value-measure>
</ej:pivotGrid-dataSource-value-measures>
</ej:pivotGrid-dataSource-value></ej:pivotGrid-dataSource-values>
</ej:pivotGrid-dataSource>
</ej:pivotGrid>

{% endhighlight %}

![](KPI_images/namedset.png)
