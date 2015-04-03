---
title: Candlestick Chart
page_title: Candlestick Chart | UI for ASP.NET AJAX Documentation
description: Candlestick Chart
slug: htmlchart/chart-types/candlestick-chart
tags: candlestick,chart
published: True
position: 5
---

# Candlestick Chart



## 

The __CandlestickChart__ describes the price movements of a financial instrument (e.g security or currency) over time.It is a combination of [BarChart]({%slug htmlchart/chart-types/bar-chart%}) and[LineChart]({%slug htmlchart/chart-types/line-chart%}) where each SeriesItem (a Candlestick) displays the__Open, High, Low__ and __Close__ prices for a single day. A Candlestick consists of:

* __Body__ - the wide part of the CandlestickSeriesItem that shows the Open and Close prices.

* If the Close price is higher than the Open price, the body iscalled __Hollow__ (usually colored white or green)and the __BackgroundColor__ property of the__CandlestickSeries -> Appearance -> FillStyle__ inner tag controls its color.

* If, however, the Close price is lower than the Open price, the bodyis called __Filled__ (usually colored black or red) andthe __DownColor__ property of the CandlestickSeries tag controls its color.

* __Wicks__ - the __long thin lines__ located above and below the body, also called__shadows__ that show the High and Low prices. The High price is represented by the top of the__Upper Wick__, while the bottom of the __Lower Wick__ indicates the Low price.![htmlchart-candlestickchart-simple-example](images/htmlchart-candlestickchart-simple-example.png)

The CandlestickChart can be fully customized:

* The color of the Hollow CandlestickSeriesItems (Open Price < Close Price)of each series is controlled via the __BackgroundColor__property of the __CandlestickSeries -> Appearance -> FillStyle__ inner tag. The colorthe Filled CandlestickSeriesItems (Open Price > Close Price) of each series is controlled via the__DownColor__ property of the CandlestickSeries tag.

* The name that is shown in the legend is chosen via the __Name__ property of the __CandlestickSeries__.

* Open, High, Low and Close values of each item are controlled respectively by __Open, High, Low__ and__Close__ properties of the __CandlestickSeries__.

* Each item can have a tooltip with an already predefined pattern by design. The tooltip pattern can be modified through the__DataFormatString__ property of the __TooltipsAppearance__ sections of theseries. The format string uses the __Open, High, Low, Close__ and the corresponing __XAxis item's value__.*(Series Labels in CandlestickSeries are not supported)*

* The axes are also fully customizable - they automatically adjust their scale to accomodate the data that comes in and forfiner tuning there are numerous properties that can change each aspect:

* Directly in the axis tag you can use its properties to control color, major and minor tick types and sizes,minimal and maximal values for the Y axis (plus a step size) whereas the X-axis requires a set of items to matchthe number of SeriesItems the series have. This is also the place where the crossing value with the other axiscan be set (the index of an item for an item axis) and whether the axis will be reversed

* The inner tags of the axis tag can control the major and minor grid lines in terms of colour and sizeand the labeles can have a DataFormatString, position and visibility set through each inner tag's properties

* The title, background colors and legend are controlled via the inner properties of the __RadHtmlChart__ control and are common for all charts.More information on the matter is available in the [Server-side API]({%slug htmlchart/server-side-programming/basic-configuration%})and in the [Element structure]({%slug htmlchart/radhtmlchart-structure%}) articles.

The chart from the image above is created with the code below:

>tip Not all properties are necessary, the RadHtmlChart will match the axes to the values if you do not declare explicit values, steps and tick properties (although the	Items for axes that need them are necessary).
>


