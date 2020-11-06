---
layout: post
title: Controls-Support
description: controls support
documentation: ug
platform: jsp
keywords: controls support,ribbon controls support
---

# Controls Support

Button, Split Button, DropdownList, Toggle button, Gallery and Custom controls can be added to each groups. You can set `type` property in group to define the controls. Default `type` is `button`. 

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
        <ej:ribbon id="defaultRibbon" width="65%" isresponsive="true">
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
                                        <ej:ribbon-tab-group-content-group id="paste" text="paste" tooltip="Paste" buttonsettings="${paste_buttonSettings}"></ej:ribbon-tab-group-content-group>
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
    .cols-sample-area {
        width: 80%;
    }
    </style>
    </html>
   
{% endhighlight %}

![](Controls-Support_images/Controls-Support_img1.png)
