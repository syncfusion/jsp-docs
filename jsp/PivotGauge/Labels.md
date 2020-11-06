---
layout: post
title: Labels
description: labels 
platform: jsp
control: PivotGauge
documentation: ug
---

# Labels

## Adding label collection

The label collection can be directly added to the scales option within the pivot gauge control.

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
            labels: [{
                angle: 20
            }]
        };					
    }
</script>

{% endhighlight %}

## Appearance customization

The appearance of the label can be customized by using the following properties:

* **angle**: Displays labels in a rotated manner. By default, the value is 0.
* **color**: Displays the label in specified color.
* **opacity**: Sets the opacity of the label. By default, the value is 1.
* **type**: Indicates the label for major intervals or minor intervals.  By default, it takes major intervals.
* **includeFirstValue**: Includes the initial value based on user requirement.  By default, the value is true.
* **font**: Sets the font size, font style, and font family of the label.

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
            labels: [{
                //customizing major labels
                type: "major",
                color: "#1AFF01",
                opacity: 0.8,
                includeFirstValue: false,
                font: {
                    size: "15px",
                    fontFamily: "Arial",
                    fontStyle: "bold"
                }
            }, 
            {
                //customizing minor labels
                type: "minor",
                color: "#FF103F",
                opacity: 0.8,
                includeFirstValue: true,
                font: {
                    size: "10px",
                    fontFamily: "Arial",
                    fontStyle: "normal"
                }
            };					
    }
</script>

{% endhighlight %}

![](Labels_images/AppearanceCustomization.png) 


## Unit text

The `unitText` property is used to add some text along with labels. Normally, the unit/measurement of the numeric value is indicated through a unit text. By using the `unitTextPosition` property, the text can be positioned either in front or back.

N> By default, the text appears at the back.

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
            labels: [{
                //for Major labels
                type: "major",
                unitText: "$",
                unitTextPosition: "front"
            }, 
            {
                //for Minor labels
                type: "minor",
                unitText: "$",
                unitTextPosition: "front"
            }]
        };					
    }
</script>

{% endhighlight %}

![](Labels_images/UnitText.png) 