````ASPNET
		<telerik:RadHtmlChart runat="server" ID="CandlestickChart" Width="800" Height="500"
			Transitions="true">
			<Appearance>
				<FillStyle BackgroundColor="White"></FillStyle>
			</Appearance>
			<ChartTitle Text="Coca Cola Hellenic Bottling Co SA (OCCH :NYSE)">
				<Appearance Align="Center" BackgroundColor="White" Position="Top">
				</Appearance>
			</ChartTitle>
			<Legend>
				<Appearance BackgroundColor="White" Position="Bottom">
				</Appearance>
			</Legend>
			<PlotArea>
				<Appearance>
					<FillStyle BackgroundColor="White"></FillStyle>
				</Appearance>
				<XAxis AxisCrossingValue="0" Color="Black" MajorTickType="Outside" MinorTickType="Outside"
					Reversed="false">
					<TitleAppearance Text="Days">
					</TitleAppearance>
					<LabelsAppearance RotationAngle="0">
					</LabelsAppearance>
					<MajorGridLines Color="#EFEFEF" Width="1"></MajorGridLines>
					<MinorGridLines Color="#F7F7F7" Width="1"></MinorGridLines>
					<Items>
						<telerik:AxisItem LabelText="Feb \'11" />
						<telerik:AxisItem LabelText="Feb \'18" />
						<telerik:AxisItem LabelText="Feb \'25" />
						<telerik:AxisItem LabelText="Mar \'04" />
						<telerik:AxisItem LabelText="Mar \'11" />
						<telerik:AxisItem LabelText="Mar \'18" />
						<telerik:AxisItem LabelText="Mar \'25" />
						<telerik:AxisItem LabelText="Apr \'01" />
						<telerik:AxisItem LabelText="Apr \'08" />
						<telerik:AxisItem LabelText="Apr \'15" />
						<telerik:AxisItem LabelText="Apr \'22" />
						<telerik:AxisItem LabelText="Apr \'29" />
						<telerik:AxisItem LabelText="May \'06" />
					</Items>
					<TitleAppearance Position="Center" RotationAngle="0" Text="Days">
					</TitleAppearance>
				</XAxis>
				<YAxis AxisCrossingValue="0" Color="Black" MajorTickType="Outside" MinorTickType="Outside"
					Reversed="false" MinValue="20" MaxValue="30" Step="1">
					<LabelsAppearance DataFormatString="{0:C}">
					</LabelsAppearance>
					<MajorGridLines Color="#EFEFEF" Width="1"></MajorGridLines>
					<MinorGridLines Color="#F7F7F7" Width="1"></MinorGridLines>
					<TitleAppearance Position="Center" RotationAngle="0" Text="Price">
					</TitleAppearance>
				</YAxis>
				<Series>
					<telerik:CandlestickSeries Name="Coca Cola" DownColor="Red">
						<Appearance>
							<FillStyle BackgroundColor="Green"></FillStyle>
						</Appearance>
						<TooltipsAppearance BackgroundColor="LightGray"></TooltipsAppearance>
						<SeriesItems>
							<telerik:CandlestickSeriesItem Open="26.29" High="26.93" Low="25.49" Close="26.00" />
							<telerik:CandlestickSeriesItem Open="26.30" High="27.09" Low="25.20" Close="25.99" />
							<telerik:CandlestickSeriesItem Open="26.25" High="27.189" Low="24.60" Close="26.87" />
							<telerik:CandlestickSeriesItem Open="26.68" High="26.82" Low="26.06" Close="26.29" />
							<telerik:CandlestickSeriesItem Open="26.22" High="28.15" Low="25.676" Close="27.91" />
							<telerik:CandlestickSeriesItem Open="27.25" High="29.44" Low="27.01" Close="27.99" />
							<telerik:CandlestickSeriesItem Open="28.15" High="28.15" Low="25.49" Close="26.76" />
							<telerik:CandlestickSeriesItem Open="26.52" High="27.06" Low="24.865" Close="24.95" />
							<telerik:CandlestickSeriesItem Open="24.84" High="26.49" Low="24.83" Close="26.20" />
							<telerik:CandlestickSeriesItem Open="25.51" High="25.845" Low="21.83" Close="22.32" />
							<telerik:CandlestickSeriesItem Open="23.18" High="24.10" Low="22.40" Close="23.25" />
							<telerik:CandlestickSeriesItem Open="24.50" High="25.90" Low="24.00" Close="24.538" />
							<telerik:CandlestickSeriesItem Open="24.47" High="26.14" Low="24.10" Close="26.14" />
						</SeriesItems>
					</telerik:CandlestickSeries>
				</Series>
			</PlotArea>
		</telerik:RadHtmlChart>
````


