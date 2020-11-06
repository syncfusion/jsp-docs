---
title: Schedule - Resource handling with multiple option
description: Handling multiple resources in Scheduler
platform: jsp
control: schedule
documentation: ug
keywords: resource, resources, multiple resources, grouping
---
# Resources

The Scheduler provides **Resources** support, with which the single Scheduler is shared by multiple resources simultaneously. Each resource in the Scheduler is arranged in a column/row wise, with individual spacing to display all its respective appointments on a single page. It also supports the grouping of resources, thus enabling the categorization of resources in a hierarchical structure and shows it either in expandable groups (**Horizontal** **view**) or else vertical hierarchy one after the other (**Vertical** **view**).

One or more resources can be assigned to the Scheduler appointments by making selection of the resource options available in the appointment window.

## Fields of Resources

The default options available within the [resources](/api/js/ejschedule#members:resources) collection are as follows,

### name (**String**)

A unique resource name which is used for differentiating various resource objects while grouping it in levels.

### title (**String**)

It holds the title name of the resource field to be displayed on the Scheduler appointment window.

### field (**String**)

It holds the name of the resource field to be bound to the Scheduler appointments which contains the resource Id.

### allowMultiple (**Boolean**)

When set to true, allows multiple selection of resource names, thus creating multiple instances of same appointment for the selected resources.

### resourceSettings (**Object**)

It holds the field names of the resources dataSource to be bound to the Scheduler.

The following are the resource fields which must be defined within the **resourceSettings** that holds the appropriate column names from the dataSource.

<table>
    <tr>
        <th>Field name<br/><br/></th>
        <th>Description<br/><br/></th>
    </tr>
    <tr>
        <td>text<br/><br/></td>
        <td>Binds the text field name in the dataSource to the resourceSettings <b>text</b>. These text gets listed out in the resources field of the appointment window. It’s mandatory.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>id<br/><br/></td>
        <td>Binds the id field name in the dataSource to the resourceSettings <b>id</b>. It’s mandatory.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>groupId<br/><br/></td>
        <td>Binds the groupId field name in the dataSource to the resourceSettings <b>groupId</b>. This field is not necessary for a resource object (resource data) defined as first level within the resources collection.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>color<br/><br/></td>
        <td>Binds the color field name in the dataSource to the resourceSettings <b>color</b>. It is optional.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>appointmentClass<br/><br/></td>
        <td>Binds the appointmentClass field name in the dataSource. It applies the custom CSS class name to the appointments based on the resources.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>start<br/><br/></td>
        <td>Binds the starting work hour field name in the dataSource. It's optional, but when provided with some numeric value will set the starting work hour for specific resources.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>end<br/><br/></td>
        <td>Binds the end work hour field name in the dataSource. It's optional, but when provided with some numeric value will set the end work hour for specific resources.<br/><br/><br/><br/></td>
    </tr>
    <tr>
        <td>workWeek<br/><br/></td>
        <td>Binds the resources working days field name in the dataSource. It's optional, and accept array of strings which is nothing but only the week day names. When provided with some values (array of day names), only those days will render for the specific resources.<br/><br/><br/><br/></td>
    </tr>
</table>

**Example**: To set the resources options using all the above specified fields,

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

    String[] group = { "Owners" };
    ArrayList<HashMap<String, Object>> resourceData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> res1 = new HashMap<String, Object>();
    res1.put("text", "Nancy");
    res1.put("id", 1);
    res1.put("color", "#f8a398");
    resourceData.add(res1);
    HashMap<String, Object> res2 = new HashMap<String, Object>();
    res2.put("text", "Steven");
    res2.put("id", 3);
    res2.put("color", "#56ca85");
    resourceData.add(res2);
    HashMap<String, Object> res3 = new HashMap<String, Object>();
    res3.put("text", "Michael");
    res3.put("id", 5);
    res3.put("color", "#51a0ed");
    resourceData.add(res3);
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>">
    <ej:schedule-group resources="<%=group%>"></ej:schedule-group>
    <ej:schedule-resources>
        <ej:schedule-resource allowMultiple="true" field="ownerId" name="Owners" title="Owner">
            <ej:schedule-resources-resourceSettings id="id" color="color" text="text" dataSource="<%=resourceData%>"></ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
    </ej:schedule-resources>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}" id="Id" subject="Subject" description="Description" startTime="StartTime" endTime="EndTime" allDay="AllDay" recurrence="Recurrence" recurrenceRule="RecurrenceRule" resourceFields="ownerId"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> The resource object defined at **first level** within the **resources** collection doesn’t make use of the **groupId** field, as there is no previous levels applicable to map.

## Data Binding

