---
title: Getting RadGrid Client Object
page_title: Getting RadGrid Client Object | UI for ASP.NET AJAX Documentation
description: Getting RadGrid Client Object
slug: grid/client-side-programming/getting-radgrid-client-object
tags: getting,radgrid,client,object
published: True
position: 1
---

# Getting RadGrid Client Object



## 

There are two possible means to reference the client grid object:

* Using the __$find(id)__ method (shortcut for the findComponent() method) of the ASP.NET AJAX framework:

````JavaScript
	<telerik:RadCodeBlock ID="RadCodeBlock1" runat="server">
	var grid = $find("<%=RadGrid1.ClientID %>");
	//execute some logic here 
	</telerik:RadCodeBlock>			
````



* Subscribing to the __OnGridCreated__ client-side event of the control. In its handler the __sender__ argument (first argument passed in the handler) will reference the client grid object. For more info you can review [this example](http://demos.telerik.com/aspnet-ajax/grid/examples/client/clientsideevents/defaultcs.aspx) from the product's QSF.

Additionally, to get reference to the *div wrapper* or the * html table element * rendered by the RadGrid instance, you can use the __$get(id)__ method (shortcut for the document.getElementById() javascript method).

More info about the $find and $get shortcut methods exposed by the ASP.NET AJAX framework you can find visiting the links below:

* [http://www.asp.net/ajaxlibrary/Reference.Sys-Application-$find-Method.ashx](http://www.asp.net/ajaxlibrary/Reference.Sys-Application-$find-Method.ashx)

* [http://www.asp.net/ajaxlibrary/Reference.Sys-UI-DomElement-$get-Method.ashx](http://www.asp.net/ajaxlibrary/Reference.Sys-UI-DomElement-$get-Method.ashx)
