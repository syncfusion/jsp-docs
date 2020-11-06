---
layout: post
title: getting-started
description: getting started for ColorPicker
platform: JSP
control: ColorPicker
documentation: ug
---

# GettingStarted

This section briefly describes about how to create a **Colorpicker** in your application with JSP. The usage of the **Colorpicker** is described in the following sections.

## Create a simple ColorPicker in JSP

You can create an JSP application and add necessary scripts with the help of the given [JSP Getting Started Documentation.](/jsp-docs/jsp/Getting-Started)

Create the JSP file and add the below given code to render **Colorpicker** control.

{% highlight javascript %}

<div class="cols-sample-area">
   <div class="control">
     <ej:colorPicker id="color" value="#278787" modelType="palette"> </ej:colorPicker>
   </div>
</div>


{% endhighlight %}

You can execute the above code example to display the **Colorpicker** control with simple control list.

![](getting-started_images/colorpicker.png) 

### Configuring ColorPicker

This section encompasses the details on how can you configure the **Colorpicker** control in your application and customize it with various properties such as preset type for **Colorpicker** according to your requirement.

To modify the preset type of the **Colorpicker**, add the following code in your JSP file.

{% highlight javascript %}

<ej:colorPicker id="color" value="#278787" modelType="palette" presetType="CandyCrush" ></ej:colorPicker>

{% endhighlight %}

The following screenshot illustrates the **Colorpicker** control with preset type property.

![](getting-started_images/colorpickerpreset.png) 
