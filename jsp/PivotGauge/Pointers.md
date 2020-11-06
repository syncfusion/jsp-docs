---
layout: post
title: Pointers
description: pointers
platform: jsp
control: PivotGauge
documentation: ug
---

# Pointers

## Pointer types

Pivot gauge has two types of pointers namely,

* Needle
* Marker

Needle type pointer is the default pointer that is always located at the center of the gauge. Following are the supported shapes for needle pointers:

* Rectangle
* Triangle
* Trapezoid
* Arrow
* Image

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
            pointers: [{
                type: "needle",
                needleType: "trapezoid",
            }]
        };					
    }
</script>

{% endhighlight %}

![](Pointers_images/NeedlePointer.png) 

For marker pointer, the available shapes are rectangle, triangle, ellipse, diamond, pentagon, circle, slider, pointer, wedge, trapezoid, rounded rectangle, and image.

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
            pointers: [{
                type: "marker",
                markerType: "diamond",
            }]
        };					
    }
</script>

{% endhighlight %}

![](Pointers_images/MarkerPointer.png) 

## Adding pointer collection

The pointer collection can be directly added to the scales option within the pivot gauge control.

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
            pointers: [
                {
                    type: "needle",
                    needleType: "triangle",
                }, 
                {
                    type: "marker",
                    markerType: "diamond"
                }     
            ]
        };					
    }
</script>

{% endhighlight %}

![](Pointers_images/PointerCollection.png) 

## Appearance customization

The appearance of the pointer can be customized through the following properties:

* **border**: Sets the color and width of the pointer border.
* **backgroundColor**: Sets the background color of the pointer.
* **length**: Sets the length of the pointer.
* **width**: Sets the width of the pointer.
* **opacity**: Sets the opacity of the pointer. By default, the value is 1.
* **type**: Sets the type of the pointer. By default, the type is needle.

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
            pointers: [
                {
                    border: {
                        color: "green",
                        width: 2
                    },
                    backgroundColor: "yellow",
                    length: 120,
                    width: 7,
                    opacity: 0.6,
                    type: "needle",
                    needleType: "triangle"
                }, 
                {
                    border: {
                        color: "green",
                        width: 2
                    },
                    backgroundColor: "yellow",
                    length: 25,
                    width: 15,
                    opacity: 0.8,
                    type: "marker",
                    markerType: "diamond"
                }
            ]
        };					
    }
</script>

{% endhighlight %}

![](Pointers_images/AppearanceCustomization.png) 

## Pointer position

The pointer can be positioned with the help of the following two properties:

* **distanceFromScale**: Defines the distance between the scale and the pointer. By default, the value is 0.
* **placement**: Defines the location of the pointer. By default, the value is center.

N> Both the properties can be applied only if the pointer type is set to marker. The needle pointer type appears only at the center of the control, which is its default position.

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
            pointers: [{
                //...
                type: "marker",
                placement: "far",
                distanceFromScale: 2
            }]
        };					
    }
</script>

{% endhighlight %}

![](Pointers_images/PointerPosition.png) 

## Pointer image

You can replace the pointers with an image. To view the pointers as an image, set the appropriate location in the `imageUrl` property.

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
            pointers: [{
                //For replacing needle pointer with image
                type: "needle",
                needleType: "image",
                imageUrl: "image.png"
            }, 
            {
                //For replacing marker pointer with image
                type: "marker",
                markerType: "image",
                imageUrl: "image.png"
            }]
        };					
    }
</script>

{% endhighlight %}

![](Pointers_images/MarkerPointerWithImage.png)

## Pointer value text

To display the current value of pointer in the pivot gauge control, the **"pointerValueText"** option in the pointer is used. Following are the properties used to enable and customize the pointer value text.
 
* **showValue**: Enables the pointer value text by setting the property to true. By default, its value is true.
* **distance**: Sets the distance between the pointer and the text.
* **color**: Sets the color of the text.
* **opacity**: Sets the opacity of the text. By default, its value is 1.
* **angle**: Sets the rotation angle of the text. By default, its value is 0.
* **font**: Sets the font size, font style, and font family of the text.

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
            pointers: [{
                //For needle type
                pointerValueText: {
                    showValue: true,
                    distance: 10,
                    color: "red",
                    opacity: 0.7,
                    angle: 20,
                    font: {
                        size: "15px",
                        fontStyle: "Normal",
                        fontFamily: "Arial"
                    }
                }
            }, 
            {
                //For marker type
                pointerValueText: {
                    showValue: true,
                    distance: 40,
                    color: "red",
                    opacity: 0.7,
                    angle: -40,
                    font: {
                        size: "15px",
                        fontStyle: "Normal",
                        fontFamily: "Arial"
                    }
                },
            }]
        };					
    }
</script>

{% endhighlight %}

![](Pointers_images/PointerValueText.png) 
