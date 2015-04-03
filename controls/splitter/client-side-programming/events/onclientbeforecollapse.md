---
title: OnClientBeforeCollapse
page_title: OnClientBeforeCollapse | UI for ASP.NET AJAX Documentation
description: OnClientBeforeCollapse
slug: splitter/client-side-programming/events/onclientbeforecollapse
tags: onclientbeforecollapse
published: False
position: 6
---

# OnClientBeforeCollapse



## 

>caution  __OnClientBeforeCollapse__ Client-Side event has been deprecated. Please, use the[OnClientCollapsing]({%slug splitter/client-side-programming/events/onclientcollapsing%})instead.
>


The __OnClientBeforeCollapse__ client-side event handler is called when a pane is about to be collapsed. The collapse can occur because the user clicks on a collapse button, or as the result of a a call to a client-side method.

>note The __OnClientBeforeCollapse__ event is supported by __RadPane__ and __RadSlidingPane__ .
>


The following two parameters are passed to the event handler:

* __sender__ is the pane that is about to be collapsed.

* __eventArgs__ has the following methods:

* __set_cancel()__ lets you prevent the pane from being collapsed.

* __get_cancel()__ returns whether the operation was cancelled.

The following example uses the __OnClientBeforeCollapse__ event to show a confirmation dialog:

````ASPNET
	     
	<script type="text/javascript">
	    function confirmCollapse(sender, eventArgs)
	    {
	    	eventArgs.set_cancel(!confirm("Are you sure you want to close " + sender.get_id() + "?"));
	    }
	</script>
	<telerik:RadSplitter runat="server" id="RadSplitter1" Orientation="Horizontal" >
	 <telerik:RadPane
	     runat="server"
	     id="RadPane1"
	     Height="80px"
	    OnClientBeforeCollapse="confirmCollapse" >
	   <telerik:RadSlidingZone runat="server" id="RadSlidingZone1" >
	     <telerik:RadSlidingPane
	       runat="server"
	       Title="Sliding Pane 1"
	       id="SlidingPane1"
	       Height="50px"
	       OnClientBeforeCollapse="confirmCollapse" >
	     </telerik:RadSlidingPane>
	     <telerik:RadSlidingPane
	       runat="server"
	       Title="Sliding Pane 2"
	       id="SlidingPane2"
	       Height="50px"
	       OnClientBeforeCollapse="confirmCollapse" >
	     </telerik:RadSlidingPane>
	   </telerik:RadSlidingZone>
	 </telerik:RadPane>
	 <telerik:RadSplitBar runat="server" id="RadSplitBar1" CollapseMode="Both"  />
	 <telerik:RadPane
	   runat="server"
	   id="RadPane2"
	   Height="90px"
	   OnClientBeforeCollapse="confirmCollapse" >
	 </telerik:RadPane>
	</telerik:RadSplitter> 
				
````



# See Also

 * [Overview]({%slug splitter/client-side-programming/overview%})

 * [RadPane Object]({%slug splitter/client-side-programming/radpane-object%})

 * [RadSlidingPane Object]({%slug splitter/client-side-programming/radslidingpane-object%})

 * [OnClientExpanding]({%slug splitter/client-side-programming/events/onclientexpanding%})

 * [OnClientCollapsed]({%slug splitter/client-side-programming/events/onclientcollapsed%})
