---
title: Schedule - Views
description: View options available in Scheduler
platform: jsp
control: schedule
documentation: ug
keywords: day, week, workweek, month, timeline, horizontal, custom
---
# Views

The number of days and its associated appointments are usually grouped together in Scheduler to organize different views. The available view options in Scheduler are as follows,

* Day
* Week
* Workweek
* Month
* Custom View
* Agenda
* Timeline View

Usually these view options are displayed as a toolbar in the date-header section of the Schedule control. The items within the views toolbar can be added/removed based on the value passed to the [views](/api/js/ejschedule#members:views) property.

By default, the Schedule control’s active view is **Week** view. Also, it is possible to change the active view of the Scheduler by setting [currentView](/api/js/ejschedule#members:currentview) option with the required view name as depicted below.

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
    String[] scheduleViews = { "Day", "WorkWeek" };
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" views="<%=scheduleViews%>" currentView="workweek">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> The **currentView** property accepts both the `string` and `ej.Schedule.CurrentView` enum value.

## Day

It represents a single day Scheduler view (single date display) with all its related appointments.

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

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" currentView="day">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

## Week

It’s a view displaying a count of 7 days (from Sunday to Saturday) with all its related appointments. The first day of the week can be changed using the [firstDayOfWeek](/api/js/ejschedule#members:firstdayofweek) API which accepts either the `integer` (Sunday=0, Monday=1, Tuesday=2, etc) or `string` (“Sunday”, “Monday”, etc) or `ej.Schedule.DayOfWeek` enum type value. The default value of this **firstDayOfWeek** depends on the current culture (language) used in the Scheduler.

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

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" currentView="week" firstDayOfWeek="monday">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

## Work Week

Work week view displays the working days of the week (count of 5 days) and its associated appointments. It is also possible to customize the days to be displayed in the work week view using [workWeek](/api/js/ejschedule#members:workweek) API which accepts the string array such as ["Monday", "Tuesday", "Wednesday", "Thursday" and "Friday"]. By default, it renders from Monday to Friday (5 days).

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
    String[] weekDays = { "Monday", "Tuesday", "Thursday", "Friday", "Saturday" };
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" currentView="workweek" workWeek="<%=weekDays%>">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

## Month

Month view displays the entire days of a particular month and all its related appointments. An alternative way to navigate to a particular date in a day view directly from Month view, clicking on the appropriate month cell date header will do so. If the week date range column is clicked, it will navigate to the corresponding week view.

The next and previous month date cells in the Month view can be shown/hidden on the Scheduler using [showNextPrevMonth](/api/js/ejschedule#members:shownextprevmonth) property by setting it to *false*.

For example – To set the Month view as current view in Scheduler and to hide the other month days in it, refer the below code example.

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

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" currentView="month" showNextPrevMonth="false">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> An appointment directly created in Month view will be considered as an all-day appointment.

## Custom

The Scheduler can be displayed with the user-specified date ranges, such as 4 days or any specific date ranges instead of default view options, by making use of the [renderDates](/api/js/ejschedule#members:renderdates) property. This property includes two sub properties namely **start** and **end**, which accepts the date object or date value in string format to specify the date range.

To display the custom view option in the toolbar-like view options in the scheduler header area, add the `CustomView` value to the views property array collection as shown below.

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
    Date startDate = new SimpleDateFormat("yyyy/MM/dd").parse("2016/5/1");
    Date endDate = new SimpleDateFormat("yyyy/MM/dd").parse("2016/5/6");
    String[] scheduleViews = { "Day", "Week", "WorkWeek", "Month", "CustomView" };
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" views="<%=scheduleViews%>" currentView="customview">
    <ej:schedule-renderDates start="<%=startDate%>" end="<%=endDate%>"></ej:schedule-renderDates>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

When the date difference between the provided start and end date is greater than 7, then the month-like view will get displayed in Vertical Scheduler mode - whereas with the date difference less than 7 days displays the Scheduler with exact count of the specified days.

N> When the `currentDate` property of Scheduler is set with a date, that lies beyond the specified custom date range - then the Scheduler navigates to the current date with the mentioned date differences.

## Agenda

This View option lists out the appointments in a grid-like view for the next 7 days by default from the current date. The count of the number of appointments to be listed in this view can be customized using the [agendaViewSettings.daysInAgenda](/api/js/ejschedule#members:agendaviewsettings-daysinagenda).

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

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" currentView="agenda">
    <ej:schedule-agendaViewSettings daysInAgenda="5"></ej:schedule-agendaViewSettings>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> In Agenda view, the templates can be applied for the date and time columns which can be referred [here](/api/js/ejschedule#members:agendaviewsettings). Also, the template passed through the [appointmentTemplateID](/api/js/ejschedule#members:appointmenttemplateid) will gets applied to the event column in Agenda view.

## Restriction on View Navigation

It is possible to restrict the users to display only the specific list of views in the Schedule header section and also not to navigate to other views that are not listed.

**For example**, if the views property is set only with `Month` view – then the Schedule header section displays only the Month option in the view toolbar and also other additional available actions like navigating to day/week view on clicking the month header dates and week date-range is stopped.

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
    String[] scheduleViews = { "Month" };
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" views="<%=scheduleViews%>">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> Even though Week view is the active view in Scheduler by default, if it is not listed in the views collection – then the first listed option in the views collection will be taken as current view of the Scheduler.

## Timeline View

Timeline view displays the day, time and its associated events horizontally arranged from left to right. By default, Scheduler renders in vertical mode and it can be changed to the timeline mode using [orientation](/api/js/ejschedule#members:orientation) property which accepts both the `string` and `ej.Schedule.Orientation` enum value.

All the applicable features in Vertical mode works similar with Timeline mode (Horizontal) and only the visualization of the layout changes based on the orientation.

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
    String[] scheduleViews = { "Month" };
%>

{% endhighlight %}

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:schedule id="Schedule1" width="100%" currentDate="<%=currentDate%>" orientation="horizontal">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}
