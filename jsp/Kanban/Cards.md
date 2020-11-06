---
layout: post
title:  Essential EJ1 Syncfusion JSP Kanban Cards
description: This section explains how to define the basic structure of cards and their features of the Syncfusion JSP Kanban component.
documentation: ug
platform: jsp
keywords: cards,kanban cards
---

# Cards

## Customization

Cards can be customized with appropriate mapping fields from the database.

The following code example describes the above behavior.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="java.util.HashMap" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %><%@ page import="datasource.GetJsonData" %>
    <body>
	<div class="cols-sample-area"><%
    GetJsonData obj=new GetJsonData();
    Object data = obj.GetKanbanJson();
    request.setAttribute("KanbanDataSource",data);
    JSONParser parser = new JSONParser();
    request.setAttribute("colorMap", parser.parse("{\"#ee4e75\": \"Bug,Story\",\"#57b94c\": \"Improvement\",\"#edba3c\": \"Epic\",\"#5187c6\": \"Others\"}"));
    %>
		<ej:kanban id="Kanban" keyField="Status" allowTitle="true" allowSelection="true" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary" priority="RankId" tag="Tags" primaryKey="Id" imageUrl="ImgUrl" color="Type"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress">
				</ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
			<ej:kanban-cardSettings colorMapping="${colorMap}"></ej:kanban-cardSettings>
		</ej:kanban>
	</div>
    </body>
    </html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Card customization in JSP kanban control](Cards_images/cards_img1.png)

## Template

Templates are used to create custom card layout as per the user convenient. HTML templates can be specified in the `template` property of the `cardSettings` as an ID of the template’s HTML element.

The following code example describes the above behavior.


{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page import="datasource.GetJsonData" %>
    <body>
    <div class="cols-sample-area">
        <%
        GetJsonData obj=new GetJsonData();
        Object data = obj.GetKanbanJson();
        request.setAttribute("KanbanDataSource",data);
        %>
        <ej:kanban id="Kanban" keyfield="Status" allowtitle="true" allowselection="true" datasource="${KanbanDataSource}">
            <ej:kanban-fields content="Summary" primarykey="Id" imageurl="ImgUrl"></ej:kanban-fields>
            <ej:kanban-columns>
                <ej:kanban-column headertext="Backlog" key="Open"></ej:kanban-column>
                <ej:kanban-column headertext="In Progress" key="InProgress"></ej:kanban-column>
                <ej:kanban-column headertext="Testing" key="Testing"></ej:kanban-column>
            </ej:kanban-columns>
            <ej:kanban-cardsettings template="#cardtemplate"></ej:kanban-cardsettings>
        </ej:kanban>
    </div>
    </body>
    <style>
    .e-templatetable {
        width: 100%;
    }

    .details > table {
        margin-left: 2px;
        border-collapse: separate;
        border-spacing: 2px;
        width: 100%;
    }

    .details td {
        vertical-align: top;
    }

    .details {
        padding: 8px 8px 10px 0;
    }

    .photo {
        padding: 8px 6px 10px 6px;
        text-align: center;
    }

    .CardHeader {
        font-weight: bolder;
        padding-right: 10px;
    }
    </style>
    <script id="cardtemplate" type="text/x-jsrender">
    <table class="e-templatetable">
        <colgroup>
            <col width="10%">
            <col width="90%">
        </colgroup>
        <tbody>
            <tr>
                <td class="photo">
                    <img src="Content/images/kanban/"{{"{{"}}:Priority{{}}}}.png">
                </td>
                <td class="details">
                    <table>
                        <colgroup>
                            <col width="10%">
                            <col width="90%">
                        </colgroup>
                        <tbody>
                            <tr>
                                <td class="CardHeader">   Assignee: </td>
                                <td>{{"{{"}}:Assignee{{}}}}</td>
                            </tr>
                            <tr>
                                <td class="CardHeader">   Summary: </td>
                                <td>{{"{{"}}:Summary{{}}}}</td>
                            </tr>
                            <tr>
                                <td class="CardHeader">   Type: </td>
                                <td>{{"{{"}}:Type{{}}}}</td>
                            </tr>
                        </tbody>
                    </table>
                </td>
            </tr>
        </tbody>
    </table>
    </script>
    </html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Card template in JSP kanban control](Cards_images/cards_img2.png)

## Tooltip

