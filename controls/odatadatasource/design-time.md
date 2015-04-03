---
title: Design Time
page_title: Design Time | UI for ASP.NET AJAX Documentation
description: Design Time
slug: odatadatasource/design-time
tags: design,time
published: True
position: 2
---

# Design Time



## 

The designer is the most important part of the control. One can easily configure the data and later bind it to the desired control. There are 2 steps in the wizard that will help you to easily configure the RadODataDataSource:

1. In the first step of the wizard you will need to enter the location of service in the __Enter service url__field. Then you will have the option to select the data fields/properties which will be used in the data model. * Next* button will be enabled only after at least one property is selected.![odatadatasource-wizard](images/odatadatasource-wizard.png)

1. In the final screen you have a list of options to enable or disable sorting, filtering and paging:![odatadatasource-wizard-step 2](images/odatadatasource-wizard-step2.png)

* __Sorting__ - You can easily configure your sorting by using the checkbox. The *Add Sorts *button opens a SortForm that enables you to furthet configure your sort expressions.

* __Filtering__ - Filtering is the same as Sorting, but with different choosers in the * FilterForm *.

* __Paging__ – Using the checkbox you can enable/disable paging. You can also set PageSize and CurrentPageIndex using textboxes.![Filtering](images/odatadatasource-filtering.png)
