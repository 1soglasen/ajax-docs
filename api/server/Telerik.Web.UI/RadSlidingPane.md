---
title: Telerik.Web.UI.RadSlidingPane
page_title: Telerik.Web.UI.RadSlidingPane
description: Telerik.Web.UI.RadSlidingPane
---

# Telerik.Web.UI.RadSlidingPane

RadSlidingPane class

## Inheritance Hierarchy

* System.Object
* System.Web.UI.Control
* System.Web.UI.WebControls.WebControl
* Telerik.Web.UI.RadWebControl
* Telerik.Web.UI.SplitterItem
* Telerik.Web.UI.SplitterPaneBase
* Telerik.Web.UI.RadSlidingPane

## Properties

###  MinHeight `Int32`

Sets/gets the min height to which the pane can be resized

###  Height `Unit`

Sets/gets the height of the sliding pane

###  MinWidth `Int32`

Sets/gets the min width to which the pane can be resized

###  Width `Unit`

Sets/gets the width of the sliding pane

###  EnableResize `Boolean`

Sets/gets whether the resize bar will be active

###  DockOnOpen `Boolean`

Sets/gets whether the sliding pane will automatically dock on open

#### Remarks
When set to true the animation is disabled, so the duration set via the 
            property of the RadSlidingZone is ignored. False by default.

###  IconUrl `String`

Gets or sets the path to an image to display for the item.

###  TabView `SplitterSlidePaneTabView`

Sets/gets way the tab of the pane is rendered

###  EnableDock `Boolean`

Sets/gets whether the pane can be docked

###  Title `String`

The title that will be displayed when the pane is docked/docked

###  ResizeText `String`

Gets or sets the text for resize bar

###  UndockText `String`

Gets or sets the text for undock image

###  DockText `String`

Gets or sets the text for dock image

###  CollapseText `String`

Gets or sets the text for collapse image

###  Overlay `Boolean`

Gets or sets a value indicating whether the sliding pane will create an overlay element.

###  OnClientDocked `String`

Gets or sets a value indicating the client-side event handler that is called when
            the RadSlidingPane is docked.

#### Remarks
Two parameters are passed to the handler:sender, the RadSlidingPane client object that fired the eventargsThis event cannot be cancelled.

###  OnClientUndocked `String`

Gets or sets a value indicating the client-side event handler that is called when
            the RadSlidingPane is undocked.

#### Remarks
Two parameters are passed to the handler:sender, the RadSlidingPane client object that fired the eventargsThis event cannot be cancelled.

###  OnClientDocking `String`

Gets or sets a value indicating the client-side event handler that is called before
            the RadSlidingPane is docked.

#### Remarks
Two parameters are passed to the handler:sender, the RadSlidingPane client object that fired the eventargsThis event can be cancelled.

###  OnClientUndocking `String`

Gets or sets a value indicating the client-side event handler that is called before
            the RadSlidingPane is undocked.

#### Remarks
Two parameters are passed to the handler:sender, the RadSlidingPane client object that fired the eventargsThis event can be cancelled.

###  SlidingZone `RadSlidingZone`

Reference to the parent SlidingZone object

###  MinWidth `Int32`

Sets/gets the min width to which the pane can be resized

###  MaxWidth `Int32`

Sets/gets the max width to which the pane can be resized

###  MinHeight `Int32`

Sets/gets the min height to which the pane can be resized

###  MaxHeight `Int32`

Sets/gets the max height to which the pane can be resized

###  Scrolling `SplitterPaneScrolling`

Sets/gets whether the content of the pane will get a scrollbars when it exceeds the pane area size

###  OnClientCollapsed `String`

Gets or sets a value indicating the client-side event handler that is called when
            the RadPane is collapsed.

#### Remarks
Two parameters are passed to the handler:sender, the pane object that raised the eventargsThis event cannot be cancelled.

###  OnClientCollapsing `String`

Gets or sets a value indicating the client-side event handler that is called before
            the RadPane is collapsed.

#### Remarks
Two parameters are passed to the handler:sender, the pane object that raised the eventargsThis event can be cancelled.

###  OnClientExpanded `String`

Gets or sets a value indicating the client-side event handler that is called when
            the RadPane is expanded.

#### Remarks
Two parameters are passed to the handler:sender, the pane object that raised the eventargsThis event cannot be cancelled.

###  OnClientExpanding `String`

Gets or sets a value indicating the client-side event handler that is called before
            the RadPane is expanded.

#### Remarks
Two parameters are passed to the handler:sender, the pane object that raised the eventargsThis event can be cancelled.

###  OnClientResized `String`

Gets or sets a value indicating the client-side event handler that is called when the RadPane is resized.

#### Remarks
Two parameters are passed to the handler:sender, the pane object that raised the eventargs with the following methods:
             			get_oldWidth - the width of the pane before the resizeget_oldHeight - the height of the pane before the resizeThis event cannot be cancelled.

###  OnClientResizing `String`

Gets or sets a value indicating the client-side event handler that is called before
            the RadPane is resized.

