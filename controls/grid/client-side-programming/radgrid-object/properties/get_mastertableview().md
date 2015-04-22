---
title: get_masterTableView()
page_title: get_masterTableView() | RadGrid for ASP.NET AJAX Documentation
description: get_masterTableView()
slug: grid/client-side-programming/radgrid-object/properties/get_mastertableview()
tags: get_mastertableview()
published: True
position: 8
---

# get_masterTableView()



## 

This property returns the MasterTableView instance for the respective grid client object.


|  **get_masterTableView()**  |
| ------ |
||

Example:

````JavaScript
	        function getMasterTableView() {
	            var grid = $find("<%=RadGrid1.ClientID %>");
	            var masterTableView = grid.get_masterTableView();              
	        }       
````


