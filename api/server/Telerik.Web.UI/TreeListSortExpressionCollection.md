---
title: Telerik.Web.UI.TreeListSortExpressionCollection
page_title: Telerik.Web.UI.TreeListSortExpressionCollection
description: Telerik.Web.UI.TreeListSortExpressionCollection
---

# Telerik.Web.UI.TreeListSortExpressionCollection

A collection of Telerik.Web.UI.TreeListSortExpression objects. Depending on the value of
            P:Telerik.Web.UI.TreeListSortExpressionCollection.AllowMultiColumnSorting it holds single
            or multiple sort expressions.

## Inheritance Hierarchy

* System.Object
* Telerik.Web.UI.TreeListSortExpressionCollection

## Properties

###  AllowMultiColumnSorting `Boolean`

If false, the collection can contain only one sort expression at a time.
            Trying to add a new one in this case will delete the existing expression
            or will change the sort order if its FiledName is the same.

###  Item `TreeListSortExpression`

This is the default indexer of the collection - takes an integer value.

###  AllowNaturalSort `Boolean`

Allow the no-sort state when changing sort order.

###  Count `Int32`

Returns the number of items in the RadTreeListSortExpressionCollection.

###  IsSynchronized `Boolean`

Gets a value indicating whether access to the RadTreeListSortExpressionCollection is
            synchronized (thread safe).

###  SyncRoot `Object`

Gets an object that can be used to synchronize access to the
                        RadTreeListSortExpressionCollection.

## Methods

###  CopyTo

#### Returns

`System.Void` 

###  GetEnumerator

Returns an enumerator that iterates through the
            RadTreeListSortExpressionCollection.

#### Returns

`System.Collections.IEnumerator` 

###  Add

Adds a  to the collection.

#### Returns

`System.Int32` 

###  Clear

Clears the RadTreeListSortExpressionCollection of all items.

#### Returns

`System.Void` 

###  CopyTo

#### Returns

`System.Void` 

###  GetExpression

Find a SortExpression in the collection if it contains any with sort field = expression

#### Parameters

#### expression `System.String`

sort field

#### Returns

`Telerik.Web.UI.TreeListSortExpression` 

###  AddSortExpression

If  is true adds the sortExpression in the collection. 
            Else any other expression previously stored in the collection wioll be removed

#### Parameters

#### sortExpression `Telerik.Web.UI.TreeListSortExpression`

#### Returns

`System.Void` 

###  AddSortExpression

If  is true adds the sortExpression in the collection. 
            Else any other expression previously stored in the collection wioll be removed

#### Parameters

#### expression `System.String`

String containing sort field and optionaly sort order (ASC or DESC)

#### Returns

`System.Void` 

###  AddAt

Adds a  to the collection at the specified
                index.

#### Remarks
As a convenience feature, adding at an index greater than zero will set the
                 to true.

#### Returns

`System.Void` 

###  RemoveSortExpression

Removes the specified  from the collection.

#### Returns

`System.Void` 

###  ContainsSortExpression

Returns true or false depending on whether the specified sorting expression exists
                in the collection. Takes a  parameter.

#### Returns

`System.Boolean` 

###  ContainsExpression

Returns true or false depending on whether the specified sorting expression
            exists in the collection. Takes a string parameter.

#### Returns

`System.Boolean` 

###  ChangeSortOrder

Adds the sort field (expression parameter) if the collection does not alreqady contain the field. Else the sort order of the field will be inverted. The default change order is
            Asc -> Desc -> No Sort. The No-Sort state can be controlled using  property

#### Parameters

#### expression `System.String`

#### Returns

`System.Void` 

###  GetSortString

Get a comma separated list of sort fields and sort-order, in the same format used by
            DataView.Sort string expression. Returns null (Nothing) if there are no sort expressions in the collection

#### Returns

`System.String` Comma separated list of sort fields and optionaly sort-order, null if there are no sort expressions in the collection

###  IndexOf

Searches for the specified
             and
            returns the zero-based index of the first occurrence within the entire
            .

#### Returns

`System.Int32` 
