---
title: Client-side Programming Overview
page_title: Overview | UI for ASP.NET AJAX Documentation
description: Overview
slug: panelbar/client-side-programming/overview
tags: overview
published: True
position: 0
---

# Client-side Programming Overview



__RadPanelBar__ provides a flexible client-side API. You can easily interact with the panel bar in the browser using the panel bar client-side object. In addition to a variety of [client-side events]({%slug panelbar/client-side-programming/events%}), the client-side object model lets you achieve complicated tasks while avoiding unnecessary post-backs.

## Getting the RadPanelBar client-side object

__RadPanelBar__ creates a client-side object with the ClientID of the panel bar. You can obtain the reference using the following JavaScript code:

````JavaScript
	
	        var panelBar = $find("<%= RadPanelBar1.ClientID %>");
	
````



## Getting the instance of a particular RadPanelItem

Once you have the client-side object of __RadPanelBar__, you can use the __findItemByText()__ method to get the instance of a particular item:

````JavaScript
	
	        var panelBar = $find("<%= RadPanelBar1.ClientID %>"); 
	        var item = panelBar.findItemByText(text);
	
````



You can also use the __findItemByValue()__ method to get a specific item by its value.

## Cancelling an action

Several client side events occur immediately before the panel bar performs some action. Most of these events all have names that end in "-ing". You can use these events to cancel the panel bar action by using the cancel property of the __eventArgs__ passed to the handler:

````JavaScript
	
	        function OnClientItemClicking(sender, eventArgs) {
	            eventArgs.set_cancel(true); 
	        }
	
````



## Calling a client-side method

When you get the instance of the __RadPanelBar__ object, you can call client-side methods to perform certain tasks. Consider the following examples:

* __expand()__

````JavaScript
	
	        function expandItem(text) {
	            var panelBar = $find("<%= RadPanelBar1.ClientID %>");
	            var item = panelBar.findItemByText(text);
	            if (item) {
	                item.expand();
	            }
	            else {
	                alert("Item with text '" + text + "' not found.");
	            } 
	         }
	
````



* __collapse()__

````JavaScript
	
	         function collapseItem(text) {
	             var panelBar = $find("<%= RadPanelBar1.ClientID %>");
	             var item = panelBar._findItemByText(text);
	             if (item) {
	                 item.collapse();
	             } 
	             else {
	                 alert("Item with text '" + text + "' not found.");
	             } 
	         }
	
````



* __disable()__

````JavaScript
	
	         function disableItem(text) {
	             var panelBar = $find("<%= RadPanelBar1.ClientID %>");
	             var item = panelBar.findItemByText(text);
	             if (item) {
	                 item.disable();
	             }
	             else {
	                 alert("Item with text '" + text + "' not found.");
	             } 
	           }
	
````



* __enable()__

````JavaScript
	
	           function enableAll() {
	               var panelBar = $find("<%= RadPanelBar1.ClientID %>");
	               for (var i = 0; i < panelBar.get_allItems().length; i++) {
	                   panelBar.get_allItems()[i].enable();
	               } 
	        }
	
````



## Preserving Changes

By default, changes made in client-side code do not persist over a post-back to the server. To preserve changes, you must use the __trackChanges__ and __commitChanges__ methods:

````JavaScript
	
	        function addNewItem() {
	            var panelBar = $find("<%= RadPanelBar1.ClientID %>");
	            var panelItem = new Telerik.Web.UI.RadPanelItem();
	            panelItem.set_text("New Item");
	            panelBar.trackChanges();
	            panelBar.get_items().add(panelItem);
	            panelBar.commitChanges(); 
	           }
	
````



# See Also

 * [RadPanelBar Object]({%slug panelbar/client-side-programming/radpanelbar-object%})

 * [RadPanelItemCollection Object]({%slug panelbar/client-side-programming/radpanelitemcollection-object%})

 * [RadPanelItem Object]({%slug panelbar/client-side-programming/radpanelitem-object%})

 * [Working With Items at the Client]({%slug panelbar/radpanelbar-items/working-with-items-at-the-client%})
