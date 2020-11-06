---
layout: post
title: getting-started
description: How to create a Scroller in JSP platform
platform: JSP
control: Scroller
documentation: ug
---

# Getting Started

This section explains breifly about how to create a Scroller in your applcation with JSP.The usage of Scroller control is described in the following sections.

## Create a Scroller in JSP Platform

To create a Essential JSP component, you should have the general knowledge about the information regarding integrating Syncfusion widget's provided in this [page](https://help.syncfusion.com/jsp/overview).

Create the JSP file and add the below given code to render Scroller control
{%highlight html%}

        <div class="cols-sample-area">
        <div class="control">
        <ej:scroller id="scrollcontent" width="100%" height="300px">
        <ej:scroller-contentTemplate>
                    
        </ej:scroller-contentTemplate>
        </ej:scroller>
        </div>
        </div>
        <script type="text/javascript">
        $(function() {

        scrollobj = $("#scrollcontent").data("ejScroller");
        $(window).bind('resize', onResizeEvent);
        });
        function destroy(args) {
        $(window).unbind('resize', onResizeEvent);
        }
        function onResizeEvent() {
        if ($("#scrollcontent").data("ejScroller"))
        scrollobj.refresh();
        }
        function destroy(args) {
        $(window).unbind('resize', onResizeEvent);
        }

        </script>

{%endhighlight%}

The above code will render the following output in the display.

![](getting-started_images/Scroller1.png)

##Configuring the Scroller
 This section encompasses the details on how to configure the Scroller component with its API properties like enableRTL,scrollOneStepBy.
 
 {%highlight html%}
 
        <div class="cols-sample-area">
        <div class="control" >
        <ej:scroller id="scrollcontent" width='100%' height="300px" scrollOneStepBy="10" enableRTL="true">
        <ej:scroller-contentTemplate >
        <div>
        <div class="sampleContent">
        <h3 style="font-size: 20px;">Popular News in 2016</h3>
        <div >
        <ul>
        <li><p>American president election was conducted in 2016.
        Hillary clinton and Donald trump were the main competitors 
        in that president election.In the time of election campaigneveryone felt that hillary will lead in the election.But,by surprise trump predominantly won the election.He will be the next president of america after Barack Obama.People expecting some good changes from their new president.
        </p></li>
        <li><p>
        In the same day of election, Narendra Modi, the prime minister of india announced the 1000 Rupees and 500 rupees Note ban in india with a surprise factor. No indian expected the enforcement of this act from the indian government.
        </p></li> </ul>		 
        </div>
        </div>
        </div>

        </ej:scroller-contentTemplate>
        </ej:scroller>
        </div>
        </div>
        <script type="text/javascript">
        $(function() {

        scrollobj = $("#scrollcontent").data("ejScroller");
        $(window).bind('resize', onResizeEvent);
        });
        function destroy(args) {
        $(window).unbind('resize', onResizeEvent);
        }
        function onResizeEvent() {
        if ($("#scrollcontent").data("ejScroller"))
        scrollobj.refresh();
        }
        function destroy(args) {
        $(window).unbind('resize', onResizeEvent);
        }

        </script>


 {%endhighlight%}
 
 The above code will render the following output in the display screen.
 
![](getting-started_images/Scroller2.png) 
