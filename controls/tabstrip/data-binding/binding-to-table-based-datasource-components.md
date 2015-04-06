---
title: Binding to Table-Based DataSource Components
page_title: Binding to Table-Based DataSource Components | UI for ASP.NET AJAX Documentation
description: Binding to Table-Based DataSource Components
slug: tabstrip/data-binding/binding-to-table-based-datasource-components
tags: binding,to,table-based,datasource,components
published: True
position: 3
---

# Binding to Table-Based DataSource Components



## 

Table-based __DataSource__ components, such as __SqlDataSource__ and __AccessDataSource__ can be used to bind the tab strip declaratively in design time. As with [binding to a DataSet, DataTable, or DataView]({%slug tabstrip/data-binding/binding-to-datatable%}), you can use the *ID-ParentID* relation to establish a hierarchy among the tabs.

>note The[Binding to a Data Source]({%slug tabstrip/getting-started/binding-to-a-data-source%})tutorial gives step-by-step instructions for binding __RadTabStrip__ to an __AccessDataSource__ .
>


To bind to a table-based DataSource component:

1. Drag the __DataSource__ component from the toolbox onto the same page as your __RadTabStrip__ component.

1. Configure the __DataSource__ component to connect to the data.

1. Set the __DataSourceID__ property of your __RadTabStrip__ to the __ID__ of the __DataSource__ component you added in step 1.

1. Set the __DataTextField__, __DataValueField__, and __DataNavigateUrlField__ properties to indicate the columns of the database table that supply values for the __Text__, __Value__, and __NavigateUrl__ properties of tabs.

1. Establish the tabstrip hierarchy by setting the __DataFieldID__ property to the key field for records, and the __DataFieldParentID__ property to the field that gives the key field value of the parent tab.

>tip The __ParentID__ of the root tabs must be __null__ ( __nothing__ ). If for some reason the data source comes without null values for the ParentID column, use a query that returns the expected value (null). For example:
>SELECT ID, Text, IF(ParentID = 0, NULL, ParentID) FROM tblDat
>


1. Bind any additional properties of the tabs using the __[TabDataBound event]({%slug tabstrip/server-side-programming/tabdatabound%})__:



````C#
	 
	
	void RadTabStrip1_TabDataBound( object sender, RadTabStripEventArgs e)
	{
	  e.Tab.ToolTip = "Read more about" + (string)DataBinder.Eval(e.Tab.DataItem, "Text");
	 
	} 
	
				
````
````VB.NET
	     
	Private Sub RadTabStrip1_TabDataBound(ByVal sender As Object, ByVal e As RadTabStripEventArgs) Handles RadTabStrip1.TabDataBound
	    e.Tab.ToolTip = "Read more about" + DirectCast(DataBinder.Eval(e.Tab.DataItem, "Text"), String)
	End Sub  
	
	
	
	
````


The resulting declaration looks something like the following:

````ASPNET
	 
	 <telerik:RadTabStrip
	      runat="server"
	      ID="RadTabStrip1"
	      DataSourceID="SqlDataSource1"
	      DataFieldID="id"
	      DataFieldParentID ="parentID"
	      DataTextField="Targetname"
	      DataNavigatUrlField ="target"
	      OnTabDataBound ="RadTabStrip1_TabDataBound">
	</telerik:RadTabStrip>
	<asp:SqlDataSource
	      runat="server"
	      ID="SqlDataSource1"
	      ConnectionString ="Persist Security Info=False;Integrated Security=true;Initial Catalog=MyDB;server=(local)"
	      ProviderName="System.Data.SqlClient"
	      SelectCommand="SELECT id, Targetname, target, tooltip, parentId from TabStripTable" /> 
````



# See Also

 * [Overview]({%slug tabstrip/data-binding/overview%})

 * [Using DataBindings]({%slug tabstrip/data-binding/using-databindings%})

 * [Binding to Hierarchical DataSource Components]({%slug tabstrip/data-binding/binding-to-hierarchical-datasource-components%})

 * [Binding to Object-Based Data Sources]({%slug tabstrip/data-binding/binding-to-object-based-data-sources%})