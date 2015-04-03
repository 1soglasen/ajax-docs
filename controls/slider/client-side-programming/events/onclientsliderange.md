---
title: OnClientSlideRange
page_title: OnClientSlideRange | UI for ASP.NET AJAX Documentation
description: OnClientSlideRange
slug: slider/client-side-programming/events/onclientsliderange
tags: onclientsliderange
published: True
position: 6
---

# OnClientSlideRange



## 

The __OnClientSlideRange__client-side event occurs as the user is sliding the selected region of RadSlider, thus changingboth __SelectionStart__ and __SelectionEnd__ values. The properties __EnableDragRange__	and __IsSelectionRangeEnabled__ of RadSlider should be set to __true__ in order to enable the sliding region of the control.

The event handler receives two parameters:

1. The slider instance that fired the event.

1. Event arguments. The parameter has no methods for this event.

The example below updates a span tag with the slider selection start and selection end value as it changes.

````ASPNET
	    <script type="text/javascript">
	       function clientSlideRange(sender, eventArgs)
	       {
	        	var message = document.getElementById("message");
	        	message.innerHTML = "Selection start: " + sender.get_selectionStart() + "; Selection end: " + sender.get_selectionEnd() + ";";
	       }
	    </script>
	    <span id="message"></span>
	    <telerik:RadSlider ID="RadSlider2" runat="server" EnableDragRange="true" IsSelectionRangeEnabled="true" OnClientSlideRange="clientSlideRange" />
````


