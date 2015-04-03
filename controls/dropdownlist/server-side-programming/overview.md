---
title: Server-side Programming Overview
page_title: Overview | UI for ASP.NET AJAX Documentation
description: Overview
slug: dropdownlist/server-side-programming/overview
tags: overview
published: True
position: 0
---

# Server-side Programming Overview



## 

__RadDropDownList__ supports a number of server-side events that let you respond to events with complex actions that can't be performed in client-side code.

* [SelectedIndexChanged]({%slug dropdownlist/server-side-programming/events/selectedindexchanged%}) occurs when the SelectedIndex has just changed.

* [ItemSelected]({%slug dropdownlist/server-side-programming/events/itemselected%}) occurs when an item from the dropdownlist is selected.

* [ItemDataBound]({%slug dropdownlist/server-side-programming/events/itemdatabound%}) occurs for each item when it is being bound to a data value.

>note The __SelectedIndexChanged__ and __ItemSelected__ events do not fire unless you set the __AutoPostBack__ property to __True__ .
>

