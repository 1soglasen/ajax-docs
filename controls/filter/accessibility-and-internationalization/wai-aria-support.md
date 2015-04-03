---
title: WAI-ARIA Support
page_title: WAI-ARIA Support | UI for ASP.NET AJAX Documentation
description: WAI-ARIA Support
slug: filter/accessibility-and-internationalization/wai-aria-support
tags: wai-aria,support
published: True
position: 1
---

# WAI-ARIA Support





## 

The __RadFilter__ control offers __WAI-ARIA__ support which can be easily enabled by setting the __EnableAriaSupport__ server property to __true__.

RadFilter ARIA attributes are __lower case__. They are shown in the table below.


>caption  

|  __Control__  |  __Attributes__  |
| ------ | ------ |
| __RadFilter__ |Aria-atomic:trueRole: presentationAria-label – control client-side idRole: group - on hierarchilcal filter expressions that have child filter expressionsRole: listitem – on filter expressions without childrenAria-level: number specifying the hierarchy level of the filter expressionRole: presentation – on inner div elementsRole:button for the buttons in the filter expressionRole:checkbox – for checkbox in Boolean filter expressionsRole:textbox: for input type textAria-disabled:false for input type text|

>note RadContextMenu is not aria compliant yet.
>


>note An issue with the use of WAI-ARIA in HTML documents is that they don’t validate. When you run a HTML document containing ARIA attributes through the W3C Validator it shows errors in the results for any ARIA attributes. The DOCTYPE declarations do not include any information about the WAI ARIA attributes and you cannot have a valid document which includes elements, attributes, and attribute values, not detailed in its DTD’s.
>


# See Also

 * [WAI-ARIA basic information](http://www.w3.org/WAI/intro/aria)
