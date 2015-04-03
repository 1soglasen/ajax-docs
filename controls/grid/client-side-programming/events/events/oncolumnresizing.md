---
title: OnColumnResizing
page_title: OnColumnResizing | UI for ASP.NET AJAX Documentation
description: OnColumnResizing
slug: grid/client-side-programming/events/events/oncolumnresizing
tags: oncolumnresizing
published: True
position: 20
---

# OnColumnResizing



## 

Sys.EventArgs OnColumnResizing Property

>note To get or set property values for client API properties, you must call property accessor methods that are named with the get_ and set_ prefixes. For example, to get or set a value for a property such as[cancel](http://msdn.microsoft.com/en-us/library/bb310859.aspx), you call the get_cancel or set_cancel.
>


This event is fired before a column is resized.


|  __Fired by__  | RadGrid |
| ------ | ------ |
| __Arguments__ | __gridColumn__ - returns a reference to the clicked[GridColumn]({%slug grid/client-side-programming/gridcolumn-object/gridcolumn-class-members%})object __domEvent__ - returns the DOM event that was raised for the current event|
| __Can be canceled__ |Yes, set eventArgs.set_cancel(true) to cancel|

Example:

````ASPNET
	    <telerik:RadGrid ID="RadGrid1" runat="server">
	        <ClientSettings>
	            <Resizing AllowColumnResize="true" />
	            <ClientEvents OnColumnResizing="ColumnResizing" />
	        </ClientSettings>
	    </telerik:RadGrid>
````



````JavaScript
	        function ColumnResizing(sender, eventArgs) {
	            alert("Resizng column with Index: " + eventArgs.get_gridColumn().get_element().cellIndex + ", width: " + eventArgs.get_gridColumn().get_element().offsetWidth);
	        }
	        //OR
	        function ColumnResizing(sender, eventArgs) {
	            eventArgs.set_cancel(true) //cancel ColumnResizing event
	        }
````


