---
title: Overview
page_title: Data Binding Overview | RadTagCloud for ASP.NET AJAX Documentation
description: Overview
slug: tagcloud/data-binding/overview
tags: overview
published: True
position: 0
---

# Data Binding Overview



## 

__RadTagCloud__ supports binding to all ASP.NET 2.0/3.5 DataSource components, including:

* AccessDataSource

* SqlDataSource

* XmlDataSource

* ObjectDataSource

* SiteMapDataSource

* LinqDataSource

* EntityDataSource



To bind to a DataSource component, you need to set the following properties:

* __DataSourceID__ property of the tagCloud to the ID of the DataSource component

* __DataTextField__ property to the field of the DataSource component that provides the text content.

* __DataNavigteUrlField__ property to the field of the DataSource component that provides the URL (NavigateUrl) content.

* __DataWeightField__ property to the field of the DataSource component that provides the weight content.



Here is an example that shows how to bind the tagCloud to an ObjectDataSource. In asimilar way the control can be bound to any of the above mentioned DataSource components.

````ASPNET
	    <div>
	        <telerik:RadTagCloud ID="RadTagCloud2" runat="server" Width="400px" MaxFontSize="50px"
	            Sorting="AlphabeticAsc" DataSourceID="ObjectDataSource1" DataTextField="Text"
	            DataWeightField="Weight" DataNavigateUrlField="NavigateUrl">
	        </telerik:RadTagCloud>
	        <asp:ObjectDataSource ID="ObjectDataSource1" runat="server" SelectMethod="GetSiteData"
	            TypeName="TagCloudDataItem"></asp:ObjectDataSource>
	    </div>
````





````C#
	
	
		/// <summary>
		/// This class is only for demonstration purposes. The class used in this example resides in the App_Code folder
		/// </summary>
		public class TagCloudDataItem
		{
			private string _text;
			private string _navigateUrl;
			private double _weight;
			public string Text
			{
				get { return _text; }
				set { _text = value; }
			}
	
			public string NavigateUrl
			{
				get { return _navigateUrl; }
				set { _navigateUrl = value; }
			}
			public double Weight
			{
				get { return _weight; }
				set { _weight = value; }
			}
			public TagCloudDataItem(string text, string navigateUrl, double weight)
			{
				_text = text;
				_navigateUrl = navigateUrl;
				_weight = weight;
			}
			public static List<TagCloudDataItem> GetSiteData()
			{
				List<TagCloudDataItem> siteData = new List<TagCloudDataItem>();
				siteData.Add(new TagCloudDataItem("Russia", "http://en.wikipedia.org/wiki/Russia", 141.9));
				siteData.Add(new TagCloudDataItem("Nigeria", "http://en.wikipedia.org/wiki/Nigeria", 154.7));
				siteData.Add(new TagCloudDataItem("Saudi Arabia", "http://en.wikipedia.org/wiki/Saudi_Arabia", 28.6));
				siteData.Add(new TagCloudDataItem("Canada", "http://en.wikipedia.org/wiki/Canada", 34.1));
				siteData.Add(new TagCloudDataItem("USA", "http://en.wikipedia.org/wiki/USA", 309.4));
				siteData.Add(new TagCloudDataItem("Sweden", "http://en.wikipedia.org/wiki/Sweden", 9.3));
				siteData.Add(new TagCloudDataItem("Germany", "http://en.wikipedia.org/wiki/Germany", 81.7));
				siteData.Add(new TagCloudDataItem("Turkey", "http://en.wikipedia.org/wiki/Turkey", 72.5));
				siteData.Add(new TagCloudDataItem("Japan", "http://en.wikipedia.org/wiki/Japan", 127.3));
				siteData.Add(new TagCloudDataItem("France", "http://en.wikipedia.org/wiki/France", 65.4));
				return siteData;
			}
		}
````
````VB.NET
	
	    ''' <summary>
	    ''' This class is only for demonstration purposes. The class used in this example resides in the App_Code folder
	    ''' </summary>
	    Public Class TagCloudDataItem
	        Private _text As String
	        Private _navigateUrl As String
	        Private _weight As Double
	        Public Property Text() As String
	            Get
	                Return _text
	            End Get
	            Set(ByVal value As String)
	                _text = value
	            End Set
	        End Property
	
	        Public Property NavigateUrl() As String
	            Get
	                Return _navigateUrl
	            End Get
	            Set(ByVal value As String)
	                _navigateUrl = value
	            End Set
	        End Property
	        Public Property Weight() As Double
	            Get
	                Return _weight
	            End Get
	            Set(ByVal value As Double)
	                _weight = value
	            End Set
	        End Property
	        Public Sub New(ByVal text As String, ByVal navigateUrl As String, ByVal weight As Double)
	            _text = text
	            _navigateUrl = navigateUrl
	            _weight = weight
	        End Sub
	        Public Shared Function GetSiteData() As List(Of TagCloudDataItem)
	            Dim siteData As New List(Of TagCloudDataItem)()
	            siteData.Add(New TagCloudDataItem("Russia", "http://en.wikipedia.org/wiki/Russia", 141.9))
	            siteData.Add(New TagCloudDataItem("Nigeria", "http://en.wikipedia.org/wiki/Nigeria", 154.7))
	            siteData.Add(New TagCloudDataItem("Saudi Arabia", "http://en.wikipedia.org/wiki/Saudi_Arabia", 28.6))
	            siteData.Add(New TagCloudDataItem("Canada", "http://en.wikipedia.org/wiki/Canada", 34.1))
	            siteData.Add(New TagCloudDataItem("USA", "http://en.wikipedia.org/wiki/USA", 309.4))
	            siteData.Add(New TagCloudDataItem("Sweden", "http://en.wikipedia.org/wiki/Sweden", 9.3))
	            siteData.Add(New TagCloudDataItem("Germany", "http://en.wikipedia.org/wiki/Germany", 81.7))
	            siteData.Add(New TagCloudDataItem("Turkey", "http://en.wikipedia.org/wiki/Turkey", 72.5))
	            siteData.Add(New TagCloudDataItem("Japan", "http://en.wikipedia.org/wiki/Japan", 127.3))
	            siteData.Add(New TagCloudDataItem("France", "http://en.wikipedia.org/wiki/France", 65.4))
	            Return siteData
	        End Function
	    End Class
````

