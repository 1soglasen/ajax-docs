---
title: Right-to-left Support
page_title: Right-to-left Support | UI for ASP.NET AJAX Documentation
description: Right-to-left Support
slug: captcha/accessibility-and-internationalization/right-to-left-support
tags: right-to-left,support
published: True
position: 1
---

# Right-to-left Support



## 

The __RadCaptcha__ fully supports right-to-left (RTL) language locales. In order to turn on the RTL support you should set __dir=rtl to the html or body__ element or at least to its parent element. You can also use the __direction:rtl__ CSS property.

````ASPNET
	    <div dir="rtl">
	        <telerik:RadCaptcha ID="RadCaptcha1" runat="server" ErrorMessage="Page not valid. The code you entered is not valid"
	            ValidationGroup="Group">
	        </telerik:RadCaptcha>
	        <asp:Button ID="btnVerify" runat="server" Text="Submit Page" Width="150px" ValidationGroup="Group" />
	    </div>
````

![radcaptcha-rtl-screenshot](images/radcaptcha-rtl-screenshot.png)

# See Also

 * [See this live in an online demo](http://demos.telerik.com/aspnet-ajax/colorpicker/examples/righttoleft/defaultcs.aspx)
