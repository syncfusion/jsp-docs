---
layout: post
title: getting-started
description: How to create a GroupButton in JSP platform
platform: JSP
control: GroupButton
documentation: ug
---

# Getting Started

This section explains breifly about how to create a GroupButton in your application with JSP.The usage of GroupButton control is described in the following sections.

## Create a GroupButton in JSP Platform

To create a Essential JSP component, you should have the general knowledge about the information regarding integrating Syncfusion widget's given in this [page](https://help.syncfusion.com/jsp/overview).

{%highlight html%}

    <body>
    <div class="cols-sample-area">
    <div class="control">
    <div class="element">
    <ej:groupButton id="grup"></ej:groupButton>
    </div>
    </div>
    </div>
    </body>
    
{%endhighlight%}

The above code will render the following output in the display.
![](getting-started_images/GroupButton1.png)

##Configuring the GroupButton
 This section encompasses the details on how to configure the group button component with its API properties like showRoundedCorner, width, height.
 {%highlight html%}
 
        <div class="control">
            
        <div class="element">
        <ej:groupButton id="grup" height="45px" width="100%" showRoundedCorner="true">
        <ej:groupButton-groupButtonItems>
                            
        <ej:groupButton-groupButtonItem id="groupbtn1" text="Sunday"></ej:groupButton-groupButtonItem>
        <ej:groupButton-groupButtonItem id="groupbtn2" text="Monday"></ej:groupButton-groupButtonItem>
        <ej:groupButton-groupButtonItem id="groupbtn3" text="Tuesday"></ej:groupButton-groupButtonItem>
        <ej:groupButton-groupButtonItem id="groupbtn4" text="Wednesday"></ej:groupButton-groupButtonItem>
        <ej:groupButton-groupButtonItem id="groupbtn5" text="Thursday"></ej:groupButton-groupButtonItem>
        <ej:groupButton-groupButtonItem id="groupbtn6" text="Friday" ></ej:groupButton-groupButtonItem>
        <ej:groupButton-groupButtonItem id="groupbtn7" text="Saturday"></ej:groupButton-groupButtonItem>
                                                
        </ej:groupButton-groupButtonItems>
        </ej:groupButton>
        </div>
        </div>
        
 {%endhighlight%}
 
 The above code will render the following output in the display screen
![](getting-started_images/GroupButton2.png) 
