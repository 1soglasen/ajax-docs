---
title: OnClientCheckedStateChanging
page_title: OnClientCheckedStateChanging | UI for ASP.NET AJAX Documentation
description: OnClientCheckedStateChanging
slug: toolbar/client-side-programming/onclientcheckedstatechanging
tags: onclientcheckedstatechanging
published: True
position: 17
---

# OnClientCheckedStateChanging



## 

The __OnClientCheckedStateChanging__ client-side event occurs before a button has been checked.

>caution To check a button it should be marked with __CheckOnClick="True"__ 
>


The event handler receives two parameters:

1. The instance of the toolbar firing the event.

1. An eventArgs parameter containing the following methods:

* __get_item__ returns a reference to the toolbar item that was checked. In this case this is a __RadToolBarButton__

* __set_cancel__ lets you prevent the drop-down from checking

* __get_domEvent__ returns the browser's event object



You can use this event to respond when a button has been checked.

````ASPNET
	     
		<script type="text/javascript">
		    function checkedStateChanging(sender, args) {
		        args.set_cancel(true);
		    }        
		</script> 
		<telerik:RadToolBar ID="RadToolBar1" runat="server" OnClientCheckedStateChanging="checkedStateChanging">    
		<Items>        
		    <telerik:RadToolBarButton Text="Button1" CheckOnClick="true">
		    </telerik:RadToolBarButton>        
		    <telerik:RadToolBarButton Text="Button1" CheckOnClick="true">
		    </telerik:RadToolBarButton>        
		    <telerik:RadToolBarButton Text="Button1" CheckOnClick="true">
		    </telerik:RadToolBarButton>    
		</Items>
		</telerik:RadToolBar>
				
````




