---
layout: post
title: Legend | JSP | PivotChart | Syncfusion
description: This document illustrates that how to define legend and its functionalities in JSP PivotChart control
platform: jsp
control: PivotChart
documentation: ug
---

# Legend

## Legend visibility

You can enable or disable the legend by using the `visible` property in the `legend` object.

N> By default, the legend is visible in the pivot chart.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.legend.visible = true;
		}
	</script>

{% endhighlight %}

![Legend visibility in JSP pivot chart control](Legend_images/Legend_img1.png) 

## Legend shape
You can customize the legend `shape` in the pivot chart control. The default value of legend shape is rectangle. Following are the legend shapes that are supported:

* Rectangle
* Circle
* Cross
* Diamond
* Pentagon
* Hexagon
* Star
* Ellipse
* Triangle and so on.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.legend.visible = true;
			args.model.legend.shape = "star";
		}
	</script>

{% endhighlight %}

![Legend shape in JSP pivot chart control](Legend_images/Legend_img2.png) 

## Legend position
By using the `position` property, you can place the legend at top, bottom, left, or right of the pivot chart.

N> The default value of legend position is bottom in the pivot chart.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.legend.visible = true;
			args.model.legend.position = "top";
		}
	</script>

{% endhighlight %}

![Legend position in JSP pivot chart control](Legend_images/Legend_img3.png) 

## Legend title
To add the legend title, you should specify the title text in the `title.text` property.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.legend.visible = true;
			args.model.legend.title.text = "Countries";
		}
	</script>

{% endhighlight %}

![Legend title in JSP pivot chart control](Legend_images/Legend_img4.png) 

## Legend alignment
You can align the legend to center, far, and near based on its position in the chart area using the `alignment` option.
 
{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.legend.visible = true;
			args.model.legend.alignment = "near";
		}
	</script>

{% endhighlight %}

![Legend alignment in JSP pivot chart control](Legend_images/Legend_img5.png)

## Legend items - size and border
By using the legend `itemStyle.width`, `itemStyle.height`, and `itemStyle.border` properties, you can change the size and border of legend items.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.legend.visible = true;
			args.model.legend.itemStyle.border.color = "magenta";
			args.model.legend.itemStyle.border.width = 1.5;
			args.model.legend.height = 12;
			args.model.legend.width = 12;
		}
	</script>

{% endhighlight %}

![Size and border of legend in JSP pivot chart control](Legend_images/Legend_img6.png)
 
## Legend border
By using the `border` option in legend, you can customize the border color and width.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.legend.visible = true;
			args.model.legend.border.color = "#FFC342";
			args.model.legend.border.width = 2;
		}
	</script>

{% endhighlight %}

![Legend border in JSP pivot chart control](Legend_images/Legend_img7.png)

## Legend text
By using the `font` option, you can customize the font family, font style, font weight, and size of the legend text.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.legend.visible = true;
			args.model.legend.font.fontFamily = "Segoe UI";
			args.model.legend.font.fontWeight = "bold";
			args.model.legend.font.fontStyle = "italic";
		}
	</script>

{% endhighlight %}

![Legend text in JSP pivot chart control](Legend_images/Legend_img8.png)