The resource data can be bound to the Schedule control through the **resourceSettings** options available within the **resources** property. The data-binding can be done either using JSON object collection or DataManager ([ej.DataManager](/js/datamanager/overview)) instance which contains the resources related data.

### JSON Data

**Example**: To set the resource data with array of **JSON** object collection

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

    String[] group = { "Owners" };
    ArrayList<HashMap<String, Object>> resourceData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> res1 = new HashMap<String, Object>();
    res1.put("text", "Nancy");
    res1.put("id", 1);
    res1.put("color", "#f8a398");
    resourceData.add(res1);
    HashMap<String, Object> res2 = new HashMap<String, Object>();
    res2.put("text", "Steven");
    res2.put("id", 3);
    res2.put("color", "#56ca85");
    resourceData.add(res2);
    HashMap<String, Object> res3 = new HashMap<String, Object>();
    res3.put("text", "Michael");
    res3.put("id", 5);
    res3.put("color", "#51a0ed");
    resourceData.add(res3);
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>">
    <ej:schedule-group resources="<%=group%>"></ej:schedule-group>
    <ej:schedule-resources>
        <ej:schedule-resource allowMultiple="true" field="ownerId" name="Owners" title="Owner">
            <ej:schedule-resources-resourceSettings id="id" color="color" text="text" dataSource="<%=resourceData%>"></ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
    </ej:schedule-resources>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}" id="Id" subject="Subject" description="Description" startTime="StartTime" endTime="EndTime" allDay="AllDay" recurrence="Recurrence" recurrenceRule="RecurrenceRule" resourceFields="ownerId"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

### Remote Data

**Example**: To set the resource data through the instance of **ejDataManager**

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
    String[] selectData = { "CategoryID", "CategoryName" };
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>">
    <ej:schedule-resources>
        <ej:schedule-resource allowMultiple="true" field="ownerId" name="Owners" title="Owner">
            <ej:schedule-resources-resourceSettings id="CategoryID" text="CategoryName">
                <ej:dataManager url="http://mvc.syncfusion.com/OdataServices/Northwnd.svc"></ej:dataManager>
                <ej:query select="<%=selectData%>" from="Categories" take="3"></ej:query>
            </ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
    </ej:schedule-resources>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}" id="Id" subject="Subject" description="Description" startTime="StartTime" endTime="EndTime" allDay="AllDay" recurrence="Recurrence" recurrenceRule="RecurrenceRule" resourceFields="ownerId"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

## Multiple Resources (Without Grouping)

It is possible to display the Scheduler in default look without visually showcasing all the resources on it, but it allow the user to assign the required resources to the appointments through the appointment window resource options.

The appointments belonging to all the resources will be displayed on the Scheduler which will be differentiated based on the resource color assigned in the **resourceSettings** (depicting to which resource that particular appointment belongs).

**Example**: To display default Scheduler with multiple resource options in the appointment window,

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

    ArrayList<HashMap<String, Object>> resourceData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> res1 = new HashMap<String, Object>();
    res1.put("text", "Nancy");
    res1.put("id", 1);
    res1.put("color", "#f8a398");
    resourceData.add(res1);
    HashMap<String, Object> res2 = new HashMap<String, Object>();
    res2.put("text", "Steven");
    res2.put("id", 3);
    res2.put("color", "#56ca85");
    resourceData.add(res2);
    HashMap<String, Object> res3 = new HashMap<String, Object>();
    res3.put("text", "Michael");
    res3.put("id", 5);
    res3.put("color", "#51a0ed");
    resourceData.add(res3);
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>">
    <ej:schedule-resources>
        <ej:schedule-resource allowMultiple="true" field="ownerId" name="Owners" title="Owner">
            <ej:schedule-resources-resourceSettings id="id" color="color" text="text" dataSource="<%=resourceData%>"></ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
    </ej:schedule-resources>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}" id="Id" subject="Subject" description="Description" startTime="StartTime" endTime="EndTime" allDay="AllDay" recurrence="Recurrence" recurrenceRule="RecurrenceRule" resourceFields="ownerId"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> Setting **allowMultiple** to **true** in the above code snippet allows the user to select multiple resources in the appointment window and also creates multiple copies of the same appointment in the Scheduler for each resources while saving.

## Grouping

Scheduler supports both single and multiple levels of resource grouping that can be customized either in horizontal or vertical Scheduler views. In Vertical view - the levels are displayed in a tree structure one after the other, but in horizontal view – the levels are grouped in a vertically expandable/collapsible structure.

### Single-Level

This type of grouping allows the Scheduler to display all the resources at a single level simultaneously. The appointments will make use of the **color** defined for the first resource instance as its background color.

