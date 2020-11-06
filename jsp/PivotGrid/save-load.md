---
layout: post
title: Save and Load Report | JSP | PivotGrid | Syncfusion
description: This document illustrates that how to save and load report to database in JSP platform of PivotGrid control 
platform: jsp
control: PivotGrid
documentation: ug
---

# Save and load report

Allows you to save the current report of the pivot grid and render the control with saved report later.

## Save report to local storage

To save the current report of the pivot grid to the local storage, call the `saveReport` method in the pivot grid.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1" saveReport="saveReport">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="saveLocal" showRoundedCorner="true" size="large" text="Save To Local"></ej:button> 
    </div>
    
	<script type="text/javascript">
    	function saveReport(){
            url = "",
            name = "report",
            storage = "local",
            pGridObj.saveReport(name, storage, url);
        }        
        function saveToLocal(args){
            localStorage.setItem("report", JSON.stringify(args.report));
        }
	</script>

{% endhighlight %}

## Load report from local storage

To load the stored report of the pivot grid from the local storage, call the `loadReport` method in the pivot grid.

{% highlight html %}

	<div>
		<ej:pivotGrid id="PivotGrid1" loadReport="loadReport">
		//...
		</ej:pivotGrid
	</div>
    <div>
        <ej:button id="button" click="saveLocal" showRoundedCorner="true" size="large" text="Save To Local"></ej:button> 
    </div>
    
	<script type="text/javascript">
    	function loadReport(){
            url = "",
            name = "report",
            storage = "local",
            pGridObj.loadReport(name, storage, url);
        }       
        function loadFromLocal(args){
            args.targetControl.model.dataSource = JSON.parse(localStorage.getItem("report"));
        }
	</script>

{% endhighlight %}