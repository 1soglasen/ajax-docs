---
title: OnClientResizeStart
page_title: OnClientResizeStart | UI for ASP.NET AJAX Documentation
description: OnClientResizeStart
slug: imageeditor/client-side-programming/events/onclientresizestart
tags: onclientresizestart
published: True
position: 8
---

# OnClientResizeStart



## 

The __OnClientResizeStart__ event is raised when the user starts resizing the control.

The event handler receives the following parameters:

1. The __RadImageEditor__ client instance that fired the event.

1. Event arguments object.

````ASPNET
	    <telerik:RadImageEditor runat="server" ID="RadImageEditor1" OnClientResizeStart="OnClientResizeStart"></telerik:RadImageEditor>
	    <script type="text/javascript">
	        function OnClientResizeStart(sender, eventArgs)
	        {
	            alert("OnClientResizeStart event fired by RadImageEditor with ID: " + sender.get_id());
	        }
	    </script>
````



# See Also

 * [Client-Side Events Basics]({%slug imageeditor/client-side-programming/events/client-side-events-basics%})
