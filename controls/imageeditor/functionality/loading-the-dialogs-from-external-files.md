---
title: Loading the Dialogs from External Files
page_title: Loading the Dialogs from External Files | UI for ASP.NET AJAX Documentation
description: Loading the Dialogs from External Files
slug: imageeditor/functionality/loading-the-dialogs-from-external-files
tags: loading,the,dialogs,from,external,files
published: True
position: 0
---

# Loading the Dialogs from External Files



## Externalizing the Dialogs

By default, all __RadImageEditor__ dialogs are embedded as resource fils in the Telerik.Web.UI.dll file, which makes their customization harder. In order to provide an easy way to modify the ImageEditor's dialogs, __since Q1 2012__, the Telerik UI for ASP.NET AJAX installation now comes with an extrafolder named __ImageEditorDialogs__ which contains the dialogs' ascx files. You can configure __RadImageEditor__ to use the external dialog files by copying the __ImageEditorDialogs__ folder to the root of the web site and setting the __ExternalDialogsPath__ property (also available since Q1 2012) to point to it, e.g.

````ASPNET
	    <telerik:RadImageEditor ID="RadImageEditor1" ExternalDialogsPath="~/ImageEditorDialogs" runat="server">
	    </telerik:RadImageEditor>
````



## Examples

This example demonstrates how to add fonts in the AddText dialog's dropdown:

1. Copy the __ImageEditorDialogs__ folder to the root of the web site.

1. Set the __ExternalDialogsPath__ property to point to the folder where you copied the files (e.g. ExternalDialogsPath="~/ImageEditorDialogs")

1. Open the __AddText.ascx__ file and locate the __RadComboBox__ with ID __fontFamily__ so you can add more options to it:

````ASPNET
	    <telerik:RadComboBox ID="fontFamily" runat="server" AutoPostBack="false" EnableViewState="false"
	        CausesValidation="false" Width="130px">
	        <Items>
	          <telerik:RadComboBoxItem Text="Arial" Value="arial" />
	          <telerik:RadComboBoxItem Text="Times New Roman" Value="times new roman" />
	          <telerik:RadComboBoxItem Text="Verdana" Value="verdana" />
	          <telerik:RadComboBoxItem Text="Tahoma" Value="tahoma" />
	
	          <telerik:RadComboBoxItem Text="Courier New" Value="courier new" />
	          <telerik:RadComboBoxItem Text="Georgia" Value="georgia" />
	          <telerik:RadComboBoxItem Text="Ms Sans Serif" Value="ms sans serif" />
	        </Items>
	      </telerik:RadComboBox>
````





If you want to __hide some functionality__ in some dialog, you can do that by applying __style="display:none"__ to it. For example, here is how to hide the Preset Size dropdown in the Resize dialog:

````ASPNET
	        <tr style="display: none;">
	            <td class="rieRightAligned">
	                <label id="lblPresetSizes" runat="server">
	                    Preset Sizes:</label>
	            </td>
	            <td colspan="2">
	                <telerik:RadComboBox ID="PresetSizes" runat="server" AutoPostBack="false" EnableViewState="false"
	                    CausesValidation="false" Width="140px">
	                    <Items>
	                        <telerik:RadComboBoxItem Text="Original W x H" Value="original" />
	                        <telerik:RadComboBoxItem Text="Custom W x H" Value="custom" />
	                        <telerik:RadComboBoxItem Text="800x600px" Value="800,600" />
	                        <telerik:RadComboBoxItem Text="1024x768px" Value="1024,768" />
	                        <telerik:RadComboBoxItem Text="1280x1024px" Value="1280,1024" />
	                        <telerik:RadComboBoxItem Text="1440x900px" Value="1440,900" />
	                    </Items>
	                </telerik:RadComboBox>
	            </td>
	        . . . . 
````


