---
layout: post
title: Getting-Started
description: getting started
platform: jsp
control: Tile
documentation: ug
---

# Getting Started

This section helps you to understand the getting started of the Tile control with the step-by-step instructions.

## Create a Tile

The following steps guide you to add a Tile control.

Create a JSP page and add the scripts and css references in the order mentioned in the following code example.

{% highlight html %}

<head>
    <title>JSP Application</title>
    <link href="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/ej.web.all.min.js" type="text/javascript"></script>
</head>

{% endhighlight %}

N> Note: For further reference, refer the common JSP Getting Started Documentation to create an application and add necessary scripts and styles for rendering the Tile control.

Create a simple Tile by adding ej:tile tag to initialize the control in the application.  

    {% highlight html %}

        <div class="e-tile-column">
               <ej:tile id="tile" imageUrl="http://js.syncfusion.com/ug/web/content/tile/map.png"  tileSize="medium" >
                  <ej:tile-caption text="Maps"></ej:tile-caption>
               </ej:tile>
        </div>

    {% endhighlight %}

Get the following output from the above mentioned code

![](Getting-Started_images/Getting-Started_img1.png)

You can easily design a home page using tile control for easy navigation. Therefore, you require many different sizes of tiles aligned in a grid-like manner. The tiles will be aligned automatically to define the necessary tile elements inside the wrapper element, that contains a "e-tile-column" class. You can define all columns elements under the wrapper element with the tile "e-tile-group" class to make ‘n’ number of tiles as a grouped tile. Add the below mentioned code to the corresponding view page.

{% highlight html %}
    
  <div class="e-tile-group">
      <div class="e-tile-column">
          <ej:tile id="tile1" imageUrl="http://js.syncfusion.com/ug/web/content/tile/people_1.png" imagePosition="fill" tileSize="medium" >
              <ej:tile-caption text="People"></ej:tile-caption>
          </ej:tile>
         <div class="e-tile-small-col-2">
              <ej:tile id="tile2" imageUrl="http://js.syncfusion.com/ug/web/content/tile/alerts.png">
              </ej:tile>
              <ej:tile id="tile3" imageUrl="http://js.syncfusion.com/ug/web/content/tile/bing.png">
              </ej:tile>
              <ej:tile id="tile4" imageUrl="http://js.syncfusion.com/ug/web/content/tile/camera.png">
              </ej:tile>
              <ej:tile id="tile5" imageUrl="http://js.syncfusion.com/ug/web/content/tile/messages.png"  >
              </ej:tile>
         </div>
              <ej:tile id="tile6" imageUrl="http://js.syncfusion.com/ug/web/content/tile/games.png" tileSize="medium"  > 
                 <ej:tile-caption text="Play"></ej:tile-caption>
              </ej:tile>
             <ej:tile id="tile7" imageUrl="http://js.syncfusion.com/ug/web/content/tile/map.png"  tileSize="medium" >
                 <ej:tile-caption text="Maps"></ej:tile-caption>
             </ej:tile>
             <ej:tile id="tile8" imageUrl="http://js.syncfusion.com/ug/web/content/tile/sports.png" imagePosition="fill" tileSize="wide">
                 <ej:tile-caption text="Sports"></ej:tile-caption>
             </ej:tile>
     </div>
     <div class="e-tile-column">
           <ej:tile id="tile9" imageUrl="http://js.syncfusion.com/ug/web/content/tile/people_2.png" imagePosition="fill"  tileSize= "medium">
              <ej:tile-caption text="People"></ej:tile-caption>
           </ej:tile>
          <ej:tile id="tile10" imageUrl="http://js.syncfusion.com/ug/web/content/tile/pictures.png" tileSize="medium">
              <ej:tile-caption text="Photo"></ej:tile-caption>
          </ej:tile>
    <div id="scrollTarget"  align="center" style="width: 100%; height: 100%;">
         <ej:tile id="tile11" imageUrl="http://js.syncfusion.com/ug/web/content/tile/weather.png" tileSize= "wide">
             <ej:tile-caption text="Weather"></ej:tile-caption>
         </ej:tile>
         <ej:tile id="tile12" imageUrl="http://js.syncfusion.com/ug/web/content/tile/music.png" tileSize= "medium">
             <ej:tile-caption text="Music"></ej:tile-caption>
         </ej:tile>
         <ej:tile id="tile13" imageUrl="http://js.syncfusion.com/ug/web/content/tile/favs.png" tileSize= "medium">
             <ej:tile-caption text="Favorites"></ej:tile-caption>
         </ej:tile>
    </div>
  </div>
</div>     
 
{% endhighlight %}

Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img2.png)

## Template support with Tile Control  

To customize the Tile images with template feature by using imageTemplateId property of Tile control. Add the below mentioned code to the corresponding view page.

{% highlight html %}

        <div class="e-tile-group">
            <div class="e-tile-column">
                <ej:tile id="tile" imagePosition="fill" tileSize="wide" imageTemplateId="imageTemplate">
                    <ej:tile-caption text="Windows Store"></ej:tile-caption>
                </ej:tile>
            </div>
            <div id="imageTemplate">
                <div id="appimage">
                </div>
                <div class="tileMargin">
                    <span class="caption">Google Search</span><br />
                    <span class="description">The world information</span><br />
                    <span class="sub">Free</span>
                </div>
            </div>
        </div>
  
{% endhighlight %}

Add the following styles to customize the tile images with template support.

{% highlight html %}

 <style>
        #appimage {
            background-image: url("http://js.syncfusion.com/UG/mobile/content/google.png");
            background-position: center center;
            background-repeat: no-repeat;
            background-size: 50% auto;
            display: table-cell;
            width: 45%;
        }

        .tileMargin {
            display: table-cell;
            padding-top: 25px;
        }

        .e-tile-template {
            display: table;
            height: 100%;
            width: 100%;
        }
    </style>
   
{% endhighlight %}

Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img3.png)

N> _Note:_ _You can find the Tile control properties from the_ [API reference](https://help.syncfusion.com/api/js/ejtile) _document_
