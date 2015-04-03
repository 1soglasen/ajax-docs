---
title: OnClientDropDownClosed
page_title: OnClientDropDownClosed | UI for ASP.NET AJAX Documentation
description: OnClientDropDownClosed
slug: toolbar/client-side-programming/onclientdropdownclosed
tags: onclientdropdownclosed
published: True
position: 12
---

# OnClientDropDownClosed



## 

The __OnClientDropDownClosed__ client-side event occurs immediately after the drop-down has closed.

The event handler receives two parameters:

1. The instance of the toolbar firing the event.

1. An eventArgs parameter containing the following methods:

* __get_item__ returns a reference to the __RadToolBarItem__ that was closed. In this case this is a drop-down.

* __get_domEvent__ - returns the browser's event object.

You can use this event to respond when the list of child buttons closes.

````ASPNET
	
	    <script>
	        function OnClientDropDownClosed(sender, args) {
	            alert(args.get_item().get_text());
	        }       
	    </script>
	
	    <telerik:radtoolbar id="RadToolBar1" runat="server" orientation="Horizontal" onclientdropdownclosed="OnClientDropDownClosed">     
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
	    </telerik:radtoolbar>
````


