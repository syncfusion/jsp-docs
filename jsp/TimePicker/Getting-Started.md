---
layout: post
title: Getting Started
description: Getting Started
platform: JSP
control: TimePicker
documentation: ug
---
# Getting Started

This section explains briefly about how to create a **TimePicker** in your application with JSP.

The usage of **TimePicker** control is described in the following sections.

## Create a TimePicker in JSP
You can create an JSP application and add necessary scripts with the help of the given [JSP Getting Started Documentation](/jsp-docs/jsp/Getting-Started).

Create the JSP file and add the below given code to render **TimePicker** control.

{% highlight html %}

        <div>TimePicker control in JSP</div>
        <ej:timePicker id="timepicker" ></ej:timePicker>
      
{% endhighlight %}

You can execute the above code example to display the **TimePicker** control.

![](Getting Started-images/Timepicker_image1.png) 

## Configuring TimePicker
This section encompasses the details on how you can setting the **MinTime**, **MaxTime** properties with **TimePicker** control in your application according to your requirement.

To set the **MinTime**, **MaxTime** in your application add the following script in your JSP file.

{% highlight javascript %}

    <script>
        var mintime = "9:00 AM";
        var maxtime = "9:00 PM";
        $(function () {
            $("#timepicker").ejTimePicker({
                minTime: mintime,
                maxTime: maxtime
            });
        });
    </script>

{% endhighlight %}

You can execute the above code example to display the **TimePicker** control with **MinTime** and **MaxTime**.

![](Getting Started-images/Timepicker_image2.png) 

