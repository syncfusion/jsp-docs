---
layout: post
title: Getting-Started
description: getting started
platform: jsp
control: RadialMenu
documentation: ug
---

# Getting Started

This section helps to understand the getting started of the **RadialMenu** control for JSP.

![](Getting_Started_images/Getting-Started_img1.png)

## Create a RadialMenu

The following steps guide you to add a RadialMenu control.

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

Create a simple RadialMenu by adding **ej:radialMenu** tag for initializing an empty RadialMenu control on the application.  

    {% highlight html %}

        <ej:radialmenu id="defaultradialmenu" autoopen="false" targetelementid="radialtarget1">

        </ej:radialmenu>

    {% endhighlight %}

## Configure Items

In order to display items in RadialMenu control, you need to use **contentTemplate** of ej:radialmenu. You can set the images for each item by giving the image URL with the **data-ej-imageUrl** attribute in the inner list element and text with **data-ej-text** attribute for the Item. 

Refer to the following code example. Initialize Radial Menu control with items and set its target content as follows.

{% highlight html %}
    
    <ej:radialmenu id="defaultradialmenu" autoopen="false" targetelementid="radialtarget1">

        <ej:radialmenu-contenttemplate>
            <ul>
                <li data-ej-imageurl="Content/images/RadialMenu/font.png" data-ej-text="Bold"></li>
                <li data-ej-imageurl="Content/images/RadialMenu/f1.png" data-ej-text="Italic"></li>
                <li data-ej-imageurl="Content/images/RadialMenu/undo.png" data-ej-text="Undo" data-ej-enabled="false"></li>
                <li data-ej-imageurl="Content/images/RadialMenu/redo.png" data-ej-text="Redo" data-ej-enabled="false"></li>
            </ul>
        </ej:radialmenu-contenttemplate>

    </ej:radialmenu>

{% endhighlight %}

Refer to the following code example to add target content to the RadialMenu. You need to perform any actions while selecting the RTE content, you need to add **select** and **change** events in RTE.

{% highlight html %}

    <div id="radialtarget1" class="content-container-fluid">

        <ej:rte id="rteSample1" width="100%" change="rteChange" select="radialShow" showtoolbar="false" showcontextmenu="false">
            <ej:rte-contenttemplate>
                &lt;p&gt;  Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the user's interaction with it.
                The model consists of application data, business rules, logic, and functions. A view can be any output representation of data, such as a chart or a diagram.
                Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants.
                The controller mediates input, converting it to commands for the model or view.The central ideas behind MVC are code reusability and in addition to dividing the application into three kinds of components, the MVC design defines the interactions between them.&lt;/p&gt;
                &lt;p&gt; A controller can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model's state (e.g., editing a document).&lt;/p&gt;
                &lt;p&gt; A model notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them. &lt;/p&gt;
                &lt;p&gt;A view requests from the model the information that it needs to generate an output representation to the user.&lt;/p&gt;
            </ej:rte-contenttemplate>
        </ej:rte>

    </div>
  
{% endhighlight %}

## Displaying RadialMenu

You can display the Radial Menu by performing desired action on the target content while selecting the text inside the target. Using **select** event handler of RTE display the RadialMenu handler. Refer to the following code example and add it to event handler function.

{% highlight javascript %}

    var rteObj, rteEle = $("#rteSample1"), radialEle = $('#defaultradialmenu'), action = 0, forRedo = 0;
    function radialShow(e) {
        var target = $("#radialtarget1"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
            iframeY = target.offset().top + e.event.clientY, iframeX = target.offset().left + e.event.clientX,
            // To set Radial Menu position within target
            x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
            y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
        radialEle.ejRadialMenu("setPosition", x, y);
        radialEle.focus();
        $('iframe').contents().find('body').blur();
    }
   
{% endhighlight %}

Run the above code and select any text inside the target. The settings icon is displayed. Click that icon to render the following output.

![](Getting_Started_images/getting-started_img2.png)

## RadialMenu item functionalities

You can add functionalities for each items using the **click** event of RadialMenu. Refer to the following code example. Define the click event for Radial Menu control as follows.

{% highlight html %}
 
    <ej:radialmenu id="defaultradialmenu" autoopen="false" targetelementid="radialtarget1">

        <ej:radialmenu-contenttemplate>
            <ul>
                <li data-ej-imageurl="Content/images/RadialMenu/font.png" data-ej-text="Bold" data-ej-click="bold"></li>
                <li data-ej-imageurl="Content/images/RadialMenu/f1.png" data-ej-text="Italic" data-ej-click="italic"></li>
                <li data-ej-imageurl="Content/images/RadialMenu/undo.png" data-ej-text="Undo" data-ej-enabled="false" data-ej-click="undo"></li>
                <li data-ej-imageurl="Content/images/RadialMenu/redo.png" data-ej-text="Redo" data-ej-enabled="false" data-ej-click="redo"></li>
            </ul>
        </ej:radialmenu-contenttemplate>

    </ej:radialmenu>

{% endhighlight %}

Refer to the following code example to add functionalities for each items in event handler for items click and you can enable items in RadialMenu by using change event.

{% highlight javascript %}

    function rteChange(e) {
        radialEle.ejRadialMenu("enableItem", "Undo");
    }
    function bold(e) {
        rteObj = rteEle.data("ejRTE");
        rteObj.executeCommand("bold");
        data = rteObj._getSelectedHtmlString() ? true : false;
        if (data) action += 1;
        forRedo = action;
        radialEle.focus();
    }
    function italic(e) {
        rteObj = rteEle.data("ejRTE");
        rteObj.executeCommand("italic");
        data = rteObj._getSelectedHtmlString() ? true : false;
        if (data) action += 1;
        forRedo = action;
        radialEle.focus();
    }
    function undo(e) {
        rteObj = rteEle.data("ejRTE");
        rteObj.executeCommand("undo");
        action -= 1;
        if (action == 0)
            radialEle.ejRadialMenu("disableItem", "Undo");
        radialEle.ejRadialMenu("enableItem", "Redo");
        radialEle.focus();
    }
    function redo(e) {
        rteObj = rteEle.data("ejRTE");
        rteObj.executeCommand("redo");
        action += 1;
        if (forRedo == action) radialEle.ejRadialMenu("disableItem", "Redo");
        radialEle.ejRadialMenu("enableItem", "Undo");
        radialEle.focus();
    }

{% endhighlight %}

Run the above code and select any text inside the target. The settings icon is displayed. Click that icon to render the RadialMenu control. Click **bold** item in RadialMenu control, to render the following output.

![](Getting_Started_images/Getting_Started_img3.png)

N> _Note:_ _You can find the RadialMenu control properties from the_ [API reference](https://help.syncfusion.com/api/js/ejradialmenu) _document_
