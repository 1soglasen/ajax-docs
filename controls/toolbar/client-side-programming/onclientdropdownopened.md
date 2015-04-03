---
title: OnClientDropDownOpened
page_title: OnClientDropDownOpened | UI for ASP.NET AJAX Documentation
description: OnClientDropDownOpened
slug: toolbar/client-side-programming/onclientdropdownopened
tags: onclientdropdownopened
published: True
position: 14
---

# OnClientDropDownOpened



## 

The __OnClientDropDownOpened__ client-side event occurs immediately after the drop-down expands to show its child buttons.

The event handler receives two parameters:

1. The instance of the toolbar firing the event.

1. An eventArgs parameter containing the following methods:

* __get_item__ returns a reference to the __RadToolBarItem__that was opened. In this case it is a drop-down.

* __get_domEvent__ returns the browser's event object

You can use this event to respond to an action right after the drop-down has been expanded:

````ASPNET
	
	    <script>
	        function OnClientDropDownOpened(sender, args) {
	            alert(args.get_item().get_buttons().get_count());
	        }       
	    </script>
	
	    <telerik:RadToolBar ID="RadToolBar1" runat="server" Orientation="Horizontal" OnClientDropDownOpened="OnClientDropDownOpened">
	        <CollapseAnimation Duration="200" Type="OutQuint" />
	        <Items>
	            <telerik:RadToolBarButton Text="button1" runat="server">
	            </telerik:RadToolBarButton>
	            <telerik:RadToolBarDropDown Text="dropdown" runat="server">
	                <Buttons>
	                    <telerik:RadToolBarButton Text="Button2" runat="server">
	                    </telerik:RadToolBarButton>
	                </Buttons>
	            </telerik:RadToolBarDropDown>
	        </Items>
	    </telerik:RadToolBar>
````




