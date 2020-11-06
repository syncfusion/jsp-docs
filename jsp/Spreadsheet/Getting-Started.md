---
layout: post
title: getting-started
description: How to create a Spreadsheet in JSP platform
platform: JSP
control: Spreadsheet
documentation: ug
---

# Getting Started

This section explains you the steps required to populate the Spreadsheet with data, format and export it as excel file. This section covers only the minimal features that you need to know to get started with the Spreadsheet.

## Create a simple Spreadsheet in JSP
You can create an JSP application and add necessary scripts with the help of the given [JSP Getting Started Documentation.](/jsp/Getting-Started)


Create the JSP file and add the below given code to render **Spreadsheet** control.

{% highlight html %}

<div class="cols-sample-area">
 <ej:spreadsheet id="spreadsheet" loadComplete="loadComplete">
 </ej:spreadsheet>
</div>


{% endhighlight %}

The above code will render the following output in the display.

![Getting-Started_images/md_img1.png](Getting-Started_images/md_img1.png)

## Configuring the Spreadsheet


### Populate Spreadsheet with data
 Now, this section explains how to populate JSON data to the Spreadsheet.Refer the below code to define the datasource of Spreadsheet.
{% highlight js %}

<%@ page language="java" contentType="text/html; charset=ISO-8859-1" pageEncoding="ISO-8859-1"%>
<%@ page session="false" import="java.util.ArrayList" %>
<%@ page session="false" import="java.util.Iterator" %>
<%@ page session="false" import="org.json.simple.parser.JSONParser" %>
<%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld"%>
<%@ page import="com.syncfusion.*"%>
<%  ArrayList < Object > array = new ArrayList<Object>();
    JSONParser parser = new JSONParser();
    array.add(parser.parse("{\"Item Name\": \"Casual Shoes\",\"Date\": \"02/14/2014\",\"Time\": \"11:34:32 AM\",\"Quantity\": \"10\",\"Price\": \"20\",\"Amount\": \"200\",\"Discount\": \"1\",\"Profit\": \"10\"}"));
	  array.add(parser.parse("{\"Item Name\": \"Sports Shoes\",\"Date\": \"06/11/2014\",\"Time\": \"05:56:32 AM\",\"Quantity\": \"20\",\"Price\": \"30\",\"Amount\": \"600\",\"Discount\": \"5\",\"Profit\": \"50\"}"));
	  array.add(parser.parse("{\"Item Name\": \"Formal Shoes\",\"Date\": \"07/27/2014\",\"Time\": \"03:32:44 AM\",\"Quantity\": \"20\",\"Price\": \"15\",\"Amount\": \"300\",\"Discount\": \"7\",\"Profit\": \"27\"}"));
	  array.add(parser.parse("{\"Item Name\": \"Sandals & Floaters\",\"Date\": \"11/21/2014\",\"Time\": \"06:23:54 AM\",\"Quantity\": \"15\",\"Price\": \"20\",\"Amount\": \"300\",\"Discount\": \"11\",\"Profit\": \"67\"}"));
	  array.add(parser.parse("{\"Item Name\": \"Flip- Flops & Slippers\",\"Date\": \"06/23/2014\",\"Time\": \"12:43:59 AM\",\"Quantity\": \"30\",\"Price\": \"10\",\"Amount\": \"300\",\"Discount\": \"10\",\"Profit\": \"70\"}"));
	  array.add(parser.parse("{\"Item Name\": \"Sneakers\",\"Date\": \"07/22/2014\",\"Time\": \"10:55:53 AM\",\"Quantity\": \"40\",\"Price\": \"20\",\"Amount\": \"800\",\"Discount\": \"13\",\"Profit\": \"66\"}"));
	  array.add(parser.parse("{\"Item Name\": \"Running Shoes\",\"Date\": \"02/04/2014\",\"Time\": \"03:44:34 AM\",\"Quantity\": \"20\",\"Price\": \"10\",\"Amount\": \"200\",\"Discount\": \"3\",\"Profit\": \"14\"}"));
	  array.add(parser.parse("{\"Item Name\": \"Loafers\",\"Date\": \"11/30/2014\",\"Time\": \"03:12:52 AM\",\"Quantity\": \"31\",\"Price\": \"10\",\"Amount\": \"310\",\"Discount\": \"6\",\"Profit\": \"29\"}"));
	  array.add(parser.parse("{\"Item Name\": \"Cricket Shoes\",\"Date\": \"07/07/2014\",\"Time\": \"11:32:14 AM\",\"Quantity\": \"41\",\"Price\": \"30\",\"Amount\": \"1210\",\"Discount\": \"12\",\"Profit\": \"166\"}"));
    array.add(parser.parse("{\"Item Name\": \"T-Shirts\",\"Date\": \"10/31/2014\",\"Time\": \"12:01:44 AM\",\"Quantity\": \"50\",\"Price\": \"10\",\"Amount\": \"500\",\"Discount\": \"9\",\"Profit\": \"55\"}"));
    request.setAttribute("DataSource", array);
%>
{% endhighlight %}
      

{% highlight html %}

