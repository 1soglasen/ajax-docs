---
title: RadAjaxManager Designer Does Not Locate All Controls
page_title: RadAjaxManager Designer Does Not Locate All Controls | UI for ASP.NET AJAX Documentation
description: RadAjaxManager Designer Does Not Locate All Controls
slug: ajax/radajaxmanager/troubleshooting/radajaxmanager-designer-does-not-locate-all-controls
tags: radajaxmanager,designer,does,not,locate,all,controls
published: True
position: 2
---

# RadAjaxManager Designer Does Not Locate All Controls



This troubleshooting help article discusses four scenarios where __RadAjaxManager__ is not able to locate some controls	on a page but they are still AJAX enabled and updated by __RadAjaxManager__.

## 

1. __Controls Are Placed in Cells of an asp:Table__The table cells need to have an ID set (__Example 1__) as well as runat="server" included and the designer will locate	all the controls within the tableExample 1: Setting the ID for table cells of an asp:Table and setting runat='server'.

````ASPNET
	    <asp:Table ID="Table1" runat="server">
	        <asp:TableRow runat="server" ID="rol_1">
	            <asp:TableCell runat="server" ID="cell_11">
	                <asp:Panel ID="Panel1" runat="server">
	                    <asp:Button ID="Button1" runat="server" Text="Button" />
	                    <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
	                </asp:Panel>
	            </asp:TableCell>
	            <asp:TableCell runat="server" ID="cell_12"></asp:TableCell>
	            <asp:TableCell runat="server" ID="cell_13"></asp:TableCell>
	        </asp:TableRow>
	        <asp:TableRow runat="server" ID="row_2">
	            <asp:TableCell runat="server" ID="cell_21">
	                <div runat="server" id="div1">
	                    <asp:CheckBox ID="CheckBox1" runat="server" />
	                </div>
	            </asp:TableCell>
	            <asp:TableCell runat="server" ID="cell_22"></asp:TableCell>
	            <asp:TableCell runat="server" ID="cell_23"></asp:TableCell>
	        </asp:TableRow>
	    </asp:Table>
````

After the IDs of the table cells have IDs and the runat="server" set, then the button, check box and text box could be located by the	designer and you can add the AJAX settings shown in __Example 2__.Example 2: AJAXify the controls placed in cells of asp:Table.

````ASPNET
	    <telerik:RadScriptManager ID="RadScriptManager1" runat="server">
	    </telerik:RadScriptManager>
	    <telerik:RadAjaxManager ID="RadAjaxManager1" runat="server">
	        <AjaxSettings>
	            <telerik:AjaxSetting AjaxControlID="Button1">
	                <UpdatedControls>
	                    <telerik:AjaxUpdatedControl ControlID="TextBox1" />
	                </UpdatedControls>
	            </telerik:AjaxSetting>
	            <telerik:AjaxSetting AjaxControlID="CheckBox1">
	                <UpdatedControls>
	                    <telerik:AjaxUpdatedControl ControlID="TextBox1" />
	                </UpdatedControls>
	            </telerik:AjaxSetting>
	        </AjaxSettings>
	    </telerik:RadAjaxManager>
````



1. __Control Is Nested in a Template of a Composite Control.__Those templates may "hide" wrapped controls from the __RadAjaxManager__ Designer. Telerik Support recommends addingAJAX settings [programmatically]({%slug ajax/radajaxmanager/how-to/add-ajaxsettings-programmatically%}) in such scenarios, which together with__FindControl__ method usage, provides __RadAjaxManager__ with the ability to AJAX-enable and updatecontrols at all "levels" of the application. For example, if the control you want to update is located within__RadDockableObject__(see [RadDock](http://www.Telerik.com/RadDock) web control),it could be found at runtime using RadDockableObject.FindControl("<controlID>") and then set it as updated control.	You can see this approach in the [AJAX RadDock online demo](http://demos.telerik.com/aspnet-ajax/dock/examples/overview/defaultcs.aspx).

1. __Controls are placed in a WebUserControl.__The previous case is valid here as well. You could use the same approach and add AJAX settings[dynamically]({%slug ajax/radajaxmanager/troubleshooting/controls-wrapped-in-ajaxpanel-and-added-to-ajaxmanager-settings%}).For example if the control is placed in a__WebUserControl__, it could be found at runtime using the WebUserControl1.FindControl("<controlID>") and then setit as an update control. See also [how to AJAX-enable user controls]({%slug ajax/radajaxmanager/how-to/radajax-and-webusercontrols%}).

1. __Controls are placed in a different content of MasterPage scenario.__You can follow the example of adding AJAX setting [programmatically]({%slug ajax/radajaxmanager/troubleshooting/controls-wrapped-in-ajaxpanel-and-added-to-ajaxmanager-settings%}) as thecontrols are hidden from the designer when placed in a content place holder. In this case you can find the control at runtime using theContentPlaceHolder1.FindControl("<controlID>") and then set it as an update control.

# See Also

 * [Add AjaxSettings Programmatically]({%slug ajax/radajaxmanager/how-to/add-ajaxsettings-programmatically%})

 * [Using RadAjaxManager and RadAjaxManagerProxy and with Master Page and Content Pages]({%slug ajax/radajaxmanager/how-to/radajax-and-masterpage%})

 * [Using RadAjaxManager and RadAjaxManager Proxy with WebUserControls]({%slug ajax/radajaxmanager/how-to/radajax-and-webusercontrols%})

 * [Demo: RadDock - Telerik's ASP.NET for AJAX Dock](http://demos.telerik.com/aspnet-ajax/dock/examples/overview/defaultcs.aspx)
