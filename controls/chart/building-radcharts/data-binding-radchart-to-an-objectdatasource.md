---
title: Data Binding RadChart to an ObjectDataSource
page_title: Data Binding RadChart to an ObjectDataSource | RadChart for ASP.NET AJAX Documentation
description: Data Binding RadChart to an ObjectDataSource
slug: chart/building-radcharts/data-binding-radchart-to-an-objectdatasource
tags: data,binding,radchart,to,an,objectdatasource
published: True
position: 11
---

# Data Binding RadChart to an ObjectDataSource

>caution  **RadChart** has been replaced by[RadHtmlChart](http://www.telerik.com/products/aspnet-ajax/html-chart.aspx), Telerik's client-side charting component.	If you are considering **RadChart** for new development, examine the[RadHtmlChart documentation](ffd58685-7423-4c50-9554-f92c70a75138)and[online demos](http://demos.telerik.com/aspnet-ajax/htmlchart/examples/overview/defaultcs.aspx)first to see if it will fit your development needs.	If you are already using **RadChart** in your projects, you can migrate to **RadHtmlChart** by following these articles:[Migrating Series](2f393f28-bc31-459c-92aa-c3599785f6cc),[Migrating Axes](3f1bea81-87b9-4324-b0d2-d13131031048),[Migrating Date Axes](93226130-bc3c-4c53-862a-f9e17b2eb7dd),[Migrating Databinding](d6c5e2f1-280c-4fb0-b5b0-2f507697511d),[Feature parity](010dc716-ce38-480b-9157-572e0f140169).	Support for **RadChart** is discontinued as of **Q3 2014** , but the control will remain in the assembly so it can still be used.	We encourage you to use **RadHtmlChart** for new development.

RadChart can be bound to [ObjectDataSource](http://msdn2.microsoft.com/en-us/library/system.web.ui.webcontrols.objectdatasource.aspx) in multi-tier application scenarios.See the MSDN article [ObjectDataSource Overview](http://msdn2.microsoft.com/en-us/library/9a4kyhcx.aspx) for more information on where and why you would use an [ObjectDataSource](http://msdn2.microsoft.com/en-us/library/system.web.ui.webcontrols.objectdatasource.aspx) control.

An [ObjectDataSource](http://msdn2.microsoft.com/en-us/library/system.web.ui.webcontrols.objectdatasource.aspx) represents a business object and provides data to data-bound controls in multi-tier applications. The application doesn't need to know how data is obtained as long as you connect the [ObjectDataSource](http://msdn2.microsoft.com/en-us/library/system.web.ui.webcontrols.objectdatasource.aspx) to an object that has [DataObjectAttribute](http://msdn2.microsoft.com/en-us/library/system.componentmodel.dataobjectattribute.aspx) and[DataObjectMethodAttribute](http://msdn2.microsoft.com/en-us/library/system.componentmodel.dataobjectmethodattribute.aspx) attributes defined.See the following examples for how to create the business object and how to bind RadChart to [ObjectDataSource](http://msdn2.microsoft.com/en-us/library/system.web.ui.webcontrols.objectdatasource.aspx):

* [Creating an object that can be consumed by ObjectDataSource]({%slug chart/building-radcharts/creating-an-object-that-can-be-consumed-by-objectdatasource%}).

* [Binding RadChart to ObjectDataSource at design-time]({%slug chart/building-radcharts/data-binding-radchart-to-objectdatasource-at-design-time%}).

* [Binding RadChart to ObjectDataSource at programmatically at run-time]({%slug chart/building-radcharts/binding-to-objectdatasource-at-run-time%}).

# See Also

 * [Data Binding RadChart]({%slug chart/building-radcharts/data-binding-radchart%})

 * [Data Binding RadChart to an Array]({%slug chart/building-radcharts/data-binding-radchart-to-an-array%})

 * [Data Binding RadChart to a Database Object]({%slug chart/building-radcharts/data-binding-radchart-to-a-database-object%})

 * [Data Binding RadChart to a Generic List]({%slug chart/building-radcharts/data-binding-radchart-to-a-generic-list%})

 * [Creating an Object that can be Consumed by ObjectDataSource]({%slug chart/building-radcharts/creating-an-object-that-can-be-consumed-by-objectdatasource%})

 * [Binding to ObjectDataSource at Run-Time]({%slug chart/building-radcharts/binding-to-objectdatasource-at-run-time%})

 * [Data Binding RadChart to an XML file]({%slug chart/building-radcharts/data-binding-radchart-to-an-xml-file%})
