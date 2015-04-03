---
title: ToolBox Troubleshooting
page_title: ToolBox Troubleshooting | UI for ASP.NET AJAX Documentation
description: ToolBox Troubleshooting
slug: introduction/radcontrols-for-asp.net-ajax-fundamentals/troubleshooting/toolbox-troubleshooting
tags: toolbox,troubleshooting
published: True
position: 4
---

# ToolBox Troubleshooting



This article explains the most common issues and their solutions related to the Visual Studio Toolbox and the Telerik UI for ASP.NET AJAX controls:

* [The Telerik UI for ASP.NET AJAX controls do not appear in the toolbox](#the-telerik-ui-for-asp.net-ajax-controls-do-not-appear-in-the-toolbox)

* [The Toolbox Contains Old Item Registrations](#the-toolbox-contains-old-item-registrations)

* [Missing or Disabled Toolbox Items](#missing-or-disabled-toolbox-items)

## The Telerik UI for ASP.NET AJAX Controls do not Appear in the Toolbox

*Problem:*

__Telerik UI for ASP.NET AJAX do not appear in the toolbox__

*Reasons and Suggested solutions:*

__Reason 1__: The Visual Studio Extensions feature if the Telerik UI for ASP.NET AJAX installer was not installed.

__Solution 1__: Uninstall Telerik UI for ASP.NET AJAX and run the installer again. Click the __"Custom"__ button in the Setup Type screen and ensure the __"Visual Studio Extensions for Visual Studio xxxx"__ feature is selected for install.



__Reason 2__: Custom/third-party/Telerik exe-installer used to register Telerik controls to the toolbox, that prevent the ToolboxControlInstaller package of the IDE run correctly.

__Solution 2__: Right-click the ToolBox and choose Reset. You would need to manually re-populate the toolbox with the items you've added previously.

Regardless of the cause, you can always try:

__Solution 3__: Run the [Toolbox Configuration tool]({%slug introduction/radcontrols-for-asp.net-ajax-fundamentals/integration-with-visual-studio/visual-studio-extensions/toolbox-configuration%}) from the[Telerik Visual Studio Extensions]({%slug introduction/radcontrols-for-asp.net-ajax-fundamentals/integration-with-visual-studio/visual-studio-extensions/overview%}).

## The Toolbox Contains Old Item Registrations

Problem:

__Uninstalled the old Telerik UI for ASp.NET AJAX version, installed the new one, but the ToolBox contains the old item registrations__

*Reason:*

The Visual Studio ToolBoxControlInstaller package did not refresh the ToolBox items during the first start of the IDE after the installation.

*Suggested solution:*

Right-click the ToolBox and choose Reset. The ToolBox should populate correctly.

## Missing or Disabled Toolbox Items

Problem:

__The Telerik controls toolbox items are missing or disabled__.

*Suggested solution:*

Unplug your wireless mouse. More information is available [here](http://blogs.telerik.com/kevinbabcock/posts/08-06-28/what_to_do_when_your_toolbox_is_devoid_of_radcontrols.aspx).

# See Also

 * [General Troubleshooting]({%slug introduction/radcontrols-for-asp.net-ajax-fundamentals/troubleshooting/general-troubleshooting%})

 * [Design-time Troubleshooting]({%slug introduction/radcontrols-for-asp.net-ajax-fundamentals/troubleshooting/design-time-troubleshooting%})

 * [Web Resources Troubleshooting]({%slug introduction/radcontrols-for-asp.net-ajax-fundamentals/troubleshooting/web-resources-troubleshooting%})

 * [Skins Troubleshooting]({%slug introduction/radcontrols-for-asp.net-ajax-fundamentals/troubleshooting/skins-troubleshooting%})
