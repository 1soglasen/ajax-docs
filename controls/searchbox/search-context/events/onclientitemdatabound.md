---
title: OnClientItemDataBound
page_title: OnClientItemDataBound | UI for ASP.NET AJAX Documentation
description: OnClientItemDataBound
slug: searchbox/search-context/events/onclientitemdatabound
tags: onclientitemdatabound
published: True
position: 0
---

# OnClientItemDataBound



The following article demonstrates the usage of the __OnClientItemDataBound__ client-side event.

## 

The __OnClientItemDataBound__ client-side event occurs for each item that is created during a __ODataDataSource__ binding.

The event handler receives two parameters:

1. The instance of the __SearchContext__ firing the event.

1. An eventArgs parameter containing the following methods:

* __get_item()__ - returns a reference of the SearchContextItem.

* __get_dataItem()__ - returns a reference to the DataItem object (data container).



````ASPNET
		<telerik:RadODataDataSource runat="server" ID="DataSource1">
	        <Transport>
	            <Read Url="http://demos.kendoui.com/service/Northwind.svc/"></Read>
	        </Transport>
	        <Schema>
	            <telerik:DataModel ModelID="Product" Set="Products">
	                <telerik:DataModelField FieldName="ProductID" />
	                <telerik:DataModelField FieldName="ProductName" />
	            </telerik:DataModel>
	                <telerik:DataModel ModelID="Supplier" Set="Suppliers">
	                <telerik:DataModelField FieldName="SupplierID" />
	                <telerik:DataModelField FieldName="ContactName" />
	            </telerik:DataModel>
	        </Schema>
	    </telerik:RadODataDataSource>
	        <telerik:RadSearchBox runat="server" ID="RadSearchBox1"
	            ODataDataSourceID="DataSource1"
	            DataModelID="Product"
	            DataKeyNames="ProductID, ProductName"
	            DataValueField="ProductID"
	            DataTextField="ProductName"
	            DataContextKeyField="SupplierID" >
	            <DropDownSettings Height="400" Width="300" />
	            <SearchContext DataModelID="Supplier" DataKeyField="SupplierID" 
	                DataTextField="ContactName"  OnClientItemDataBound="OnClientItemDataBound">
	            </SearchContext>
	        </telerik:RadSearchBox>
	        <script type="text/javascript">
	            function OnClientItemDataBound(sender, args) {
	                var contactName = args.get_dataItem().ContactName;
	                args.get_item().set_imageUrl(contactName + "_small.png");
	            }
	        </script>
````


