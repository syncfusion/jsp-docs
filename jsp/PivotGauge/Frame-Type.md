---
layout: post
title: Frame Type
description: frame type 
platform: jsp
control: PivotGauge
documentation: ug
---

# Frame type

## Full circle

The full circle frame is used to display the pivot gauge in circular shape. The frame type can be set by using the `frameType` property. By default, the frame type is "fullcircle".

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGauge id="PivotGauge1" beforePivotEnginePopulate="beforePivotEnginePopulate">
    //...
<ej:pivotGauge-frame frameType="fullcircle"></ej:pivotGauge-frame>
</ej:pivotGauge>
</div>

{% endhighlight %}

![](Frame-Type_images/FullCircle.png)

## Half circle
The half circle frame is used to display the pivot gauge in semi-circular shape. For this, set the the frame type to "halfcircle" within the `frameType` property, and then set the `startAngle` and `sweepAngle` for the pivot gauge in the `scales` property.


{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGauge id="PivotGauge1" beforePivotEnginePopulate="beforePivotEnginePopulate">
    //...
<ej:pivotGauge-frame frameType="halfcircle"></ej:pivotGauge-frame>
</ej:pivotGauge>
</div>
<script type="text/javascript">

    function beforePivotEnginePopulate(args) {
        this.model.backgroundColor = "transparent";
        this.model.frame.halfCircleFrameStartAngle = 180;
		this.model.frame.halfCircleFrameEndAngle = 360;
		this.model.scales = [];
		this.model.scales[0] = {"showRanges":true,"radius":150,"showScaleBar":true,"size":1,"border":{"width":0.5},"showIndicators":true,"showLabels":true,"pointers":[{"showBackNeedle":true,"backNeedleLength":20,"length":120,"width":7},{"type":"marker","markerType":"diamond","distanceFromScale":5,"placement":"center","backgroundColor":"#29A4D9","length":25,"width":15}],"ticks":[{"type":"major","distanceFromScale":2,"height":16,"width":1,"color":"#8c8c8c"},{"type":"minor","height":6,"width":1,"distanceFromScale":2,"color":"#8c8c8c"}],"labels":[{"color":"#8c8c8c"}],"ranges":[{"distanceFromScale":-5,"backgroundColor":"#fc0606","border":{"color":"#fc0606"}},{"distanceFromScale":-5}],"customLabels":[{"position":{"x":180,"y":290},"font":{"size":"10px","fontFamily":"Segoe UI","fontStyle":"Normal"},"color":"#666666"},{"position":{"x":180,"y":320},"font":{"size":"10px","fontFamily":"Segoe UI","fontStyle":"Normal"},"color":"#666666"},{"position":{"x":180,"y":150},"font":{"size":"12px","fontFamily":"Segoe UI","fontStyle":"Normal"},"color":"#666666"}],"pointerCap":{"radius":7,"borderWidth":3,"interiorGradient":null,"borderColor":null,"backgroundColor":null},"sweepAngle":180,"startAngle":180,"majorIntervalValue":10,"minorIntervalValue":2,"maximum":null,"minimum":null,"backgroundColor":null,"direction":"clockwise","showPointers":true,"showTicks":true,"opacity":1,"shadowOffset":0,"indicators":[{"height":15,"width":15,"type":"circle","imageUrl":null,"position":{"x":0,"y":0},"stateRanges":[{"endValue":0,"startValue":0,"backgroundColor":null,"borderColor":null,"text":"","textColor":null,"font":null}]}],"subGauges":[{"height":150,"width":150,"position":{"x":0,"y":0}}]};					
    }
</script>

{% endhighlight %}

![](Frame-Type_images/HalfCircle.png)
