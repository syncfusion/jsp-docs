---
layout: post
title: getting-started
description: getting started for CheckBox
platform: JSP
control: CheckBox
documentation: ug
---

# GettingStarted

This section briefly describes about how to create a **Checkbox** in your application with JSP.

## Create a simple CheckBox in JSP

You can create an JSP application and add necessary scripts with the help of the given [JSP Getting Started Documentation.](/jsp-docs/jsp/Getting-Started)

Create the JSP file and add the below given code to render **Checkbox** control.

{% highlight javascript %}

<div>
     <br /> Hobbies <br /> <br />
     <table>
        <tr>
            <td>
                <ej:checkBox id="check1" checked="true" size="small"></ej:checkBox>
                <label for="check1">Music</label>
            </td>
            <td colspan="2">
                <ej:checkBox id="Checkbox3" checked="true" size="small"></ej:checkBox>
                <label for="Checkbox3">Sports</label>
            </td>
            <td colspan="2">
                <ej:checkBox id="Checkbox4" size="small"></ej:checkBox>
                <label for="Checkbox4">Bike Riding</label>
            </td>
        </tr>
     </table>
     <br /> <br /> Favorite Search Engines <br /> <br />
     <table>
        <tr>
            <td>
                <ej:checkBox id="Checkbox1" checked="true" size="medium"></ej:checkBox>
                <label for="Checkbox1">Google</label>
            </td>
            <td colspan="2">
                <ej:checkBox id="Checkbox5" checked="true" size="medium"></ej:checkBox>
                <label for="Checkbox5">Yahoo</label>
            </td>
            <td colspan="2">
                <ej:checkBox id="Checkbox6" size="medium"></ej:checkBox>
                <label for="Checkbox6">Bing</label>
            </td>
        </tr>
     </table>
     <br /> <br /> Favorite Social networks <br /> <br />
     <table>
        <tr>
            <td>
                <ej:checkBox id="Checkbox2" enableTriState="true" size="medium" checkState="indeterminate"></ej:checkBox>
                <label for="Checkbox2">Facebook</label>
            </td>
            <td colspan="2">
                <ej:checkBox id="Checkbox7" enableTriState="true" size="medium" checkState="indeterminate"></ej:checkBox>
                <label for="Checkbox7">GPlus</label>
            </td>
            <td colspan="2">
                <ej:checkBox id="Checkbox8" enableTriState="true" size="medium" checkState="indeterminate"></ej:checkBox>
                <label for="Checkbox8">Twitter</label>
            </td>
        </tr>
     </table>
     <br />
</div>

{% endhighlight %}

You can execute the above code example to display the **Checkbox** control.

![](getting-started_images/Checkbox.png)
