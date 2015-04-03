---
title: Button Settings
page_title: Button Settings | UI for ASP.NET AJAX Documentation
description: Button Settings
slug: dropdowntree/functionality/button-settings
tags: button,settings
published: True
position: 3
---

# Button Settings



You can take advantage of the additional functionality that we implemented with the RadDropDownTree control by usingthe ButtonSettings described below.

## Button Settings

>note These settings are available after the __Q2 2013__ release of the Telerik controls.
>


* __ShowCheckAll__ - displays a checkbox that allows checking of all checkboxes in the dropdown;![Checkall Property](images/dropdowntree_checkall.png)

* __ShowClear__ - displays a button that clears the entries from the entry area.![Clear Button](images/dropdowntree_clearbutton.png)

Here is sample code demonstrating how to set them inline:

````ASPNET
	            <telerik:RadDropDownTree ID="RadDropDownTree1" runat="server" Width="250px" 
	                DefaultMessage="Please select" CheckBoxes="SingleCheck"
	                DataSourceID="ObjectDataSource1" DataFieldID="ID" DataFieldParentID="ParentID"
	                DataTextField="Text">
	                <ButtonSettings ShowCheckAll="true" ShowClear="true" />
	            </telerik:RadDropDownTree>
````


