---
title: OnClientTemplateDataBound
page_title: OnClientTemplateDataBound | UI for ASP.NET AJAX Documentation
description: OnClientTemplateDataBound
slug: combobox/client-side-programming/events/onclienttemplatedatabound
tags: onclienttemplatedatabound
published: True
position: 16
---

# OnClientTemplateDataBound



## OnClientTemplateDataBound

The __OnClientTemplateDataBound__ client-side event of the RadComboBox is fired after the client template is bound and the binding expression are evaluated.

The event handler receives two parameters:

1. The instance of the combobox firing the event.

1. An eventArgs parameter containing the following methods:

* __get_dataItem()__ returns the dataItem object that the current item is being bound to.

* __get_html()__ gets the rendered template HTML.

* __set_html()__ sets the rendered template HTML.

* __get_template()__ – returns the template function that’s used to bind the dataItem to the template text.

# See Also

 * [Client Templates Overview]({%slug combobox/templates/client-templates%})

 * [Online Demo](http://demos.telerik.com/aspnet-ajax-beta/combobox/examples/functionality/clienttemplates/defaultcs.aspx)
