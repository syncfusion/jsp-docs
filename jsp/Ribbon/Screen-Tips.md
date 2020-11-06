---
layout: post
title:  Screen Tips
description: screen tips
documentation: ug
platform: jsp
keywords: screen tips,ribbon screen tips
---

# Screen Tips

ScreenTip/Tooltip is used to reduce the controls related Help that are needed to the end user to do control related actions.

## HTML Tooltip

Standard `html tooltip` can be set using `tooltip` property of each group item.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %>
    <link rel="stylesheet" href="Content/ejthemes/ribbon-css/ej.icons.css" >
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
		request.setAttribute("copy_buttonSettings",parser.parse("{\"contentType\": \"textandimage\",\"prefixIcon\": \"e-icon e-ribbon e-ribboncopy\" }"));
	    %>
			<ej:ribbon id="defaultRibbon" width="65%" isResponsive="true">
				<ej:ribbon-applicationTab type="menu" menuItemID="ribbonmenu"></ej:ribbon-applicationTab>
				<ej:ribbon-tabs>
					<ej:ribbon-tab id="home" text="Home">
						<ej:ribbon-tab-groups>
							<ej:ribbon-tab-group text="Clipboard" alignType="rows">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="cut" text="Cut" toolTip="Remove the selection and put it on clipboard"></ej:ribbon-tab-group-content-group>
											<ej:ribbon-tab-group-content-group id="copy" text="Copy" toolTip="Put a copy of selection on clipboard" buttonSettings="${copy_buttonSettings}"></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" width="60" isBig="false"></ej:ribbon-tabs-groups-content-defaults>
									</ej:ribbon-tab-group-content>
								</ej:ribbon-tab-group-contentCollection>
							</ej:ribbon-tab-group>
						</ej:ribbon-tab-groups>
					</ej:ribbon-tab>
				</ej:ribbon-tabs>
			</ej:ribbon>
		</div>
	</body>
	<style>
    .cols-sample-area{
    width:80%;
    }
    </style>
    </html>
     
{% endhighlight %}

![](Screen-Tips_images/Screen-Tips_img1.png)
