---
layout: post
title: getting-started
description: How to craete a ToggleButton in JSP platform
platform: JSP
control: ToggleButton
documentation: ug
---

# Getting Started

This section explains breifly about how to create a ToggleButton in your application with JSP.The usage of ToggleButton control is described in the following sections.

## Create a ToggleButton in JSP Platform

To create a Essential JSP component, you should have the general knowledge about the information regarding integrating Syncfusion widget's provided in this [page](https://help.syncfusion.com/jsp/overview).

Create the JSP file and add the below given code to render ToggleButton control

{%highlight html%}

        <div class="cols-sample-area">
        <div class="control">
        <table>
        <tr>
        <td class="btnsht">
        <label for="check15">Toggle</label>
        <ej:toggleButton id="check15"  size="large"  defaultText="On" activeText="Off"  contentType="text”></ej:toggleButton>                  
        </td>
        </tr>
        </table>
        </div>
        </div>


{%endhighlight%}

The above code will render the following output in the display.

![](getting-started_images/ToggleButton1.png)

##Configuring the ToggleButton in JSP Platform

 This section encompasses the details on how to configure the ToggleButton component with its API properties like showRoundedCorner, Size, defaultPrefixIcon, activePrefixIcon..
 
 {%highlight html%}
 
        <div class="cols-sample-area">
        <div class="control">
        <table>
                    
        <tr>
        <td class="btnsht">
        <label for="check15">Toggle</label>
        <ej:toggleButton id="check15" showRoundedCorner="true" size="large"  defaultText="play" activeText="Pause"  contentType="textandimage" defaultPrefixIcon="e-icon e-mediaplay" activePrefixIcon="e-icon e-mediapause"></ej:toggleButton>                  
        </td>
        </tr>
        </table>
        </div>
        </div>



 {%endhighlight%}
 
 The above code will render the following output in the display screen.
 
![](getting-started_images/ToggleButton2.png) 
