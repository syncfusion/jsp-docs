---
layout: post
title: getting-started
description: How to create a SplitButton in JSP platform
platform: JSP
control: SplitButton
documentation: ug
---

# Getting Started

This section explains breifly about how to create a SplitButton in your applcation with JSP.The usage of SplitButton control is described in the following sections.

## Create a SplitButton in JSP Platform

To create a Essential JSP component, you should have the general knowledge about the information regarding integrating Syncfusion widget's provided in this [page](https://help.syncfusion.com/jsp/overview).

Create the JSP file and add the below given code to render SplitButton control

{%highlight html%}

        <div class="cols-sample-area">
        <div class="control">
        <table>

        <td >
        <ej:splitButton id="large text="Login contentType="text">
        <ej:splitButton-splitButtonItems>
        <ej:splitButton-splitButtonItem text="User"></ej:splitButton-splitButtonItem>
        <ej:splitButton-splitButtonItem text="Guest"></ej:splitButton-splitButtonItem>
        <ej:splitButton-splitButtonItem text="Admin"></ej:splitButton-splitButtonItem>
        </ej:splitButton-splitButtonItems>
        </ej:splitButton></td>
                
        </table>
        </div>
        </div>

{%endhighlight%}

The above code will render the following output in the display.

![](getting-started_images/SplitButton1.png)

##Configuring the SplitButton
 This section encompasses the details on how to configure the SplitButton component with its API properties like showRoundedCorner, width, height, prefixIcon.

 {%highlight html%}
 
        <div class="cols-sample-area">
        <div class="control">
        <table>

        <td >
        <ej:splitButton id="large"
        showRoundedCorner="true" size="large" text="Login"
        contentType="textandimage" prefixIcon="e-icon e-login">
        <ej:splitButton-splitButtonItems>
        <ej:splitButton-splitButtonItem text="User"></ej:splitButton-splitButtonItem>
        <ej:splitButton-splitButtonItem text="Guest"></ej:splitButton-splitButtonItem>
        <ej:splitButton-splitButtonItem text="Admin"></ej:splitButton-splitButtonItem>
        </ej:splitButton-splitButtonItems>
        </ej:splitButton></td>
                
        </table>
        </div>
        </div>

 {%endhighlight%}
 
 The above code will render the following output in the display screen.
 
![](getting-started_images/SplitButton2.png) 
