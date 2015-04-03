---
title: OnDayRender
page_title: OnDayRender | UI for ASP.NET AJAX Documentation
description: OnDayRender
slug: calendar/client-side-programming/events/ondayrender
tags: ondayrender
published: True
position: 3
---

# OnDayRender



## 

The __OnDayRender__client-side event handler is called for every calendar day cell when the calendar is rendered as a result of client-side navigation. This event mimics the server-side __DayRender__ event, giving final control over the output of a specific calendar day cell. This event can be used to apply changes to the calendar cells when the user navigates that are identical to the server-side event handler applied to the cells in the initial view.

>note The __OnDayRender__ event is supported by: __RadCalendar__ .
>


The event handler receives two arguments:

1. the [RadCalendar object]({%slug calendar/client-side-programming/radcalendar-object%}) that fired the event.

1. an event arguments object that exposes the following methods:OnDayRender event arguments object


| Name | Return Type | Arguments | Description |
| ------ | ------ | ------ | ------ |
| __get_renderDay()__ |[RenderDay client-side object]({%slug calendar/client-side-programming/renderday-object%})||Returns the client-side RenderDay object that represents the day being rendered. This value is null if the cell represents a valueoutside the range specified by __RangeMinDate__ and __RangeMaxDate__ .|
| __get_date()__ |Array object||Returns the triplet for the date the cell represents.|
| __get_cell()__ |Cell element||Returns object for the cell being rendered.|

The following example uses the __OnDayRender__event to change the text for the non-current month and for dates that fall outside the selectable range. It also changes the background color on weekend days:

````ASPNET
	<script type="text/javascript">
	    function RenderADay(sender, eventArgs) {
	        var cell = eventArgs.get_cell();
	        var day = eventArgs.get_renderDay();
	        if (day) {
	            var view = day.RadCalendarView;
	            if (eventArgs.get_date()[1] != view._MonthStartDate[1]) {
	                cell.innerText = "(" + cell.innerText + ")";
	            }
	
	            if (day.get_isWeekend())
	                cell.style.backgroundColor = "#efefef";
	        }
	        else
	            cell.innerText = "";
	    }
	</script>
	<telerik:RadCalendar ID="RadCalendar1" runat="server">
	    <ClientEvents OnDayRender="RenderADay" />
	</telerik:RadCalendar>  			
````



# See Also

 * [DayRender]({%slug calendar/server-side-programming/server-side-events/dayrender%})
