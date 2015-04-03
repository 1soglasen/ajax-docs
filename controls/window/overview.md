---
title: Window Overview
page_title: Overview | UI for ASP.NET AJAX Documentation
description: Overview
slug: window/overview
tags: overview
published: True
position: 0
---

# Window Overview



## 

Telerik RadWindow lets you build customized dialog boxes and modal or non-modal windows for a web application.Each RadWindow object generates a popup window that appears in the browser. However, unlike browser windows, RadWindow objects offer several advantages:

* __The appearance of Telerik RadWindow can be easily customized__ using [skins]({%slug window/appearance-and-styling/skins%}). This allows you to easily blend it with the design of your web application. RadWindowfeatures new transparency and animation effects. In addition in the new version you can have different skins for different RadWindows on the same page.

* __RadWindow offers full control over window visibility and location__ using simple design-time properties to control [showing]({%slug window/getting-started/showing-and-positioning%}) and positioning of windows.

* __RadWindow supports a rich client event model__.____You can use the [client-side events]({%slug window/client-side-programming/events/overview%}) to provide a level of interaction with the user typically possible only in windows applications.

* __Built-in dialogs for alert, confirm, and prompt boxes can replace the browser dialogs__ to blend into the look and feel of your Web site. The predefined [alert, confirm, and prompt dialogs]({%slug window/alert,-confirm,-prompt-dialogs/overview%}) offer you more control over the look and behavior of these dialogs.

* __RadWindow objects are cached__so that once a window is loaded it is not destroyed when you hide it. The next time your application shows the window, there is no loading time. You can still execute initialization code and pre-set the elements in the window by adding an __OnClientShow__[event handler]({%slug window/client-side-programming/events/overview%}).

* __RadWindow supports a cross-browser look and feel on modal dialogs.__ Creating cross-browser modal dialogs has always been a challenging task for developers, but RadWindow has built-in cross-browser support so you can do this simply by just setting the __Modal__ property on your windows.

* __RadWindow supports passing arguments__ to your windows and lets you easily return those arguments. You can [use the argument attribute]({%slug window/application-scenarios/using-radwindow-as-a-dialog%}), or [pass parameters as part of a URL]({%slug window/application-scenarios/use-querystring-to-provide-arguments-to-radwindow%}).

* __RadWindow objects can be minimized into minimize zones__.____By using [minimize zones]({%slug window/getting-started/minimize-zone%}) you can create a taskbar effect in your applications.

* __RadWindow objects are not suppressed by the Windows XP SP2 popup blocker mechanism__. By using RadWindow, your application interface works without users having to adjust the security settings of their browsers.
>caption 

![](images/window-vistawindows.png)

# See Also

 * [Differences from RadDock]({%slug window/getting-started/differences-from-raddock%})