<div class="cols-sample-area">
  <ej:spreadsheet id="spreadsheet" loadComplete="loadComplete">
    <ej:spreadsheet-sheets>
     <ej:spreadsheet-sheet>
      <ej:spreadsheet-sheet-rangeSettings>
       <ej:spreadsheet-sheet-rangeSetting dataSource="${DataSource}">
	   </ej:spreadsheet-sheet-rangeSetting>
      </ej:spreadsheet-sheet-rangeSettings>
     </ej:spreadsheet-sheet>
    </ej:spreadsheet-sheets>
  </ej:spreadsheet>
</div>
<script>
function loadComplete(args) {
   var xlFormat = this.XLFormat;
   if (!this.isImport) {
       this.setWidthToColumns([140, 128, 105, 100, 100, 110, 120, 120, 100]);
       xlFormat.format({ "style": { "font-weight": "bold" } }, "A1:H1");
       this.XLRibbon.updateRibbonIcons();
        }
    }
</script>

 {% endhighlight %}
 
 The above code will render the following output in the display screen.
 
![Getting-Started_images/md_img2.png](Getting-Started_images/md_img2.png)

N> For more details about `data binding` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/data-binding# "link")

### Apply Conditional Formatting

Conditional formatting helps you to apply formats to a cell or range with certain color based on the cells values. You can use [`allowConditionalFormats`](http://help.syncfusion.com/js/api/ejspreadsheet#members:allowconditionalformats "allowConditionalFormats") property to enable/disable Conditional formats.

To apply conditional formats for a range use [`setCFRule`](http://help.syncfusion.com/js/api/ejspreadsheet#methods:xlcformat-setcfrule "setCFRule") method. The following code example illustrates this,


{% highlight html %}


<%@page import="datasource.GetJsonData" %>
<%
   GetJsonData obj =new GetJsonData();
    Object data = obj.getSpreadCFData();
    request.setAttribute("DataSource", data);
    %>
 <div class="cols-sample-area">
   <ej:spreadsheet id="spreadsheet" loadComplete="loadComplete">
     <ej:spreadsheet-sheets>
	  <ej:spreadsheet-sheet>
	   <ej:spreadsheet-sheet-rangeSettings>
	    <ej:spreadsheet-sheet-rangeSetting dataSource="${DataSource}" showHeader="false">
	    </ej:spreadsheet-sheet-rangeSetting>
	   </ej:spreadsheet-sheet-rangeSettings>
	  </ej:spreadsheet-sheet>
     </ej:spreadsheet-sheets>
   </ej:spreadsheet>
 </div>
<script>
 function loadComplete(args) {
   this.setWidthToColumns([165, 130, 37, 165, 130, 37, 129, 132]);
   this.XLCFormat.setCFRule({ "action": "greaterthan", "inputs": ["10"], "color": "redft", "range": "D3:D8" });
   this.XLFormat.format({ "style": { "font-weight": "bold", "font-size": "10pt", "vertical-align": "middle", "text-align": "center" } }, "A1:A13");
    }
</script>

{% endhighlight %}

![Getting-Started_images/md_img3.png](Getting-Started_images/md_img3.png)

N> For more details about `Conditional Formatting` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/data-presentation#conditional-formatting "link")

## Export Spreadsheet as Excel File

The Spreadsheet can save its data, style, format into an excel file. To enable save option in Spreadsheet set [`allowExporting`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings-allowexporting "allowExporting") option in [`exportSettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings "exportSettings") as `true`. Since Spreadsheet uses server side helper to save documents set [`excelUrl`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings-excelurl "excelUrl") in [`exportSettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings "exportSettings") option. The following code example illustrates this,


{% highlight html %}


<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
	pageEncoding="ISO-8859-1"%>
<%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld"%>
<%@ page import="com.syncfusion.*"%>
<%@page import="datasource.GetJsonData" %>
<%
   GetJsonData obj =new GetJsonData();
    Object data = obj.getSpreadData();
    request.setAttribute("DataSource", data);
    %>

<div class="cols-sample-area">
  <ej:spreadsheet id="spreadsheet">
   <ej:spreadsheet-exportSettings 
      excelUrl="http://js.syncfusion.com/demos/ejservices/api/Spreadsheet/ExcelExport" >
   </ej:spreadsheet-exportSettings>
   <ej:spreadsheet-sheets>
    <ej:spreadsheet-sheet>
     <ej:spreadsheet-sheet-rangeSettings>
      <ej:spreadsheet-sheet-rangeSetting dataSource="${DataSource}">
      </ej:spreadsheet-sheet-rangeSetting>
     </ej:spreadsheet-sheet-rangeSettings>
    </ej:spreadsheet-sheet>
   </ej:spreadsheet-sheets>
  </ej:spreadsheet>
</div>

{% endhighlight %}

Use shortcut [`Ctrl + S`](http://help.syncfusion.com/js/spreadsheet/keyboard-shortcuts# "Ctrl + S") to save Spreadsheet as excel file.


N> 1. For more details about `Export` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/open-and-save#save "link")
N> 2. For more details about `Server Configuration` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/open-and-save#server-configuration "link")       