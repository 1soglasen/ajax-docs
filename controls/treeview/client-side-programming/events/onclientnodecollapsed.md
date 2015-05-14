---
title: OnClientNodeCollapsed
page_title: OnClientNodeCollapsed | RadTreeView for ASP.NET AJAX Documentation
description: OnClientNodeCollapsed
slug: treeview/client-side-programming/events/onclientnodecollapsed
tags: onclientnodecollapsed
published: True
position: 16
---

# OnClientNodeCollapsed



## 

The **OnClientNodeCollapsed** client-side event occurs after the user clicks the collapse (minus) button.

The event handler receives parameters:

1. The **TreeView** instance that fired the event.

1. Event arguments with functions:

* **get_node()** retrieves a reference to the clicked on node.

* **get_domEvent()** retrieves a DOM event object of the node collapsing.

The example below demonstrates retrieving a reference to the collapsed parent node.

````ASPNET
<telerik:RadTreeView ID="RadTreeView1" 
     runat="server"  
     OnClientNodeCollapsed="ClientNodeCollapsed">
</telerik:RadTreeView>			
````
````JavaScript
function ClientNodeCollapsed(sender, eventArgs) {
	var node = eventArgs.get_node();
	alert(node.get_text() + " has collapsed");
}
````



# See Also

 * [OnClientNodeCollapsing]({%slug treeview/client-side-programming/events/onclientnodecollapsing%})

 * [RadTreeNode]({%slug treeview/client-side-programming/objects/radtreenode%})
