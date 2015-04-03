---
title: OnCellSelecting
page_title: OnCellSelecting | UI for ASP.NET AJAX Documentation
description: OnCellSelecting
slug: grid/client-side-programming/events/events/oncellselecting
tags: oncellselecting
published: True
position: 4
---

# OnCellSelecting



## 

Telerik.Web.UI.GridColumnEventArgs OnCellSelecting Property

>note To get or set property values for client API properties, you must call property accessor methods that are named with the get_ and set_ prefixes. For example, to get or set a value for a property such as[cancel](http://msdn.microsoft.com/en-us/library/bb310859.aspx), you call the get_cancel or set_cancel.
>


This event is fired before a cell is selected.


|  __Fired by__  | RadGrid |
| ------ | ------ |
| __Arguments__ | __get_column__ - returns a reference to the corresponding[GridColumn]({%slug grid/client-side-programming/gridcolumn-object/gridcolumn-class-members%})object __get_gridDataItem__ - returns a reference to the corresponding GridDataItem object __get_row__ - returns a reference to the correspong table row element __cancel__ - gets or sets the canceled status of the event|
| __Can be canceled__ |Yes, set eventArgs.set_cancel(true) to cancel|

Example:

````JavaScript
	        function cellSelecting(sender, args) {
	            var selectedRow = args.get_row();
	            var selectedColumn = args.get_column();
	            var dataItem = args.get_gridDataItem();
	            var output = String.format("The selected cell is located in column with name: " + selectedColumn.get_uniqueName() + " and in row with index: " + dataItem.get_itemIndexHierarchical()+".");
	            alert(output);
	        }
````



````ASPNET
	        <ClientSettings>
	            <Selecting CellSelectionMode="MultiCell" />
	            <Scrolling AllowScroll="true" UseStaticHeaders="true" />
	            <ClientEvents OnCellSelecting="cellSelecting" />
	        </ClientSettings>
````



A list of the possible options for the CellSelectionMode property could be found [here.]({%slug grid/functionality/selecting/selecting-cells-and-columns%})
