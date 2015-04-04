---
title: Use Custom FileBrowserContentProvider
page_title: Use Custom FileBrowserContentProvider | UI for ASP.NET AJAX Documentation
description: Use Custom FileBrowserContentProvider
slug: fileexplorer/server-side-programming/use-custom-filebrowsercontentprovider
tags: use,custom,filebrowsercontentprovider
published: True
position: 3
---

# Use Custom FileBrowserContentProvider



__The FileBrowserContentProvider__ abstract class allows for different file sources to be used for the content in the __RadFileExplorer__ control, such as file system, database system, CMS-specific resource system or even online storage systems such as Amazon S3.

The __FileBrowserContentProvider__ implementation in __RadFileExplorer__ is an instance of __Telerik.Web.UI.Widgets.FileSystemContentProvider. It works with the underlying machine's physical file system.__

While the default implementation is good for most scenarios, in some cases (see above) the RadFileExplorer should be hooked to a different file source, such as when using it in a CMS system. This can be achieved in 2 ways:

1. By subclassing the existing __Telerik.Web.UI.Widgets.FileSystemContentProvider__ and overriding only the methods that you need changed.

1. By implementing a new __Telerik.Web.UI.Widgets.FileBrowserContentProvider__

## 1. Subclassing existing FileSystemContentProvider

The following example shows how to override the __ResolveDirectory__ method so it does not show files that have names starting with "private_":

>tabbedCode

````C#
	
	
		protected void Page_Load(object sender, EventArgs e)
		{
			string[] paths = new string[] { "~/" };
			RadFileExplorer1.Configuration.ViewPaths = paths;
			RadFileExplorer1.Configuration.UploadPaths = paths;
			RadFileExplorer1.Configuration.DeletePaths = paths;
	
			#region assign-provider_cs
			RadFileExplorer1.Configuration.ContentProviderTypeName = typeof(ExtendedFileProvider).AssemblyQualifiedName;
````
````VB.NET
	
	    Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs)
	        Dim paths As String() = New String() {"~/"}
	        RadFileExplorer1.Configuration.ViewPaths = paths
	        RadFileExplorer1.Configuration.UploadPaths = paths
	        RadFileExplorer1.Configuration.DeletePaths = paths
	
	
	        '#region assign-provider_vb
	        RadFileExplorer1.Configuration.ContentProviderTypeName = GetType(ExtendedFileProvider).AssemblyQualifiedName
````
>end

## 2. Implementing a custom Telerik.Web.UI.Widgets.FileBrowserContentProvider

When subclassing is not enough to do the job, you can design a completely new FileBrowserContentProvider. The steps to implement are:

1. Extend the abstract __Telerik.Web.UI.Widgets.FileBrowserContentProvider__ class and implement its methods.

>tabbedCode

````C#
	
		public class myNewProvider : Telerik.Web.UI.Widgets.FileBrowserContentProvider
		{
			//constructor must be present when overriding a base content provider class
			//you can leave it empty
			public myNewProvider(HttpContext context, string[] searchPatterns, string[] viewPaths, string[] uploadPaths, string[] deletePaths, string selectedUrl, string selectedItemTag)
				: base(context, searchPatterns, viewPaths, uploadPaths, deletePaths, selectedUrl, selectedItemTag)
			{
			}
			public override Telerik.Web.UI.Widgets.DirectoryItem ResolveRootDirectoryAsTree(string path)
			{
				throw new NotImplementedException();
			}
			public override Telerik.Web.UI.Widgets.DirectoryItem ResolveDirectory(string path)
			{
				throw new NotImplementedException();
			}
			public override string GetFileName(string url)
			{
				throw new NotImplementedException();
			}
			public override string GetPath(string url)
			{
				throw new NotImplementedException();
			}
			public override System.IO.Stream GetFile(string url)
			{
				throw new NotImplementedException();
			}
			public override string StoreBitmap(System.Drawing.Bitmap bitmap, string url, System.Drawing.Imaging.ImageFormat format)
			{
				throw new NotImplementedException();
			}
			public override string StoreFile(Telerik.Web.UI.UploadedFile file, string path, string name, params string[] arguments)
			{
				throw new NotImplementedException();
			}
			public override string DeleteFile(string path)
			{
				throw new NotImplementedException();
			}
			public override string DeleteDirectory(string path)
			{
				throw new NotImplementedException();
			}
			public override string CreateDirectory(string path, string name)
			{
				throw new NotImplementedException();
			}
			public override string MoveFile(string path, string newPath)
			{
				return base.MoveFile(path, newPath);
			}
			public override string MoveDirectory(string path, string newPath)
			{
				return base.MoveDirectory(path, newPath);
			}
			public override string CopyFile(string path, string newPath)
			{
				return base.CopyFile(path, newPath);
			}
			public override string CopyDirectory(string path, string newPath)
			{
				return base.CopyDirectory(path, newPath);
			}
	
			// ##############################################################################
			// !!! IMPORTANT !!!
			// The compilator will not complain if these methods are not overridden, but it is highly recommended to override them
	
			public override bool CheckDeletePermissions(string folderPath)
			{
				return base.CheckDeletePermissions(folderPath);
			}
			public override bool CheckWritePermissions(string folderPath)
			{
				return base.CheckWritePermissions(folderPath);
			}
	
			//Introduced in the 2010.2.826 version of the control
			public override bool CheckReadPermissions(string folderPath)
			{
				return base.CheckReadPermissions(folderPath);
			}
			// ##############################################################################
		}
