---
layout: post
title:  Ribbon - Getting-Started
description: Getting-Started
documentation: ug
platform: jsp
keywords: getting started,ribbon getting started
---

# Getting Started

This section explains briefly how to create a `Ribbon`.

## Script & CSS Reference 

You can create an JSP application and add necessary scripts with the help of the given [JSP Getting Started Documentation.](https://help.syncfusion.com/jsp/getting-started)

## Control Initialization


Ribbon can be initialized with `Application Tab` and UL list is needed for binding menu to application menu which can be specified through `menuItemID` which denotes `id` of UL.

Define the Application Tab with `type` as `menu` to render simple Ribbon control.

{% highlight html %}

	<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
	<%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %>
	<%@ page import="com.syncfusion.*" %>
	<%@ page session="false" import="java.util.ArrayList" %>
	<%@ page session="false" import="java.util.Iterator" %>
	<%@ page session="false" import="org.json.simple.parser.JSONParser" %>
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
					<li>
						<a>Save</a>
					</li>
					<li>
						<a>Print</a>
					</li>
				</ul>
			</li>
		</ul>
		<div class="cols-sample-area">
			<ej:ribbon id="defaultRibbon" width="500px">
				<ej:ribbon-applicationTab type="menu" menuItemID="ribbonmenu"></ej:ribbon-applicationTab>
				<ej:ribbon-tabs>
					<ej:ribbon-tab id="home" text="Home">
						<ej:ribbon-tab-groups>
							<ej:ribbon-tab-group text="New" alignType="rows">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="new" text="New" toolTip="New" buttonSettings="${new_buttonSettings}"></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" height="70" width="60"></ej:ribbon-tabs-groups-content-defaults>
									</ej:ribbon-tab-group-content>
								</ej:ribbon-tab-group-contentCollection>
							</ej:ribbon-tab-group>	
						</ej:ribbon-tab-groups>
					</ej:ribbon-tab>
				</ej:ribbon-tabs>
			</ej:ribbon>
		</div>
	</body>
    </html>

{% endhighlight %}

![](/js/Ribbon/Getting-Started_images/Getting-Started_img1.png)

N> Set the required `width` to Ribbon, else default parent container or window width will be considered

## Adding Tabs

Tab is a set of related groups which are combined into single item. For creating Tab, `id` and `text` properties should be specified. 

{% highlight html %}

	<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
	<%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %>
	<%@ page import="com.syncfusion.*" %>
	<%@ page session="false" import="java.util.ArrayList" %>
	<%@ page session="false" import="java.util.Iterator" %>
	<%@ page session="false" import="org.json.simple.parser.JSONParser" %>
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
					<li>
						<a>Save</a>
					</li>
					<li>
						<a>Print</a>
					</li>
				</ul>
			</li>
		</ul>
		<div class="cols-sample-area">
			<ej:ribbon id="defaultRibbon" width="500px">
				<ej:ribbon-applicationTab type="menu" menuItemID="ribbonmenu"></ej:ribbon-applicationTab>
				<ej:ribbon-tabs>
					<ej:ribbon-tab id="home" text="Home">
						<ej:ribbon-tab-groups>
							<ej:ribbon-tab-group text="New" alignType="rows">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="new" text="New" toolTip="New" buttonSettings="${new_buttonSettings}"></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" height="70" width="60"></ej:ribbon-tabs-groups-content-defaults>
									</ej:ribbon-tab-group-content>
								</ej:ribbon-tab-group-contentCollection>
							</ej:ribbon-tab-group>	
						</ej:ribbon-tab-groups>
					</ej:ribbon-tab>
				</ej:ribbon-tabs>
			</ej:ribbon>
		</div>
	</body>
    </html>

{% endhighlight %}

![](/js/Ribbon/Getting-Started_images/Getting-Started_img2.png)

## Configuring Groups

List of controls are combined as logical `groups` into Tab. Group alignment type as `row/column`, Default is `row`. 

Create group item with `text` specified and add content group to Groups collection with ejButton control settings.

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
					<li>
						<a>Save</a>
					</li>
					<li>
						<a>Save As</a>
					</li>
					<li>
						<a>Print</a>
					</li>
				</ul>
			</li>
		</ul>
		<div class="cols-sample-area"><%
    JSONParser parser = new JSONParser();
	request.setAttribute("new_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"imagePosition\": \"imagetop\",\"prefixIcon\": \"e-icon e-ribbon e-new\" }"));%>
			<ej:ribbon id="defaultRibbon" width="500">
				<ej:ribbon-applicationTab type="menu" menuItemID="ribbonmenu"></ej:ribbon-applicationTab>
				<ej:ribbon-tabs>
					<ej:ribbon-tab id="home" text="Home">
						<ej:ribbon-tab-groups>
							<ej:ribbon-tab-group text="New" alignType="rows">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="new" text="New" toolTip="New" buttonSettings="${new_buttonSettings}"></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" height="70" width="60"></ej:ribbon-tabs-groups-content-defaults>
									</ej:ribbon-tab-group-content>
								</ej:ribbon-tab-group-contentCollection>
							</ej:ribbon-tab-group>
						</ej:ribbon-tab-groups>
					</ej:ribbon-tab>
				</ej:ribbon-tabs>
			</ej:ribbon>
		</div>
	</body>
    </html>