You can enable HTML tooltip for Kanban card elements by setting `enable` property as true in `tooltipSettings`.

The following code example describes the above behavior.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="java.util.HashMap" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %><%@ page import="datasource.GetJsonData" %>
    <body>
	<div class="cols-sample-area"><%
    GetJsonData obj=new GetJsonData();
    Object data = obj.GetKanbanJson();
    request.setAttribute("KanbanDataSource",data);
    JSONParser parser = new JSONParser();
    %>
		<ej:kanban id="Kanban" keyField="Status" dataSource="${KanbanDataSource}">
			<ej:kanban-fields content="Summary"  tag="Tags" primaryKey="Id"></ej:kanban-fields>
			<ej:kanban-columns>
				<ej:kanban-column headerText="Backlog" key="Open"></ej:kanban-column>
				<ej:kanban-column headerText="In Progress" key="InProgress">
				</ej:kanban-column>
				<ej:kanban-column headerText="Done" key="Close"></ej:kanban-column>
			</ej:kanban-columns>
			<ej:kanban-tooltipSettings enable="true"></ej:kanban-tooltipSettings>
		</ej:kanban>
	</div>
    </body>
    </html>

{% endhighlight %}
 
The following output is displayed as a result of the above code example.

![Card tooltip in JSP kanban control](Cards_images/cards_img3.png)

### Template

By making use of template feature with tooltip, all the field names that are mapped from the `dataSource` can be accessed to define the `template` tooltip for card. The `tooltipSettings.enable` must be enabled first.

The following code example describes the tooltip template.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="java.util.HashMap" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %><%@ page import="datasource.GetJsonData" %>
    <body>
    <div class="cols-sample-area">
        <%
        GetJsonData obj=new GetJsonData();
        Object data = obj.GetKanbanJson();
        request.setAttribute("KanbanDataSource",data);
        JSONParser parser = new JSONParser();
        %>
        <ej:kanban id="Kanban" keyfield="Status" datasource="${KanbanDataSource}">
            <ej:kanban-fields content="Summary" tag="Tags" primarykey="Id"></ej:kanban-fields>
            <ej:kanban-columns>
                <ej:kanban-column headertext="Backlog" key="Open"></ej:kanban-column>
                <ej:kanban-column headertext="In Progress" key="InProgress">
                </ej:kanban-column>
                <ej:kanban-column headertext="Done" key="Close"></ej:kanban-column>
            </ej:kanban-columns>
            <ej:kanban-tooltipsettings template="#tooltipTemp" enable="true"></ej:kanban-tooltipsettings>
        </ej:kanban>
    </div>
    </body>
    <script id="tooltipTemp" type="text/x-jsrender">
    <div class='e-kanbantooltiptemplate'>
        <table>
            <tr>
                <td class="photo">
                    <img src="{{"{{"}}:ImgUrl{{}}}}">
                </td>
                <td class="details">
                    <table>
                        <colgroup>
                            <col width="30%">
                            <col width="70%">
                        </colgroup>
                        <tbody>
                            <tr>
                                <td class="CardHeader">Assignee:</td>
                                <td>{{"{{"}}:Assignee{{}}}}</td>
                            </tr>
                            <tr>
                                <td class="CardHeader">Type:</td>
                                <td>{{"{{"}}:Type{{}}}}</td>
                            </tr>
                            <tr>
                                <td class="CardHeader">Estimate:</td>
                                <td>{{"{{"}}:Estimate{{}}}}</td>
                            </tr>
                            <tr>
                                <td class="CardHeader">Summary:</td>
                                <td>{{"{{"}}:Summary{{}}}}</td>
                            </tr>
                        </tbody>
                    </table>
                </td>
            </tr>
        </table>
    </div>
    </script>
    <style>
    .details > table {
        width: 100%;
        margin-left: 2px;
        border-collapse: separate;
        border-spacing: 1px;
    }

    .e-kanbantooltiptemplate {
        width: 250px;
        padding: 3px;
    }

        .e-kanbantooltiptemplate > table {
            width: 100%;
        }

        .e-kanbantooltiptemplate td {
            vertical-align: top;
        }

    td.details {
        padding-left: 10px;
    }

    .CardHeader {
        font-weight: bolder;
    }
    </style>
    </html>

{% endhighlight %}

 
The following output is displayed as a result of the above code example.

![Card tooltip template in JSP kanban control](Cards_images/cards_img4.png)
