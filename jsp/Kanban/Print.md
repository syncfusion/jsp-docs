---
layout: post
title:  Essential EJ1 Syncfusion JSP Kanban Print
description: This section explains how to perform printing feature and its functionalities using the Syncfusion JSP Kanban component.
documentation: ug
platform: jsp
---

# Print

 Set `allowPrinting` as true, to enable Print icon in the Kanban toolbar.  You can use `print()` method from Kanban instance to print the Kanban.

The following code example describes the above behavior.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page import="datasource.GetJsonData" %>
    <body>
	<div class="cols-sample-area"><%
			GetJsonData obj=new GetJsonData();
    Object data = obj.GetKanbanJson();
    JSONParser parser = new JSONParser();
    request.setAttribute("KanbanDataSource",data);
    %>
		<ej:kanban id="Kanban" keyField="Status" allowTitle="true" allowPrinting="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" primaryKey="Id"></ej:kanban-fields>
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

![Print in JSP kanban control](Printing_images/print_img1.png)


