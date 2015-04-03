---
title: How To Configure Animations
page_title: How To Configure Animations | UI for ASP.NET AJAX Documentation
description: How To Configure Animations
slug: rotator/getting-started/how-to-configure-animations
tags: how,to,configure,animations
published: True
position: 1
---

# How To Configure Animations



This article explains how the animation options of the __CoverFlow, CoverFlowButtons, Carousel and CarouselButton__[types](http://demos.telerik.com/aspnet-ajax/rotator/examples/rotatortypes/defaultcs.aspx) of the __RadRotator__ can be configured to provide different effects than the default.

## 

The animation options are a JavaScript object that can be fed to the rotator's code through the __set_scrollAnimationOptions(string, object)__client-side method of the __Telerik.Web.UI.RadRotatorAnimation__ object. How this is done is shown in the[CoverFlow Mode Online Demo](http://demos.telerik.com/aspnet-ajax/rotator/examples/coverflowmode/defaultcs.aspx).

Essentially, the required properties must be set to an object and provided as the second argument to the method after the RadRotator declaration,while the first argument is a string containing the ClientID of the rotator that will be affected:

````JavaScript
		<telerik:RadRotator ID="RadRotator1" runat="server" Width="200" ItemWidth="100" Height="100"
			ItemHeight="100" DataSourceID="XmlDataSource1" FrameDuration="1000">
			<ItemTemplate>
				<asp:Image CssClass="itemTemplate" ID="Image2" runat="server" ImageUrl='<%# XPath("ImageURL") %>'
					AlternateText="IMAGE" />
			</ItemTemplate>
		</telerik:RadRotator>
		<script type="text/javascript">
			var animationOptions = {
				minScale: 0.8, // The size scale [0; 1], applied to the items that are not selected.
				yO: 60, // The offset in pixels of the center of the selected item from the top edge of the rotator.
				xR: -30, // The offset in pixels between the selected items and the first item on the left and on the right of the selected item.
				xItemSpacing: 50, // The offset in pixels between the items in the rotator.
				matrix: { m11: 1, m12: 0, m21: -0.1, m22: 1 }, // The 2d transformation matrix, applied to the items that appear on the right of the selected item.
				reflectionHeight: 0.5, // The height of the reflection
				reflectionOpacity: 1 // The opacity, applied to the reflection
			}
	
			// The set_scrollAnimationOptions method takes two arguments - the first one is the ClientID of the rotator, which we want to configure and the second one is
			// a hash table with the options we want to apply.
			Telerik.Web.UI.RadRotatorAnimation.set_scrollAnimationOptions("<%= RadRotator1.ClientID %>", animationOptions);
		</script>
````



Here follows a list with the available options and their effect:

* __minScale__ - the size scale [0; 1], applied to the items that are not selected relative to the item's size from the rotator's properties

* __xO__ - the offset in pixels of the center of the selected item from the left edge of the rotator

* __yO__ - the offset in pixels of the center of the selected item from the top edge of the rotator

* __xR__ - the offset in pixels between the selected item and the first item on its left / right

* __yR__ - the offset in pixels between the selected item and the first item on its top / bottom

* __selectedItemOffsetX__ - the selected item's offset in pixels from the first item on its left

* __selectedItemOffsetY__ - the selected item's offset in pixels from the first item to its top

* __xItemSpacing__ - the horizontal offset in pixels between the items in the rotator

* __yItemSpacing__ - the vertical offset in pixels between the items in the rotator

* __matrix__ - the 2d transformation matrix applied to the items that appear on the right of the selected item

* __reflectionHeight__ - the height of the reflection

* __reflectionOpacity__ - the opacity, applied to the reflection

# See Also

 * [CoverFlow Mode Online Demo](http://demos.telerik.com/aspnet-ajax/rotator/examples/coverflowmode/defaultcs.aspx)

 * [RadRotator Types Online Demo](http://demos.telerik.com/aspnet-ajax/rotator/examples/rotatortypes/defaultcs.aspx)
