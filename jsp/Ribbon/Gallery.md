---
layout: post
title: Gallery
description: gallery
documentation: ug
platform: jsp
keywords: gallery,ribbon gallery
---

# Gallery

Galleries are used to display items that can be arranged in a grid-type layout. Items in the gallery can be customized as `button`/`menu` to display images, text, or both images and text. You can set `type` of group as `gallery`.

## Gallery Items

`Gallery items` are collection of the items to be included in the main gallery. You can set `text` and `toolTip` to gallery item which can also be customized with `buttonSettings`.
 
Number of `columns` to display in gallery for each row should be specified and the Number of columns in Expanded State `(expandedColumns)` can be customized, if not set, `columns` count will be set as default. 

N> The `itemHeight` and `itemWidth` for gallery item can be set, if not set default values will be used.

{% highlight html %}

    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %>
    <link rel="stylesheet" href="Content/ejthemes/ribbon-css/ej.icons.css">
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
            </ul>
        </li>
    </ul>
    <div class="cols-sample-area">
        <%
        JSONParser parser = new JSONParser();
        request.setAttribute("gallery1_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent1 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery2_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent2 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery3_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent3 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery4_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent4 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery5_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent5 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery6_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent6 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery7_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent7 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery8_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent8 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery9_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent9 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        %>
        <ej:ribbon id="defaultRibbon" width="100%">
            <ej:ribbon-applicationtab type="menu" menuitemid="ribbonmenu"></ej:ribbon-applicationtab>
            <ej:ribbon-tabs>
                <ej:ribbon-tab id="home" text="Home">
                    <ej:ribbon-tab-groups>
                        <ej:ribbon-tab-group text="Gallery" aligntype="rows">
                            <ej:ribbon-tab-group-contentcollection>
                                <ej:ribbon-tab-group-content>
                                    <ej:ribbon-tab-group-content-groups>
                                        <ej:ribbon-tab-group-content-group id="Gallery" columns="2" itemheight="54" itemwidth="68" expandedcolumns="3" type="gallery">
                                            <ej:ribbon-tab-group-content-group-galleryitems>
                                                <ej:ribbon-tab-group-content-group-galleryitem text="GalleryContent1" tooltip="GalleryContent1" buttonsettings="${gallery1_buttonSettings}"></ej:ribbon-tab-group-content-group-galleryitem>
                                                <ej:ribbon-tab-group-content-group-galleryitem text="GalleryContent2" tooltip="GalleryContent2" buttonsettings="${gallery2_buttonSettings}"></ej:ribbon-tab-group-content-group-galleryitem>
                                                <ej:ribbon-tab-group-content-group-galleryitem text="GalleryContent3" tooltip="GalleryContent3" buttonsettings="${gallery3_buttonSettings}"></ej:ribbon-tab-group-content-group-galleryitem>
                                                <ej:ribbon-tab-group-content-group-galleryitem text="GalleryContent4" tooltip="GalleryContent4" buttonsettings="${gallery4_buttonSettings}"></ej:ribbon-tab-group-content-group-galleryitem>
                                            </ej:ribbon-tab-group-content-group-galleryitems>
                                        </ej:ribbon-tab-group-content-group>
                                    </ej:ribbon-tab-group-content-groups>
                                </ej:ribbon-tab-group-content>
                            </ej:ribbon-tab-group-contentcollection>
                        </ej:ribbon-tab-group>
                    </ej:ribbon-tab-groups>
                </ej:ribbon-tab>
            </ej:ribbon-tabs>
        </ej:ribbon>
    </div>
    </body>
    <style>
    .e-ribbon .e-groupdiv .e-gallerybtn, .e-ribbon .e-groupdiv .e-gallerybtn:hover, .e-ribbon .e-groupdiv .e-galleryselect, .e-ribbon .e-resizediv .e-gallerybtn, .e-ribbon .e-resizediv .e-gallerybtn:hover, .e-ribbon .e-resizediv .e-galleryselect {
        border-width: 3px !important;
        border-style: solid;
    }

    .e-gallerycontent1 {
        background-position: 0 -105px;
    }

    .e-gallerycontent2 {
        background-position: -69px -105px;
    }

    .e-gallerycontent3 {
        background-position: -136px -105px;
    }

    .e-gallerycontent4 {
        background-position: 0 -53px;
    }

    .e-gallerycontent5 {
        background-position: -69px -53px;
    }

    .e-gallerycontent6 {
        background-position: -136px -53px;
    }

    .e-gallerycontent7 {
        background-position: 0 0px;
    }

    .e-gallerycontent8 {
        background-position: -69px 0px;
    }

    .e-gallerycontent9 {
        background-position: -136px 0px;
    }

    .e-gbtnposition {
        margin-top: 5px;
    }

    .e-gbtnimg {
        background-image: url("Content/ejthemes/common-images/ribbon/homegallery.png");
        background-repeat: no-repeat;
        height: 64px;
        width: 64px;
    }

    .e-extracontent .e-extrabtnstyle {
        padding-left: 28px;
        text-align: left;
    }
    </style>
	 </html>

{% endhighlight %}


![](Gallery_images/Gallery_img1.png)

Ribbon Gallery.
{:.caption}


![](Gallery_images/Gallery_img2.png)

Gallery at Expanded State
{:.caption}

## Custom Gallery Items

`Custom gallery items` are the additional items to be displayed at gallery expanded state. You can set `customItemType` as `button` or `menu`, Default is `button`.

You can also set `text` and `toolTip` to custom gallery item which can also be customized with `buttonSettings`/`menuSettings` based on the `customItemType` specified.

{% highlight html %}

      
    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%><%@ taglib prefix="ej" uri="/WEB-INF/EJ.tld" %><%@ page import="com.syncfusion.*" %><%@ page session="false" import="java.util.ArrayList" %><%@ page session="false" import="java.util.Iterator" %><%@ page session="false" import="org.json.simple.parser.JSONParser" %>
    <link rel="stylesheet" href="Content/ejthemes/ribbon-css/ej.icons.css">
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
            </ul>
        </li>
    </ul>
    <ul id="extramenu">
        <li>
            <a>New Quick Step</a>
            <ul>
                <li>
                    <a>Move to new folder</a>
                </li>
                <li>
                    <a>Categorize & Move</a>
                </li>
                <li>
                    <a>Flag & Move</a>
                </li>
            </ul>
        </li>
    </ul>
    <div class="cols-sample-area">
        <%
        JSONParser parser = new JSONParser();
        request.setAttribute("gallery1_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent1 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery2_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent2 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery3_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent3 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery4_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent4 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery5_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent5 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery6_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent6 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery7_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent7 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery8_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent8 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("gallery9_buttonSettings",parser.parse("{\"contentType\": \"imageonly\",\"prefixIcon\": \"e-icon e-gallerycontent9 e-gbtnimg\",\"cssClass\": \"e-gbtnposition\" }"));
        request.setAttribute("customGal2_menuSettings",parser.parse("{\"openOnClick\":false }"));
        request.setAttribute("customGal3_buttonSettings",parser.parse("{\"cssClass\": \"e-extrabtnstyle\" }"));
        %>
        <ej:ribbon id="defaultRibbon" width="100%">
            <ej:ribbon-applicationtab type="menu" menuitemid="ribbonmenu"></ej:ribbon-applicationtab>
            <ej:ribbon-tabs>
                <ej:ribbon-tab id="home" text="Home">
                    <ej:ribbon-tab-groups>
                        <ej:ribbon-tab-group text="Gallery" aligntype="rows">
                            <ej:ribbon-tab-group-contentcollection>
                                <ej:ribbon-tab-group-content>
                                    <ej:ribbon-tab-group-content-groups>
                                        <ej:ribbon-tab-group-content-group id="Gallery" columns="2" itemheight="54" itemwidth="68" expandedcolumns="3" type="gallery">
                                            <ej:ribbon-tab-group-content-group-galleryitems>
                                                <ej:ribbon-tab-group-content-group-galleryitem text="GalleryContent1" tooltip="GalleryContent1" buttonsettings="${gallery1_buttonSettings}"></ej:ribbon-tab-group-content-group-galleryitem>
                                                <ej:ribbon-tab-group-content-group-galleryitem text="GalleryContent2" tooltip="GalleryContent2" buttonsettings="${gallery2_buttonSettings}"></ej:ribbon-tab-group-content-group-galleryitem>
                                                <ej:ribbon-tab-group-content-group-galleryitem text="GalleryContent3" tooltip="GalleryContent3" buttonsettings="${gallery3_buttonSettings}"></ej:ribbon-tab-group-content-group-galleryitem>
                                                <ej:ribbon-tab-group-content-group-galleryitem text="GalleryContent4" tooltip="GalleryContent4" buttonsettings="${gallery4_buttonSettings}"></ej:ribbon-tab-group-content-group-galleryitem>
                                            </ej:ribbon-tab-group-content-group-galleryitems>
                                            <ej:ribbon-tab-group-content-group-customgalleryitems>
                                                <ej:ribbon-tab-group-content-group-customgalleryitem customitemtype="menu" menuid="extramenu" menusettings="${customGal2_menuSettings}"></ej:ribbon-tab-group-content-group-customgalleryitem>
                                                <ej:ribbon-tab-group-content-group-customgalleryitem text="Clear Formatting" tooltip="Clear Formatting" customitemtype="button" buttonsettings="${customGal3_buttonSettings}"></ej:ribbon-tab-group-content-group-customgalleryitem>
                                            </ej:ribbon-tab-group-content-group-customgalleryitems>
                                        </ej:ribbon-tab-group-content-group>
                                    </ej:ribbon-tab-group-content-groups>
                                </ej:ribbon-tab-group-content>
                            </ej:ribbon-tab-group-contentcollection>
                        </ej:ribbon-tab-group>
                    </ej:ribbon-tab-groups>
                </ej:ribbon-tab>
            </ej:ribbon-tabs>
        </ej:ribbon>
    </div>
    </body>
    <style>

    .e-ribbon .e-groupdiv .e-gallerybtn, .e-ribbon .e-groupdiv .e-gallerybtn:hover, .e-ribbon .e-groupdiv .e-galleryselect, .e-ribbon .e-resizediv .e-gallerybtn, .e-ribbon .e-resizediv .e-gallerybtn:hover, .e-ribbon .e-resizediv .e-galleryselect {
        border-width: 3px !important;
        border-style: solid;
    }

    .e-gallerycontent1 {
        background-position: 0 -105px;
    }

    .e-gallerycontent2 {
        background-position: -69px -105px;
    }

    .e-gallerycontent3 {
        background-position: -136px -105px;
    }

    .e-gallerycontent4 {
        background-position: 0 -53px;
    }

    .e-gallerycontent5 {
        background-position: -69px -53px;
    }

    .e-gallerycontent6 {
        background-position: -136px -53px;
    }

    .e-gallerycontent7 {
        background-position: 0 0px;
    }

    .e-gallerycontent8 {
        background-position: -69px 0px;
    }

    .e-gallerycontent9 {
        background-position: -136px 0px;
    }

    .e-gbtnposition {
        margin-top: 5px;
    }

    .e-gbtnimg {
        background-image: url("Content/ejthemes/common-images/ribbon/homegallery.png");
        background-repeat: no-repeat;
        height: 64px;
        width: 64px;
    }

    .e-extracontent .e-extrabtnstyle {
        padding-left: 28px;
        text-align: left;
    }
    </style>
	</html>

{% endhighlight %}

![](Gallery_images/Gallery_img3.png)