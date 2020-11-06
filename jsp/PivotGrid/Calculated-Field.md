---
layout: post
title: Calculated Field | JSP | PivotGrid | Syncfusion
description: This document illustrates that how to define calculated field through code-behind/UI in JSP PivotGrid control 
platform: jsp
control: PivotGrid
documentation: ug
---

# Calculated field

N> This feature is applicable only for the relational data source.

The pivot grid provides support to insert a new calculated field based on existing pivot fields through the Calculated Field dialog or code behind.

### Through UI
To insert a new calculated Field, open the Calculated Field dialog using the grouping bar context menu. You can define "Name" for the new calculated field and "Formula" can be entered by inserting required fields through the fields section. For inserting numbers and operators, you can use formula pop-up as shown in the following screenshot:

![Calculated field dialog in JSP pivot grid control](Calculated-Field_images/Calculated-Field-Popup.png)

Click **Add** to add the respective Calculated Field and **OK** to populate the pivot grid control.

### Through code-behind

The calculated field can be created at code-behind by defining formula based on existing Pivot Fields in the pivot grid. To indicate a field as a calculated field, set the `isCalculatedField` property to true and `formula` property to set the expression.

{% highlight html %}

<div class="cols-sample-area">
<ej:pivotGrid id="PivotGrid1" load="onLoad">
<ej:pivotGrid-dataSource>
<ej:pivotGrid-dataSource-rows>
<ej:pivotGrid-dataSource-row fieldName="Product" fieldCaption="Product"></ej:pivotGrid-dataSource-row>
</ej:pivotGrid-dataSource-rows>
<ej:pivotGrid-dataSource-columns>
<ej:pivotGrid-dataSource-column fieldName="Date" fieldCaption="Date"></ej:pivotGrid-dataSource-column>
</ej:pivotGrid-dataSource-columns>
<ej:pivotGrid-dataSource-values>
<ej:pivotGrid-dataSource-value fieldName="Amount" fieldCaption="Amount"></ej:pivotGrid-dataSource-value>
<ej:pivotGrid-dataSource-value fieldName="Price" fieldCaption="Price" isCalculatedField="true" formula="Amount * 15"></ej:pivotGrid-dataSource-value>
</ej:pivotGrid-dataSource-values>
</ej:pivotGrid-dataSource>
</ej:pivotGrid>
</div>
<script type="text/javascript">

    function onLoad(args) {
        args.model.dataSource.data = [
	                       { Amount: 100, Country: "Canada", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Alberta" },
	                       { Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Van", Quantity: 3, State: "British Columbia" },
	                       { Amount: 300, Country: "Canada", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Brunswick" },
	                       { Amount: 150, Country: "Canada", Date: "FY 2008", Product: "Bike", Quantity: 3, State: "Manitoba" },
	                       { Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Car", Quantity: 4, State: "Ontario" },
	                       { Amount: 100, Country: "Canada", Date: "FY 2007", Product: "Van", Quantity: 1, State: "Quebec" },
	                       { Amount: 200, Country: "France", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Charente-Maritime" },
	                       { Amount: 250, Country: "France", Date: "FY 2006", Product: "Van", Quantity: 4, State: "Essonne" },
	                       { Amount: 300, Country: "France", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Garonne (Haute)" },
	                       { Amount: 150, Country: "France", Date: "FY 2008", Product: "Van", Quantity: 2, State: "Gers" },
	                       { Amount: 200, Country: "Germany", Date: "FY 2006", Product: "Van", Quantity: 3, State: "Bayern" },
	                       { Amount: 250, Country: "Germany", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Brandenburg" },
	                       { Amount: 150, Country: "Germany", Date: "FY 2008", Product: "Car", Quantity: 4, State: "Hamburg" },
	                       { Amount: 200, Country: "Germany", Date: "FY 2008", Product: "Bike", Quantity: 4, State: "Hessen" },
	                       { Amount: 150, Country: "Germany", Date: "FY 2007", Product: "Van", Quantity: 3, State: "Nordrhein-Westfalen" },
	                       { Amount: 100, Country: "Germany", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Saarland" },
	                       { Amount: 150, Country: "United Kingdom", Date: "FY 2008", Product: "Bike", Quantity: 5, State: "England" },
	                       { Amount: 250, Country: "United States", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Alabama" },
	                       { Amount: 200, Country: "United States", Date: "FY 2005", Product: "Van", Quantity: 4, State: "California" },
	                       { Amount: 100, Country: "United States", Date: "FY 2006", Product: "Bike", Quantity: 2, State: "Colorado" },
	                       { Amount: 150, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "New Mexico" },
	                       { Amount: 200, Country: "United States", Date: "FY 2005", Product: "Bike", Quantity: 4, State: "New York" },
	                       { Amount: 250, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "North Carolina" },
	                       { Amount: 300, Country: "United States", Date: "FY 2007", Product: "Van", Quantity: 4, State: "South Carolina" }
	       ];
    }

</script>

{% endhighlight %}

![JSP pivot grid control with user-defined field, aka calculated field](Calculated-Field_images/Calculated-Field1.png)