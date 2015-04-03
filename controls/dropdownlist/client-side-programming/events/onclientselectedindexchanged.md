---
title: OnClientSelectedIndexChanged
page_title: OnClientSelectedIndexChanged | UI for ASP.NET AJAX Documentation
description: OnClientSelectedIndexChanged
slug: dropdownlist/client-side-programming/events/onclientselectedindexchanged
tags: onclientselectedindexchanged
published: True
position: 8
---

# OnClientSelectedIndexChanged



## 

The __OnClientSelectedIndexChanged__ client-side event occurs immediately after the SelectedItem has been changed.

The event handler receives two parameters:

1. The instance of the DropDownList firing the event.

1. An eventArgs parameter containing the following method:

* __get_index()__ returns the index of the item, that has just been selected.

Use this event to respond to the newly selected item:

````ASPNET
	        <script type="text/javascript">
	            function OnClientSelectedIndexChanged(sender, eventArgs) {
	                alert("You selected item with index : " + eventArgs.get_index());
	            }
	        </script>
	
	        <telerik:RadDropDownList
	            ID="RadDropDownList1"
	            runat="server"
	            OnClientSelectedIndexChanged="OnClientSelectedIndexChanged">
	            <Items>
	                <telerik:DropDownListItem Text="Item 1" Value="1" />
	                <telerik:DropDownListItem Text="Item 2" Value="2" />
	                <telerik:DropDownListItem Text="Item 3" Value="3" />
	                <telerik:DropDownListItem Text="Item 4" Value="4" />
	            </Items>
	        </telerik:RadDropDownList>
````


