---
title: Changes and Backward Compatibility
page_title: Changes and Backward Compatibility | UI for ASP.NET AJAX Documentation
description: Changes and Backward Compatibility
slug: menu/changes-and-backward-compatibility
tags: changes,and,backward,compatibility
published: False
position: 3
---

# Changes and Backward Compatibility



## RadMenu for ASP.NET AJAX Q1 2014

In this version we modifed the RadMenu client scripts. In case that you are still using an older version of the controls and you want to disable the embedded scripts please refer to the code snippet below to simply add the required script files using the ScriptMnager.

````ASPNET
	        <scripts>
	            <asp:ScriptReference Path="~/Scripts/Common/Core.js" />
	            <asp:ScriptReference Path="~/Scripts/Common/jQuery.js" />
	            <asp:ScriptReference Path="~/Scripts/Common/jQueryPlugins.js" />
	            <asp:ScriptReference Path="~/Scripts/Common/Navigation/NavigationScripts.js" />
	            <asp:ScriptReference Path="~/Scripts/Menu/RadMenuScripts.js" />
	    </scripts>
````



Please refer to the following code snippet if you use Q1 2014 version or newer:

````ASPNET
	        <scripts>
			    <asp:ScriptReference Path="~/Scripts/Common/Core.js" />
	            <asp:ScriptReference Path="~/Scripts/Common/jQuery.js" />
	            <asp:ScriptReference Path="~/Scripts/Common/jQueryPlugins.js" />
	            <asp:ScriptReference Path="~/Scripts/Common/Navigation/OverlayScript.js" />
	            <asp:ScriptReference Path="~/Scripts/Common/Navigation/NavigationScripts.js" />
	            <asp:ScriptReference Path="~/Scripts/Menu/RadMenuScripts.js" />
	            <!-- RadMenuItem script is used when RenderMode is set to Classic or Lightweight. It works in cooperation with ClassicView.js or LiteView.js/-->
	            <asp:ScriptReference Path="~/Scripts/Menu/MenuItem/RadMenuItem.js" />
	            <!-- MobileMenuItem script is required only when RenderMode is set to Mobile/-->
	            <asp:ScriptReference Path="~/Scripts/Menu/MenuItem/MobileMenuItem.js" />
	            <!-- ClassicView script is is used when RenderMode is set to Classic/-->
	            <asp:ScriptReference Path="~/Scripts/Menu/Views/ClassicView.js" />
	            <!-- LiteView script is is used when  RenderMode is set to Lightweight/-->
	            <asp:ScriptReference Path="~/Scripts/Menu/Views/LiteView.js" />
		</scripts>
````



## RadMenu for ASP.NET AJAX Q2 2010

Since Q2 2010 all major changes for the controls are listed in the official Release Notes posted [here](http://www.telerik.com/products/aspnet-ajax/whats-new/release-history.aspx).

## RadMenu for ASP.NET AJAX Q3 SP2 2009 (Version Number 2009.3.1314)

RadMenu for ASP.NET AJAX is fully backward compatible with its previous version.

## RadMenu for ASP.NET AJAX Q3 SP1 2009 (Version Number 2009.3.1208)

RadMenu for ASP.NET AJAX is fully backward compatible with its previous version.

## RadMenu for ASP.NET AJAX Q3 2009 (Version Number 2009.3.1103)

RadMenu for ASP.NET AJAX is fully backward compatible with its previous version.

## RadMenu for ASP.NET AJAX Q2 2009 SP1 (Version Number 2009.2.826)

RadMenu for ASP.NET AJAX is fully backward compatible with its previous version.

## RadMenu for ASP.NET AJAX Q2 2009 (Version Number 2009.2.701)

RadMenu for ASP.NET AJAX is fully backward compatible with its previous version.

## RadMenu for ASP.NET AJAX Q1 2009 SP2 (Version Number 2009.1.527)

RadMenu for ASP.NET AJAX is fully backward compatible with its previous version.

## RadMenu for ASP.NET AJAX Q1 2009 SP1 (Version Number 2009.1.402)

RadMenu for ASP.NET AJAX is fully backward compatible with its previous version.

## RadMenu for ASP.NET AJAX Q1 2009 (Version Number 2009.1.311)

* Three skins have been removed - Gray, Inox and SkyBlue.

* Animations are using the jQuery library now. If you have disabled the embedded scripts you need to manually register the jQuery.js and jQueryPlugins.js files as described here: [ Disabling Embedded Resources ](F02D3323-FFA7-46E6-A4DE-303D5EF15A43)

* Design-time code is placed in a new assembly - Telerik.Web.Design.dll. Read [this blog post](http://blogs.telerik.com/atanaskorchev/posts/09-03-06/Meet_Telerik_Web_Design_dll.aspx) for more information.

## RadMenu for ASP.NET AJAX Q3 2008 (Version Number 2008.3.1105)

RadMenu for ASP.NET AJAX Q3 2008 is fully backward compatible with its previous version (Q2 2008)



## RadMenu for ASP.NET AJAX Q2 SP1 2008 (Version Number 2008.2.826)

* Changed the XML loading logic. Consider this XML fragment:

Consider this XML fragment (from our XmlDefinition demo):

````XML
	    <?xml version="1.0" encoding="utf-8" ?>
	    <menu>
	        <group flow="Horizontal">    
	            <Item  Text="File" Key="F" >			
````



In version prior to Q2 SP1 this was interpreted as:

````ASPNET
	    <telerik:RadMenu Flow="Horizontal" ... />
````



The new interpretation is:

````ASPNET
	    <telerik:RadMenu ... />
	        <DefaultGroupSettings Flow="Horizontal" />    			
````



The fix is to move the Flow attribute to the Menu tag:

````XML
	    <?xml version="1.0" encoding="utf-8" ?>
	        <Menu Flow="Horizontal">
	            <Group>
	                <Item  Text="File" Key="F" > 			
````



# See Also

 * [What is New]({%slug menu/what-is-new%})
