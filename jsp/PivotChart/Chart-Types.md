---
layout: post
title: Chart Types | JSP | PivotChart | Syncfusion
description: This document illustrates that how to define chart types and its customization in JSP PivotChart control
platform: jsp
control: PivotChart
documentation: ug
---

# Chart types

The Essential **PivotChart JSP** supports 17 types of charts:

* Column
* Stacking column
* Bar
* Stacking bar
* Pie
* Pyramid
* Funnel
* Line
* Step line
* Spline
* Area
* Step area
* Spline area
* Stacking area
* Doughnut
* Scatter
* Bubble

## Column chart

The **column chart** is the most commonly used chart type. This uses vertical bars (called columns) to display different values of one or more items. Points from adjacent series are drawn as bars to compare frequency, count, total, or average of data in different categories. Column chart is ideal to show the variations in the value of an item over a period of time.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="column"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **column chart**:

![JSP column chart control](Chart-Types_images/Chart-Types_img1.png)

Column chart
{:.caption}

## Stacking column chart

The **stacking column** chart is similar to the column chart except for the Y-values. The Y-values stack on top of each other in a specified series order. This helps to visualize the relationship of parts to the whole chart across various categories.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="stackingColumn"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **stacking column chart**:


![JSP stacking column chart control](Chart-Types_images/Chart-Types_img2.png) 

Stacking Column Chart
{:.caption}

## Bar chart

The **bar chart** displays horizontal bars for each point in the adjacent series. Bar charts are used to compare values across various categories for displaying the variations in the value of an item over a period of time or comparing the values of several items at a single point of time.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		<ej:pivotChart-commonSeriesOptions type="bar"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.primaryXAxis.labelRotation = 0;
		}
	</script>

{% endhighlight %}

The following screenshot displays **bar chart**:

![JSP bar chart control](Chart-Types_images/Chart-Types_img3.png) 

Bar Chart
{:.caption}

## Stacking bar chart

The **stacking bar chart** is a regular **bar** chart with X-values stacked on top of each other in the specified series order.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		<ej:pivotChart-commonSeriesOptions type="stackingBar"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.primaryXAxis.labelRotation = 0;
		}
	</script>

{% endhighlight %}

The following screenshot displays **stacking bar chart**:

![JSP stacking bar chart control](Chart-Types_images/Chart-Types_img4.png) 

Stacking Bar Chart
{:.caption}

## Pie chart

The **pie chart** is used to summarize a set of categorical data or display different values of a given variable (e.g., percentage distribution). This type of chart is in a circular form that is divided into several segments. Each segment represents a particular category.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="pie"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **pie chart**:

![JSP pie chart control](Chart-Types_images/pie.png) 

Pie Chart
{:.caption}

## Pyramid chart

The **pyramid chart** displays data in the form of a triangle. You can visualize data in a hierarchical structure without any axes.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="pyramid"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **pyramid chart**:


![JSP pyramid chart control](Chart-Types_images/pyramid.png)

Pyramid Chart
{:.caption}


## Funnel chart

The **funnel chart** displays data in the form of an inverted triangle. You can visualize data in a hierarchical structure without any axes.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="funnel"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>
	</script>

{% endhighlight %}

The following screenshot displays **funnel chart**:


![JSP funnel chart control](Chart-Types_images/funnel.png)

Funnel Chart
{:.caption}

## Line chart

The **line chart** joins the data points on a plot by using straight lines that show the trends in data at equal intervals.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="line"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **line chart**:

![JSP line chart control](Chart-Types_images/Chart-Types_img7.png) 

Line Chart
{:.caption}

## Step line chart

The **step line chart** uses horizontal and vertical lines to connect data points resulting in a step like progression. 

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="stepLine"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays the **step line chart**:

![JSP step line chart control](Chart-Types_images/Chart-Types_img8.png) 

Step Line Chart
{:.caption}

## Spline chart

The **spline chart** is similar to the line chart except that it connects different data points with curve lines instead of straight lines.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="spline"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **spline chart**:

![JSP spline chart control](Chart-Types_images/Chart-Types_img9.png) 

Spline Chart
{:.caption}

## Area chart

The **area chart** emphasizes the degree of change of values over a period of time. Instead of rendering data as discrete bars or columns, the area chart renders the continuous ebb-and-flow pattern as defined against the Y-axis.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="area"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **area chart**:

![JSP area chart control](Chart-Types_images/Chart-Types_img10.png) 

Area Chart
{:.caption}

## Step area chart

The **step area** chart is similar to the regular area chart except for a straight line tracing the shortest path between the data points. The values are connected by continuous vertical and horizontal lines to form a step like progression.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="stepArea"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **step area chart**:

![JSP step area chart control](Chart-Types_images/Chart-Types_img11.png) 

Step Area Chart
{:.caption}

## Spline area chart

The **spline area** chart is similar to the area chart but differs by connecting data points in a series. This connects each series of points by a smooth **spline curve**.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="splineArea"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **spline area chart**:

![JSP spline area chart control](Chart-Types_images/Chart-Types_img12.png) 

Spline Area Chart
{:.caption}

## Stacking area chart

The **stacking area** chart is similar to the regular area chart except for the Y-values. The Y-values stack on top of each other in the specified series order. This helps to visualize the relationship of parts to the whole chart across various categories.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="stackingArea"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **stacking area chart**:

![JSP stacking area chart control](Chart-Types_images/Chart-Types_img13.png) 

Stacking Area Chart
{:.caption}

## Doughnut chart

The **doughnut chart** is a doughnut like structure used to summarize a set of categorical data that is divided into several segments. Each segment represents a particular category.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="doughnut"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **doughnut chart**:

![JSP doughnut chart control](Chart-Types_images/DoughnutChart.png)

Doughnut Chart
{:.caption}

## Scatter chart

The **scatter chart** displays data as a collection of points corresponding to the associated values.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="scatter"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **scatter chart**:

![JSP scatter chart control](Chart-Types_images/ScatterChart.png) 

Scatter Chart
{:.caption}

## Bubble chart

The **bubble chart** displays data as a collection of bubbles.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		<ej:pivotChart-commonSeriesOptions type="bubble"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>

{% endhighlight %}

The following screenshot displays **bubble chart**:

![JSP bubble chart control](Chart-Types_images/BubbleChart.png)

Bubble Chart
{:.caption}

## Combination chart

The **combination chart** combines two or more series types in a single chart, but there are some limitations in the combination chart. They are:

1. The combination chart cannot combine column and bar series.
2. The pie chart cannot be used with other series types.



{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		<ej:pivotChart-commonSeriesOptions type="column"></ej:pivotChart-commonSeriesOptions>
		</ej:pivotChart
	</div>	
    
	<script>
		function onLoad(args) {
			//...
			args.model.seriesRendering = function(){
				args.model.series[5].type = "line";
				args.model.series[5].marker.visible = true;
			}
		}
	</script>

{% endhighlight %}

The following screenshot displays **combination chart**:

![JSP combination of charts](Chart-Types_images/combinationalchart.png)
