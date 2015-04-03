---
title: showInsertItem
page_title: showInsertItem | UI for ASP.NET AJAX Documentation
description: showInsertItem
slug: listview/client-side-programming/radlistview/methods/showinsertitem
tags: showinsertitem
published: True
position: 7
---

# showInsertItem



## 

Method which fires the InitInsert command for the respective __RadListView__ object. As a result of its call the RadListView insert item is displayed as first or last item.


| function showInsertItem(RadListViewInsertItemPosition) |  |  |
| ------ | ------ | ------ |
| __RadListViewInsertItemPosition__ |Integer or String.Empty|The insert item will be displayed at the corresponding position.|

````ASPNET
	    <telerik:RadCodeBlock ID="RadCodeBlock1" runat="server">
	        <script type="text/javascript">
	            function OpenInsertItemAsFirstItem() {
	                var listView = $find("<%= RadListView1.ClientID %>");
	                listView.showInsertItem(1);
	            }
	            function OpenInsertItemAsLastItem() {
	                var listView = $find("<%= RadListView1.ClientID %>");
	                listView.showInsertItem(0);
	            } 
	        </script>
	    </telerik:RadCodeBlock>
````


