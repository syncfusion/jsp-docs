---
layout: post
title:  Essential EJ1 Syncfusion JSP Kanban Drag and Drop
description: This section explains how to drag and drop Kanban cards and their features of the Syncfusion JSP Kanban component.
documentation: ug
platform: jsp
keywords: drag and drop,kanban drag and drop
---

# Drag and Drop

By default `allowDragAndDrop` is true.Cards can be transited from one column to another column, by dragging and dropping. And it has drop position indicator which enables easier positioning of cards

## Prioritization of cards

Prioritizing cards is easy with drag-and-drop re-ordering that helps you to categorize most important work at the top.Cards can be categorized with priority by mapping specific database field into `priority` property.

`RankId` defined in the dataSource which is consist priority of cards. The `RankId` will be changed while card ordering changes through `Drag and Drop` and `Editing`.

The following code example describes the above behavior.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1" pageEncoding="ISO-8859-1"%>
	<%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %>
	<%@ page import="com.syncfusion.*" %><%@ page import="datasource.GetJsonData" %> 
    <body>
	<div class="cols-sample-area"><%
    GetJsonData obj=new GetJsonData();
    Object data = obj.GetKanbanJson();
    request.setAttribute("KanbanDataSource",data);%>
    <ej:kanban id="Kanban" keyField="Status" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" primaryKey="Id" priority="RankId" ></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
			
    </ej:kanban>
	</div>
    </body>
    </html>
    
{% endhighlight %}

The following output is displayed as a result of the above code example.

![Prioritization of cards in JSP kanban control](Drag_and_Drop_images/drag_and_drop_img1.png)

