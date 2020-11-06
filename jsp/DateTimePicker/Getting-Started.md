---
layout: post
title: getting-started
description: getting started for DateTimePicker
platform: JSP
control: DateTimePicker
documentation: ug
---

# GettingStarted

This section briefly describes about how to create a **DateTimepicker** in your application with JSP.

## Create a simple DateTimepicker in JSP

You can create an JSP application and add necessary scripts with the help of the given [JSP Getting Started Documentation.](/jsp-docs/jsp/Getting-Started)

Create the JSP file and add the below given code to render **DateTimepicker** control.

{% highlight javascript %}

<div >
     <div class="control" margin="auto" align="center">
       <ej:dateTimePicker id="datetimepicker"  width="50%"></ej:dateTimePicker>
     </div>
</div>

{% endhighlight %}

You can execute the above code example to display the **DateTimepicker** control.

![](getting-started_images/Datetimepicker.png) 

### Configuring DateTimepicker

This section encompasses the details on how can you configure the **DateTimepicker** control in your application and customize it with various properties for **DateTimepicker** according to your requirement.

To modify the mindatetime and maxdatetime, add the following code in your JSP file.

{% highlight javascript %}

<ej:dateTimePicker id="datetimepicker" minDateTime="12/01/2016 09:00 AM"  maxDateTime="12/30/2016 09:00 PM" width=”30%”></ej:dateTimePicker>

{% endhighlight %}

The following screenshot illustrates the **DateTimepicker** control with preset type property.

![](getting-started_images/Datetime Picker.png)
