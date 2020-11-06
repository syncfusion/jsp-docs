---
layout: post
title: Globalization and Localization with Ribbon widget for Syncfusion Essential JS
description: How to use globalization and localization 
platform: jsp
control: Ribbon
documentation: ug
---
# Globalization and Localization

## Localization

The localization support allows to customize the display of text within the Ribbon in a user-specific culture and locale. The Ribbon control can be localized in specific culture using the common API `locale` along with the collection of localized words defined for that culture using the ej.Ribbon.Locale [culture-code].Please find the table with list of properties and its value in locale object.

N> By default, the Ribbon control is localized in `en-US` culture.

For further information on – how to refer the required culture scripts into your application

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %>
    <link rel="stylesheet" href="Content/ejthemes/ribbon-css/ej.icons.css">
    <body>
    <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li>
                    <a>New</a>
                </li>
                <li>
                    <a>Open</a>
                </li>

            </ul>
        </li>
    </ul>
    <div class="cols-sample-area">
        <%
        JSONParser parser = new JSONParser();
        request.setAttribute("paste_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-ribbon e-ribbonpaste\" }"));
        %>
        <ej:ribbon id="defaultRibbon" width="100%" locale="es-ES" showqat="true">
            <ej:ribbon-applicationtab type="menu" menuitemid="ribbonmenu"></ej:ribbon-applicationtab>
            <ej:ribbon-tabs>
                <ej:ribbon-tab id="home" text="Home">
                    <ej:ribbon-tab-groups>
                        <ej:ribbon-tab-group text="Clipboard" aligntype="columns">
                            <ej:ribbon-tab-group-contentcollection>
                                <ej:ribbon-tab-group-content>
                                    <ej:ribbon-tab-group-content-groups>
                                        <ej:ribbon-tab-group-content-group id="paste" text="paste" tooltip="Paste" quickaccessmode="toolbar" buttonsettings="${paste_buttonSettings}"></ej:ribbon-tab-group-content-group>
                                    </ej:ribbon-tab-group-content-groups>
                                    <ej:ribbon-tabs-groups-content-defaults type="button" width="50" height="70" isbig="true"></ej:ribbon-tabs-groups-content-defaults>
                                </ej:ribbon-tab-group-content>
                            </ej:ribbon-tab-group-contentcollection>
                        </ej:ribbon-tab-group>
                    </ej:ribbon-tab-groups>
                </ej:ribbon-tab>
            </ej:ribbon-tabs>
        </ej:ribbon>
    </div>
    </body>
    <style>
    .e-ribbon .e-rbnquickaccessbar .e-ribbonpaste:before {
        font-size: 27px;
        left: -5px;
        top: -6px;
    }
    </style>
    <script>
    ej.Ribbon.Locale["es-ES"] = {
        CustomizeQuickAccess: "Agordu Rapida Aliro",
        RemovefromQuickAccessToolbar: "Forigu de Rapida Aliro Ilobreto",
        AddtoQuickAccessToolbar: "Aldoni al Rapida Aliro Ilobreto",
        ShowAbovetheRibbon: "Montru Super la Ribbona",
        ShowBelowtheRibbon: "Montru Sube la Ribbon",
        MoreCommands: "pli Komando"
    };
    </script>
    </html>
	
{% endhighlight %}

![](Globalizationandlocalization_images/Globalizationandlocalization._img1.png)

## Right to Left - RTL

By default, Ribbon render its content and layout from left to right. To customize Ribbon direction, you can change direction from LTR to RTL by using `enableRTL` as true.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %>
    <link rel="stylesheet" href="Content/ejthemes/ribbon-css/ej.icons.css">
    <body>
    <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li>
                    <a>New</a>
                </li>
                <li>
                    <a>Open</a>
                </li>
            </ul>
        </li>
    </ul>
    <div class="cols-sample-area">
        <%
        JSONParser parser = new JSONParser();
        request.setAttribute("new_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"imagePosition\": \"imagetop\",\"prefixIcon\": \"e-icon e-ribbon e-new\" }"));
        request.setAttribute("paste_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-ribbon e-ribbonpaste\" }"));
        %>
        <ej:ribbon id="defaultRibbon" width="100%" enablertl="true">
            <ej:ribbon-applicationtab type="menu" menuitemid="ribbonmenu"></ej:ribbon-applicationtab>
            <ej:ribbon-tabs>
                <ej:ribbon-tab id="home" text="Home">
                    <ej:ribbon-tab-groups>
                        <ej:ribbon-tab-group text="New" aligntype="rows">
                            <ej:ribbon-tab-group-contentcollection>
                                <ej:ribbon-tab-group-content>
                                    <ej:ribbon-tab-group-content-groups>
                                        <ej:ribbon-tab-group-content-group id="new" text="New" tooltip="New" buttonsettings="${new_buttonSettings}"></ej:ribbon-tab-group-content-group>
                                    </ej:ribbon-tab-group-content-groups>
                                    <ej:ribbon-tabs-groups-content-defaults type="button" height="70" width="60"></ej:ribbon-tabs-groups-content-defaults>
                                </ej:ribbon-tab-group-content>
                            </ej:ribbon-tab-group-contentcollection>
                        </ej:ribbon-tab-group>
                        <ej:ribbon-tab-group text="Clipboard" aligntype="columns">
                            <ej:ribbon-tab-group-contentcollection>
                                <ej:ribbon-tab-group-content>
                                    <ej:ribbon-tab-group-content-groups>
                                        <ej:ribbon-tab-group-content-group id="paste" text="paste" tooltip="Paste" quickaccessmode="toolbar" buttonsettings="${paste_buttonSettings}"></ej:ribbon-tab-group-content-group>
                                    </ej:ribbon-tab-group-content-groups>
                                    <ej:ribbon-tabs-groups-content-defaults type="button" width="50" height="70" isbig="true"></ej:ribbon-tabs-groups-content-defaults>
                                </ej:ribbon-tab-group-content>
                            </ej:ribbon-tab-group-contentcollection>
                        </ej:ribbon-tab-group>
                    </ej:ribbon-tab-groups>
                </ej:ribbon-tab>

            </ej:ribbon-tabs>
        </ej:ribbon>
    </div>
    </body>
    </html>

{% endhighlight %}

![](Globalizationandlocalization_images/Globalizationandlocalization._img2.png)


