---
title: Getting Started for React JS PivotChart
description: How to create a PivotChart with data source.
platform: JSP
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, jsp pivotchart
---

# Getting started

This section explains how to populate the pivot chart in your application with **JSP** wrapper classes of EJ controls. This section covers only the minimal features that are needed to get started with the pivot chart.


## Create pivot chart widget

You can create a JSP application and add necessary scripts and styles with the help of the given [JSP Getting Started Documentation.](/jsp/Getting-Started)

Refer to the required scripts and CSS files in your JSP page as mentioned below to render the pivot chart control:

{% highlight html %}

	<!DOCTYPE html>
	<html>
		<head>
			<title>Getting Started - PivotChart</title>
			<link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
			<link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css" rel="stylesheet" />
			<script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
			<script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
			<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
		</head>
	</html>

{% endhighlight %}

## Relational

Add the following code example to add list of items to the **pivot chart** and initialize the **pivot chart** widget with relational data source.

{% highlight html %}

	<div>
	<ej:pivotChart id="PivotChart1" isResponsive="true" load="onLoad">
	<ej:pivotChart-dataSource>
	<ej:pivotChart-dataSource-rows>
	<ej:pivotChart-dataSource-row fieldName="Country" fieldCaption="Country"></ej:pivotChart-dataSource-row>
	</ej:pivotChart-dataSource-rows>
	<ej:pivotChart-dataSource-columns>
	<ej:pivotChart-dataSource-column fieldName="Product" fieldCaption="Product"></ej:pivotChart-dataSource-column>
	</ej:pivotChart-dataSource-columns>
	<ej:pivotChart-dataSource-values>
	<ej:pivotChart-dataSource-value fieldName="Amount" fieldCaption="Amount"></ej:pivotChart-dataSource-value>
	</ej:pivotChart-dataSource-values>
	</ej:pivotChart-dataSource>
	<ej:pivotChart-commonSeriesOptions type="column"></ej:pivotChart-commonSeriesOptions>
	</ej:pivotChart>
	</div>

	<script type="text/javascript">
    function onLoad(args) {
        args.model.dataSource.data = [
	                    { Amount: 100, Country: "Canada", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Alberta" },
	                    { Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Van", Quantity: 3, State: "British Columbia" },
	                    { Amount: 300, Country: "Canada", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Brunswick" },
	                    { Amount: 150, Country: "Canada", Date: "FY 2008", Product: "Bike", Quantity: 3, State: "Manitoba" },
	                    { Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Car", Quantity: 4, State: "Ontario" },
	                    { Amount: 100, Country: "Canada", Date: "FY 2007", Product: "Van", Quantity: 1, State: "Quebec" },
	                    { Amount: 200, Country: "France", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Charente-Maritime" },
	                    { Amount: 250, Country: "France", Date: "FY 2006", Product: "Van", Quantity: 4, State: "Essonne" },
	                    { Amount: 300, Country: "France", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Garonne (Haute)" },
	                    { Amount: 150, Country: "France", Date: "FY 2008", Product: "Van", Quantity: 2, State: "Gers" },
	                    { Amount: 200, Country: "Germany", Date: "FY 2006", Product: "Van", Quantity: 3, State: "Bayern" },
	                    { Amount: 250, Country: "Germany", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Brandenburg" },
	                    { Amount: 150, Country: "Germany", Date: "FY 2008", Product: "Car", Quantity: 4, State: "Hamburg" },
	                    { Amount: 200, Country: "Germany", Date: "FY 2008", Product: "Bike", Quantity: 4, State: "Hessen" },
	                    { Amount: 150, Country: "Germany", Date: "FY 2007", Product: "Van", Quantity: 3, State: "Nordrhein-Westfalen" },
	                    { Amount: 100, Country: "Germany", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Saarland" },
	                    { Amount: 150, Country: "United Kingdom", Date: "FY 2008", Product: "Bike", Quantity: 5, State: "England" },
	                    { Amount: 250, Country: "United States", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Alabama" },
	                    { Amount: 200, Country: "United States", Date: "FY 2005", Product: "Van", Quantity: 4, State: "California" },
	                    { Amount: 100, Country: "United States", Date: "FY 2006", Product: "Bike", Quantity: 2, State: "Colorado" },
	                    { Amount: 150, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "New Mexico" },
	                    { Amount: 200, Country: "United States", Date: "FY 2005", Product: "Bike", Quantity: 4, State: "New York" },
	                    { Amount: 250, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "North Carolina" },
	                    { Amount: 300, Country: "United States", Date: "FY 2007", Product: "Van", Quantity: 4, State: "South Carolina" }
	    ];
        args.model.commonSeriesOptions.enableAnimation = true;
        args.model.commonSeriesOptions.tooltip.visible = true;
        args.model.primaryYAxis.title.text = "Amount";
		args.model.size.height = "450px";
		args.model.size.width = "100%";
		args.model.zooming.enableScrollbar = true;
    }
	</script>

{% endhighlight %}

The above code will generate a simple pivot chart with sales amount over products in different regions.

![](Getting-Started_images/relational_default.png)

## OLAP

Add the following code example to add list of items to the **pivot chart** and initialize the **pivot chart** widget with OLAP data source.

{% highlight html %}

	<div class="cols-sample-area">
	<ej:pivotChart id="PivotChart1" isResponsive="true" load="onLoad">
	<ej:pivotChart-dataSource data="//bi.syncfusion.com/olap/msmdpump.dll" catalog="Adventure Works DW 2008 SE" cube="Adventure Works">
	<ej:pivotChart-dataSource-rows>
	<ej:pivotChart-dataSource-row fieldName="[Date].[Fiscal]"></ej:pivotChart-dataSource-row>
	</ej:pivotChart-dataSource-rows>
	<ej:pivotChart-dataSource-columns>
	<ej:pivotChart-dataSource-column fieldName="[Customer].[Customer Geography]"></ej:pivotChart-dataSource-column>
	</ej:pivotChart-dataSource-columns>
	<ej:pivotChart-dataSource-values>
	<ej:pivotChart-dataSource-value axis="columns">
	<ej:pivotChart-dataSource-value-measures>
	<ej:pivotChart-dataSource-value-measure fieldName="[Measures].[Internet Sales Amount]"></ej:pivotChart-dataSource-value-measure>
	</ej:pivotChart-dataSource-value-measures>
	</ej:pivotChart-dataSource-value>
	</ej:pivotChart-dataSource-values>
	</ej:pivotChart-dataSource>
	<ej:pivotChart-commonSeriesOptions type="column"></ej:pivotChart-commonSeriesOptions>
	</ej:pivotChart>
	</div>

	<script type="text/javascript">
    function onLoad(args) {
        args.model.commonSeriesOptions.enableAnimation = true;
        args.model.commonSeriesOptions.tooltip.visible = true;
        args.model.primaryYAxis.title.text = "Internet Sales Amount";     
		args.model.size.height = "450px";
		args.model.size.width = "100%";
		args.model.zooming.enableScrollbar = true;
    }
</script>

{% endhighlight %}

The above code will generate a simple pivot chart with internet sales amount over a period of fiscal years across different customer geographic locations.

![](Getting-Started_images/olap_default.png)