{% endhighlight %}

![](/js/Ribbon/Getting-Started_images/Getting-Started_img3.png)

## Adding Controls to Group

Syncfusion JavaScript Controls can be added to group’s content with corresponding `type` specified like button, split button, toggle button, dropdown list, gallery, custom, etc. Default type is `button`.

In ribbon button setting button model can be assigned using JSONParser.

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
					<li>
						<a>Save</a>
					</li>
					<li>
						<a>Save As</a>
					</li>
					<li>
						<a>Print</a>
					</li>
				</ul>
			</li>
		</ul>
		<div class="cols-sample-area"><%
    JSONParser parser = new JSONParser();
	request.setAttribute("new_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"imagePosition\": \"imagetop\",\"prefixIcon\": \"e-icon e-ribbon e-new\" }"));
	request.setAttribute("paste_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-ribbon e-ribbonpaste\" }"));
	request.setAttribute("cut_buttonSettings",parser.parse("{\"contentType\": \"textandimage\",\"prefixIcon\": \"e-icon e-ribbon e-ribboncut\" }"));
	request.setAttribute("copy_buttonSettings",parser.parse("{\"contentType\": \"textandimage\",\"prefixIcon\": \"e-icon e-ribbon e-ribboncopy\" }"));
	request.setAttribute("clear_buttonSettings",parser.parse("{\"contentType\": \"textandimage\",\"prefixIcon\": \"e-icon e-ribbon clearAll\" }"));
	%>
			<ej:ribbon id="defaultRibbon" width="500px" >
				<ej:ribbon-applicationTab type="menu" menuItemID="ribbonmenu"></ej:ribbon-applicationTab>
				<ej:ribbon-tabs>
					<ej:ribbon-tab id="home" text="Home">
						<ej:ribbon-tab-groups>
							<ej:ribbon-tab-group text="New" alignType="rows">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="new" text="New" toolTip="New" buttonSettings="${new_buttonSettings}"></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" height="70" width="60"></ej:ribbon-tabs-groups-content-defaults>
									</ej:ribbon-tab-group-content>
								</ej:ribbon-tab-group-contentCollection>
							</ej:ribbon-tab-group>
							<ej:ribbon-tab-group text="Clipboard" alignType="columns">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="paste" text="paste" toolTip="Paste"  buttonSettings="${paste_buttonSettings}"></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" width="50" height="70" isBig="true"></ej:ribbon-tabs-groups-content-defaults>
									</ej:ribbon-tab-group-content>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="cut" text="Cut" toolTip="Cut" buttonSettings="${cut_buttonSettings}"></ej:ribbon-tab-group-content-group>
											<ej:ribbon-tab-group-content-group id="copy" text="Copy" toolTip="Copy" buttonSettings="${copy_buttonSettings}"></ej:ribbon-tab-group-content-group>
											<ej:ribbon-tab-group-content-group id="clear" text="Clear" toolTip="Clear All" buttonSettings="${clear_buttonSettings}"></ej:ribbon-tab-group-content-group>
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
    </html>
  
{% endhighlight %}

![](/js/Ribbon/Getting-Started_images/Getting-Started_img4.png)