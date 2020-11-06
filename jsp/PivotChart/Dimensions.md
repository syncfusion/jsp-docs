---
layout: post
title: Dimensions
description: dimensions
platform: jsp
control: PivotChart
documentation: ug
---

# Dimensions

## Set size in percentage

You can customize the pivot chart dimension by setting the width and height of the control in percentage.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.size.height = "80%";
			args.model.size.width = "80%";
		}
	</script>

{% endhighlight %}

## Set size in pixels

You can customize the pivot chart dimension by setting the width and height of the control in pixels.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1" load="onLoad">
		//...
		</ej:pivotChart
	</div>
	<script type="text/javascript">
		function onLoad(args) {
			//...
			args.model.size.height = "460px";
			args.model.size.width = "950px";
		}
	</script>

{% endhighlight %}
 
![](Dimensions_images/Dimensions.png) 

## Responsive

The pivot chart control supports responsive rendering based on the target device (desktop and tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in the pivot chart by setting the `isResponsive` property to true.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1" isResponsive="true">
		//...
		</ej:pivotChart
	</div>

{% endhighlight %}

![](Dimensions_images/NormalView.png)

_Normal View_

![](Dimensions_images/ResponsiveView.png)

_ResponsiveView_

