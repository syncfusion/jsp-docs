---
layout: post
title:  Essential EJ1 Syncfusion JSP Kanban Columns
description: This section explains how to define the columns and their features of the Syncfusion JSP Kanban component.
documentation: ug
platform: jsp
keywords: columns,kanban columns
---

# Columns 

Column fields are present in the `dataSource` schema and it is rendering cards based its mapping column values.

## Key Mapping

To render Kanban with simple cards, you need to map the `dataSource` fields to Kanban cards and `columns`.

N> 1. If the column with `keyField` is not in the dataSource and `key` values specified will not available in column values, then the cards will not be rendered.
N> 2. If the `fields.content` is not in the dataSource, then empty cards will be rendered.

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
			<ej:kanban-fields content="Summary" primaryKey="Id"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress"></ej:kanban-column>
				<ej:kanban-column headerText="Testing" key="Testing"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
    </ej:kanban>
	</div>
    </body>
    </html>
    
{% endhighlight %}

The following output is displayed as a result of the above code example.

![Key mapping in JSP kanban control](Columns_images/column_img.png)

## Multiple Key Mapping

You can map more than one datasource fields as `key` values to show different key cards into single column. For e.g , you can map "Validate,In progress" keys under "In progress" column. 

The following code example and screenshot which describes the above behavior.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1" pageEncoding="ISO-8859-1"%>
	<%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %>
	<%@ page import="com.syncfusion.*" %><%@ page import="datasource.GetJsonData" %> 
    <body>
	<div class="cols-sample-area"><%
    GetJsonData obj=new GetJsonData();
    Object data = obj.GetKanbanJson();
    request.setAttribute("KanbanDataSource",data);%>
    <ej:kanban id="Kanban" keyField="Status" allowTitle="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" primaryKey="Id"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress or Validate" key="InProgress,Validate"></ej:kanban-column>
				<ej:kanban-column headerText="Testing" key="Testing"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
    </ej:kanban>
	</div>
    </body>
    </html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Multiple key mapping in JSP kanban control](Columns_images/column_img9.png)

## Headers

### Header Template

The template design that applies on for the column header. To render template, set `headerTemplate` property of the `columns`.

The following code example describes the above behavior.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1" pageEncoding="ISO-8859-1"%>
	<%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %>
	<%@ page import="com.syncfusion.*" %><%@ page import="datasource.GetJsonData" %>
    <body>
    <div class="cols-sample-area">
        <%
        GetJsonData obj=new GetJsonData();
        Object data = obj.GetKanbanJson();
        request.setAttribute("KanbanDataSource",data);%>
        <ej:kanban id="Kanban" keyfield="Status" allowtitle="true" datasource="${KanbanDataSource}">
            <ej:kanban-fields content="Summary" primarykey="Id"></ej:kanban-fields>
            <ej:kanban-columns>
                <ej:kanban-column headertext="Backlog" key="Open" headertemplate="#column1"></ej:kanban-column>
                <ej:kanban-column headertext="In Progress" key="InProgress"></ej:kanban-column>
                <ej:kanban-column headertext="Testing" key="Testing"></ej:kanban-column>
                <ej:kanban-column headertext="Done" key="Close" headertemplate="#column4"></ej:kanban-column>
            </ej:kanban-columns>
        </ej:kanban>
    </div>
    </body>
    <style>
    .e-backlog, .e-done {
        font-size: 16px;
        padding-right: 5px;
        display: inline-block;
       }

        .e-backlog:before {
            content: "\e807";
        }

        .e-done:before {
            content: "\e80a";
        }
    </style>
    <script id="column1" type="text/x-jsrender">
    <span class="e-backlog e-icon"></span> Backlog
    </script>
    <div id="column4">
    <span class="e-done e-icon"></span> Done
    </div>
    </html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Header template in JSP kanban control](Columns_images/column_img1.png)


## Visibility 

You can hide particular column in Kanban by setting `visible` property of it as false.

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
    <ej:kanban id="Kanban" keyField="Status" allowTitle="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" primaryKey="Id"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress"></ej:kanban-column>
				<ej:kanban-column headerText="Testing" key="Testing" visible="false" ></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
    </ej:kanban>
	</div>
    </body>
    </html>


{% endhighlight %}

The following output is displayed as a result of the above code example.

![Column visibility in JSP kanban control](Columns_images/column_img3.png)

## Toggle 

You can set particular column collapsed state in Kanban by setting `isCollapsed` property of it as true. You need to set `allowToggleColumn` as true to use “Expand/Collapse” Column.

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
    <ej:kanban id="Kanban" keyField="Status" allowToggleColumn="true" allowTitle="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" primaryKey="Id"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open" isCollapsed="true"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress"></ej:kanban-column>
				<ej:kanban-column headerText="Testing" key="Testing"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
    </ej:kanban>
	</div>
    </body>
    </html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Toggle column in JSP kanban control](Columns_images/column_img4.png)

## Allow Dragging

You can enable and disable drag behavior to the cards in the Kanban columns using the `allowDrag` property and the default value is `true`.

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
				<ej:kanban-column headerText="Backlog" key="Open" allowDrag="false"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
    </ej:kanban>
	</div>
    </body>
    </html>
    
{% endhighlight %}

The following output is displayed as a result of the above code example.

![Allow dragging in JSP kanban control](Columns_images/column_img5.png)

## Allow Dropping

You can enable and disable drop behavior to the cards in the Kanban columns using the `allowDrop` property and the default value is `true`.

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
				<ej:kanban-column headerText="Done" key="Close" allowDrop="false"></ej:kanban-column>
			</ej:kanban-columns>
    </ej:kanban>
	</div>
    </body>
    </html>
    
{% endhighlight %}

The following output is displayed as a result of the above code example.

![Allow dropping in JSP kanban control](Columns_images/column_img6.png)

##Items Count

You can show total cards count in each column's header using the property `enableTotalCount` and the default value is `false`.

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
    <ej:kanban id="Kanban" keyField="Status" enableTotalCount="true" dataSource="${KanbanDataSource}">
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

![Items count in JSP kanban control](Columns_images/column_img7.png)

