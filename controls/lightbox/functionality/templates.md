---
title: Templates
page_title: Templates | UI for ASP.NET AJAX Documentation
description: Templates
slug: lightbox/functionality/templates
tags: templates
published: True
position: 0
---

# Templates



__Templates__ are fully supported by RadLightBox control. __RadLightBox__ supports two base templatetypes - *ItemTemplate* and *DescriptionTemplate*. The first one is instantiated at the top part of the control, where the main content is placed. The latter resides on the bottom, where theTitle and Description are normally displayed.

Using these templates, you can display different type of content, for example:

* HTML markup

* iframes

* Server Controls

>caution The built-in __LoadingPanel__ will not work when templates are used. Nevertheless if you have AJAX-enabled __RadLightBox__ by using a __RadAjaxManager__ or __RadAjaxPanel__ and you have applied a __RadLoadingPanel__ , the loading animation will appear when navigating between the templates.
>


>note By using __PreserveCurrentItemTemplates__ property you can determines whether the template should be disposed afterclosing the LightBox or	after navigating to another item.
>


## Example

The following example shows how to use templates to create the following __RadLightBox__![lightbox-template-form](images/lightbox-template-form.png)

An <ItemTemplate> section is added to the RadLightBoxItems declaration. The controls needed for the form are placed accordingly into the item template.

````ASPNET
	    <telerik:radlightbox id="FeedbackLightBox" runat="server" width="400px" height="350px"
	        cssclass="lb_feedback" modal="true">
	        <ClientSettings>
	            <AnimationSettings HideAnimation="Resize" NextAnimation="Fade" PrevAnimation="Fade" ShowAnimation="Resize" />
	        </ClientSettings>
	        <Items>
	            <telerik:RadLightBoxItem>
	                <ItemTemplate>
	                    <asp:Label ID="FormTitle" runat="server" Text="SHARE YOUR FEEDBACK" CssClass="feedback_header"></asp:Label>
	                    <br />
	                    <asp:Label Text="FirstName:" ID="FirstNameLabel" runat="server" CssClass="feedback_label" />
	                    <telerik:RadTextBox runat="server" ID="FirstNameTextBox" Width="245px" />
	                    <br />
	                    <asp:Label Text="LastName:" ID="LastNameLabel" runat="server" CssClass="feedback_label" />
	                    <telerik:RadTextBox runat="server" ID="LastNameTextBox" Width="245px" />
	                    <br />
	                    <asp:Label Text="Email:" ID="EmailLabel" runat="server" CssClass="feedback_label" />
	                    <telerik:RadTextBox runat="server" ID="EmailTextBox" Width="245px" />
	                    <br />
	                    <asp:Label Text="Comments:" ID="CommentsLabel" runat="server" CssClass="feedback_label" />
	                    <telerik:RadTextBox runat="server" Resize="None" TextMode="MultiLine" Width="245px" Height="100px"></telerik:RadTextBox>
	                    <br />
	                    <telerik:RadButton ID="RadButton1" Text="Submit Feedback" runat="server" Skin="Silk" CssClass="submit_feedback_btn rbPrimaryButton"></telerik:RadButton>
	                </ItemTemplate>
	            </telerik:RadLightBoxItem>
	        </Items>
	    </telerik:radlightbox>
````


