---
title: Binding to a Data Source
page_title: Binding to a Data Source | UI for ASP.NET AJAX Documentation
description: Binding to a Data Source
slug: panelbar/getting-started/binding-to-a-data-source
tags: binding,to,a,data,source
published: True
position: 1
---

# Binding to a Data Source



## 

This tutorial will show how to bind __RadPanelBar__ to an __AccessDataSource__:

1. Locate the "Nwind.mdb" file that appears in the "Live Demos\App_Data" sub-folder of the folder where you installed RadControls "for ASP.NET Ajax".

1. Drag this file ("Northwind.mdf") to the "App_Data" folder in the Solution Explorer for your project:![Nwind MDB](images/panelbar_nwindmdb.png)

1. Add the following connection string in the web config file under the connection string section:![Connection String](images/panelbar_connection_string.png)

1. Drag a __RadPanelBar__ component from the toolbox onto your Web page. The __RadPanelBar__[Smart Tag]({%slug panelbar/design-time/smart-tag%}) should appear automatically:![PanelBar Tasks](images/panelbar_gettingstarted1.png)

1. In the __RadPanelBar__ Smart Tag, use the __Skin__ drop-down to change the [skin]({%slug panelbar/appearance-and-styling/skins%}) for the __RadPanelBar__ to "Vista":![Vista Skin](images/panelbar_skinvista.png)

1. Still in the Smart Tag, open the __Choose Data Source__ drop-down and select __New Data Source__.![New Data Source](images/panelbar_newdatasource.png)

1. The Data Source Configuration Wizard appears. In the Select a DataSource Type screen, specify an __SqlDataSource__ and click __OK.__![Choose A DataSourcecType](images/panelbar_chooseadatasourcetype.png)

1. In the __Choose your Data Connection__ screen, click the __Browse__ button, and select the "NorthwindConnectionString". Then choose __Next__ to continue:![Choose A Database](images/panelbar_chooseadatabase.png)

1. In the __Configure the Select Statement__ screen, choose __Specify columns from a table or view__.

1. In the __Name__ drop-down, select the "Employees" table.

1. In the __Columns__ panel, Select the "EmployeeID", "FirstName", and "ReportsTo" fields. Then choose __Next__ to continue:![Configure Select](images/panelbar_configureselect.png)

1. Click the __Test Query__ button to see the data. Then click __Finish__ to exit the Configure Data Source Wizard:![Query Test](images/panelbar_testquery.png)

1. In the Properties pane for the __RadPanelBar__ component,

* Set the __DataFieldId__ property to "EmployeeID".

* Set the __DataFieldParentId__ property to "ReportsTo".

* Set the __DataTextField__ property to "FirstName":![Data Fields](images/panelbar_datafields.png)

1. Run the application. The panel bar has a single root level item (for the one record with a null value in the "ReportsTo" field). When you expand this item, you can see level 1 items for every record that had Andrew's ID in the "ReportsTo" field. You can expand the item labelled "Steven" to see the level 2 items for records that had Steven's ID in the "ReportsTo" field:![Bound PanelBar](images/panelbar_bound.png)

# See Also

 * [Overview]({%slug panelbar/data-binding/overview%})

 * [Overview]({%slug panelbar/getting-started/overview%})
