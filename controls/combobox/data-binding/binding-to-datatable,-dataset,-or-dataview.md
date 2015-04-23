---
title: Binding to DataTable, DataSet, or DataView
page_title: Binding to DataTable, DataSet, or DataView | RadComboBox for ASP.NET AJAX Documentation
description: Binding to DataTable, DataSet, or DataView
slug: combobox/data-binding/binding-to-datatable,-dataset,-or-dataview
tags: binding,to,datatable,,dataset,,or,dataview
published: True
position: 2
---

# Binding to DataTable, DataSet, or DataView



## 

**RadComboBox** can be bound to a **DataTable**, **DataSet**, and **DataView**. The following example shows binding to a **DataTable** object.

The declaration of RadComboBox object includes no DataSourceID property or `<items>` section:

````ASPNET
<telerik:radcombobox id="RadComboBox1" runat="server" />
````



In the **Page_Load** event handler, create and fill the **DataTable** object, then bind it to the RadComboBox. The **DataBind** method must be called after setting the **DataSource** property.



````C#
	
protected void Page_Load(object sender, EventArgs e)
{
	if (!Page.IsPostBack)
	{
		BindToDataTable(RadComboBox1);
	}

}

private void BindToDataTable(RadComboBox combo)
{

	SqlConnection con = new SqlConnection("Data Source=LOCAL;Initial Catalog=Combo;Integrated Security=True");

	SqlDataAdapter adapter = new SqlDataAdapter("SELECT [Text], [Value] FROM [Links]", con);
	DataTable links = new DataTable();

	adapter.Fill(links);

	combo.DataTextField = "Text";
	combo.DataValueField = "Value";
	combo.DataSource = links;
	combo.DataBind();
}
	          
````
````VB.NET
	
Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
	If Not Page.IsPostBack Then
		BindToDataTable(RadComboBox1)
	End If
End Sub 'Page_Load

Private Sub BindToDataTable(ByVal combo As RadComboBox)

	Dim con As New SqlConnection("Data Source=LOCAL;Initial Catalog=Combo;Integrated Security=True")

	Dim adapter As New SqlDataAdapter("SELECT [Text], [Value] FROM [Links]", con)
	Dim links As New DataTable()

	adapter.Fill(links)

	combo.DataTextField = "Text"
	combo.DataValueField = "Value"
	combo.DataSource = links
	combo.DataBind()
End Sub 'BindToDataTable
	
````

