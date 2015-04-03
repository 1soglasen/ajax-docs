---
title: Pie Chart
page_title: Pie Chart | UI for ASP.NET AJAX Documentation
description: Pie Chart
slug: htmlchart/chart-types/pie-chart
tags: pie,chart
published: True
position: 10
---

# Pie Chart



## 

The Pie chart displays the data as sectors from a circle and is therefore useful for displaying data as parts of a whole.The Pie chart displays a single series of data in a two-dimensional circle. This help article shows which properties touse to customize a Pie chart (__Figure 1__) and shows sample code (__Example 1__) to create one.
>caption Figure 1: A Pie chart with one item exploded.

![htmlchart-piechart-simple-example](images/htmlchart-piechart-simple-example.png)

You can customize a Pie chart:

* The color is controlled via the __BackgroundColor__ property of the __PieSeriesItem__.

* The name that is shown in the legend is set via the __Name__ property of the __PieSeriesItem__.

* Whether the sector is separated from the rest of the circle is controlled via the __Exploded__ property of the__PieSeriesItem__.The Pie chart and the Donut chart are the only chart types in whose context the __Exploded__property is meaningful and will have effect.

* The size of a segment of the Pie is controlled by its __Y__ property of the __PieSeriesItem__and its relation to the other items' value.

>important Only positive values have meaning in the context of a Pie chart and the developer must make sure that only positive value data is passed to the chart.
>


* Each item can have a label and a tooltip that follow the common pattern defined in the __DataFormatString__ property of the__LabelsAppearance__ and __TooltipsAppearance__ sections of the series.The format string uses the __Y__ of the item. You can also load custom text from data source fields in labels and tooltips by using the composite [ClientTemplate]({%slug htmlchart/functionality/clienttemplate/overview%}) property.

* The title, background colors and legend are controlled via the inner properties of the __RadHtmlChart__ control and are common for all charts.You can find more information on the matter is available in the [Server-side API]({%slug htmlchart/server-side-programming/basic-configuration%})and in the [Element structure]({%slug htmlchart/radhtmlchart-structure%}) articles.

The Pie chart from __Figure 1__ was created with the code in __Example 1__.

__Example 1__: Creating the simple Pie chart in __Figure 1__ using hard coded data.

````ASPNET
	    <telerik:RadHtmlChart runat="server" ID="PieChart1" Transitions="true">
	        <PlotArea>
	            <Series>
	                <telerik:PieSeries StartAngle="90">
	                    <LabelsAppearance Position="OutsideEnd" DataFormatString="{0} %" />
	                    <TooltipsAppearance DataFormatString="{0} %" />
	                    <SeriesItems>
	                        <telerik:PieSeriesItem BackgroundColor="Purple" Exploded="true" Name="Internet Explorer" Y="18.3" />
	                        <telerik:PieSeriesItem BackgroundColor="Orange" Exploded="false" Name="Firefox" Y="35.8" />
	                        <telerik:PieSeriesItem BackgroundColor="Green" Exploded="false" Name="Chrome" Y="38.3" />
	                        <telerik:PieSeriesItem BackgroundColor="Blue" Exploded="false" Name="Safari" Y="4.5" />
	                        <telerik:PieSeriesItem BackgroundColor="Red" Exploded="false" Name="Opera" Y="2.3" />
	                    </SeriesItems>
	                </telerik:PieSeries>
	            </Series>
	        </PlotArea>
	        <ChartTitle Text="Browser Usage for April 2012">
	        </ChartTitle>
	    </telerik:RadHtmlChart>
````



>note The Pie chart does not have axes as they are not applicable in its context.
>


>caution Currently the __RadHtmlChart__ supports only one Pie series per chart. Adding more than one willresult in overlapping charts and an extended legend.
>


# See Also

 * [Choose a Data Source for Your RadHtmlChart:]({%slug htmlchart/design-time/overview%})

 * [- Configuration Wizard]({%slug htmlchart/design-time/overview%})

 * [- SqlDataSource]({%slug htmlchart/data-binding/sqldatasource%})

 * [- LinqDataSource]({%slug htmlchart/data-binding/linqdatasource%})

 * [- EntityDataSource]({%slug htmlchart/data-binding/entitydatasource%})

 * [- ObjectDataSource]({%slug htmlchart/data-binding/objectdatasource%})

 * [- XmlDataSource]({%slug htmlchart/data-binding/xmldatasource%})

 * [- Generic List]({%slug htmlchart/data-binding/generic-list-of-custom-objects%})

 * [- DataSet]({%slug htmlchart/data-binding/dataset%})

 * [- Array]({%slug htmlchart/data-binding/array%})

 * [RadHtmlChart Element Structure]({%slug htmlchart/radhtmlchart-structure%})

 * [RadHtmlChart Donut Chart]({%slug htmlchart/chart-types/donut-chart%})

 * [RadHtmlChart Server-side API Overview]({%slug htmlchart/server-side-programming/overview%})
