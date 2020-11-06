---
layout: post
title:  Essential EJ1 Syncfusion JSP Kanban Filtering
description: This section explains how to enable filtering and its functionalities using the Syncfusion JSP Kanban component.
documentation: ug
platform: jsp
keywords: filtering,kanban filtering
---

# Filtering

Filtering allows to filter the collection of cards from `dataSource` which meets the predefined `query` in the quick filters collection. To enable filtering, define `filterSettings` collection with display `text` and `ej.Query`. 

You can also define display tip to describe filter definition to user using property `description`. If the `description` property is not defined, given `text` will act as display tip.

We can also customize filter option through external button or `customToolbarItems` by using `filterCards()` method.

The following code example describes the above behavior.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page import="datasource.GetJsonData" %>
    <body>
	<div class="cols-sample-area"><%
    GetJsonData obj=new GetJsonData();
    Object data = obj.GetKanbanJson();
    request.setAttribute("KanbanDataSource",data);
    %>
		<ej:kanban id="Kanban" keyField="Status" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" primaryKey="Id"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
			<ej:kanban-filterSettings>
				<ej:kanban-filterSetting text="Janet Issues" query="new ej.Query().where('Assignee', 'equal', 'Janet Leverling')" description="Displays issues which matches the assignee as 'Janet Leverling'"></ej:kanban-filterSetting>
				<ej:kanban-filterSetting text="Testing Issues" query="new ej.Query().where('Status', 'equal', 'Testing')" description="Display the issues of 'Testing'"></ej:kanban-filterSetting>
			</ej:kanban-filterSettings>
		</ej:kanban>
	</div>
    </body>
    </html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Filtering in JSP kanban control](Filtering_images/filter_img1.png)