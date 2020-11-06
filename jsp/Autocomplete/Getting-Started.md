---
layout: post
title: getting started
description: getting started
platform: js
control: Control Name undefined
documentation: ug
---

## Getting Started

This section helps to understand the getting started of the Autocomplete control for JSP.

### Creating an AutoComplete in JSP

The following steps guide you to add an Autocomplete control.

Create a JSP page and add the scripts and CSS references in the order mentioned in the following code example.

{% highlight html %}


<html>
<head>
<meta name="viewport"
content="width=device-width, initial-scale=1.0 user-scalable=no" />
<meta name="author" content="Syncfusion" />
<title>Essential JSP - Autocomplete</title>
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



Create a simple Autocomplete by adding ej:autocomplete tag for initializing an empty Autocomplete component on the application.

{% highlight html %}


<ej:autocomplete id="carlist">
</ej:autocomplete>



{% endhighlight %}



This will render an Autocomplete with no suggestion on executing.

![](getting_started_images\creatinganautocompleteinjsp_img1.png)


### Data Binding



The data for AutoComplete suggestion list which can be populated using the dataSource property.

To configure data for Autocomplete component, define an object array data. You need to import datasource in JSP sample and access the data in datasource by creating object of it. Refer the below code to define the datasource for the Autocomplete.



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

{% highlight js %}

<%
    GetCarDataSource obj =**new** GetCarDataSource();
    Object data = obj.getData1();
    request.setAttribute("CarDataSource", data);
   %>


{% endhighlight %}



Refer the below code to render Autocomplete with datasource.

{% highlight html %}


<ej:autocomplete id="carlist" width="300px" watermarkText="Select a car" dataSource="${CarDataSource}" >
</ej:autocomplete>



{% endhighlight %}



Run the above code to get the following output.

![](getting_started_images\databinding_img1.png)


### Enable Popup Button



We can enable the popup button of AutoComplete by using showPopupButton property which helps you to show all the available suggestions on clicking it.

{% highlight html %}


<ej:autocomplete id="auto" width="300px" watermarkText="Select a car" dataSource="${CarDataSource}" showPopupButton="true" >
</ej:autocomplete>



{% endhighlight %}



Run the above code to get the following output.

![](getting_started_images\enablepopupbutton_img1.png)



Note: You can find the Autocomplete properties from the [API reference](https://help.syncfusion.com/api/js/ejautocomplete) document 







