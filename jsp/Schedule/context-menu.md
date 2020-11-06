---
title: Schedule - Context Menu	
description: Default and Custom context menu options for appointments and cells in Scheduler
platform: jsp
control: schedule
documentation: ug
keywords: context-menu
---
# Context Menu

Scheduler provides default context menu options for both appointments as well as work cells. It also allows to define additional custom context menu options.

The options that are available under [contextMenuSettings](/api/js/ejschedule#members:contextmenusettings) are as follows,

* **enable** - Enables/disables the context menu option in Scheduler.
* **menuItems** - Contains the sub-menu collections related to both the appointment and cells.

## Default Menu Options

The menu items contains two separate collection based on the appointment and cells.

### Appointment

The appointment collection includes the following options.

<table>
    <tr>
        <td>Open Appointment (default)</td>
    </tr>
    <tr>
        <td>Delete Appointment (default)</td>
    </tr>
    <tr>
        <td>Print Appointment</td>
    </tr>
    <tr>
        <td>Categorize</td>
    </tr>
</table>

### Cells

The default options available within the cell collection includes -

<table>
    <tr>
        <td>New Appointment</td>
    </tr>
    <tr>
        <td>New Recurring Appointment</td>
    </tr>
    <tr>
        <td>Today</td>
    </tr>
    <tr>
        <td>Go to date</td>
    </tr>
    <tr>
        <td>Settings (View, TimeMode, Work Hours) </td>
    </tr>
</table>

The following code snippet shows how to enable the context menu settings in Scheduler and to make use of it with default available options.

{% highlight js %}

<%@ page import="datasource.schedule.*"%>
<%@ page import="java.util.ArrayList"%>
<%@ page import="java.util.Date"%>
<%@ page import="java.text.SimpleDateFormat"%>
<%
    ScheduleGetDataSource obj = new ScheduleGetDataSource();
    ArrayList<ScheduleDataSource> scheduleData = obj.getData();
    request.setAttribute("scheduleData", scheduleData);
    Date currentDate = new SimpleDateFormat("yyyy/MM/dd").parse("2016/5/4");

    ArrayList<HashMap<String, Object>> contextAppData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> appData1 = new HashMap<String, Object>();
    appData1.put("id", "open");
    appData1.put("text", "Open Appointment");
    contextData.add(appData1);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "delete");
    appData2.put("text", "Delete Appointment");
    contextData.add(appData2);

    ArrayList<HashMap<String, Object>> contextCellData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> cellData1 = new HashMap<String, Object>();
    cellData1.put("id", "new");
    cellData1.put("text", "New Appointment");
    contextData.add(cellData1);
    HashMap<String, Object> cellData2 = new HashMap<String, Object>();
    cellData2.put("id", "recurrence");
    cellData2.put("text", "New Recurring Appointment");
    contextData.add(cellData2);
    HashMap<String, Object> cellData3 = new HashMap<String, Object>();
    cellData3.put("id", "today");
    cellData3.put("text", "Today");
    contextData.add(cellData3);
    HashMap<String, Object> cellData4 = new HashMap<String, Object>();
    cellData4.put("id", "goToDate");
    cellData4.put("text", "Go to date");
    contextData.add(cellData4);
    HashMap<String, Object> cellData5 = new HashMap<String, Object>();
    cellData5.put("id", "settings");
    cellData5.put("text", "Settings");
    contextData.add(cellData5);
    HashMap<String, Object> cellData6 = new HashMap<String, Object>();
    cellData6.put("id", "view");
    cellData6.put("text", "View");
    cellData6.put("parentId", "settings");
    contextData.add(cellData6);
    HashMap<String, Object> cellData7 = new HashMap<String, Object>();
    cellData7.put("id", "timeMode");
    cellData7.put("text", "TimeMode");
    cellData7.put("parentId", "settings");
    contextData.add(cellData7);
    HashMap<String, Object> cellData8 = new HashMap<String, Object>();
    cellData8.put("id", "view_Day");
    cellData8.put("text", "Day");
    cellData8.put("parentId", "view");
    contextData.add(cellData8);
    HashMap<String, Object> cellData9 = new HashMap<String, Object>();
    cellData9.put("id", "view_Week");
    cellData9.put("text", "Week");
    cellData9.put("parentId", "view");
    contextData.add(cellData9);
    HashMap<String, Object> cellData10 = new HashMap<String, Object>();
    cellData10.put("id", "view_Workweek");
    cellData10.put("text", "Workweek");
    cellData10.put("parentId", "view");
    contextData.add(cellData10);
    HashMap<String, Object> cellData11 = new HashMap<String, Object>();
    cellData11.put("id", "view_Month");
    cellData11.put("text", "Month");
    cellData11.put("parentId", "view");
    contextData.add(cellData11);
    HashMap<String, Object> cellData12 = new HashMap<String, Object>();
    cellData12.put("id", "timeMode_Hour12");
    cellData12.put("text", "12 Hour");
    cellData12.put("parentId", "timeMode");
    contextData.add(cellData12);
    HashMap<String, Object> cellData13 = new HashMap<String, Object>();
    cellData13.put("id", "timeMode_Hour24");
    cellData13.put("text", "24 Hour");
    cellData13.put("parentId", "timeMode");
    contextData.add(cellData13);
    HashMap<String, Object> cellData14 = new HashMap<String, Object>();
    cellData14.put("id", "workhours");
    cellData14.put("text", "Work Hours");
    cellData14.put("parentId", "settings");
    contextData.add(cellData14);
