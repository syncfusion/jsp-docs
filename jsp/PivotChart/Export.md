---
layout: post
title: Export | JSP | PivotChart | Syncfusion
description: This document illustrates that how to define exporting and its customization in JSP PivotChart control
platform: jsp
control: PivotChart
documentation: ug
---

# Exporting

The pivot chart control can be exported to the following file formats:

* Microsoft Excel
* Microsoft Word
* PDF
* Image

The pivot chart control can be exported by invoking the **“exportPivotChart”** method with an appropriate export option as a parameter.

## Excel export

You can export the contents of the pivot chart to an Excel document for future archival, references, and analysis purposes.

To achieve Excel export, the method name **"ExcelExport"** and the file name are set as parameters.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		</ej:pivotChart
	</div>
    <div>
        <ej:button id="button" text="Export" size="large" showRoundedCorner="true" click="exportButtonClick"></ej:button>
    <div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var chartObj = $('#PivotChart1').data("ejPivotChart");
                chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ExcelExport","fileName");
            }
	</script>

{% endhighlight %}


## Word export
You can export the contents of the pivot chart to a Word document for future archival, references, and analysis purposes.

To achieve Word export, the method name **"WordExport"** and the file name are set as parameters.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		</ej:pivotChart
	</div>
    <div>
        <ej:button id="button" text="Export" size="large" showRoundedCorner="true" click="exportButtonClick"></ej:button>
    <div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var chartObj = $('#PivotChart1').data("ejPivotChart");
                chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/WordExport","fileName");
            }
	</script>

{% endhighlight %}


## PDF export

You can export the contents of the pivot chart to a PDF document for future archival, references, and analysis purposes.

To achieve Word export, the method name **"PDFExport"** and the file name are set as parameters.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		</ej:pivotChart
	</div>
    <div>
        <ej:button id="button" text="Export" size="large" showRoundedCorner="true" click="exportButtonClick"></ej:button>
    <div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var chartObj = $('#PivotChart1').data("ejPivotChart");
                chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/PDFExport","fileName");
            }
	</script>

{% endhighlight %}

## Image export
You can export the contents of the pivot chart to image format for future archival, references, and analysis purposes. You can export the pivot chart to the following image formats:

* PNG
* EMF
* JPG
* GIF
* BMP

To achieve image export, the method name **"ImageExport"** ,**“ej.PivotChart.ExportOptions.PNG”** and the file name are set as the parameter. This is similar to other image formats.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1>
		//...
		</ej:pivotChart
	</div>
    <div>
        <ej:button id="button" text="Export" size="large" showRoundedCorner="true" click="exportButtonClick"></ej:button>
    <div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var chartObj = $('#PivotChart1').data("ejPivotChart");
                chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ImageExport","fileName","png");
            }
	</script>

{% endhighlight %}

## Pivot chart format selection

I> This option is applicable only for the pivot chart specifically when exported to an Excel document.

You can set an option to export the pivot chart to an Excel document as an image or pivot chart format itself by setting the Boolean property `exportChartAsImage` in the `beforeExport` event.

N> By default, the pivot chart will be exported in image format to an Excel document.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 beforeExport="BeforeExport">
		//...
		</ej:pivotChart
	</div>
    <div>
        <ej:button id="button" text="Export" size="large" showRoundedCorner="true" click="exportButtonClick"></ej:button>
    <div>
    
	<script type="text/javascript">
        function BeforeExport(args) {
			args.exportChartAsImage = false; //you can set the chart format here
		}
		function exportButtonClick(args) {
                var chartObj = $('#PivotChart1').data("ejPivotChart");
                chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ExcelExport","fileName");
            }
	</script>

{% endhighlight %}

The following screenshot shows the control exported to an Excel document showing its own format (pivoting chart):

![Exporting format of JSP pivot chart control](Export_images/Export_ExcelChartClient.png)

## Exporting customization

You can add the title and description to the exporting document by using the title and description property obtained in the "beforeExport" event.

N> The title and description cannot be added to image formats.

{% highlight html %}

	<div>
		<ej:pivotChart id="PivotChart1 beforeExport="BeforeExport">
		//...
		</ej:pivotChart
	</div>
    <div>
        <ej:button id="button" text="Export" size="large" showRoundedCorner="true" click="exportButtonClick"></ej:button>
    <div>
    
	<script type="text/javascript">
        function BeforeExport(args) {
			args.title = "PivotChart";
            args.description = "Visualizes both OLAP and Relational datasource in graphical format";
		}
		function exportButtonClick(args) {
                var chartObj = $('#PivotChart1').data("ejPivotChart");
                chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ExcelExport","fileName");
            }
	</script>

{% endhighlight %}

The name of the document can be customized as per the user's requirements.

You should send the file name as parameter to the **“exportPivotChart”**  method along with service URL.

{% highlight javascript %}

function exportButtonClick(args)
{
    var chartObj = $('#PivotChart1').data("ejPivotChart ");
    chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ExcelExport", "fileName");
}
{% endhighlight %}    

The following screenshot shows the pivot chart control exported to an Excel document:

![Excel exporting in JSP pivot chart control](Export_images/Export_ExcelClient.png)

The following screenshot shows the pivot chart control exported to a PDF document:

![PDF exporting in JSP pivot chart control](Export_images/Export_PDFClient.png)

The following screenshot shows the pivot chart control exported to a Word document:

![Word exporting in JSP pivot chart control](Export_images/Export_WordClient.png)

The following screenshot shows the pivot chart control exported to a PNG format:

![PNG exporting in JSP pivot chart control](Export_images/Export_PNGClient.png)