---
title: OnClientDoubleClick
page_title: OnClientDoubleClick | UI for ASP.NET AJAX Documentation
description: OnClientDoubleClick
slug: treeview/client-side-programming/events/onclientdoubleclick
tags: onclientdoubleclick
published: True
position: 24
---

# OnClientDoubleClick



## 

The __OnClientDoubleClick__client-side event occurs when the end user double-clicks a node.

The event handler receives parameters:

1. The treeview instance that fired the event.

1. Event arguments with functions:

* __get_node()__ retrieves a reference to the clicked on node.

* __get_domEvent()__ retrieves a DOM event object of the double click.

The example below displays the text for the double-clicked node.

````ASPNET
	
	    <script type="text/javascript" language="javascript">
	        function DoubleClick(sender, eventArgs) {
	            var node = eventArgs.get_node();
	            alert("You double clicked " + node.get_text());
	        }
	    </script>
	
	    <telerik:RadTreeView ID="RadTreeView1" runat="server" OnClientDoubleClick="ClientDoubleClick">
	    </telerik:RadTreeView>
````



# See Also

 * [RadTreeNode]({%slug treeview/client-side-programming/objects/radtreenode%})