**Example**: To display the Scheduler with single level resource grouping options,

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

    String[] group = { "Owners" };
    ArrayList<HashMap<String, Object>> resourceData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> res1 = new HashMap<String, Object>();
    res1.put("text", "Nancy");
    res1.put("id", 1);
    res1.put("color", "#f8a398");
    resourceData.add(res1);
    HashMap<String, Object> res2 = new HashMap<String, Object>();
    res2.put("text", "Steven");
    res2.put("id", 3);
    res2.put("color", "#56ca85");
    resourceData.add(res2);
    HashMap<String, Object> res3 = new HashMap<String, Object>();
    res3.put("text", "Michael");
    res3.put("id", 5);
    res3.put("color", "#51a0ed");
    resourceData.add(res3);
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>">
    <ej:schedule-group resources="<%=group%>"></ej:schedule-group>
    <ej:schedule-resources>
        <ej:schedule-resource allowMultiple="true" field="ownerId" name="Owners" title="Owner">
            <ej:schedule-resources-resourceSettings id="id" color="color" text="text" dataSource="<%=resourceData%>"></ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
    </ej:schedule-resources>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}" id="Id" subject="Subject" description="Description" startTime="StartTime" endTime="EndTime" allDay="AllDay" recurrence="Recurrence" recurrenceRule="RecurrenceRule" resourceFields="ownerId"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> The **name** field mentioned in the **resource** object needs to be specified within the **group** property in order to enable the grouping option in Scheduler.

### Multi-Level

This type of grouping displays the resources in the Scheduler at multiple levels with a set of resources grouped under each parent. The appointments will make use of the **color** defined for the first/top level resource instance as its background color.

**Example**: To display the Scheduler with multiple level resource grouping options,

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

    String[] group = { "Rooms", "Owners" };
    ArrayList<HashMap<String, Object>> roomData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> room1 = new HashMap<String, Object>();
    room1.put("text", "ROOM 1");
    room1.put("id", 1);
    room1.put("groupId", 1);
    room1.put("color", "#cb6bb2");
    roomData.add(room1);
    HashMap<String, Object> room2 = new HashMap<String, Object>();
    room2.put("text", "ROOM 2");
    room2.put("id", 2);
    room2.put("groupId", 1);
    room2.put("color", "#56ca85");
    roomData.add(room2);
    HashMap<String, Object> room3 = new HashMap<String, Object>();
    room3.put("text", "ROOM 3");
    room3.put("id", 3);
    room3.put("groupId", 1);
    room3.put("color", "#f8a398");
    roomData.add(room3);

    ArrayList<HashMap<String, Object>> resourceData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> owner1 = new HashMap<String, Object>();
    owner1.put("text", "Nancy");
    owner1.put("id", 1);
    owner1.put("groupId", 1);
    owner1.put("color", "#ffaa00");
    resourceData.add(owner1);
    HashMap<String, Object> owner2 = new HashMap<String, Object>();
    owner2.put("text", "Steven");
    owner2.put("id", 3);
    owner2.put("groupId", 2);
    owner2.put("color", "#f8a398");
    resourceData.add(owner2);
    HashMap<String, Object> owner3 = new HashMap<String, Object>();
    owner3.put("text", "Michael");
    owner3.put("id", 5);
    owner3.put("groupId", 1);
    owner3.put("color", "#51a0ed");
    resourceData.add(owner3);
    HashMap<String, Object> owner4 = new HashMap<String, Object>();
    owner4.put("text", "Laura");
    owner4.put("id", 7);
    owner4.put("groupId", 2);
    owner4.put("color", "#ffaa00");
    resourceData.add(owner4);
    HashMap<String, Object> owner5 = new HashMap<String, Object>();
    owner5.put("text", "Robert");
    owner5.put("id", 8);
    owner5.put("groupId", 1);
    owner5.put("color", "#f8a398");
    resourceData.add(owner5);
    HashMap<String, Object> owner6 = new HashMap<String, Object>();
    owner6.put("text", "Janet");
    owner6.put("id", 4);
    owner6.put("groupId", 2);
    owner6.put("color", "#51a0ed");
    resourceData.add(owner6);
    HashMap<String, Object> owner7 = new HashMap<String, Object>();
    owner7.put("text", "Milan");
    owner7.put("id", 13);
    owner7.put("groupId", 3);
    owner7.put("color", "#99ff99");
    resourceData.add(owner7);
    HashMap<String, Object> owner8 = new HashMap<String, Object>();
    owner8.put("text", "Paul");
    owner8.put("id", 15);
    owner8.put("groupId", 3);
    owner8.put("color", "#cc99ff");
    resourceData.add(owner8);
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>">
    <ej:schedule-group resources="<%=group%>"></ej:schedule-group>
    <ej:schedule-resources>
        <ej:schedule-resource allowMultiple="false" field="roomId" name="Rooms" title="Room">
            <ej:schedule-resources-resourceSettings id="id" groupId="groupId" color="color" text="text" dataSource="<%=roomData%>"></ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
        <ej:schedule-resource allowMultiple="true" field="ownerId" name="Owners" title="Owner">
            <ej:schedule-resources-resourceSettings id="id" groupId="groupId" color="color" text="text" dataSource="<%=resourceData%>"></ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
    </ej:schedule-resources>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}" id="Id" subject="Subject" description="Description" startTime="StartTime" endTime="EndTime" allDay="AllDay" recurrence="Recurrence" recurrenceRule="RecurrenceRule" resourceFields="roomId,ownerId"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> Here, the appointments will make use of the **color** defined for the Owners resource instance as its background color.

