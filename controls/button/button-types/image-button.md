---
title: Image Button
page_title: Image Button | RadButton for ASP.NET AJAX Documentation
description: Image Button
slug: button/button-types/image-button
tags: image,button
published: True
position: 2
---

# Image Button



## 

**RadButton**provides an easy way to show a custom image on the control.The image can be used as a background, or can represent the button itself (Image Button).When using the **RadButton**control as an Image Button, the user mustset **Width** and **Height**, because we don't use an actual <img/> tag, but the image is setas background to the Button's wrapper element (<span>). All the Image-related properties are controlled through the **RadButton.Image**property.
>caption Figure 1: RadButton used as ImageButton (the image represents the button).

![ImageButton](images/button-imagebuttons01.png)
>caption Figure 2: RadButton with background image, icons and text.

![ImageButton2](images/button-imagebuttons02.png)



There are two ways to display an image on the control:

1. The first and the easiest way is to set the **Image.ImageUrl** propertyto the location of the image used. Setting the **IsBackgroundImage** totrue enables the developer to use the image as background, and set text and icons to his/her button.

1. The second way to set the image using **RadButton**'s **CssClass**property. Basically we set the background-image in the **CssClass**, and enable theimage button functionality by setting**Image.EnableImageButton=true** (**Example 1**).

This approach is preferred when you want to use an image sprite for the button (see sample below). You setthe background-image and background-position in the **CssClass**, and then in the**HoveredCssClass** and **PressedCssClass**, only thebackground-position of the hovered and pressed image. If the user wants she/he can display adifferent image when the mouse is hovering over the control, or the button is pressedusing the **HoveredImageUrl** and **PressedImageUrl** properties respectively.

**Example 1**: Configure a RadButton as an Image Button through the **CssClass** and **Image.EnableImageButton=true** properties.

````XML
		<style type="text/css">
			.classImage
			{
				background: url(img/categories.png);
				background-position: 0 0;
				width: 150px;
				height: 94px;
			}
			.classHoveredImage
			{
				background-position: 0 -100px;
			}
			.classPressedImage
			{
				background-position: 0 -200px;
			}
		</style>
````



````ASPNET
	<telerik:radbutton id="RadButton1" runat="server" text="Image Button" cssclass="classImage"
			hoveredcssclass="classHoveredImage" pressedcssclass="classPressedImage">
		<Image EnableImageButton="true" />
	</telerik:radbutton>
````







>note Note: It is always good to set the **Text** property, no matter if the control is used solely as image button (no text and icons shown), because this way the accessibility of the control is improved.
>




# See Also

 * [Button - Image Buttons](http://demos.telerik.com/aspnet-ajax/button/examples/imagebutton/defaultcs.aspx)

 * [Overview]({%slug button/button-types/overview%})

 * [Overview]({%slug button/button-types/icons/overview%})

 * [Split Button]({%slug button/button-types/split-button%})

 * [Toggle button]({%slug button/button-types/toggle-button%})
