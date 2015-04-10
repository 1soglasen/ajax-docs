---
title: Web Pages Validation
page_title: Web Pages Validation | UI for ASP.NET AJAX Documentation
description: Web Pages Validation
slug: calendar/how-to/web-pages-validation
tags: web,pages,validation
published: True
position: 3
---

# Web Pages Validation



## 

The __RadDatePicker__, __RadTimePicker__, and __RadDateTimePicker__ controls can work seamlessly with standard ASP.NET validation controls.

The following example shows a sample period selection page.The user has to enter two dates, the second one being after the first. It uses two __RequiredFieldValidator__ instances to ensure the date pickers are not left empty.A __CompareValidator__ ensures that the second date is greater than the first one.

````ASPNET
	<table bgcolor="#cccccc">
	    <tr>
	        <td>Start:</td>
	        <td>
	            <telerik:RadDatePicker ID="StartDate" MinDate="2008/1/1" runat="server" >
	            </telerik:RadDatePicker>
	            <asp:RequiredFieldValidator runat="server" ID="validator1"
	            ControlToValidate="StartDate"
	            ErrorMessage="enter a starting date!">
	            </asp:RequiredFieldValidator>
	        </td>
	    </tr>
	    <tr>
	        <td>End:</td>
	        <td>
	            <telerik:RadDatePicker ID="EndDate" MinDate="2008/1/1" runat="server" >
	            </telerik:RadDatePicker>
	            <asp:RequiredFieldValidator runat="server" ID="validator2"
	            ControlToValidate="EndDate"
	            ErrorMessage="enter an ending date!">
	            </asp:RequiredFieldValidator>
	        </td>
	    </tr>
	    <tr>
	        <td></td>
	        <td>
	            <asp:CompareValidator ID="dateCompareValidator" runat="server"
	            ControlToValidate="EndDate"
	            ControlToCompare="StartDate"
	            Operator="GreaterThan"
	            Type="Date"
	            ErrorMessage="The end date must be after the start one.">
	            </asp:CompareValidator>
	        </td>
	    </tr>
	    <tr>
	        <td colspan=2>
	            <asp:Button runat="server" Text="Submit" ID="Button1" />
	        </td>
	    </tr>
	</table>	
````



>note You need to set the __Type__ property of the __CompareValidator__ to "Date" in order to work with a __RadDatePicker__ . When working with __RadTimePicker__ , or __RadDateTimePicker__ control, the property must be set to "String".
>


For a live example of using validators with a __RadDatePicker__ control, see [Date Picker Validation](http://demos.telerik.com/aspnet-ajax/Calendar/Examples/DatePicker/Validation/DefaultCS.aspx).
