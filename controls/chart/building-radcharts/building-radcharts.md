---
title: Building RadCharts
page_title: Building RadCharts | UI for ASP.NET AJAX Documentation
description: Building RadCharts
slug: chart/building-radcharts/building-radcharts
tags: building,radcharts
published: True
position: 0
---

# Building RadCharts



>caution  __RadChart__ has been replaced by[RadHtmlChart](http://www.telerik.com/products/aspnet-ajax/html-chart.aspx), Telerik's client-side charting component.	If you are considering __RadChart__ for new development, examine the[RadHtmlChart documentation](ffd58685-7423-4c50-9554-f92c70a75138)and[online demos](http://demos.telerik.com/aspnet-ajax/htmlchart/examples/overview/defaultcs.aspx)first to see if it will fit your development needs.	If you are already using __RadChart__ in your projects, you can migrate to __RadHtmlChart__ by following these articles:[Migrating Series](2f393f28-bc31-459c-92aa-c3599785f6cc),[Migrating Axes](3f1bea81-87b9-4324-b0d2-d13131031048),[Migrating Date Axes](93226130-bc3c-4c53-862a-f9e17b2eb7dd),[Migrating Databinding](d6c5e2f1-280c-4fb0-b5b0-2f507697511d),[Feature parity](010dc716-ce38-480b-9157-572e0f140169).	Support for __RadChart__ is discontinued as of __Q3 2014__ , but the control will remain in the assembly so it can still be used.	We encourage you to use __RadHtmlChart__ for new development.
>


## 

To provide flexibility and best ease-of-use, Telerik provides multiple avenues to populate RadChart. There are four main techniques for building the chart: interactively at design-time, declaratively in the ASP.NET HTML markup, programmatically at runtime and by data binding.

In simple scenarios or to test out a design you can use the design-time interface to build the entire chart. Collection editors provide a consistent interface and easy navigation over all your chart series and series items. You can also use the RadChart Wizard to display a subset of the data.

If your design style leans towards working with the ASP.NET HTML code directly you can declaratively define your chart series and chart series items.

Most business applications display some sort of database data so RadChart fully supports binding data sources to labels and data elements. RadChart also supports data binding to the X-Axis. In addition to database data, RadChart can bind to XML. RadChart binds to ObjectDataSource to support enterprise multi-tier scenarios.And of course you can bind your chart to arrays, collections, generic lists of simple types and lists of objects.

To create and populate the RadChart, [ChartSeries]({%slug chart/understanding-radchart-elements/series-overview%}) and [ChartSeriesItem]({%slug chart/understanding-radchart-elements/series-items%}) collections:

* At design time by [using the editors for ChartSeries and ChartSeriesItem collections]({%slug chart/building-radcharts/populate-radchart-at-design-time%}) or [using the RadChart Wizard]({%slug chart/understanding-radchart-ui/the-radchart-user-interface%}).

* [Declaratively in the ASP.NET HTML markup]({%slug chart/building-radcharts/creating-radchart-declaratively%}).

* [Binding to a datasource]({%slug chart/building-radcharts/data-binding-radchart%}) at run time or design time.

* Bind to a datasource programmatically to populate the ChartSeries and ChartSeriesItem collections. See this [minimal example of creating and populating a RadChart programmatically]({%slug chart/building-radcharts/creating-radchart-programmatically%}) or this [more complex example]({%slug chart/building-radcharts/creating-radchart-programmatically---more-complex-example%}).

# See Also

 * [Populate RadChart at Design-Time]({%slug chart/building-radcharts/populate-radchart-at-design-time%})

 * [Creating RadChart Declaratively]({%slug chart/building-radcharts/creating-radchart-declaratively%})

 * [Creating RadChart Programmatically]({%slug chart/building-radcharts/creating-radchart-programmatically%})

 * [Creating RadChart Programmatically - more complex example]({%slug chart/building-radcharts/creating-radchart-programmatically---more-complex-example%})

 * [Data Binding RadChart]({%slug chart/building-radcharts/data-binding-radchart%})

 * [Data Binding RadChart to an Array]({%slug chart/building-radcharts/data-binding-radchart-to-an-array%})

 * [Data Binding RadChart to a Database Object]({%slug chart/building-radcharts/data-binding-radchart-to-a-database-object%})

 * [Data Binding RadChart to a Generic List]({%slug chart/building-radcharts/data-binding-radchart-to-a-generic-list%})

 * [Data Binding RadChart to a Generic List of Simple Types]({%slug chart/building-radcharts/data-binding-radchart-to-a-generic-list-of-simple-types%})

 * [Data Binding RadChart to a Generic List of Objects]({%slug chart/building-radcharts/data-binding-radchart-to-a-generic-list-of-objects%})

 * [Data Binding RadChart to a Generic List of Objects]({%slug chart/building-radcharts/data-binding-radchart-to-a-generic-list-of-objects%})

 * [Data Binding RadChart to an ObjectDataSource]({%slug chart/building-radcharts/data-binding-radchart-to-an-objectdatasource%})

 * [Binding to ObjectDataSource at Run-Time]({%slug chart/building-radcharts/binding-to-objectdatasource-at-run-time%})

 * [Data Binding RadChart to ObjectDataSource at Design-Time]({%slug chart/building-radcharts/data-binding-radchart-to-objectdatasource-at-design-time%})

 * [Data Binding RadChart to an XML file]({%slug chart/building-radcharts/data-binding-radchart-to-an-xml-file%})

 * [Binding to XML at Design-Time using an XMLDataSource]({%slug chart/building-radcharts/binding-to-xml-at-design-time-using-an-xmldatasource%})

 * [Binding to XML Directly at Run-Time]({%slug chart/building-radcharts/binding-to-xml-directly-at-run-time%})
