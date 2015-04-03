---
title: Service Configuration
page_title: Service Configuration | UI for ASP.NET AJAX Documentation
description: Service Configuration
slug: clientdatasource/service-configuration
tags: service,configuration
published: True
position: 3
---

# Service Configuration



The __ClientDataSource__ control's [schema](http://docs.telerik.com/kendo-ui/api/framework/datasource#configuration-schema) serves to provide metadata for the underlying types of objects returned from the service. You can specify property names, their types and other configuration settings:

## Schema


|  __ *Property* __  |  __ *Description* __  |
| ------ | ------ |
| __ResponseType__ |Gets or sets the data type of the server response. Only JSON and XML are supported. Only XML and JSON(default) are supported. Serialized on the client-side to[this](http://docs.telerik.com/kendo-ui/api/framework/datasource#configuration-schema.type)kendo setting.|
| __DataName__ |Gets or sets the name of the collection that holds the data items. Serialized on the client-side to[this](http://docs.telerik.com/kendo-ui/api/framework/datasource#configuration-schema.data)Kendo setting.|
| __AggregateResultsName__ |Gets or sets the name of the field from the response which contains the aggregate results. Serialized on the client-side to[this](http://docs.telerik.com/kendo-ui/api/framework/datasource#configuration-schema.aggregates)Kendo setting.|
| __GroupsName__ |Gets or sets the name of the field from the server response which contains the groups. Serialized on the client-side to[this](http://docs.telerik.com/kendo-ui/api/framework/datasource#configuration-schema.groups)kendo setting.|
| __ErrorsName__ |Gets or sets the name of the field from the server response which contains server-side errors. Serialized on the client-side to[this](http://docs.telerik.com/kendo-ui/api/framework/datasource#configuration-schema.errors)kendo setting.|
|TotalName|Gets or sets the name of the field from the server response which contains the total number of data items. Serialized on the client-side to[this](http://docs.telerik.com/kendo-ui/api/framework/datasource#configuration-schema.total)kendo setting|

## Model

The __ClientDataSource____Model__ actually demonstrates model of the schema which holds the structure of the entity and various other settings.(See __Example 1__)

These are the properties that you can use for configuring the __Model__:

* __ID__ - Gets or sets the field serving as ID of the model. Necessary for CRUD operations!

* __Fields__ - Represents a collection of __ClientDataSourceModelFields__ configuring the settings for each field:

* __FieldName__ - Gets or sets the name of the field from the model.

* __OriginalFieldName__ - Gets or sets the name of the orginal field from the data.

* __ParseFunctionName__ - Gets or sets the name of function which will parse the field value. If not set default parsers will be used.

* __Editable__ – Gets or sets field from the Model is editable. Default is true.

* __Nullable__ – Gets or sets field from the Model is nullable. Default is true.

* __DefaultValue__ – Gets or sets the default value of the field from the model.

* __DataType__ – Gets or sets the corresponding client-side type of the field from the model. Currently enumeration:

* Data

* String

* Number

* Boolean

````C#
	  <telerik:RadClientDataSource ID="RadClientDataSource1" runat="server">
	            <DataSource>
	                <WebServiceDataSourceSettings ServiceType="OData">
	                    <Select Url="http://demos.telerik.com/kendo-ui/service/Northwind.svc/Products" DataType="JSONP" />
	                </WebServiceDataSourceSettings>
	            </DataSource>
	            <Schema GroupsName="ProductName" ResponseType="JSONP">
	                <Model ID="Model1">
	                    <telerik:ClientDataSourceModelField FieldName="ProductName" DataType="String" Editable="true" IgnoreCase="true" />
	                    <telerik:ClientDataSourceModelField FieldName="QuantityPerUnit" DataType="String" Nullable="false" />
	                    <telerik:ClientDataSourceModelField FieldName="UnitPrice" DataType="Number" DataType="Number"  />
	                    <telerik:ClientDataSourceModelField FieldName="UnitsInStock" DataType="Number" />
	                    <telerik:ClientDataSourceModelField FieldName="Discontinued" DataType="Boolean" />
	                </Model>
	            </Schema>
	            <GroupExpressions>
	                <telerik:ClientDataSourceGroupExpression FieldName="ProductName">
	                </telerik:ClientDataSourceGroupExpression>
	            </GroupExpressions>
	        </telerik:RadClientDataSource>
	
````


