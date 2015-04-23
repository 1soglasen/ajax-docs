---
title: SelectedDateChanged
page_title: SelectedDateChanged | RadCalendar for ASP.NET AJAX Documentation
description: SelectedDateChanged
slug: calendar/server-side-programming/server-side-events/selecteddatechanged
tags: selecteddatechanged
published: True
position: 6
---

# SelectedDateChanged



## 

**RadDatePicker**, **RadTimePicker**, **RadDateTimePicker** and **RadMonthYearPicker** provide the **SelectedDateChanged**server event, which occurs when theuser changes the value of the control, either when input area loses focus after the user has typed a new value, or when the user selects a new value in the popup calendar or time viewcontrol. This event does not fire unless the **AutoPostBack** property is**True** (**RadDatePicker**, **RadTimePicker** and **RadMonthYearPicker**) or the **AutoPostBackControl** property is not"None" (**RadDateTimePicker**).

>note The event handler is not called unless the date and/or time actually changes. If the user makes a change that results in the same value (for example, typing a different string thatparses to the same value), a postback occurs but the **SelectedDateChanged** event handler is not called.
>


The **SelectedDateChanged** event handler receives two arguments:

1. The control whose value has just changed. This argument is of type object, but can be cast to the appropriate type.

1. A **SelectedDateChangedEventArgs** object. This object has the following two properties:

* **OldDate** is the value before the change.

* **NewDate**is the value after the change.

You can use this event to respond in server-side code when the user changes the value:



````C#
	
	
	    protected void RadDateTimePicker1_SelectedDateChanged(object sender, SelectedDateChangedEventArgs e)
	    {
	        Label1.Text = "Change from ";
	        if (e.OldDate == null)
	            Label1.Text += "nothing";
	        else Label1.Text += e.OldDate.ToString();
	        Label1.Text += " to ";
	        if (e.NewDate == null)
	            Label1.Text += "nothing";
	        else Label1.Text += e.NewDate.ToString();
	    }		
````
````VB.NET
	     
	
	    Protected Sub RadDateTimePicker1_SelectedDateChanged(ByVal sender As Object, ByVal e As SelectedDateChangedEventArgs) Handles RadDateTimePicker1.SelectedDateChanged
	        Label1.Text = "Change from "
	        If e.OldDate = Nothing Then
	            Label1.Text += "nothing"
	        Else
	            Label1.Text += e.OldDate.ToString()
	        End If
	        Label1.Text += " to "
	        If e.NewDate = Nothing Then
	            Label1.Text += "nothing"
	        Else
	            Label1.Text += e.NewDate.ToString()
	        End If
	    End Sub
````


# See Also

 * [OnDateSelected]({%slug calendar/client-side-programming/events/ondateselected%})

 * [OnClientTimeSelected]({%slug calendar/client-side-programming/events/onclienttimeselected%})
