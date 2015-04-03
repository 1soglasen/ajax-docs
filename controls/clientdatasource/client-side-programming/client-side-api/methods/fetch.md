---
title: fetch
page_title: fetch | UI for ASP.NET AJAX Documentation
description: fetch
slug: clientdatasource/client-side-programming/client-side-api/methods/fetch
tags: fetch
published: True
position: 4
---

# fetch



## fetch

Method which returns data from the web service after calling the select method from the transport settings. The __fetch__ method makes a request to the remote service only the first time it is called while the __view__ method will return the data after all the settings are applied.


|  __Parameters__  |  __Description__  |
| ------ | ------ |
| __callback__ Function( * __optional__ * )|The optional function which is executed when the remote request is finished.|

````ASPNET
	     <telerik:RadClientDataSource runat="server" ID="RadClientDataSource1">
	        <DataSource>
	            <WebServiceDataSourceSettings ServiceType="OData">
	                <Select Url="http://demos.telerik.com/aspnet-ajax/Services/SampleODataService.svc/Products" />
	            </WebServiceDataSourceSettings>
	        </DataSource>
	    </telerik:RadClientDataSource>
````



````JavaScript
	        <script type="text/javascript"> 
	            function pageLoad() {
	                var dataSource = $find('<%= RadClientDataSource1.ClientID %>');
	                dataSource.fetch(function (args) {
	                    var data = args.get_data();
	                    alert(data.length);  // displays "12"
	                    alert(data[0].ProductName); // displays "Chai"
	                });
	            }
	        </script>
````


