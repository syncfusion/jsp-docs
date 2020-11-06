---
layout: post
title: getting started  
description: getting started  
platform: js
control: ListBox
documentation: ug
---

## Getting Started  


This section helps to understand the getting started of the Essential JSP ListBox with the step-by-step instructions.

### Create an ListBox 

The following steps guide you to add a Listbox control.

Create a JSP page and add the scripts and CSS references in the order mentioned in the following code example.

{% highlight html %}


<html>
<head>
<meta name="viewport"
content="width=device-width, initial-scale=1.0 user-scalable=no" />
<meta name="author" content="Syncfusion" />
<title>Essential JSP - ListBox</title>
<link rel="shortcut icon" href="Content/images/favicon.ico" />
<link href="//cdn.syncfusion.com//{{site.releaseversion}}/js/web/material/ej.web.all.min.css"
rel="stylesheet" />
<script src="https://code.jquery.com/jquery-3.1.1.min.js" type="text/javascript"> </script>    
<script type="text/javascript" src="//cdn.syncfusion.com//{{site.releaseversion}}/js/web/ej.web.all.min.js"></script>
</head>
<body>

</body>
</html>




{% endhighlight %}



Create a simple ListBox by adding ej:listBox tag for initializing an listbox component on the application.

{% highlight html %}

<ej:listBox id="mylist" >

</ej:listBox>


{% endhighlight %}



Run the above code to render the following output.

![](gettingstarted_images\createanlistbox_img1.png)



### Data binding

The data for the ListBox’s  list can be populated using the **dataSource** property. 

To configure data for ListBox control, define the data in Datasource. You need to import datasource in JSP sample and access the data in datasource by creating object of it. Refer the below code to define the datasource for the Listbox.

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



Refer the below code to render Listbox with datasource.

{% highlight html %}

<ej:listBox id="carlist"  dataSource="${CarDataSource}" >

</ej:listBox>


{% endhighlight %}





Run the above code to render the following output.



![](gettingstarted_images\databinding_img1.png)



### Selection

The Essential JSP **ListBox** control supports initial item selection using selectedIndex property.

Use the following code to render the ListBox with selection


{% highlight html %}

<ej:listBox id="mylist" dataSource="${CarDataSource}" selectedIndex="4" >

</ej:listBox>


{% endhighlight %}



Run the above code to render the following output.

![](gettingstarted_images\selection_img1.png)

 Note: You can find the Listbox properties from the [API reference](https://help.syncfusion.com/api/js/ejlistbox) document


