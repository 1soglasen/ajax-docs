---
title: Right-to-left Support
page_title: Right-to-left Support | UI for ASP.NET AJAX Documentation
description: Right-to-left Support
slug: slider/accessibility-and-internationalization/right-to-left-support
tags: right-to-left,support
published: True
position: 2
---

# Right-to-left Support



## 

The __RadSlider__ fully supports right-to-left (RTL) language locales. In order to turn on the RTL support you should set its __IsDirectionReversed__ property to __true__ as well as __dir=rtl to the html or body__ elements or to its direct parent.

````ASPNET
	    <div dir="rtl">
	        <telerik:RadSlider runat="server" Skin="Simple" ID="RadSlider1" Orientation="Horizontal" Width="300"
	            Height="50" MinimumValue="0" MaximumValue="50" LargeChange="10" ItemType="Tick" IsDirectionReversed="true"
	            EnableServerSideRendering="true">
	        </telerik:RadSlider>
	    </div>
````

![radslider-rtl-screenshot](images/radslider-rtl-screenshot.png)

# See Also

 * [See this live in an online demo](http://demos.telerik.com/aspnet-ajax/slider/examples/righttoleft/defaultcs.aspx)
