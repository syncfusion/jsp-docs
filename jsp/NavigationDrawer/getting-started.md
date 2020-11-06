---
layout: post
title: getting-started
description: getting started
platform: jsp
control: navigation drawer
documentation: ug
---

# Getting Started

This section helps you to understand the getting started of the Navigation Drawer control with the step-by-step instructions.

## Create a Navigation Drawer

The following steps guide you to add a Navigation Drawer control.

Create a JSP page and add the scripts and css references in the order mentioned in the following code example.

{% highlight html %}

<head>
    <title>JSP Application</title>
    <link href="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/ej.web.all.min.js" type="text/javascript"></script>
</head>

{% endhighlight %}

N> Note: For further reference, refer the common JSP Getting Started Documentation to create an application and add necessary scripts and styles for rendering the Navigation Drawer control.

Create a simple Navigation Drawer by adding ej:navigationdrawer tag to initialize the control in the application. 

To add the list item to Navigation Drawer inside the ej:navigationdrawer-contenttemplate tag by using data-ej-text property and access the List View control properties by enabling the enableListView property.

    {% highlight html %}

    <ej:navigationdrawer id="navpane" enableListView="true" type="overlay" direction="left">

        <ej:navigationdrawer-contenttemplate>

            <ul>
                <li data-ej-text="Home"></li>
                <li data-ej-text="Profile"></li>
                <li data-ej-text="Photos"></li>
            </ul>

        </ej:navigationdrawer-contenttemplate>

    </ej:navigationdrawer>

    {% endhighlight %}

Create the target element as follows to display the list items by clicking target icon.

{% highlight html %}

    <div id="container">
        <div class="e-lv">
            <div class="e-header">
                <div id="butdrawer"
                     class="drawericon e-icon">
                </div>
            </div>
        </div> 
    </div>

{% endhighlight %}

To set the target icon image and with the correct position as using the below mentioned styles .

{% highlight css %}

    <style>
    
      .drawericon {
        background-position: center center;
        background-repeat: no-repeat;
        height: 32px;
        width: 32px;
        background-size: 100% 100%;
        padding-right: 10px;
     }
     .drawericon:before {
        content: "\e76b";
        font-size: 28px;
        height: 26px;
     }

    </style>

{% endhighlight %}

![](Getting-Started_images/getting-started-img1.png)

To open the list items by clicking on target element, set the elements ID to targetId property.  

{% highlight html %}

<ej:navigationdrawer id="navpane" enableListView="true" type="overlay" direction="left" targetId="butdrawer">

        <ej:navigationdrawer-contenttemplate>

            <ul>
                <li data-ej-text="Home"></li>
                <li data-ej-text="Profile"></li>
                <li data-ej-text="Photos"></li>
            </ul>

        </ej:navigationdrawer-contenttemplate>

    </ej:navigationdrawer>
  
{% endhighlight %}

![](Getting-Started_images/getting-started-img2.png)

To set the images for list items of the Navigation Drawer by using the data-ej-imageurl property as follows.

{% highlight html %}

  <ej:navigationdrawer id="navpane" enableListView="true" type="overlay" direction="left" targetId="butdrawer">

        <ej:navigationdrawer-contenttemplate>

            <ul>
               <li data-ej-imageurl="http://js.syncfusion.com/demos/web/content/images/navigationdrawer/home.png" data-ej-text="Home"></li>
               <li data-ej-imageurl="http://js.syncfusion.com/demos/web/content/images/navigationdrawer/profile.png" data-ej-text="Profile"></li>
               <li data-ej-imageurl="http://js.syncfusion.com/demos/web/content/images/navigationdrawer/photo.png" data-ej-text="Photos"></li>     
            </ul>

        </ej:navigationdrawer-contenttemplate>

    </ej:navigationdrawer>

{% endhighlight %}

![](Getting-Started_images/getting-started-img3.png)

## Customize Direction

By using direction property, to change the list view open direction. The possible directions are Right, Left and the Left is default value. Refer to the below mentioned code.

{% highlight html %}

    <ej:navigationdrawer id="navpane" enableListView="true" type="overlay" direction="right" targetId="butdrawer">

        <ej:navigationdrawer-contenttemplate>

            <ul>
               <li data-ej-imageurl="http://js.syncfusion.com/demos/web/content/images/navigationdrawer/home.png" data-ej-text="Home"></li>
               <li data-ej-imageurl="http://js.syncfusion.com/demos/web/content/images/navigationdrawer/profile.png" data-ej-text="Profile"></li>
               <li data-ej-imageurl="http://js.syncfusion.com/demos/web/content/images/navigationdrawer/photo.png" data-ej-text="Photos"></li>     
            </ul>

        </ej:navigationdrawer-contenttemplate>

    </ej:navigationdrawer>

{% endhighlight %}

![](Getting-Started_images/getting-started-img5.png)

N> You can find the Navigation Drawer control properties from the [API reference](https://help.syncfusion.com/api/js/ejnavigationdrawer).
