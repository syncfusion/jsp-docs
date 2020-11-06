---
layout: post
title: Getting Started | JSP | Syncfusion
description: Getting Started.
platform: JSP 
control: Common 
documentation: ug
---

# Getting Started

## Essential JS for JSP

### Steps to deploy the Essential JS for JSP component demos in Apache Tomcat 

1.	Download the Apache Tomcat from the official download page
2.	You can find a sample JSP web site in the /Samples directory of the Essential JS for JSP distribution. To run the web site, copy this directory to your webapps folder of Apache Tomcat
3.	Run the startup.bat file from the Tomcat location (Tomcat bin folder)
4.	JSP SampleBrowser will be launched under the default port 8080 (localhost: 8080/SampleBrowser/index.jsp).
5.	Browse product samples using the Sample Browser.

![](Getting-Started_images/Getteing-Started_img5.PNG)

### Steps to utilize Essential JS for JSP components in Dynamic web application with Eclipse environment

To use Essential JS for JSP in eclipse environment, follow the steps below:


1. Eclipse IDE with Apache Tomcat 7 configured 

  ![](Getting-Started_images/Getteing-Started_img1.png)


2. Create a Dynamic web application in eclipse

   *	Choose File > New > Project....
   *	In the upcoming wizard choose Web > Dynamic Web Project.
   ![](Getting-Started_images/Getteing-Started_img2.PNG)

  And create a new Dynamic web project in eclipse.

3. Add a new JSP page to your project’s.
   *	Right-click the WebContent folder. 
   *	Select New > JSP file. 
   *	Enter a file name and click Finish.


4. Copy Essential JavaScript and CSS files from /SampleBrowser/Scripts and /SampleBrowser/Content to your project’s /WebContent and Configure your JSP page to include the Essential JavaScript and CSS files to the page, as shown in the example below.

    <b>Example</b>

    {% highlight html %}

    <head>

    <link href="Content/ejthemes/material/ej.web.all.min.css" rel="stylesheet" />

    <script type="text/javascript" src="Scripts/ej.web.all.min.js"></script>

    </head>

    {% endhighlight %}

    ![](Getting-Started_images/Getteing-Started_img3.PNG)

5. Now add the Essential JS for JSP source package from \SampleBrowser\WEB-INF\lib\syncfusion-taglib-[version].jar to your project's /WebContent/WEB-INF/lib folder.

6. Add the Custom taglib from \SampleBrowser\WEB-INF\EJ.tld to your project’s /WebContent/WEB-INF.
 
7. Import the Essential JS for JSP component package into your JSP page.

    <b>Example</b>

    {% highlight html %}

    <%@ page import="com.syncfusion.*"%>

    {% endhighlight %}

8. Add the mapping Tag Library descriptor (tld) file to support Essential JS for JSP custom tags.

    <b>Example</b>

    {% highlight html %}

    <%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld"%>

    {% endhighlight %}

9. Use the Essential JS for JSP custom tag within your JSP file.

    <b>Example</b>

    {% highlight html %}

    <ej:datePicker id="datepicker”></ej:datePicker>

    {% endhighlight %}

10. Finally, right-click your project’s in the Eclipse Project Explorer.

   * Select Run As > Run on server.
  ![](Getting-Started_images/Getteing-Started_img4.PNG)




