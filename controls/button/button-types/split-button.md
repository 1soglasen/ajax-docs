---
title: Split Button
page_title: Split Button | UI for ASP.NET AJAX Documentation
description: Split Button
slug: button/button-types/split-button
tags: split,button
published: True
position: 1
---

# Split Button



__RadButton__ enables the developer to show an additional button next to the main button (__Figure 1__), whosepurpose is to enhance the usability of the primary button. You can enable the split button functionality by settingthe __EnableSplitButton__ property to __true__.
>caption Figure 1: RadButton configured as a split button. The code that creates this figure is available in Example 1.

![button-splitbutton](images/button-splitbutton.png)

The extra button is rendered on the right (default) or the left,depending on the value set to the __SplitButtonPosition__ property. The developer can also apply customstyling to the control using the __SplitButtonCssClass__ property.

>caution It is not possible to have both __PrimaryIcon__ and split button with __SplitButtonPosition__ =" __Left__ ", enabled. The same is true for the __SecondaryIcon__ and __SplitButtonPosition__ =" __Right__ ".
>


## How to use the Split button functionality on the Client-side

You can handle the client-side [OnClientClicked]({%slug button/client-side-programming/events/onclientclicking%}) or[OnClientClicking]({%slug button/client-side-programming/events/onclientclicking%}) event, and then execute a desired action, depending on the clicked button by the user. See a sample in __Example 1__.

__Example 1__: Utilizing the split button functionality on the client-side.

````ASPNET
	<telerik:RadButton ID="SplitButton1" Text="SplitButton" runat="server" EnableSplitButton="true"
	OnClick="SplitButton1_Click" OnCommand="SplitButton1_Command">
	</telerik:RadButton> 
````



````JavaScript
	    	function OnClientClicked(sender, args) {
	    		if (args.IsSplitButtonClick()) {
	    			//TODO: Execute SplitButton logic
	    			alert("Split button clicked!");
	    		}
	    		else {
	    			//TODO: Execute main button logic
	    			alert("Main button clicked!");
	    		}
	    	}
````



## How to use the Split button functionality on the Server-side

The server-side Click and Command events can be handled to execute "split button" specific logic.The event arguments parameter should be cast to the respective ButtonClick or ButtonCommand event args, so thatwe can determine which button issued the click. You can find a simple project in __Example 2__.

__Example 2__: Utilizing the split button functionality on the server-side.

````ASPNET
	<telerik:RadButton EnableSplitButton="true" ID="SplitButton" AutoPostBack="false" runat="server" Text="Transfer Item" OnClientClicked="OnClientClicked"></telerik:RadButton> 
````



>tabbedCode

````C#
	C# 	Copy Code
	protected void SplitButton1_Command(object sender, CommandEventArgs e)
	{
	Telerik.Web.UI.ButtonCommandEventArgs args = e as Telerik.Web.UI.ButtonCommandEventArgs;
	if (args.IsSplitButtonClick)
	{
	 //TODO: Split button logic
	}
	}
	protected void SplitButton1_Click(object sender, EventArgs e)
	{
	Telerik.Web.UI.ButtonClickEventArgs args = e as Telerik.Web.UI.ButtonClickEventArgs;
	if (args.IsSplitButtonClick)
	{
	 //TODO: Split button logic
	}
	} 
````



````VB.NET
		Protected Sub SplitButton1_Command(ByVal sender As Object, ByVal e As CommandEventArgs)
			Dim args As Telerik.Web.UI.ButtonCommandEventArgs = TryCast(e, Telerik.Web.UI.ButtonCommandEventArgs)
			If args.IsSplitButtonClick Then
				'TODO: Split button logic
			End If
		End Sub
		Protected Sub SplitButton1_Click(ByVal sender As Object, ByVal e As EventArgs)
			Dim args As Telerik.Web.UI.ButtonClickEventArgs = TryCast(e, Telerik.Web.UI.ButtonClickEventArgs)
			If args.IsSplitButtonClick Then
				'TODO: Split button logic
			End If
		End Sub
````


>end

# See Also

 * [Overview]({%slug button/button-types/overview%})

 * [Overview]({%slug button/button-types/icons/overview%})

 * [Image Button]({%slug button/button-types/image-button%})

 * [Toggle button]({%slug button/button-types/toggle-button%})
