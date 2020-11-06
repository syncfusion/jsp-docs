---
layout: post
title: Paging | JSP | PivotGrid | Syncfusion
description: This document illustrates that how to define paging with respective to the modes in JSP PivotGrid control
platform: jsp
control: PivotGrid
documentation: ug
---

# Paging

## Pager 

Paging helps to improve the rendering performance of the pivot grid control by dividing a large amount of data into several sections and displaying one section at a time. You can enable the paging option in the pivot grid by setting the `enablePaging` property to true. You can provide the page size and current page details for each axis in the `pagerOptions` property.

You should initialize the widget using the **ejPivotPager** tag. In the **ejPivotPager** tag, the enumeration property mode should be set to **ej.PivotPager.Mode.Both** to display both categorical pager and series pager. The other enumerations such as **ej.PivotPager.Mode.Categorical** and **ej.PivotPager.Mode.Series** will display only the categorical pager and series pager respectively.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" load="onLoad" enablePaging="true">
	//...
</ej:pivotGrid>
<ej:pivotPager id="PivotPager" mode="both" targetControlID="PivotGrid1"></ej:pivotPager>
</div>
<script type="text/javascript">

    function onLoad(args) {
		args.model.dataSource.pagerOptions= {
                                    categoricalPageSize: 5,
                                    seriesPageSize: 5,
                                    categoricalCurrentPage: 1,
                                    seriesCurrentPage: 1
                                };
	}
</script>

{% endhighlight %} 

Following are the navigation options available in the pager:

* Move first: Navigates to the first page.
* Move last: Navigates to the last page. 
* Move previous: Navigates to the previous page from the current page.
* Move next: Navigates to the next page from the current page.
* Numeric box: Navigates to the desired page by entering an appropriate page number in the numeric value.

![Paging in JSP pivot grid control](Paging_images/paging.png)


## Virtual scrolling

Virtual scrolling is a technique that allows you to view the pivot grid information page by page with the use of vertical and horizontal scrollbars. You can enable the virtual scrolling option in the pivot grid by setting the `enableVirtualScrolling` property to true. You can provide the page size and current page details for each axis in the `pagerOptions` property.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" load="onLoad" enableVirtualScrolling="true">
	//...
</ej:pivotGrid>
</div>
<script type="text/javascript">

    function onLoad(args) {
		args.model.dataSource.pagerOptions= {
                                    categoricalPageSize: 5,
                                    seriesPageSize: 5,
                                    categoricalCurrentPage: 1,
                                    seriesCurrentPage: 1
                                };
	}
</script>

{% endhighlight %} 

![Virtual scrolling in JSP pivot grid control](Paging_images/virtual-scrolling.png)

## Page settings

The properties associated to paging are:

* enablePaging: Enables/disables paging in the pivot client control.
* pagerOptions.categoricalPageSize: Specifies the number of categorical columns to be displayed within a page of the pivot client control.
* pagerOptions.seriesPageSize: Specifies the number of series rows to be displayed within a page of the pivot client control.
* pagerOptions.categoricalCurrentPage: Sets the current page of the categorical axis in the pivot client control.
* pagerOptions.seriesCurrentPage: Sets the current page of the series axis in the pivot client control.

Page setting for categorical and series axes should be set in the data source property by using the following properties:

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" load="onLoad" enablePaging="true">
	//...
</ej:pivotGrid>
<ej:pivotPager id="PivotPager" mode="both" targetControlID="PivotGrid1"></ej:pivotPager>
</div>
<script type="text/javascript">

    function onLoad(args) {
		args.model.dataSource.pagerOptions= {
                                    categoricalPageSize: 5,
                                    seriesPageSize: 5,
                                    categoricalCurrentPage: 1,
                                    seriesCurrentPage: 1
                                };
	}
</script>

{% endhighlight %} 