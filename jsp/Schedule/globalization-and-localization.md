---
title: Globalization and Localization
description: Globalizing and localizing Scheduler
platform: jsp
control: schedule
documentation: ug
keywords: globalize, localize, localization, globalization
---
# Globalization and Localization

## Globalization

The Scheduler control is built with default **globalization** support as it format the dates according to the user’s locale automatically and processes it internally without any need for manual conversions. This kind of default handling of Scheduler dates is achieved through the built-in **ej.globalize** library which globalize the date, day and month names accordingly.

## Localization

Scheduler also comes with default localization support which allows it to customize the display of text within the Scheduler in a user-specific culture and locale. The Schedule control can be localized in specific culture using the common API [locale](/api/js/ejschedule#members:locale) along with the collection of localized words defined for that culture using the ej.Schedule.Locale [**culture-code**].

N> By default, the Schedule control is localized in **en-US** culture.

To localize Scheduler into any particular culture, it is necessary to refer the culture-specific script files in your application after the reference of **ej.web.all.min.js** file, which are available under the following location.

_<**Installed location**>\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n_

The following code example shows how to localize the Schedule control in **fr-FR** culture.

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

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>" locale="fr-FR">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

{% highlight javascript %}

$(function () {
    ej.Schedule.Locale["fr-FR"] = {
        ReminderWindowTitle: "Fenêtre de rappel",
        CreateAppointmentTitle: "créer un rendez-",
        RecurrenceEditTitle: "Modifier répétition nomination",
        RecurrenceEditMessage: "Comment voulez-vous changer le cas dans la série?",
        RecurrenceEditOnly: "Seulement cette nomination",
        RecurrenceEditSeries: "La série entière",
        PreviousAppointment: "Nomination précédente",
        NextAppointment: "prochain rendez-vous",
        AppointmentSubject: "sujet",
        StartTime: "Heure de début",
        EndTime: "Heure de fin",
        AllDay: "toute la journée",
        Today: "aujourd'hui",
        Recurrence: "répétition",
        Done: "Terminé",
        Cancel: "annuler",
        Ok: "Ok",
        RepeatBy: "Répétez par",
        RepeatEvery: "répéter chaque",
        RepeatOn: "répéter l'opération sur",
        StartsOn: "démarre sur",
        Ends: "extrémités",
        Summary: "résumé",
        Daily: "quotidien",
        Weekly: "hebdomadaire",
        Monthly: "mensuel",
        Yearly: "annuel",
        Every: "tous",
        EveryWeekDay: "chaque jour de la semaine",
        Never: "jamais",
        After: "après",
        Occurrence: "apparition",
        On: "sur",
        Edit: "Modifier",
        RecurrenceDay: "Jour (s)",
        RecurrenceWeek: "Semaine (s)",
        RecurrenceMonth: "Mois (s)",
        RecurrenceYear: "Année (s)",
        The: "la",
        OfEvery: "de chaque",
        First: "première",
        Second: "deuxième",
        Third: "troisième",
        Fourth: "quatrième",
        Last: "dernier",
        WeekDay: "jour de la semaine",
        WeekEndDay: "Jour de week-end",
        Subject: "sujet",
        Categorize: "Catégories",
        DueIn: "En raison",
        DismissAll: "rejeter tout",
        Dismiss: "rejeter",
        OpenItem: "Ouvrir l'élément",
        Snooze: "répétition",
        Day: "jour",
        Week: "semaine",
        WorkWeek: "Semaine de travail",
        Month: "mois",
        AddEvent: "Ajouter événement",
        CustomView: "Vue personnalisée",
        Agenda: "ordre du jour",
        Detailed: "détaillé",
        EventBeginsin: "Nomination commence dans",
        Editevent: "Modifier nomination",
        Editseries: "Modifier série",
        Times: "fois",
        Until: "jusqu'à",
        Eventwas: "rendez-vous était",
        Hours: "hrs",
        Minutes: "minutes",
        Overdue: "en retard",
        Days: "jour (s)",
        Event: "Sujet",
        Select: "sélectionner",
        Previous: "prev",
        Next: "suivant",
        Close: "proche",
        Delete: "effacer",
        Date: "date",
        Showin: "montrer en",
        Gotodate: "Aller à la date",
        Resources: "RESSOURCES",
        RecurrenceDeleteTitle: "Supprimer répétition rendez-",
        Location: "emplacement",
        Priority: "priorité",
        RecurrenceAlert: "alerte",
        WrongPattern: "Le modèle de récurrence est pas valable",
        CreateError: "La durée de la nomination doit être plus courte que la façon dont elle se produit fréquemment. Raccourcir la durée ou changer le modèle de récurrence dans la boîte de dialogue Récurrence de rendez.",
        DragResizeError: "Impossible de replanifier une occurrence du rendez-vous récurrent. si elle saute sur une occurrence ultérieure du même rendez-vous.",
        StartEndError: "L'heure de fin doit être supérieur à l'heure de début",
        MouseOverDeleteTitle: "supprimer un rendez-",
        DeleteConfirmation: "Êtes-vous sûr de vouloir supprimer ce rendez-vous?",
        Time: "Temps"
    };
});

{% endhighlight %}

N> Refer the **ej.culture.fr-FR.min.js** file in your HTML application and also define the **locale** property for the Schedule control with the appropriate **culture-code** [**fr-FR**].

For further information on – how to refer the required culture scripts into your application, refer [here](/jsp/localization).

### Localizing Specific Words

To customize or localize only some specific words in the default `ej.Schedule.Locale["en-US"]` collection, the words to be localized/customized can be defined in a separate variable and then extended to the original collection as depicted in the following code example.

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
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

{% highlight javascript %}

var customizationMessage = {
    // customize the appointment window title
    CreateAppointmentTitle: "Create Event",
    // customize the view options text in the Schedule header
    Day: "1 Day",
    Week: "7 Days",
    WorkWeek: "5 Days",
    Month: "Month"
};

// Extend only the required changes to the original locale collection
$.extend(ej.Schedule.Locale["en-US"], customizationMessage);

{% endhighlight %}

## Time Zone

The Scheduler makes use of the System time zone by default. If it needs to follow some other user-specific time zone, then the API [timeZone](/api/js/ejschedule#members:timezone) can be used. Also, the Scheduler can be set to observe the Daylight Saving Time (DST) with its **isDST** property which is set to **false** by default.

When [isDST](/api/js/ejschedule#members:isdst) property is set to **true**, the Scheduler internally processes the time difference values (for the Start and end time of the appointments) related to the Scheduler time zone that observes daylight savings time.

The following code example shows the way to set the specific time zone value with the daylight savings time observed in the Scheduler.

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

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>" timeZone="UTC +05:30" isDST="true">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

### Setting different TimeZone for Scheduler Appointments

Apart from the default action of applying specific timezone to the entire Scheduler, it is also possible to set different time zone values for each appointments through the properties **startTimeZone** and **endTimeZone** which can be defined as separate fields within the appointment dataSource. When these properties are not explicitly defined for appointments, the appointments Start and End time will be processed based on the Scheduler time zone.

N> The **isDST** property closely relies on the appointment fields like [StartTimeZone](/api/js/ejschedule#members:appointmentsettings-starttimezone) and [EndTimeZone](/api/js/ejschedule#members:appointmentsettings-endtimezone), for appropriate time difference calculations. If these two fields are not defined for appointments, then **isDST** depends on the System **timeZone** value.

The following code snippet shows how to define isDST and the time zones for specific appointments.

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

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>"isDST="true">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

### Customizing the TimeZone Collection

It is also possible to define or customize the default time zone collection of the Scheduler, by using the [timeZoneCollection](/api/js/ejschedule#members:timezonecollection) API as follows.

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

    ArrayList<HashMap<String, Object>> timeZoneData = new ArrayList<HashMap<String, Object>>();
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC -04:00");
    timeData.put("id", "10");
    timeData.put("value", "UTC -04:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC -03:30");
    timeData.put("id", "11");
    timeData.put("value", "UTC -03:30");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC -03:00");
    timeData.put("id", "12");
    timeData.put("value", "UTC -03:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC -02:00");
    timeData.put("id", "13");
    timeData.put("value", "UTC -02:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC -01:00");
    timeData.put("id", "14");
    timeData.put("value", "UTC -01:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC +00:00");
    timeData.put("id", "15");
    timeData.put("value", "UTC +00:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC +01:00");
    timeData.put("id", "16");
    timeData.put("value", "UTC +01:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC +02:00");
    timeData.put("id", "17");
    timeData.put("value", "UTC +02:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC +03:00");
    timeData.put("id", "18");
    timeData.put("value", "UTC +03:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC +04:00");
    timeData.put("id", "19");
    timeData.put("value", "UTC +04:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC +05:00");
    timeData.put("id", "20");
    timeData.put("value", "UTC +05:00");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC +05:30");
    timeData.put("id", "21");
    timeData.put("value", "UTC +05:30");
    timeZoneData.add(timeData);
    HashMap<String, Object> timeData = new HashMap<String, Object>();
    timeData.put("text", "UTC +06:00");
    timeData.put("id", "22");
    timeData.put("value", "UTC +06:00");
    timeZoneData.add(timeData);
%>

{% endhighlight %}

{% highlight html %}

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>">
    <ej:schedule-timeZoneCollection dataSource="<%=timeZoneData%>" text="text" id="id" value="value"></ej:schedule-timeZoneCollection>
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> The values defined within the **timeZoneCollection** dataSource are usually the only options displayed within the start and end time zone dropdown fields of the appointment window.

## Time Mode

The time mode of the Scheduler can be either **12** or **24 hours** format which is based on the [locale](/api/js/ejschedule#members:locale) set to the Scheduler. Since the default locale value of the Scheduler is **en-US**, therefore the time mode will be set to **12 hours** format (by default) automatically based on the culture.

The user can also set specific time mode for the Scheduler using [timeMode](/api/js/ejschedule#members:timemode) property which accepts either **String** or **enum** value. It accepts the following **enum** values,

* ej.Schedule.TimeMode.Hour12
* ej.Schedule.TimeMode.Hour24

The following code snippet shows the way to set specific **24 hour format** time mode for the Scheduler.

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

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>" timeMode="24">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> If the **timeMode** property is not set with specific value, then the value will be taken based on the locale assigned for the Scheduler.

## Date Format

Scheduler can be used with all valid date formats. The default date format used in Scheduler is “MM/dd/yyyy”.

If the [dateFormat](/api/js/ejschedule#members:dateformat) property is not specified particularly, then it will be taken based on the locale that is assigned to the Scheduler. The default locale applied on the Scheduler is “en-US”, which makes it to follow the “MM/dd/yyyy” pattern by default.

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

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>"dateFormat="yyyy/MM/dd">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

## First Day of Week

The [firstDayOfWeek](/api/js/ejschedule#members:firstdayofweek) property allows to set any of the week days as start of the week/workweek/month view in Scheduler. It accepts either the `integer` (Sunday=0, Monday=1, Tuesday=2, etc) or `string` (“Sunday”, “Monday”, etc) or `ej.Schedule.DayOfWeek` enum type value. The default value of this `firstDayOfWeek` depends on the current culture (language) assigned to the Scheduler.

To set different first day of week in Scheduler,

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

<ej:schedule id="Schedule1" width="100%" height="525px" currentDate="<%=currentDate%>" currentView="week" firstDayOfWeek="monday">
    <ej:schedule-appointmentSettings dataSource="${scheduleData}"></ej:schedule-appointmentSettings>
</ej:schedule>

{% endhighlight %}

N> The sub-control datepicker which is used within Scheduler for start/end time fields in appointment window and for date navigation purposes will also follow the same first day of week.
