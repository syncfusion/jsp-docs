---
layout: post
title: Scales
description: scales
platform: jsp
control: PivotGauge
documentation: ug
---

# Scale

## Adding scale

The scale can be added to the pivot gauge control.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGauge id="PivotGauge1" beforePivotEnginePopulate="beforePivotEnginePopulate">
    //...
</ej:pivotGauge>
</div>
<script type="text/javascript">

    function beforePivotEnginePopulate(args) {
		this.model.scales = [];
		this.model.scales[0] = {
            showScaleBar: true,
            radius: 150
            //...
        };					
    }
</script>

{% endhighlight %}

![](Scales_images/AddingScale.png) 

## Scale customization

### Pointer cap
The pointer cap is a circular shape element located at the center of the pivot gauge. This can be customized with the `PointerCap` property in the scales option. Following are the properties used to customize its appearance:

* **radius**: Sets the radius of the pointer cap.
* **borderColor**: Sets the color of the pointer cap border.
* **borderWidth**: Sets the width of the pointer cap border.
* **backgroundColor**: Sets the background color of the pointer cap.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGauge id="PivotGauge1" beforePivotEnginePopulate="beforePivotEnginePopulate">
    //...
</ej:pivotGauge>
</div>
<script type="text/javascript">

    function beforePivotEnginePopulate(args) {
		this.model.scales = [];
		this.model.scales[0] = {
            //...
            showScaleBar: true,
            pointerCap: {
                radius: 5,
                borderWidth: 2,
                borderColor: "green",
                backgroundColor: "yellow"
            }
        };					
    }
</script>

{% endhighlight %}

![](Scales_images/PointerCap.png) 

### Appearance
The appearance of the scale can be customized through the following properties:

* **radius**: Sets the radius of the scale.
* **backgroundColor**: Sets the background color of the scale.
* **border**: Sets the border of the scale with color and width properties.
* **size**: Sets the size of the scale.
* **minimum**: Sets the least value of the scale.
* **maximum**: Sets the highest value of the scale.
* **majorIntervalValue**: Sets the interval between minor ticks in the scale.
* **minorIntervalValue**: Sets the interval between major ticks in the scale.
* **direction**: Sets the direction of the scale. By default, it takes clockwise direction.

The `showIndicators`, `showTicks`, `showRanges`, `showPointers`, and `showScaleBar` properties are used to enable/disable the indicators, ticks, ranges, pointers, and scale bar respectively. By default, `showTicks` and `showPointers` are set to true, and other properties are set to false.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGauge id="PivotGauge1" beforePivotEnginePopulate="beforePivotEnginePopulate">
    //...
</ej:pivotGauge>
</div>
<script type="text/javascript">

    function beforePivotEnginePopulate(args) {
		this.model.scales = [];
		this.model.scales[0] = {
            //...
            showScaleBar: true,
            radius: 120,
            backgroundColor: "yellow",
            border: {
                color: "Blue",
                width: 3
            },
            size: 10,
            minimum: 20,
            maximum: 120,
            majorIntervalValue: 20,
            minorIntervalValue: 5,
            direction: ej.datavisualization.CircularGauge.Directions.CounterClockwise
        };					
    }
</script>

{% endhighlight %}

![](Scales_images/Appearance.png)