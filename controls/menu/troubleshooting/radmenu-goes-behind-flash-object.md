---
title: RadMenu Goes Behind Flash Object
page_title: RadMenu Goes Behind Flash Object | UI for ASP.NET AJAX Documentation
description: RadMenu Goes Behind Flash Object
slug: menu/troubleshooting/radmenu-goes-behind-flash-object
tags: radmenu,goes,behind,flash,object
published: True
position: 1
---

# RadMenu Goes Behind Flash Object



## 

__Q:__ Why does my RadMenu goes behind flash objects in Firefox browser?

__A:__ Set the __W-MODE__ attribute of the Flash to __opaque__ (preferably) or __transparent__.

To the Embed tag, add the following attribute:

````ASPNET
	     
	
	<embed ... wmode="opaque" ...>
				
````





Here is a couple of articles for additional information on Flash and W-MODE options:

[Flash, DHTML Menus and Accessibility](http://www.communitymx.com/content/article.cfm?cid=e5141)

[WHAT IS W-MODE?](http://mediakit.go.com/support/whatis_wmode.html)
