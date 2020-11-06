---
layout: post
title: Getting-Started
description: getting started
platform: jsp
control: RadialSlider
documentation: ug
---

# Getting Started

This section helps to get started of the **RadialSlider** control in a JSP application.

![](Getting_Started_images/getting-started-img1.png)

## Create a RadialSlider

The following steps guide you to add a RadialSlider control.

Create a new HTML file and include the below scripts and styles for rendering Essential JavaScript controls.

{% highlight html %}

    <head>
        <title>JSP Application</title>
        <link href="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
        <script src="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/ej.web.all.min.js" type="text/javascript"></script>
    </head>

{% endhighlight %}

N> Note: For further reference, refer the common JSP Getting Started Documentation to create an application and add necessary scripts and styles for rendering our control.

Create a simple RadialSlider by adding **ej:radialSlider** tag for initializing an empty RadialSlider control on the application.

    {% highlight html %}

        <ej:radialSlider id="radialslider"></ej:radialSlider>

    {% endhighlight %}

## Image Configuration

You can customize the center image for RadialSlider using **innerCircleImageUrl** property, by setting an image URL to it.

{% highlight html %}
    
    <ej:radialSlider id="radialslider" innerCircleImageUrl="Content/images/radialslider/chevron-right.png"></ej:radialSlider>

{% endhighlight %}

![](Getting_Started_images/getting-started-img1.png)

N> _Note:_ _You can find the RadialSlider control properties from the_ [API reference](https://help.syncfusion.com/api/js/ejradialslider) _document_
