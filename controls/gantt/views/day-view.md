---
title: Day View
page_title: Day View | RadGantt for ASP.NET AJAX Documentation
description: Day View
slug: gantt/views/day-view
tags: day,view
published: True
position: 1
---

# Day View



The **Day View** shows all loaded tasks for a RadGantt, distributed in columns that have duration of one hour. All those one hour time spans that belong to a single day are grouped in one day time span. 

![RadGantt in Day View](images/gantt-views-dayview.png)

## Day View Settings:

**Table 1** demonstrates the properties, that are available within the **DayViewSettings** object.

| Name | Type | Description |
| ------ | ------ | ------ |
| **DayHeaderDateFormat** |string|Gets or sets the day header date format string in **DayView**.|
| **HourSpan** |int|Gets or sets the hour span for each cell in **DayView**.|
| **SlotWidth** |Unit|Gets or sets the slot width in pixels for the respective view.|
| **TimeHeaderDateFormat** |string|Gets or sets the time header date format string in **DayView**.|
| **Type** |Telerik.Web.UI.GanttViewType enumeration|Gets the type of the **View**, which the settings are applied to - Day, Week, Month or Year.|
| **UserSelectable** |bool|Gets or sets a value indicating whether to render a tab for the current view in the view chooser.|


# See Also

 * [Views Overview]({%slug gantt/views/overview%})
 
 * [Week View]({%slug gantt/views/week-view%})

 * [Month View]({%slug gantt/views/month-view%})

 * [Year View]({%slug gantt/views/year-view%})
 
 * [View types demo](http://demos.telerik.com/aspnet-ajax/gantt/examples/functionality/view-types/defaultcs.aspx)


