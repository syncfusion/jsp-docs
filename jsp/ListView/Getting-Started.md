---
layout: post
title: getting started
description: getting started
platform: js
control: Control Name undefined
documentation: ug
---

## Getting Started

This section helps to understand the getting started of the Essential JSP ListView with the step-by-step instructions.

### Create an ListView 

The following steps guide you to add a Listview control.

Create a JSP page and add the scripts and CSS references in the order mentioned in the following code example.

{% highlight html %}


<html>
<head>
<meta name="viewport"
content="width=device-width, initial-scale=1.0 user-scalable=no" />
<meta name="author" content="Syncfusion" />
<title>Essential JSP - ListView</title>
<link rel="shortcut icon" href="Content/images/favicon.ico" />
<link href="//cdn.syncfusion.com//{{site.releaseversion}}/js/web/material/ej.web.all.min.css"
rel="stylesheet" />
<script src="https://code.jquery.com/jquery-3.1.1.min.js" type="text/javascript"> </script>    
<script type="text/javascript" src="//cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
<script type="text/javascript" src="//cdn.syncfusion.com//{{site.releaseversion}}/js/web/ej.web.all.min.js"></script>
</head>
<body>

</body>
</html>


{% endhighlight %}





Create a simple Listview by adding ej:listView tag for initializing an ListView control on the application. Then in order to display list items in control, you need to use **contentTemplate** of **ej:**listView. You can set text with **data-ej-text** attribute for the Item.

{% highlight html %}


<ej:listView id="listview" width="300px" > 
<ej:listview-contentTemplate>

            <li data-ej-text=_"Inbox"_></li>
            <li data-ej-text=_"VIP"_></li>
            <li data-ej-text=_"Drafts"_></li>
            <li data-ej-text=_"Sent"_></li>
            <li data-ej-text=_"Junk"_></li>
            <li data-ej-text=_"All mails"_></li>
            <li data-ej-text=_"Mail"_></li>

</ej:listview-contentTemplate>
</ej:listView>


{% endhighlight %}


Run the above code to render the following output.



![](gettingstarted_images\createanlistview_img1.png)


### Data binding



The data for the ListView can be populated using the **dataSource** property.

To configure data for ListView control, define the object array data in datasource package. You need to import datasource package in JSP sample and access the data in datasource by creating object of it. Refer the below code to define the datasource for the ListView.



{% highlight c# %}

**package** datasource;

**import** java.util.ArrayList;

**public****class** GetCarDataSource {
	ArrayList<CarDataSource> data= **new** ArrayList<CarDataSource>();

**public** ArrayList<CarDataSource> getData1(){
data.add(**new** CarDataSource("Audi S6 "));
data.add(**new** CarDataSource("Aston Martin"));
            data.add(**new** CarDataSource("Alfa Romeo"));
            data.add(**new** CarDataSource("Aston Martin"));
data.add(**new** CarDataSource("BMW 7"));
data.add(**new** CarDataSource("Bentley Mulsanne"));
data.add(**new** CarDataSource("Bugatti Veyron"));
data.add(**new** CarDataSource("Chevrolet Camaro"));
data.add(**new** CarDataSource("Cadillac"));
data.add(**new** CarDataSource("Duesenberg J"));
data.add(**new** CarDataSource("Elantra"));
data.add(**new** CarDataSource("Ferrari"));
data.add(**new** CarDataSource("Honda"));
data.add(**new** CarDataSource("Hyundai Santro"));
data.add(**new** CarDataSource("Isuzu Swift"));
data.add(**new** CarDataSource("Volkswagen Shirako"));

**return** data;
}
}


{% endhighlight %}



Access the data from datasource by using below code,

{% highlight html %}

<%
    GetCarDataSource obj =**new** GetCarDataSource();
    Object data = obj.getData1();
    request.setAttribute("CarDataSource", data);
   %>


{% endhighlight %}



Refer the below code to render ListView datasource in sample.

{% highlight html %}


<ej:listView id="listview" width="300px" dataSource="${CarDataSource}"> </ej:listView>



{% endhighlight %}



Run the above code to render the following output.



![](gettingstarted_images\databinding_img1.png)


### Add Header

We can add a header for Essential JSP **ListView** using **showHeader** and **headerTitle** properties. Refer to the following script.

{% highlight html %}


<ej:listView id="listview" width="300px" showHeader="true" headerTitle="MyCarList" dataSource="${CarDataSource}"> </ej:listView>



{% endhighlight %}



Run the above code to render the following output.



![](gettingstarted_images\addheader_img1.png)

Note: You can find the ListView properties from the [API reference](https://help.syncfusion.com/api/js/ejlistview) document 





