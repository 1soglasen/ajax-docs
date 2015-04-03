---
title: OnClientImageChanged
page_title: OnClientImageChanged | UI for ASP.NET AJAX Documentation
description: OnClientImageChanged
slug: imageeditor/client-side-programming/events/onclientimagechanged
tags: onclientimagechanged
published: True
position: 6
---

# OnClientImageChanged



## 

The __OnClientImageChanged__ event is raised after the image has changed. The event is fired after __OnClientImageChanging__ event.

The event handler receives the following parameters:

1. The __RadImageEditor__ client instance that fired the event.

1. Event arguments object.

````ASPNET
	    <telerik:RadImageEditor runat="server" ID="RadImageEditor1" OnClientImageChanged="OnClientImageChanged"></telerik:RadImageEditor>
	    <script type="text/javascript">
	        function OnClientImageChanged(sender, eventArgs)
	        {
	            alert("OnClientImageChanged event fired by RadImageEditor with ID: " + sender.get_id());
	        }
	    </script>
````



# See Also

 * [Client-Side Events Basics]({%slug imageeditor/client-side-programming/events/client-side-events-basics%})
