---
title: Binding to DataTable, DataSet, or DataView
page_title: Binding to DataTable, DataSet, or DataView | UI for ASP.NET AJAX Documentation
description: Binding to DataTable, DataSet, or DataView
slug: autocompletebox/data-binding/binding-to-datatable,-dataset,-or-dataview
tags: binding,to,datatable,,dataset,,or,dataview
published: True
position: 2
---

# Binding to DataTable, DataSet, or DataView



**RadAutoCompleteBox** can be bound to a **DataTable**,**DataSet**, and **DataView**. The following example shows binding to a DataTable object.

## Binding to a DataTable at runtime

The declaration of **RadAutoCompleteBox** in the markup includes no **DataSourceID** property or **Items** section.

````ASPNET
<telerik:RadAutoCompleteBox ID="RadAutoCompleteBox1" InputType="Text" runat="server">
</telerik:RadAutoCompleteBox>
````



In the **Page_Load** event handler, create and fill the **DataTable** object, then bind it to RadAutoCompleteBox. The **DataBind** method must be called after setting the **DataSource** property.



````C#
	
protected void Page_Load(object sender, EventArgs e)
{
	RadAutoCompleteBox1.DataSource = GetData();
	RadAutoCompleteBox1.DataTextField = "ProductName";
	RadAutoCompleteBox1.DataValueField = "ProductID";
}

private static DataTable GetData()
{
	SqlDataAdapter adapter = new SqlDataAdapter(@"SELECT [ProductID], [ProductName], [SupplierID], [CategoryID], [QuantityPerUnit], [UnitPrice], 
		[UnitsInStock], [UnitsOnOrder], [ReorderLevel], [Discontinued] FROM [Products]",
		ConfigurationManager.ConnectionStrings["NorthwindConnectionString"].ConnectionString);

	DataTable data = new DataTable();
	adapter.Fill(data);

	return data;
}
	
````
````VB.NET
Protected Sub Page_Load(sender As Object, e As EventArgs) Handles Me.Load
	RadAutoCompleteBox1.DataSource = GetData()
	RadAutoCompleteBox1.DataTextField = "ProductName"
	RadAutoCompleteBox1.DataValueField = "ProductID"
End Sub

Private Shared Function GetData() As DataTable
	Dim adapter As New SqlDataAdapter("SELECT * FROM [Products]", ConfigurationManager.ConnectionStrings("NorthwindConnectionString").ConnectionString)

	Dim data As New DataTable()
	adapter.Fill(data)

	Return data
End Function
````


# See Also

 * [Overview]({%slug autocompletebox/server-side-programming/overview%})
