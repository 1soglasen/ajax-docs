---
title: OnClientExpanded
page_title: OnClientExpanded | UI for ASP.NET AJAX Documentation
description: OnClientExpanded
slug: splitter/client-side-programming/events/onclientexpanded
tags: onclientexpanded
published: True
position: 11
---

# OnClientExpanded



## 

The __OnClientExpanded__ client-side event handler is called when a pane has just been expanded. The expansion can occur because of a user action such as clicking an expand button or sliding zone tab, on page load, or as the result of a a call to a client-side method.

>note The __OnClientExpanded__ event is supported by __RadPane__ and __RadSlidingPane__ .
>


The following parameter is passed to the event handler:

* __sender__ is the pane that is has just been expanded.

The following example uses the __OnClientExpanded__ event to update the content of the pane:

````ASPNET
	     
	<script type="text/javascript">
	    function countExpands(pane)
	    {
	        // expandCount is a custom variable
	        var count = pane.expandCount;
	        if (count)
	            count = count + 1;
	        else
	            count = 1;
	        pane.expandCount = count;
	        var id = pane.get_id();
	        if (id == "RadPane2") // RadPane
	            pane.set_content("This pane has expanded " + count + " times.");
	        else // RadSlidingPane
	            pane.setContent("This pane has expanded " + count + " times.");
	    }
	</script>
	<telerik:RadSplitter runat="server" id="RadSplitter1" Width="90%" Orientation="Horizontal" >
	 <telerik:RadPane runat="server" id="RadPane1" Height="80px" >
	   <telerik:RadSlidingZone runat="server" id="RadSlidingZone1" >
	     <telerik:RadSlidingPane runat="server"
	       Title="Pane1"
	       id="SlidingPane1"
	       Height="50px"
	       OnClientExpanded="countExpands" >
	       This pane has expanded 0 times.
	     </telerik:RadSlidingPane>
	     <telerik:RadSlidingPane
	       runat="server"
	       Title="Pane2"
	       id="SlidingPane2"
	       Height="50px"
	       OnClientExpanded="countExpands">
	       This pane has expanded 0 times.
	     </telerik:RadSlidingPane>
	   </telerik:RadSlidingZone>
	 </telerik:RadPane>
	 <telerik:RadSplitBar runat="server" id="RadSplitBar1" CollapseMode="Both"  />
	 <telerik:RadPane
	   runat="server"
	   id="RadPane2"
	   Height="90px"
	   OnClientExpanded="countExpands">
	     This pane has expanded 0 times.
	 </telerik:RadPane>
	</telerik:RadSplitter> 
				
````



# See Also

 * [Overview]({%slug splitter/client-side-programming/overview%})

 * [RadPane Object]({%slug splitter/client-side-programming/radpane-object%})

 * [RadSlidingPane Object]({%slug splitter/client-side-programming/radslidingpane-object%})

 * [OnClientBeforeExpand]({%slug splitter/client-side-programming/events/onclientbeforeexpand%})

 * [OnClientCollapsed]({%slug splitter/client-side-programming/events/onclientcollapsed%})
