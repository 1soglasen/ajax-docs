---
title: OnItemDropped
page_title: OnItemDropped | UI for ASP.NET AJAX Documentation
description: OnItemDropped
slug: listview/client-side-programming/events/onitemdropped
tags: onitemdropped
published: True
position: 6
---

# OnItemDropped



## 

This client-side event is fired when a RadListView item is dropped after dragging.


|  __Fired by__  | RadListView |
| ------ | ------ |
| __Arguments__ | __dataKeyValues__ - Array of the item key fields set through the ClientDataKeyNames property of the RadListView control __itemIndex__ - the index of the dragged item __destinationElement__ - the destination HTML element __domEvent__ - dom event|
| __Can be canceled__ |No|

Example:

````ASPNET
	        <telerik:RadListView ID="RadListView1" runat="server" ClientDataKeyNames="Title, Artist">
	            <ClientSettings AllowItemsDragDrop="true">
	                <ClientEvents OnItemDropped="ItemDropped" />
	            </ClientSettings>
	        </telerik:RadListView>
````



````JavaScript
	        function ItemDropped(sender, eventArgs) {
	            var dest = eventArgs.get_destinationElement();
	            var itemIndex = eventArgs.get_itemIndex();
	            var title = eventArgs.get_dataKeyValues().Title;
	            var artist = eventArgs.get_dataKeyValues().Artist;
	            alert("Item " + itemIndex + " with Title - " + title + ", Artist - " + artist + " was dropped in " + dest.id);
	        }
````



>caution To get or set property values for client API properties, you must call property accessor methods that are named with the get_ and set_ prefixes. For example, to get or set a value for a property such as[cancel](http://msdn.microsoft.com/en-us/library/bb310859.aspx), you call the get_cancel() or set_cancel().
>

