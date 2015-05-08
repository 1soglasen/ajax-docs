---
title: OnClientSelectionChange
page_title: OnClientSelectionChange | RadEditor for ASP.NET AJAX Documentation
description: OnClientSelectionChange
slug: editor/client-side-programming/events/onclientselectionchange
tags: onclientselectionchange
published: True
position: 8
---

# OnClientSelectionChange

The OnClientSelectionChange event signals that the selection within the editor content area has changed.

|  **function OnClientSelectionChange(editor, args)**  |  |  |
| ------ | ------ | ------ |
| **editor** | **object** |Returns a reference to RadEditor client object|
| **args** | **object** |Returns the needed information about the event|

The example below alerts the editor content when the user clicks inside the content area or makes a selection:

````ASP.NET	 
<script type="text/javascript">
	function OnClientSelectionChange(editor, args)
	{
		alert("selection changed" + editor.getSelectionHtml());
	}
</script>
<telerik:radeditor runat="server" ID="RadEditor1"
	OnClientSelectionChange="OnClientSelectionChange">
	<Content>
		 <strong>Sample Content</strong>
	</Content>
</telerik:radeditor> 			
````