%>

{% endhighlight %}

{% highlight html %}

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>">
    <ej:schedule-contextMenuSettings enable="true">
        <ej:schedule-contextMenuSettings-menuItems appointment="<%=contextAppData%>" cells="<%=contextCellData%>"></ej:schedule-contextMenuSettings-menuItems>
        </ej:schedule-contextMenuSettings>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> In agenda view, only the appointment menu items shows up in the context menu options. For default menu items, the id must be defined the same as mentioned in the above code example – as we have processed the menus based on this id within our source.

## Custom Menu Options

Apart from the default available options, it is also possible to add custom menu options to the context-menu of both the appointment and cell collection.

The following code example depicts how **to add the custom menu items** to the appointment and cell collection of the context menu settings.

{% highlight js %}

<%@ page import="datasource.schedule.*"%>
<%@ page import="java.util.ArrayList"%>
<%@ page import="java.util.Date"%>
<%@ page import="java.text.SimpleDateFormat"%>
<%
    ScheduleGetDataSource obj = new ScheduleGetDataSource();
    ArrayList<ScheduleDataSource> scheduleData = obj.getData();
    request.setAttribute("scheduleData", scheduleData);
    Date currentDate = new SimpleDateFormat("yyyy/MM/dd").parse("2016/5/4");

    ArrayList<HashMap<String, Object>> contextAppData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> appData1 = new HashMap<String, Object>();
    appData1.put("id", "open");
    appData1.put("text", "Open Appointment");
    contextAppData.add(appData1);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "delete");
    appData2.put("text", "Delete Appointment");
    contextAppData.add(appData2);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "option1");
    appData2.put("text", "User option 1");
    contextAppData.add(appData2);

    ArrayList<HashMap<String, Object>> contextCellData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> cellData1 = new HashMap<String, Object>();
    cellData1.put("id", "celloprion1");
    cellData1.put("text", "Custom option 1");
    contextCellData.add(cellData1);
%>

{% endhighlight %}

{% highlight html %}

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>">
    <ej:schedule-contextMenuSettings enable="true">
        <ej:schedule-contextMenuSettings-menuItems appointment="<%=contextAppData%>" cells="<%=contextCellData%>"></ej:schedule-contextMenuSettings-menuItems>
    </ej:schedule-contextMenuSettings>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> The **id** given for the custom menu items **must be unique** in both the appointment and cell collection.

## Handling Menu Actions

To define specific actions for a click made on the custom menu items, the client-side event [menuItemClick](/api/js/ejschedule#events:menuitemclick) can be used as depicted in the below code example.

{% highlight js %}

<%@ page import="datasource.schedule.*"%>
<%@ page import="java.util.ArrayList"%>
<%@ page import="java.util.Date"%>
<%@ page import="java.text.SimpleDateFormat"%>
<%
    ScheduleGetDataSource obj = new ScheduleGetDataSource();
    ArrayList<ScheduleDataSource> scheduleData = obj.getData();
    request.setAttribute("scheduleData", scheduleData);
    Date currentDate = new SimpleDateFormat("yyyy/MM/dd").parse("2016/5/4");

    ArrayList<HashMap<String, Object>> contextAppData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> appData1 = new HashMap<String, Object>();
    appData1.put("id", "open");
    appData1.put("text", "Open Appointment");
    contextData.add(appData1);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "delete");
    appData2.put("text", "Delete Appointment");
    contextData.add(appData2);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "option1");
    appData2.put("text", "User option 1");
    contextData.add(appData2);
%>

{% endhighlight %}

{% highlight html %}

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>" menuItemClick="onMenuItemClick">
    <ej:schedule-contextMenuSettings enable="true">
        <ej:schedule-contextMenuSettings-menuItems appointment="<%=contextAppData%>"></ej:schedule-contextMenuSettings-menuItems>
    </ej:schedule-contextMenuSettings>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

{% highlight javascript %}

function onMenuItemClick(args) {
    //args.events contains information of the clicked menu item.
    if (args.events.ID == "option1") {
        alert("Custom menu clicked");
    }
}

{% endhighlight %}

