---
title: Disable AJAX when Client Browser Does Not Support it
page_title: Disable AJAX when Client Browser Does Not Support it | UI for ASP.NET AJAX Documentation
description: Disable AJAX when Client Browser Does Not Support it
slug: ajax/application-scenarios/disable-ajax-when-client-browser-does-not-support-it
tags: disable,ajax,when,client,browser,does,not,support,it
published: True
position: 7
---

# Disable AJAX when Client Browser Does Not Support it



## 

Telerik RadAjax controls won't work in browsers that do not support [XmlHttpRequests](http://en.wikipedia.org/wiki/XMLHttpRequest). You may want to disable AJAX when such a browser opensyour site. To disable AJAX, you can set the __EnableAJAX__ property of Telerik __RadAjaxManager__ or __RadAjaxPanel__ control to __false__ both on client- and server-side.

The .NET 2.0 framework provides the __SupportsXmlHttp__ property and it should be used to check if the browsersupports __XmlHttpRequest__:

>tabbedCode

````C#
	
	        RadAjaxManager1.EnableAJAX = Page.Request.Browser.SupportsXmlHttp;
	
````
````VB
	
	        RadAjaxManager1.EnableAJAX = Page.Request.Browser.SupportsXmlHttp
	
````
>end

When this check is made in the __Page_Load__ event handler, it will make your page work as if it was in a standard postback scenario for those browsers.

>caution Some browsers do support __XmlHttpRequests__ and still return __false__ for the __SupportsXmlHttp__ property.In such cases, you should define Browser definition files. You can find more info in the links below.
>


# See Also

 * [Browser Definition File Schema (browsers Element) in MSDN](http://msdn.microsoft.com/en-us/library/ms228122%28v=vs.100%29.aspx)

 * [Browser Detection using ASP.NET](http://www.codeproject.com/aspnet/browsercaps.asp)