## Different Working days and Hours for Resources

It is possible to assign different workdays and workhours for each resources present within the Scheduler. The process of assigning different working days for every individual resources is applicable only for the vertical Scheduler mode and not for timeline view, whereas the customization of workhours for each resources is applicable on both the Scheduler orientation.  The custom workdays and workhours needs to be defined within the `resourceSettings` property using the following 3 sub-properties available within it.

* [start](/api/js/ejschedule#members:resources-resourcesettings-start) is used to define the work start hour for each individual resources.
* [end](/api/js/ejschedule#members:resources-resourcesettings-end) is used to define the work end hour for each individual resources.
* [workWeek](/api/js/ejschedule#members:resources-resourcesettings-workWeek) is used to define different working days for each individual resources.

**Example**: To display the Scheduler with each individual resources having different workhours and workdays, the code example is depicted below.

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

    String[] group = { "Rooms", "Owners" };
    ArrayList<HashMap<String, Object>> roomData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> room1 = new HashMap<String, Object>();
    room1.put("text", "ROOM 1");
    room1.put("id", 1);
    room1.put("groupId", 1);
    room1.put("color", "#cb6bb2");
    roomData.add(room1);
    HashMap<String, Object> room2 = new HashMap<String, Object>();
    room2.put("text", "ROOM 2");
    room2.put("id", 2);
    room2.put("groupId", 1);
    room2.put("color", "#56ca85");
    roomData.add(room2);

    String[] ownerDays1 = { "monday", "wednesday", "friday" };
    String[] ownerDays2 = { "tuesday", "thursday" };
    String[] ownerDays3 = { "sunday", "tuesday", "thursday", "saturday" };

    ArrayList<HashMap<String, Object>> resourceData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> owner1 = new HashMap<String, Object>();
    owner1.put("text", "Nancy");
    owner1.put("id", 1);
    owner1.put("groupId", 1);
    owner1.put("color", "#ffaa00");
    owner1.put("on", "10");
    owner1.put("off", "18");
    owner1.put("customDays", "<%=ownerDays1%>");
    resourceData.add(owner1);
    HashMap<String, Object> owner2 = new HashMap<String, Object>();
    owner2.put("text", "Steven");
    owner2.put("id", 3);
    owner2.put("groupId", 2);
    owner2.put("color", "#f8a398");
    owner2.put("on", "6");
    owner2.put("off", "10");
    owner2.put("customDays", "<%=ownerDays2%>");
    resourceData.add(owner2);
    HashMap<String, Object> owner3 = new HashMap<String, Object>();
    owner3.put("text", "Michael");
    owner3.put("id", 5);
    owner3.put("groupId", 1);
    owner3.put("color", "#51a0ed");
    owner3.put("on", "11");
    owner3.put("off", "15");
    owner3.put("customDays", "<%=ownerDays3%>");
    resourceData.add(owner3);
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>">
    <ej:schedule-group resources="<%=group%>"></ej:schedule-group>
    <ej:schedule-resources>
        <ej:schedule-resource allowMultiple="false" field="roomId" name="Rooms" title="Room">
            <ej:schedule-resources-resourceSettings id="id" groupId="groupId" color="color" text="text" dataSource="<%=roomData%>"></ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
        <ej:schedule-resource allowMultiple="true" field="ownerId" name="Owners" title="Owner">
            <ej:schedule-resources-resourceSettings id="id" groupId="groupId" color="color" text="text" start="on" end="off" workWeek="customDays" dataSource="<%=resourceData%>"></ej:schedule-resources-resourceSettings>
        </ej:schedule-resource>
    </ej:schedule-resources>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}" id="Id" subject="Subject" description="Description" startTime="StartTime" endTime="EndTime" allDay="AllDay" recurrence="Recurrence" recurrenceRule="RecurrenceRule" resourceFields="roomId,ownerId"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}
