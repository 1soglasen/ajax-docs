---
title: SpellCheckValidator
page_title: SpellCheckValidator | UI for ASP.NET AJAX Documentation
description: SpellCheckValidator
slug: spell/how-to/spellcheckvalidator
tags: spellcheckvalidator
published: True
position: 6
---

# SpellCheckValidator



## 

__SpellCheckValidator__validates a form based on a __RadSpell__ control. It can be used to enforce spell checking before form submission. The __ControlToValidate__must be set to the ID of a RadSpell control. The RadSpell control should be separately set up with a control to check and other options.

SpellCheckValidator descends from [CustomValidator](http://msdn2.microsoft.com/en-us/library/system.web.ui.webcontrols.customvalidator(VS.71).aspx) and ultimately [BaseValidator](http://msdn2.microsoft.com/en-us/library/system.web.ui.webcontrols.basevalidator(VS.71).aspx) and so shares behavior and properties with the other ASP.NET Standard validation controls.

The following below demonstrates spell checking a standard TextBox when the page is submitted.

>caution The example requires that you spell check the entry, even if none of the words are misspelled.
>

>caption 

![](images/spell-validator001.png)

````ASPNET
	<asp:TextBox ID="TextBox1" runat="server">thes iz mispellled</asp:TextBox>
	<telerik:SpellCheckValidator ID="SpellCheckValidator1" runat="server" ControlToValidate="RadSpell1"
	   ErrorMessage="Please spellcheck first!" Display="Dynamic"></telerik:SpellCheckValidator>
	<asp:Button ID="Button1" runat="server" Text="Submit Page" OnClick="Button1_Click" />
	<telerik:RadSpell ID="RadSpell1" runat="server" ButtonType="PushButton" ControlToCheck="TextBox1" />
	<br />
	<asp:ValidationSummary ID="ValidationSummary1" runat="server" /> 
````


