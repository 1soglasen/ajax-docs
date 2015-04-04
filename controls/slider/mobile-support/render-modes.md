---
title: Render Modes
page_title: Render Modes | UI for ASP.NET AJAX Documentation
description: Render Modes
slug: slider/mobile-support/render-modes
tags: render,modes
published: True
position: 1
---

# Render Modes



__RadSlider__ has different render modes that can change the behavior of the control under different screen resolutions. They are exposed via the __RenderMode__ property that has four possible values - __Classic__,__Lightweight__, __Mobile__ and __Auto__.

The possible options for the __RenderMode__ property are:

* __Classic__ - this mode is the rendering that is used by default. It remains without changes.

* __Lightweight__ - this mode emphasizes on semantic HTML and CSS3. It reduces the amount of markup the control renders and makes it easierto customize. All of this decreases the overall size and complexity of each skin, including custom ones.The [elastic capabilities of RadSlider]({%slug slider/mobile-support/responsive,-adaptive-and-elastic-capabilities%}) are enabled in this mode.

* __Mobile__ - this mode is currently not supported. If you set it, the mode will fall back automatically to __Classic__.

* __Auto__ - this mode makes the control choose the appropriate rendering mode according to the browser. Currently it is now supported and it will automatically fall back to __Classic__.

>important  __RadSlider__ , as well as the other controls included in the Telerik UI for ASP.NET AJAX suite that utilize render modes, supports only one type of render mode per page. All such controls must have the same __RenderMode__ on a given page. This also includes instances from user controls and master pages.
>


## Setting Render Mode

There are two ways to configure the rendering mode of the controls:

* The __RenderMode__ property in the markup or in the code-behind that can be used for a particular instance:

````ASPNET
	    <telerik:RadSlider runat="server" ID="RadSlider1" RenderMode="Lightweight">
	    </telerik:RadSlider>
````



>tabbedCode

````C#
	        RadSlider1.RenderMode = Telerik.Web.UI.RenderMode.Lightweight;
````
````VB.NET
			RadSlider1.RenderMode = Telerik.Web.UI.RenderMode.Lightweight
	#End Region
	End Class


>end

* A __global setting in the web.config__ file that will affect the entire application, unless a concrete value is specified for a given control instance:

````XML
	<appSettings>
	  <add key="Telerik.Web.UI.Slider.RenderMode" value="lightweight" />
	</appSettings>
````



# See Also

 * [RadSlider Responsive, Adaptive and Elastic Capabilities]({%slug slider/mobile-support/responsive,-adaptive-and-elastic-capabilities%})
