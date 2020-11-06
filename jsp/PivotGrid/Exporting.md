---
layout: post
title: Exporting | JSP | PivotGrid | Syncfusion
description: This document illustrates that how to define exporting and its customization in JSP PivotGrid control
platform: jsp
control: PivotGrid
documentation: ug
---

# Exporting

The pivot grid control can be exported to the following file formats:

* Microsoft Excel
* Microsoft Word
* PDF
* CSV

The pivot grid control can be exported by invoking the **“exportPivotGrid”** method with an appropriate export option as a parameter.

## JSON export

### Excel export

You can export the contents of the pivot grid to an Excel document for future archival, references, and analysis purposes.

To achieve Excel export, the URL and the file name are set as parameters.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="exportButtonClick" showRoundedCorner="true" size="large" text="Export"></ej:button> 
    </div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
                pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport","fileName");
            }
	</script>

{% endhighlight %} 

### Word export

You can export the contents of the pivot grid to a Word document for future archival, references, and analysis purposes.

To achieve Word export, the URL and the file name are set as parameters.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="exportButtonClick" showRoundedCorner="true" size="large" text="Export"></ej:button> 
    </div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
                pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/WordExport","fileName");
            }
	</script>

{% endhighlight %} 

### PDF export

You can export the contents of the pivot grid to a PDF document for future archival, references, and analysis purposes.

To achieve Word export, the URL and the file name are set as parameters.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="exportButtonClick" showRoundedCorner="true" size="large" text="Export"></ej:button> 
    </div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
                pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/PDFExport","fileName");
            }
	</script>

{% endhighlight %} 

### CSV export

You can export the contents of the pivot grid to a CSV document for future archival, references, and analysis purposes.

To achieve CSV export, the URL and the file name are set as parameters.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="exportButtonClick" showRoundedCorner="true" size="large" text="Export"></ej:button> 
    </div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
                pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/CSVExport","fileName");
            }
	</script>

{% endhighlight %} 

### Customize the export document name

For customizing file name, set the file name as parameter to the **“exportPivotGrid”** method along with method name.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="exportButtonClick" showRoundedCorner="true" size="large" text="Export"></ej:button> 
    </div>
    
	<script type="text/javascript">
		function exportButtonClick(args) {
                var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
                pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/WordExport","fileName");
            }
	</script>

{% endhighlight %} 


## Exporting customization

You can add the title and description to the exporting document by using the title and description properties respectively, obtained in the `beforeExport` event. Similarly, you can enable or disable the styling on the exported document by using the `exportWithStyle` property.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1" beforeExport="BeforeExport">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="exportButtonClick" showRoundedCorner="true" size="large" text="Export"></ej:button> 
    </div>
    
	<script type="text/javascript">
        function BeforeExport(args) {
			args.title = "PivotGrid";
            args.description = "Displays both OLAP and Relational datasource in tabular format";
			args.exportWithStyle = false;   // by default it sets as true. It improves performance on exporting huge data when it sets as false.
	    }
		function exportButtonClick(args) {
                var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
                pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/WordExport","fileName");
            }
	</script>

{% endhighlight %} 

### Exporting complete data on paging

When the paging is enabled, you can export the complete data by enabling the `enableCompleteDataExport` property. It is supported in both types of JSON and pivot engine export and it is applicable for all kinds of exporting formats available in the pivot grid.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1" beforeExport="BeforeExport" enableCompleteDataExport="true">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="exportButtonClick" showRoundedCorner="true" size="large" text="Export"></ej:button> 
    </div>
    
	<script type="text/javascript">
        function BeforeExport(args) {
			args.title = "PivotGrid";
            args.description = "Displays both OLAP and Relational datasource in tabular format";
			args.exportWithStyle = false;   // by default it sets as true. It improves performance on exporting huge data when it sets as false.
	    }
		function exportButtonClick(args) {
                var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
                pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/WordExport","fileName");
            }
	</script>

{% endhighlight %}

The following screenshot shows the pivot grid control exported to an Excel document:

![Excel exporting in JSP pivot grid control](Exporting_images/ExportPivotExcel.png)

The following screenshot shows the pivot grid control exported to a Word document:

![Word exporting in JSP pivot grid control](Exporting_images/ExportPivotWord.png)

The following screenshot shows the pivot grid control exported to a PDF document:

![PDF exporting in JSP pivot grid control](Exporting_images/ExportPivotPDF.png)

The following screenshot shows the pivot grid control exported to a CSV document:

![CSV exporting in JSP pivot grid control](Exporting_images/ExportPivotCSV.png)

