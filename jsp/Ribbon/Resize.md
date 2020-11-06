---
layout: post
title:  Resize
description: resize
documentation: ug
platform: jsp
keywords: resize,ribbon resize,responsive
---

# Resize 

Ribbon control dynamically resizes to display possible number of controls in the optimal layout as the application window size changes.

As the window is narrowed, controls in the Ribbon will be combined as group button with dropdown arrow, in which controls can be expanded with dropdown arrow.

## Tablet Layout 

Set `isResponsive` as true to enable responsive layout in Ribbon.If client width is above  420px or control content exceeds the page then, the ribbon will render in Tablet mode.

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
		<div class="cols-sample-area">
			<ej:ribbon id="defaultRibbon" width="65%" isResponsive="true">
				<ej:ribbon-applicationTab type="menu" menuItemID="ribbonmenu"></ej:ribbon-applicationTab>
				<ej:ribbon-tabs>
					<ej:ribbon-tab id="home" text="Home">
						<ej:ribbon-tab-groups>
							<ej:ribbon-tab-group text="Clipboard" alignType="rows">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="cut" text="Cut" toolTip="Cut" ></ej:ribbon-tab-group-content-group>
											<ej:ribbon-tab-group-content-group id="copy" text="Copy" toolTip="Copy" ></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" width="60" isBig="false"></ej:ribbon-tabs-groups-content-defaults>
									</ej:ribbon-tab-group-content>
								</ej:ribbon-tab-group-contentCollection>
							</ej:ribbon-tab-group>
							<ej:ribbon-tab-group text="Font" alignType="rows">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="bold" text="Bold" toolTip="Bold" ></ej:ribbon-tab-group-content-group>
											<ej:ribbon-tab-group-content-group id="italic" text="Italic" toolTip="Italic" ></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" isBig="false" ></ej:ribbon-tabs-groups-content-defaults>
									</ej:ribbon-tab-group-content>		
								</ej:ribbon-tab-group-contentCollection>
							</ej:ribbon-tab-group>
							<ej:ribbon-tab-group text="Alignment" alignType="rows">
								<ej:ribbon-tab-group-contentCollection>
									<ej:ribbon-tab-group-content>
										<ej:ribbon-tab-group-content-groups>
											<ej:ribbon-tab-group-content-group id="left" text="Left" toolTip="Left" ></ej:ribbon-tab-group-content-group>
											<ej:ribbon-tab-group-content-group id="right" text="Right" toolTip="Right" ></ej:ribbon-tab-group-content-group>
										</ej:ribbon-tab-group-content-groups>
										<ej:ribbon-tabs-groups-content-defaults type="button" isBig="false" ></ej:ribbon-tabs-groups-content-defaults>
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

![](Resize_images/Resize_img1.png)

