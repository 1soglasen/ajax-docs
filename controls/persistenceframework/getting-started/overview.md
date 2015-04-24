---
title: Overview
page_title: RadPersistenceManager Getting Started | UI for ASP.NET AJAX Documentation
description: RadPersistenceManager Getting Started Overview
slug: persistenceframework/getting-started/overview
tags: overview
published: True
position: 0
---

# Getting Started Overview



The below tutorial will walk you through enabling a state persistence for a page containing several Telerik controls.

1. Drag a **RadPersistenceManager** from the Visual Studio **Toolbox** onto your webpage.

2. The [Smart Tag]() should appear automatically. From there, choose **Open PersistenceManager configuration wizard**.
![persistence-framework-getting-started-st](images/persistence-framework-getting-started-st.png)

3. In the **Configuration Wizard** window select the controls which state should be persisted.
![persistence-framework-getting-started-designer](images/persistence-framework-getting-started-designer.png)

4. Add button controls that will be used to trigger the **Save** and **Load** methods of **RadPersistenceManager**

````ASPNET
<telerik:RadPersistenceManager id="RadPersistenceManager1" runat="server">
	.......
</telerik:RadPersistenceManager>

<telerik:RadButton ID="saveBtn" Text="Save State" runat="server" Width="67px" OnClick="saveBtn_Click">
</telerik:RadButton>
<telerik:RadButton ID="loadBtn" Text="Load State" runat="server" Width="67px" OnClick="loadBtn_Click">
</telerik:RadButton>
````
````C#
protected void loadBtn_Click(object sender, EventArgs e)
{
	RadPersistenceManager1.LoadState();
}

protected void saveBtn_Click(object sender, EventArgs e)
{
	RadPersistenceManager1.SaveState();
}
````
````VB.NET
Protected Sub loadBtn_Click(sender As Object, e As EventArgs)
	RadPersistenceManager1.LoadState()
End Sub

Protected Sub saveBtn_Click(sender As Object, e As EventArgs)
	RadPersistenceManager1.SaveState()
End Sub
````


# See Also

 * [Persistence Framework online demos](http://demos.telerik.com/aspnet-ajax/persistence-framework/examples/overview/defaultcs.aspx)
