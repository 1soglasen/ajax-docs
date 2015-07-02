---
title: Telerik.Web.UI.TreeListTemplateColumnEditor
page_title: Telerik.Web.UI.TreeListTemplateColumnEditor
description: Telerik.Web.UI.TreeListTemplateColumnEditor
---

# Telerik.Web.UI.TreeListTemplateColumnEditor

Represents the default column editor for the Telerik.Web.UI.TreeListTemplateColumn

## Inheritance Hierarchy

* System.Object
* Telerik.Web.UI.TreeListColumnEditor
* Telerik.Web.UI.TreeListTemplateColumnEditor

## Properties

###  Template `ITemplate`

Gets a reference to the ITemplate object used for the editor.

###  ContainerControl `Control`

Gets a reference to the Control object which will hold the editor template.

###  Column `TreeListEditableColumn`

Gets the column for which the column editor is created.

## Methods

###  Initialize

Initializes the editor control.

#### Parameters

#### editItem `Telerik.Web.UI.TreeListEditableItem`

The TreeListEditableItem where the editor will be added.

#### container `System.Web.UI.Control`

The container Control to which Controls collection the editor control will be added.

#### Returns

`System.Void` 

###  SetValues

#### Returns

`System.Void` 

###  GetValues

Returns a collection of the edit values contained in the editor.

#### Returns

`System.Collections.IEnumerable` An enumerable object holding the values.

###  GetFirstValueFromEnumerable

Returns the first value from an object implementing IEnumerable, passed as argument. 
            If the collection is empty, returns null.

#### Parameters

#### enumerable `System.Collections.IEnumerable`

An instance of a class that implements IEnumerable.

#### Returns

`System.Object` The first value form the enumerable collection.

###  GetFirstValue

Get the first value from the values of the current .
            This method returns the first item from , if any.

#### Returns

`System.Object` 

###  Initialize

Initializes the column editor for the TreeListColumn.

#### Parameters

#### editItem `Telerik.Web.UI.TreeListEditableItem`

The  which will hold the edit control.

#### container `System.Web.UI.Control`

The container control to which the editor will be added.

#### Returns

`System.Void` 

###  SetValues

Sets the edit values in the column editor.

#### Parameters

#### values `System.Collections.IEnumerable`

A collection of the values which will be used to populate the editor control.

#### Returns

`System.Void` 

###  GetValues

Returns a collection of the values in the editor control.

#### Returns

`System.Collections.IEnumerable` 