#### Remarks
Two parameters are passed to the handler:sender, the event objectargs with the following methods:
             			get_delta - the delta with which the pane will be resizedget_resizeDirection - the direction in which the pane will be resized. You can use the Telerik.Web.UI.SplitterDirection hash to check the direction. The 2 possible values are : Forward and BackwardThis event can be cancelled.

###  PersistScrollPosition `Boolean`

Sets/gets whether the scrolls position will be persisted acrosss postbacks

###  Index `Int32`

This property is being used internally by the RadSplitter control.
            Setting it may lead to unpredictable results.

#### Remarks
The Index property is used internally.

###  RegisterWithScriptManager `Boolean`

Gets or sets the value, indicating whether to register with the ScriptManager control on the page.

#### Remarks
If RegisterWithScriptManager is set to false the control can be rendered on the page using Web Services or normal callback requests/page methods.

###  Skin `String`

Gets or sets the skin name for the control user interface.

#### Remarks
If this property is not set, the control will render using the skin named "Default".
            If EnableEmbeddedSkins is set to false, the control will not render skin.

###  IsSkinSet `String`

For internal use.

###  EnableEmbeddedScripts `Boolean`

Gets or sets the value, indicating whether to render script references to the embedded scripts or not.

#### Remarks
If EnableEmbeddedScripts is set to false you will have to register the needed Scripts files by hand.

###  EnableEmbeddedSkins `String`

Gets or sets the value, indicating whether to render links to the embedded skins or not.

#### Remarks
If EnableEmbeddedSkins is set to false you will have to register the needed CSS files by hand.

###  EnableEmbeddedBaseStylesheet `Boolean`

Gets or sets the value, indicating whether to render the link to the embedded base stylesheet of the control or not.

#### Remarks
If EnableEmbeddedBaseStylesheet is set to false you will have to register the needed control base CSS file by hand.

###  RuntimeSkin `String`

Gets the real skin name for the control user interface. If Skin is not set, returns
            "Default", otherwise returns Skin.

###  EnableAjaxSkinRendering `String`

Gets or sets the value, indicating whether to render the skin CSS files during Ajax requests

#### Remarks
If EnableAjaxSkinRendering is set to false you will have to register the needed control base CSS file by hand when adding/showing the control with Ajax.

###  ClientStateFieldID `String`

###  RenderMode `RenderMode`

Specifies the rendering mode of the control. Setting the mode to Lightweight will yield
            HTML 5/CSS 3 html and css.

#### Remarks
Lightweight rendering mode might change the outlook of the component in some older browsers
            that don't support CSS3/HTML5.

###  ResolvedRenderMode `RenderMode`

Returns resolved RenderMode should the original value was Auto

###  CssClassFormatString `String`

The CssClass property will now be used instead of the former Skin 
            and will be modified in AddAttributesToRender()

###  ClientIDMode `ClientIDMode`

This property is overridden in order to support controls which implement INamingContainer.
            The default value is changed to "AutoID".

###  ScriptManager `ScriptManager`

###  RadScriptManager `ScriptManager`

## Methods

###  RenderBeginTag

#### Returns

`System.Void` 

###  RenderContents

#### Returns

`System.Void` 

###  RenderEndTag

#### Returns

`System.Void` 

###  AddAttributesToRender

#### Returns

`System.Void` 

###  OnPreRender

#### Returns

`System.Void` 

###  ControlPreRender

Code moved into this method from OnPreRender to make sure it executed when the framework skips OnPreRender() for some reason

#### Returns

`System.Void` 

###  RegisterScriptControl

Registers the control with the ScriptManager

#### Returns

`System.Void` 

###  RegisterCssReferences

Registers the CSS references

#### Returns

`System.Void` 

###  LoadClientState

Loads the client state data

#### Parameters

#### clientState `System.Collections.Generic.Dictionary{System.String,System.Object}`

#### Returns

`System.Void` 

###  SaveClientState

Saves the client state data

#### Returns

`System.String` 

###  RenderClientStateField

#### Returns

`System.Void` 

###  RenderBeginTag

#### Returns

`System.Void` 

###  RenderEndTag

#### Returns

`System.Void` 

###  Render

#### Returns

`System.Void` 

###  RenderScriptsNoScriptManager

#### Returns

`System.Void` 

###  RenderDescriptorsNoScriptManager

#### Returns

`System.Void` 

###  RenderContents

#### Returns

`System.Void` 

###  ApplyConditionalRendering

Use this from RenderContents of the inheritor

#### Returns

`System.Void` 

###  DescribeComponent

#### Returns

`System.Void` 

###  DescribeProperty

#### Returns

`System.Void` 

###  DescribeIDReferenceProperty

#### Returns

`System.Void` 

###  DescribeEvent

#### Returns

`System.Void` 

###  GetEmbeddedSkinNames

Returns the names of all embedded skins. Used by Telerik.Web.Examples.

#### Returns

`System.Collections.Generic.List`1` 

###  LoadPostData

Executed when post data is loaded from the request

#### Parameters

#### postDataKey `System.String`

#### postCollection `System.Collections.Specialized.NameValueCollection`

#### Returns

`System.Boolean` 

###  RaisePostDataChangedEvent

Executed when post data changes should invoke a changed event

#### Returns

`System.Void` 