Also, it is possible to predict the target on which the right click is made, either on the cells or appointments with the use of the event [beforeContextMenuOpen](/api/js/ejschedule#events:beforecontextmenuopen). The below code example shows how to block the display of context menu, when right clicked on the cells by setting **args.cancel** as **true**.

{% highlight js %}

<%@ page import="datasource.schedule.*"%>
<%@ page import="java.util.ArrayList"%>
<%@ page import="java.util.Date"%>
<%@ page import="java.text.SimpleDateFormat"%>
<%
    ScheduleGetDataSource obj = new ScheduleGetDataSource();
    ArrayList<ScheduleDataSource> scheduleData = obj.getData();
    request.setAttribute("scheduleData", scheduleData);
    Date currentDate = new SimpleDateFormat("yyyy/MM/dd").parse("2016/5/4");

    ArrayList<HashMap<String, Object>> contextAppData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> appData1 = new HashMap<String, Object>();
    appData1.put("id", "open");
    appData1.put("text", "Open Appointment");
    contextData.add(appData1);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "delete");
    appData2.put("text", "Delete Appointment");
    contextData.add(appData2);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "option1");
    appData2.put("text", "User option 1");
    contextData.add(appData2);
%>

{% endhighlight %}

{% highlight html %}

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>" beforeContextMenuOpen="onBeforeContextMenuOpen">
    <ej:schedule-contextMenuSettings enable="true">
        <ej:schedule-contextMenuSettings-menuItems appointment="<%=contextAppData%>"></ej:schedule-contextMenuSettings-menuItems>
    </ej:schedule-contextMenuSettings>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

{% highlight javascript %}

function onBeforeContextMenuOpen(args) {
    //args.events.target – target information to depict either cell/appointment
    if ($(args.events.target).hasClass("e-workcells") || $(args.events.target).hasClass("e-monthcells"))
    args.cancel = true;
}

{% endhighlight %}

## Adding Categorize Option

To include the default categorize option within the context menu, it is necessary to enable the [categorizeSettings](/api/js/ejschedule#members:categorizesettings) property as shown in the below code example.

{% highlight js %}

<%@ page import="datasource.schedule.*"%>
<%@ page import="java.util.ArrayList"%>
<%@ page import="java.util.Date"%>
<%@ page import="java.text.SimpleDateFormat"%>
<%
    ScheduleGetDataSource obj = new ScheduleGetDataSource();
    ArrayList<ScheduleDataSource> scheduleData = obj.getData();
    request.setAttribute("scheduleData", scheduleData);
    Date currentDate = new SimpleDateFormat("yyyy/MM/dd").parse("2016/5/4");

    ArrayList<HashMap<String, Object>> contextAppData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> appData1 = new HashMap<String, Object>();
    appData1.put("id", "open");
    appData1.put("text", "Open Appointment");
    contextData.add(appData1);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "delete");
    appData2.put("text", "Delete Appointment");
    contextData.add(appData2);
    HashMap<String, Object> appData2 = new HashMap<String, Object>();
    appData2.put("id", "option1");
    appData2.put("text", "User option 1");
    contextData.add(appData2);
%>

{% endhighlight %}

{% highlight html %}

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>">
    <ej:schedule-categorizeSettings enable="true"></ej:schedule-categorizeSettings>
    <ej:schedule-contextMenuSettings enable="true">
        <ej:schedule-contextMenuSettings-menuItems appointment="<%=contextAppData%>"></ej:schedule-contextMenuSettings-menuItems>
    </ej:schedule-contextMenuSettings>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> The **categorize** option must be added only to the **appointment** collection, which displays on right clicking the appointments.

## Remote Data Binding for Categorize

In Schedule, we can also binding the categorize datasource using remote data. The below code example shows how to bind the datasource to categorizeSettings.

{% highlight js %}

<%@ page import="datasource.schedule.*"%>
<%@ page import="java.util.ArrayList"%>
<%@ page import="java.util.Date"%>
<%@ page import="java.text.SimpleDateFormat"%>
<%
    ScheduleGetDataSource obj = new ScheduleGetDataSource();
    ArrayList<ScheduleDataSource> scheduleData = obj.getData();
    request.setAttribute("scheduleData", scheduleData);
    Date currentDate = new SimpleDateFormat("yyyy/MM/dd").parse("2016/5/4");
%>

{% endhighlight %}

{% highlight html %}

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>">
    <ej:schedule-categorizeSettings enable="true" allowMultiple="true" id="Id" text="Text" color="Color" fontColor="Fontcolor">
        <ej:dataManager url="Home/GetCategorizeData" adaptor="UrlAdaptor"></ej:dataManager>
    </ej:schedule-categorizeSettings>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

The server-side controller code to handle the CRUD operations are as follows.

{% highlight c# %}

public JsonResult GetCategorizeData()
{
    // ScheduleDataDataContext is a LINQ-to-SQL data class name that is defined in the .dbml file to access the tables from the database
    IEnumerable data = new ScheduleDataDataContext().CategoryData;
    return Json(data, JsonRequestBehavior.AllowGet);
}

{% endhighlight %}
