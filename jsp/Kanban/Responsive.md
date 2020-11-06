---
layout: post
title:  Responsive | Kanban | JSP | Syncfusion
description: This section explains the responsive behavior of the Syncfusion JSP Kanban component based on the client browser width and height.
documentation: ug
platform: jsp
keywords: responsive,kanban responsive
---

# Responsive

The Kanban control has support for responsive behavior based on client browser’s width and height. To enable responsive, `isResponsive` property should be true.There are two modes of responsive layout is available in Kanban based on client width. They are.

* Mobile(<480px)
* Desktop(>480px)

You can check the image representation of touch actions from the below image.

![Responsive layout in JSP kanban control](Responsive_images/KanbanOverlayImage.png)

## Mobile Layout

If client width is less than 480px, the Kanban will render in mobile mode. In which, you can see that kanban user interface is customized and redesigned for best view in small screens.To enable responsive, [`isResponsive`](https://help.syncfusion.com/api/js/ejkanban#members:isresponsive) property should be true.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %><%@ page import="datasource.GetJsonData" %>
    <script type="text/javascript" src="Scripts/jquery.validate.min.js"></script>
    <script type="text/javascript" src="Scripts/jquery.validate.unobtrusive.min.js"></script>
    <body>
	<div class="cols-sample-area"><%
    GetJsonData obj=new GetJsonData();
    Object data = obj.GetKanbanJson();
    JSONParser parser = new JSONParser();
    request.setAttribute("KanbanDataSource",data);
	request.setAttribute("StringValidation",parser.parse("{\"required\": true,\"number\":true}"));
	request.setAttribute("GetNumericParam",parser.parse("{\"decimalPlaces\":2}"));
	request.setAttribute("Estimatevalidation",parser.parse("{\"range\": [0, 1000] }"));
	request.setAttribute("TextareaValdation",parser.parse("{\"required\": \"true\"}"));
    %>
		<ej:kanban id="Kanban" keyField="Status" isResponsive="true" allowSearching="true" allowKeyboardNavigation="true" allowTitle="true" allowSelection="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" primaryKey="Id" imageUrl="ImgUrl"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress"></ej:kanban-column>
				<ej:kanban-column headerText="Testing" key="Testing"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
				<ej:kanban-filterSettings>
				<ej:kanban-filterSetting text="Janet Issues" query="new ej.Query().where('Assignee', 'equal', 'Janet Leverling')" description="Displays issues which matches the assignee as 'Janet Leverling'"></ej:kanban-filterSetting>
				<ej:kanban-filterSetting text="Testing Issues" query="new ej.Query().where('Status', 'equal', 'Testing')" description="Display the issues of 'Testing'"></ej:kanban-filterSetting>
			</ej:kanban-filterSettings>
			<ej:kanban-editSettings allowAdding="true" allowEditing="true">
				<ej:kanban-editSettings-editItems>
					<ej:kanban-editSettings-editItem field="Id" editType="stringedit" validationRules="${StringValidation}"></ej:kanban-editSettings-editItem>
					<ej:kanban-editSettings-editItem field="Status" editType="dropdownedit"></ej:kanban-editSettings-editItem>
					<ej:kanban-editSettings-editItem field="Assignee" editType="dropdownedit"></ej:kanban-editSettings-editItem>
					<ej:kanban-editSettings-editItem field="Estimate" editType="numericedit"  editParams="${GetNumericParam}" validationRules="${Estimatevalidation}"></ej:kanban-editSettings-editItem>
					<ej:kanban-editSettings-editItem field="Summary" editType="textarea" validationRules="${TextareaValdation}"></ej:kanban-editSettings-editItem>
				</ej:kanban-editSettings-editItems>
			</ej:kanban-editSettings>
		</ej:kanban>
	 </div>
     </body>
     </html>

{% endhighlight %}

![Mobile layout in JSP kanban control](Responsive_images/Responsive_img2.png)


W> IE8 and IE9 does not support responsive kanban. `ej.responsive.css` should be referred to display Responsive Kanban.

![CRUD mobile layout in JSP kanban control](Responsive_images/Responsive_img3.png)
{:caption}
CRUD in mobile layout

![Filtering mobile layout in JSP kanban control](Responsive_images/Responsive_img4.png)
{:caption}
Filtering in mobile layout

![Searching mobile layout in JSP kanban control](Responsive_images/Responsive_img5.png)
{:caption}
Searching in mobile layout

![Swim-lane mobile layout in JSP kanban control](Responsive_images/Responsive_img6.png)

![Swim-lane options mobile layout in JSP kanban control](Responsive_images/Responsive_img7.png)
{:caption}
Kanban with Swim-lane

## Width

By default, the Kanban is adaptable to its parent container. It can adjust its width of columns based on parent container width. You can also assign width of `columns` in percentage. 

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
			<ej:kanban-fields content="Summary" primaryKey="Id" tag="Tags"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open" width="10%" ></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress" width="10%"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close" width="10%"></ej:kanban-column>
			</ej:kanban-columns>
		</ej:kanban>
	</div>
    </body>
    </html>

{% endhighlight %}

N> `allowScrolling` should be false while defining width in percentage.

## Min Width

Min Width is used to maintain minimum width for the Kanban. If the Kanban width is less than `minWidth` then the scrollbar will be displayed to maintain minimum width.

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
		<ej:kanban id="Kanban" keyField="Status" minWidth="700" isResponsive="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" primaryKey="Id" tag="Tags"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open" width="120" ></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress" width="110"></ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close" width="110"></ej:kanban-column>
			</ej:kanban-columns>
		</ej:kanban>
	</div>
    </body>
    </html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Minimum width mobile layout in JSP kanban control](Responsive_images/responsive_img1.png)
