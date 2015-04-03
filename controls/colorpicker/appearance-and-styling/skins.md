---
title: Skins
page_title: Skins | UI for ASP.NET AJAX Documentation
description: Skins
slug: colorpicker/appearance-and-styling/skins
tags: skins
published: True
position: 0
---

# Skins



To make customizing the appearance of __RadColorPicker__as easy as possible, this control uses __skins.__ A skin is a set of images and a CSS stylesheet that are applied to the HTML elements which make up the control, defining the look and feel.

To apply a skin, set the __Skin__ property of the __RadColorPicker__control. You can set the __Skin__ property using the properties pane or the control's [Smart Tag]({%slug colorpicker/design-time%}).

__RadColorPicker__is installed with a number of predefined skins:
>caption 

![radcolorpicker-skins](images/radcolorpicker-skins.png)

>note The __Hay__ , __Forest__ , __Sitefinity__ and __Transparent__ skins are obsolete and have been removed from the Telerik.Web.UI.Skins.dll assembly as of __Q1 2014__ .You can find more information on the matter in[this blog post](http://blogs.telerik.com/aspnet-ajax/posts/13-04-11/6-telerik-asp.net-ajax-skins-going-obsolete).
>


## Customizing Skins

You can tweak the existing skins, or create your own. Each skin has two main elements: images and a stylesheet. When creating your own, it is a good idea to start with the stylesheet for an existing skin and alter that. See the [Tutorial: Creating a Custom Skin]({%slug colorpicker/appearance-and-styling/creating-a-custom-skin%}) topic for a step-by-step walk through. To use your own skin

1. Add the new CSS file to your project.

1. Drag and drop the CSS file from the Project Explorer onto your Web page.

1. Set the __EnableEmbeddedSkins__ property of the controls that use the skin to __False__.

The stylesheet for a __RadColorPicker__skin has the name __ColorPicker.[SkinName].css__ and can be found in the __...Skins/[SkinName]__ directory. The images are found in the __...Skins/[SkinName]/ColorPicker__directory. For example, the stylesheet for the "Black" skin is called ColorPicker.Black.css and is located in the ...Skins/Black directory.The images are found in the ...Skins/Black/ColorPicker directory. The images are referenced by name from within the stylesheet.

For information on the CSS File structure, see the [Understanding the Skin CSS File]({%slug colorpicker/appearance-and-styling/understanding-the-skin-css-file%}) topic.

# See Also

 * [Controlling Appearance]({%slug colorpicker/appearance-and-styling/controlling-appearance%})

 * [Creating a Custom Skin]({%slug colorpicker/appearance-and-styling/creating-a-custom-skin%})

 * [Understanding the Skin CSS File]({%slug colorpicker/appearance-and-styling/understanding-the-skin-css-file%})
