---
layout: post
title:  Essential EJ1 Syncfusion JSP Kanban Scrolling
description: This section explains how to achieve the scrolling behavior and its functionalities using the Syncfusion JSP Kanban component.
documentation: ug
platform: jsp
keywords: scrolling,kanban scrolling
---

# Scrolling

Scrolling can be enabled by setting `allowScrolling` as true. The height and width can be set to Kanban by using the properties `scrollSettings.height` and `scrollSettings.width` respectively.

N> The height and width can be set in percentage and pixel. The default value for `height` and `width` in `scrollSettings` is 0 and auto respectively.

## Set width and height in pixel

To specify the `scrollSettings.width` and `scrollSettings.height` in pixel, by set the pixel value as integer.

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
		<ej:kanban id="Kanban" keyField="Status" allowScrolling="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" tag="Tags" primaryKey="Id"></ej:kanban-fields>
		
			<ej:kanban-scrollSettings width="80" height="100"></ej:kanban-scrollSettings>
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

![Scrolling width and height in pixel for JSP kanban control](Scrolling_images/scroll_img1.png)

## Set height and width in percentage

To specify the `scrollSettings.width` and `scrollSettings.height` in percentage, by set the percentage value as string.

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
		<ej:kanban id="Kanban" keyField="Status" allowScrolling="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" tag="Tags" primaryKey="Id"></ej:kanban-fields>
		
			<ej:kanban-scrollSettings width="70%" height="70%"></ej:kanban-scrollSettings>
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

![Scrolling width and height in percentage for JSP kanban control](Scrolling_images/scroll_img2.png)

## Set width as auto

Specify `width` property of `scrollSettings` as auto, then the scrollbar is rendered only when the Kanban width exceeds the browser window width.

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
		<ej:kanban id="Kanban" keyField="Status" allowScrolling="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" tag="Tags" primaryKey="Id"></ej:kanban-fields>
		
			<ej:kanban-scrollSettings width="auto" height="70%"></ej:kanban-scrollSettings>
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

![Set width as auto in JSP kanban control](Scrolling_images/scroll_img3.png)

## Enabling freeze swim lane

Set `allowFreezeSwimlane` as true. This enables scrolling with freezing of swim lane until you scroll to the next Swim lane, which helps user to aware of current swim lane target.

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
		<ej:kanban id="Kanban" keyField="Status" allowScrolling="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" swimlaneKey="Assignee" tag="Tags" primaryKey="Id"></ej:kanban-fields>
		
			<ej:kanban-scrollSettings width="auto" height="70%" allowFreezeSwimlane="true"></ej:kanban-scrollSettings>
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

![Enabling freeze swim lane in JSP kanban control](Scrolling_images/scroll_img4.png)

N> `allowFreezeSwimlane` is applicable when swim lane grouping enabled by setting `swimlaneKey`.

