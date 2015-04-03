---
title: OnClientTimeSelecting
page_title: OnClientTimeSelecting | UI for ASP.NET AJAX Documentation
description: OnClientTimeSelecting
slug: calendar/client-side-programming/events/onclienttimeselecting
tags: onclienttimeselecting
published: True
position: 14
---

# OnClientTimeSelecting



## 

It is sometimes necessary for a __TimeView__ selection to be canceled. This may be the case when we have disabled a particular TimeView cell. An example of this is when the user should be able to select given time intervals, but not other.

>note The __OnClientTimeSelecting__ event is supported by: __RadTimeView__ .
>


The event handler receives two arguments:

1. the [RadTimeView]({%slug calendar/client-side-programming/radtimeview-object%}) object that fired the event.

1. an event arguments object that exposes the following methods:OnClientTimeSelecting event arguments object


| Name | Return Type | Arguments | Description |
| ------ | ------ | ------ | ------ |
| __get_oldTime()__ |Date object||Returns the time before the user selected a new time value.|
| __get_newTime()__ |Date object||Returns the newly selected time value.|
| __set_cancel(value)__ ||bool|Lets you prevent the selection or deselection from occurring.|

In this case, one can use the OnClientTimeSelecting client side event handler, which is cancelable. One usage is demonstrated by the code sample below:

````ASPNET
	     
	
	<telerik:RadTimePicker runat="server" Id="Picker1">
	    <TimeView runat="server" ID="TimeView1" OnClientTimeSelecting="ClientTimeSelecting">
	    </TimeView>
	</telerik:RadTimePicker>
				
````



````XML
	 <script type="text/javascript">
	     function ClientTimeSelecting(sender, eventArgs) {
	         eventArgs.set_cancel(true);
	     }
	</script>		
````



# See Also

 * [OnPopupClosing]({%slug calendar/client-side-programming/events/onpopupclosing%})

 * [OnPopupOpening]({%slug calendar/client-side-programming/events/onpopupopening%})
