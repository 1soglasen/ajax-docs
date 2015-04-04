---
title: Placing RadDock In UpdatePanel
page_title: Placing RadDock In UpdatePanel | UI for ASP.NET AJAX Documentation
description: Placing RadDock In UpdatePanel
slug: dock/troubleshooting/placing-raddock-in-updatepanel
tags: placing,raddock,in,updatepanel
published: True
position: 0
---

# Placing RadDock In UpdatePanel



This article treats the most common issues related to placing __RadDock__ in an __UpdatePanel__, [RadAjaxPanel](6b8eb9b2-e5b9-44ee-93e0-7cc55cffe577) or adding it as updated control in [RadAjaxManager](546BFFA1-0A6D-4ACF-83E2-02D9592E7857).

>note The focus of the article is the combination of RadDock and UpdatePanel, because this is the base scenario. Nevertheless, the included information and code samples are valid for RadAjaxPanel and RadAjaxManager as well.
>


The article contains the following sections:

* [Floating RadDock Basics](#floating-raddock-basics)—this section explains how a floating dock is rendered on the page, which is related to the behavior of the dock in an update panel and as a result it is important for understanding the next sections.

* [Floating RadDock In UpdatePanel](#floating-raddock-in-updatepanel)—this section describes the problem that occurs when you place a floating dock in an update panel and the two ways to resolve it.

* [Docked RadDock In UpdatePanel](#docked-raddock-in-updatepanel)—this section describes the issues that may arise when you place a docked dock in an update panel and how to resolve them.

## Floating RadDock Basics

Before describing the problems you can encounter when placing a dock in an update panel, we need to explain the specific behavior of the dock that is vital to understanding why it cannot be combined with an update panel in some scenarios.

A dock control that is outside of a __RadDockZone__ is a floating dock. This can be either a dragged dock or a dock that is not wrapped in a dock zone. Floating docks are rendered as direct children of the form tag of the page. Even if you declare the dock in a container somewhere in the page, for example in the content of a div tag, the HTML representation of the dock will be moved in the form tag and as a result it will no longer be where you declared it originally.

## Floating RadDock In UpdatePanel

When you place a floating dock in an update panel (__Example 1__), the first AJAX request will result in the error message

__Two components with the same id 'RadDock1' can't be added to the application__

Subsequent requests will result in the __Invalid JSON primitive__ error.

This happens because the floating dock becomes a child of the form tag, but the update panel recreates the missing dock when the response is received. As a result there are two identical components with the same ID, which is not allowed.

__Example 1__: Placing a floating dock in an update panel results in JavaScript errors.

````ASPNET
	        <asp:UpdatePanel ID="UpdatePanel1" runat="server">
	            <ContentTemplate>
	                <telerik:RadDock runat="server" ID="RadDock1"></telerik:RadDock>
	                <asp:Button ID="Button1" Text="Trigger Postback" runat="server" />
	            </ContentTemplate>
	        </asp:UpdatePanel>
	
````



You can __avoid this problem__ by moving the update panel in the ContentTemplate of the dock (__Example 2__) if you want to __keep the dragging functionality__ of the dock and you AJAX-enabled it only to update its content asynchronously.

__Example 2__: Moving the update panel in the content of the dock.

````ASPNET
	        <telerik:RadDock runat="server" ID="RadDock1">
	            <ContentTemplate>
	                <asp:UpdatePanel ID="UpdatePanel1" runat="server">
	                    <ContentTemplate>
	                        <asp:Button ID="Button1" Text="Trigger Postback" runat="server" />
	                    </ContentTemplate>
	                </asp:UpdatePanel>
	            </ContentTemplate>
	        </telerik:RadDock>
	
	
````



If you do not need to drag the dock, you can also place it in a RadDockZone and set the __DockMode__ dock property to __Docked__ (__Example 3__). This way the dock will remain in the update panel and it will not be possible to drag it outside of the update panel.

__Example 3__: Moving the floating dock in a dock zone.

````ASPNET
	        <asp:UpdatePanel ID="UpdatePanel1" runat="server">
	            <ContentTemplate>
	                <telerik:RadDockZone runat="server" ID="RadDockZone1" Width="300px">
	                    <telerik:RadDock runat="server" DockMode="Docked" ID="RadDock1"></telerik:RadDock>
	                </telerik:RadDockZone>
	                <asp:Button ID="Button1" Text="Trigger Postback" runat="server" />
	            </ContentTemplate>
	        </asp:UpdatePanel>
	
	
````



## Docked RadDock In UpdatePanel

You can get the same JavaScript errors with a docked dock in the following scenario (__Example 4__):

1. Place the dock with the dock zone in an update panel.

1. Trigger an AJAX request by clicking the button.

1. Start dragging the dock while the request is still being processed. This is indicated by the *Processing...* text.

1. When the server returns a response, you will receive an error__Two components with the same id 'RadDock1' can't be added to the application__

1. Drop the dock in the dock zone and click the button again. This, as well as subsequent updates of the update panel, will result in __Invalid JSON primitive__ error.

What happens is that the dock becomes a child of the form while being dragged. When the processing of the AJAX request is finished, the update panel creates a duplicate dock, because the original dock is still being dragged, thus it is outside of the update panel. This leads to having two identical components with the same ID, which is not allowed.

__Example 4__: Placing a docked dock in an update panel may lead to JavaScript errors.

````ASPNET
	        <asp:UpdatePanel ID="UpdatePanel1" runat="server">
	            <ContentTemplate>
	                <telerik:RadDockZone runat="server" ID="RadDockZone1" Width="300px">
	                    <telerik:RadDock runat="server" ID="RadDock1" DockMode="Docked"></telerik:RadDock>
	                </telerik:RadDockZone>
	                <asp:Button ID="Button1" OnClick="Button1_Click" Text="Trigger Postback" runat="server" />
	            </ContentTemplate>
	        </asp:UpdatePanel>
	        <asp:UpdateProgress ID="UpdateProgress1" runat="server">
	            <ProgressTemplate>
	                Processing...
	            </ProgressTemplate>
	        </asp:UpdateProgress>
	
````



>tabbedCode

````C#
	
	
	    protected void Button1_Click(object sender, EventArgs e)
	    {
	        System.Threading.Thread.Sleep(3000);
	    }
	
	
````
````VB
	
	    Protected Sub Button1_Click(sender As Object, e As EventArgs)
	        System.Threading.Thread.Sleep(3000)
	    End Sub
	
````
>end

You can __avoid this error by preventing the dragging__ of the dock while an AJAX request is processed. The [RadAjaxLoadingPanel](17E31C56-1D2D-4C8D-9A43-1BEF6D86E7F2) control, used in combination with RadAjaxPanel, is quite useful for this purpose (__Example 5__).

__Example 5__: Preventing the dragging of the dock by showing a loading panel.

````ASPNET
	        <telerik:RadAjaxPanel runat="server" ID="RadAjaxPanel1" LoadingPanelID="RadAjaxLoadingPanel1">
	            <telerik:RadDockZone runat="server" ID="RadDockZone1" Width="300px">
	                <telerik:RadDock runat="server" ID="RadDock1" DockMode="Docked"></telerik:RadDock>
	            </telerik:RadDockZone>
	            <asp:Button ID="Button1" OnClick="Button1_Click" Text="Trigger Postback" runat="server" />
	        </telerik:RadAjaxPanel>
	        <telerik:RadAjaxLoadingPanel runat="server" ID="RadAjaxLoadingPanel1" Skin="Default">
	        </telerik:RadAjaxLoadingPanel> 
	
````



There is another solution if you AJAX-enabled the dock only to update its content asynchronously. You can move the update panel in the content of the dock (__Example 2__).

### Triggering AJAX Update With Timer

If the updating of the update panel is triggered by a __Timer__ (__Example 6__) or by another automated trigger, the solution with RadAjaxLoadingPanel will not prevent the dragging of a dock in all cases. In this scenario the AJAX request could be triggered while a dock is being dragged, which will lead to the JavaScript errors examined in the sections above.

__Example 6__: The update panel that updates the dock could be triggered by a timer.

````ASPNET
	        <asp:UpdatePanel ID="UpdatePanel1" runat="server">
	            <ContentTemplate>
	                <telerik:RadDockZone runat="server" ID="RadDockZone1" Width="300px">
	                    <telerik:RadDock runat="server" ID="RadDock1" DockMode="Docked">
	                    </telerik:RadDock>
	                </telerik:RadDockZone>
	            </ContentTemplate>
	            <Triggers>
	                <asp:AsyncPostBackTrigger ControlID="Timer1" />
	            </Triggers>
	        </asp:UpdatePanel>
	        <asp:Timer runat="server" ID="Timer1" Interval="3000">
	        </asp:Timer>
````



You can __avoid the errors in this case by stopping the timer while a dock is being dragged__. First, you need to set a handler for the[OnClientDragStart]({%slug dock/client-side-programming/events/onclientdragstart%}) event. You can stop the timer in the body of this event handler. Then, you need to set ahandler for the [OnClientDragEnd]({%slug dock/client-side-programming/events/onclientdragend%}) event. You can restart the timer in the body of this event handler.

The result should be similar to the implementation that is shown in __Example 7__.

__Example 7__: Stopping the timer while a dock is being dragged.

````ASPNET
	        <script type="text/javascript">
	            function getTimer() {
	                return $find("<%=Timer1.ClientID %>");
	            }
	
	            function dockDragStart(sender, eventArgs) {
	                getTimer()._stopTimer();
	            }
	
	            function dockDragEnd(sender, eventArgs) {
	                getTimer()._startTimer();
	            }
	        </script>
	        <asp:UpdatePanel ID="UpdatePanel1" runat="server">
	            <ContentTemplate>
	                <telerik:RadDockZone runat="server" ID="RadDockZone1" Width="300px">
	                    <telerik:RadDock runat="server" ID="RadDock1" DockMode="Docked" 
	                        OnClientDragStart="dockDragStart" OnClientDragEnd="dockDragEnd">
	                    </telerik:RadDock>
	                </telerik:RadDockZone>
	            </ContentTemplate>
	            <Triggers>
	                <asp:AsyncPostBackTrigger ControlID="Timer1" />
	            </Triggers>
	        </asp:UpdatePanel>
	        <asp:Timer runat="server" ID="Timer1" Interval="3000">
	        </asp:Timer>
````



# See Also

 * [Drag And Drop]({%slug dock/getting-started/drag-and-drop%})[RadAjaxPanel Overview](6b8eb9b2-e5b9-44ee-93e0-7cc55cffe577)[RadAjaxManager Overview](546BFFA1-0A6D-4ACF-83E2-02D9592E7857)[RadAjaxLoadingPanel Overview](17E31C56-1D2D-4C8D-9A43-1BEF6D86E7F2)

 * [RadDock OnClientDragStart event]({%slug dock/client-side-programming/events/onclientdragstart%})

 * [RadDock OnClientDragEnd event]({%slug dock/client-side-programming/events/onclientdragend%})