````
````VB.NET
	
	    Public Class myNewProvider
	        Inherits Telerik.Web.UI.Widgets.FileBrowserContentProvider
	        'constructor must be present when overriding a base content provider class
	        'you can leave it empty
	        Public Sub New(ByVal context As HttpContext, ByVal searchPatterns As String(), ByVal viewPaths As String(), ByVal uploadPaths As String(), ByVal deletePaths As String(), ByVal selectedUrl As String, _
	         ByVal selectedItemTag As String)
	            MyBase.New(context, searchPatterns, viewPaths, uploadPaths, deletePaths, selectedUrl, _
	             selectedItemTag)
	        End Sub
	        Public Overloads Overrides Function ResolveRootDirectoryAsTree(ByVal path As String) As Telerik.Web.UI.Widgets.DirectoryItem
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function ResolveDirectory(ByVal path As String) As Telerik.Web.UI.Widgets.DirectoryItem
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function GetFileName(ByVal url As String) As String
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function GetPath(ByVal url As String) As String
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function GetFile(ByVal url As String) As System.IO.Stream
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function StoreBitmap(ByVal bitmap As System.Drawing.Bitmap, ByVal url As String, ByVal format As System.Drawing.Imaging.ImageFormat) As String
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function StoreFile(ByVal file As Telerik.Web.UI.UploadedFile, ByVal path As String, ByVal name As String, ByVal ParamArray arguments As String()) As String
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function DeleteFile(ByVal path As String) As String
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function DeleteDirectory(ByVal path As String) As String
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function CreateDirectory(ByVal path As String, ByVal name As String) As String
	            Throw New NotImplementedException()
	        End Function
	        Public Overloads Overrides Function MoveFile(ByVal path As String, ByVal newPath As String) As String
	            Return MyBase.MoveFile(path, newPath)
	        End Function
	        Public Overloads Overrides Function MoveDirectory(ByVal path As String, ByVal newPath As String) As String
	            Return MyBase.MoveDirectory(path, newPath)
	        End Function
	        Public Overloads Overrides Function CopyFile(ByVal path As String, ByVal newPath As String) As String
	            Return MyBase.CopyFile(path, newPath)
	        End Function
	        Public Overloads Overrides Function CopyDirectory(ByVal path As String, ByVal newPath As String) As String
	            Return MyBase.CopyDirectory(path, newPath)
	        End Function
	
	
	        ' ##############################################################################
	        ' !!! IMPORTANT !!!
	        ' The compilator will not complain if these methods are not overridden, but it is highly recommended to override them
	        Public Overrides Function CheckDeletePermissions(ByVal folderPath As String) As Boolean
	            Return MyBase.CheckDeletePermissions(folderPath)
	        End Function
	
	        Public Overrides Function CheckWritePermissions(ByVal folderPath As String) As Boolean
	            Return MyBase.CheckWritePermissions(folderPath)
	        End Function
	
	        ' Introduced in the 2010.2.826 version of the control
	        Public Overrides Function CheckReadPermissions(ByVal folderPath As String) As Boolean
	            Return MyBase.CheckReadPermissions(folderPath)
	        End Function
	        ' ##############################################################################
	
	
	    End Class
	
````
>end

1. Set the __RadFileExplorer's__ property __Configuration__.__ContentProviderTypeName__to the fully qualified assembly name of your custom content provider. The general format of the assembly name should be __"Full.Class.Name.Including.The.Namespace, Assembly.Name"__. For example:

>tabbedCode

````C#
			RadFileExplorer1.Configuration.ContentProviderTypeName = typeof(ExtendedFileProvider).AssemblyQualifiedName;
````
````VB.NET
	        RadFileExplorer1.Configuration.ContentProviderTypeName = GetType(ExtendedFileProvider).AssemblyQualifiedName
````
>end



Below you can see the order of calling the various methods of FileBrowserContentProvider's common operations such as initial loading, moving, deleting and uploading files



__Initial Loading__

1. __ResolveRootDirectoryAsTree__ - Called from the server in order to bind the treeview and get the root folder

1. __ResolveRootDirectoryAsTree__ - Get all subfolders of the root folder

1. __ResolveRootDirectoryAsTree__ - Checks all folders in the root for subfolders (*called for every folder*)

1. __ResolveRootDirectoryAsTree__ - Updates folders in grid

1. __ResolveDirectory__- Updates files in grid



__Moving File__

1. __GetPath__ - Gets the current item's parent folder

1. __ResolveDirectory__ - Checks permissions

1. __GetPath__ - Gets the parent folder where the file will be copied (including file's name)

1. __ResolveDirectory__ - Checks permissions

1. __MoveFile__ - Moves the file

1. __ResolveRootDirectoryAsTree__ - Updates the RadTreeView in RadFileExplorer

1. __ResolveDirectory__ - Updates the RadTreeView in RadFileExplorer

1. __ResolveRootDirectoryAsTree__ - Updates the RadGrid

1. __ResolveDirectory__ - Updates the RadGrid



__Deleting File__

1. __GetPath__ - Gets the parent folder for the deleted item

1. __ResolveDirectory__ - Checks permissions

1. __DeleteFile__ - Deletes the item

1. __ResolveRootDirectoryAsTree__ - Updates the parent tree node

1. __ResolveDirectory__ - Updates the parent tree node

1. __ResolveRootDirectoryAsTree__ - Updates the RadGrid

1. __ResolveDirectory__ - Updates the RadGrid



__Uploading File__

1. __GetFile__ - Returns Stream for accessing the contents of the file item with the given Url

1. __StoreFile__ - Creates a file item from a Telerik.Web.UI.UploadedFile in the given path with the given name.

1. __ResolveRootDirectoryAsTree__ - Update the RadTreeView in RadFileExplorer

1. __ResolveDirectory__ - Updates the RadTreeView

1. __ResolveRootDirectoryAsTree__ - Updates the RadGrid

1. __ResolveDirectory__ - Updates the RadGrid





## FileBrowserContentProvider's properties and methods:

__ResolveRootDirectoryAsTree(string path):__ called for every path set in the ViewPaths collection per request. It returns all subfolders in the root folder given as a parameter.*Sample:**string path: "/FileExplorerCustomProvider"returns:dir: {C:\Work\InHouse\FileExplorerCustomProvider}virtualName: "FileExplorerCustomProvider"virtualParentPath: "/"path: "/FileExplorerCustomProvider"*

__ResolveRootDirectoryAsList(string path):__ This method is obsolete and you do not need to implement it

__ResolveDirectory(string path)__ is used mainly in the Ajax calls and returns all immediate children of the directory passed as the path parameter. This includes both files and sub-folders.*Sample:string path: "/FileExplorerCustomProvider"returns:dir: {C:\Work\InHouse\FileExplorerCustomProvider}path: "/FileExplorerCustomProvider"*

__CreateDirectory(string path, string name):__ Creates a directory item with the given parameters:

1. path (string) - The path where the directory item should be created.

1. name (string) - The name of the new directory item.

*Sample:string path: "/FileExplorerCustomProvider/"string name: "NewFolder"returns: string.Empty (operation successful)*

__GetFileName(string url):__ Gets the name of the file with the given Url. Returns a string containing the file name

__GetPath(string url):__ Gets the virtual path of the item with the given Url.Returns a string containing the path of the item.

__GetFile(string url):__ Returns Stream for accessing the contents of the file item with the given url.

__StoreBitmap(Bitmap bitmap, string url, ImageFormat format):__ Used when creating new images in the Image Editor dialog. Stores an image with the given Url and image format. Returns string.Empty when the operation was successful, otherwise returns a string with the error message to be displayed to the user. Accepts the following parameters:

1. The Bitmap object to be stored

1. The Url of the bitmap as string

1. The image format of the bitmap.

__StoreFile(UploadedFile file, string path, string name, params string[] arguments):__ Creates a file item from a Telerik.Web.UI.UploadedFile in the given path with the given name. Returns string containing the full virtual path (including the file name) of the file item. The method receives the following parameters:

1. The UploadedFile instance to store.

1. The virtual path where the file item should be created.

1. The name of the file item.

1. Additional values to be stored such as Description, DisplayName, etc.

*Sample:parameters:file: {Telerik.Web.UI.PostedFile}string path: "/FileExplorerCustomProvider/"string name: "smiley.jpg"argument: {string[0]}returns: string targetFullPath: "/FileExplorerCustomProvider/smiley.jpg"*

__DeleteFile(string path):__ Deletes the file item with the given virtual path. Returns string.Empty when the operation was successful.*Sample:string path: "/FileExplorerCustomProvider/smiley.jpg"*

*Returns: string.Empty (operation successful)*

__DeleteDirectory(string path):__ Deletes the directory item with the given virtual path. Returns string.Empty when the operation was successful.*Sample:string path: "/FileExplorerCustomProvider/NewSubFolder"Returns: string.Empty (operation successful)*

__CreateDirectory(string path, string name):__ Creates a directory item in the given path with the given name. Returns string.Empty when the operation was successful, otherwise returns a string with the error message to be displayed to the user. The method receives the following parameters:

1. The path where the directory item should be created.

1. The name of the new directory item.

__MoveFile(string path, string newPath):__ Moves a file from a one virtual path to a new one. This method can also be used for renaming items. Returns string.Empty when the operation was successful, otherwise returns a string with the error message to be displayed to the user. The method receives the following parameters:

1. old virtual location

1. new virtual location

*Sample:string path: "/FileExplorerCustomProvider/smiley.jpg"string newPath: "/FileExplorerCustomProvider/NewFolder/smiley.jpg"Returns: string.Empty (operation successful)*

__MoveDirectory(string path, string newPath):__ Moves a directory from a one virtual path to a new one. This method can also be used for renaming items. Returns string.Empty when the operation was successful, otherwise returns a string with the error message to be displayed to the user. The method receives the following parameters:

1. old virtual location

1. new virtual location

*Sample:string path: "/FileExplorerCustomProvider/NewFolder/NewSubFolder" string newPath: "/FileExplorerCustomProvider/NewSubFolder" Returns: string.Empty (operation successful) *

__DisplayMode:__ This property is obsolete. You do not need to override it.

__CanCreateDirectory:__ Gets a value indicating whether the ContentProvider can create directory items or not.

__Context:__ Provides a reference to the current HttpContext object, set in the constructor of the class.

__SelectedUrl:__ Gets or sets the url of the selected item. The file browser will navigate to the item which has this url. __SearchPatterns:__ Gets the search patterns for the file items to be displayed in the FileBrowser control. This property is set in the constructor of the class. Supports wildcards.

__ViewPaths:__ Gets the paths which will be displayed in the dialog. This is passed by RadEditor and is one of the values of ImagesPaths, DocumentsPaths, MediaPaths, FlashPaths, TemplatesPaths properties. You can disregard this value if you have custom mechanism for determining the rights for directory / file displaying. __UploadPaths:__ Gets the paths which will allow uploading in the dialog. This is passed by RadEditor and is one of the values of UploadImagesPaths, UploadDocumentsPaths, UploadMediaPaths, UploadFlashPaths, UploadTemplatesPaths properties. You can disregard this value if you have custom mechanism for determining the rights for uploading.

__DeletePaths:__ The paths which will allow deleting in the dialog. This is passed by RadEditor and is one of the values of DeleteImagesPaths, DeleteDocumentsPaths, DeleteMediaPaths, DeleteFlashPaths, DeleteTemplatesPaths properties. You can disregard this value if you have custom mechanism for determining the rights for deleting.

# See Also

 * [Overview]({%slug fileexplorer/client-side-programming/overview%})[RadEditor's Custom FileBrowserContent Provider](E04CA8C6-F600-49EC-8414-F49C2698BEA5)

 * [Use RadFileExplorer with physical paths and different content types (KB article)](http://www.telerik.com/support/kb/aspnet-ajax/fileexplorer/physical-paths-and-different-content-types.aspx)

 * [Amazon S3 FileBrowserContentProvider](http://www.telerik.com/community/code-library/aspnet-ajax/file-explorer/amazon-s3-filebrowsercontentprovider.aspx)
