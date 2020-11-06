---
layout: post
title: Getting-Started
description: Getting Started
platform: jsp
control: dialog
documentation: ug
---

# Getting Started

This section helps you to understand the getting started of the Dialog control with the step-by-step instructions.

# Create a Dialog

The following steps guide you to add a Dialog control.

Create a JSP page and add the scripts and css references in the order mentioned in the following code example.

{% highlight html %}

    <head>
        <title>JSP Application</title>
        <link href="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
        <script src="https://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/ej.web.all.min.js" type="text/javascript"></script>
    </head>

{% endhighlight %}

N> Note: For further reference, refer the common JSP Getting Started Documentation to create an application and add necessary scripts and styles for rendering the Dialog control.

Create a simple Dialog by adding ej:dialog tag to initialize the control in the application. 

{% highlight html %}

        <ej:dialog id="basicDialog" width="450">
        </ej:dialog>
  
{% endhighlight %}

To get the following output from the above-mentioned code.

![](getting-started-images/getting-started-img1.png)

## Add dialog content

You can add any content to dialog inside the ej:dialog-contentTemplate tag. The below code will render dialog control with content.

{% highlight html %}

        <ej:dialog id="basicDialog" width="450">
          <ej:dialog-contentTemplate>
              <div>    
              <p> This is a simple dialog </p>
              </div> 
            </ej:dialog-contentTemplate>
        </ej:dialog>
       
{% endhighlight %}

You will get the following output from the above-mentioned code

![](getting-started-images/getting-started-img2.png)

## Set a header

To set header for the dialog control, the title property is used.

{% highlight html %}

        <ej:dialog id="basicDialog" title="Dialog" width="450">
          <ej:dialog-contentTemplate>
              <div>    
              <p> This is a simple dialog </p>
              </div> 
            </ej:dialog-contentTemplate>
        </ej:dialog>
      
{% endhighlight %}

You will get the following output from the above-mentioned code.

![](getting-started-images/getting-started-img3.png)

## Open Dialog dynamically

In most cases, the Dialog controls are needed only in dynamic actions like showing some messages on clicking a button, to provide alert, etc. So, the Dialog control provides “open” and “close” methods to open/close the dialogs dynamically.
The Dialog control can be hidden on initialize using showOnInit property which should be set to false.
The dialog will be opened on clicking the Button control. Refer to the below mentioned code.

{% highlight html %}

     <% request.setAttribute("prop", false);   %>
       <div>
          <ej:button id="btnOpen" click="BtnClick" text="Click Here to Open dialog"></ej:button>
          <ej:dialog id="basicDialog" title="Dialog" width="450" showOnInit="${prop}">
            <ej:dialog-contentTemplate>
               <div>    
	             <p> This is a simple dialog </p>
               </div> 
             </ej:dialog-contentTemplate>
          </ej:dialog>
       </div> 

{% endhighlight %}

{% highlight javascript %}

      function BtnClick(){
        	$("#basicDialog").ejDialog("open");
        }
        
{% endhighlight %}

To get the following output from the above-mentioned code.

![](getting-started-images/getting-started-img4.png)


N> You can find the Dialog control properties from the [API reference](https://help.syncfusion.com/api/js/ejdialog).             
