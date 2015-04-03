---
title: Getting Started
page_title: Getting Started | UI for ASP.NET AJAX Documentation
description: Getting Started
slug: ziplibrary/getting-started
tags: getting,started
published: True
position: 2
---

# Getting Started



The __Zip Library__ allows you to load data from existing ZIP archives or create and edit ZIPs that can be used by other applications. You can also create ZIP archives in memory or use a stream to get data and add it to a ZIP archive.

The ZIP archive is represented by __ZipArchive__ class. It can be used in 3 modes:

* __Read__: Allows reading of the existing ZIP archive. In this mode it is not possible to add or update archive entries.

* __Create__: Allows creation of a new archive. In this mode you can add new entries in the archive but cannot read or update content of the entries which have been written already.

* __Update__: Allows update of the existing ZIP archive. In this mode you can add new entries, read and update existing entries.

ZipArchive class was introduced in Q2 2014. In case you are using an older version of Telerik UI for ASP.NET AJAX refer to [this article](de058bf2-18db-43a8-9840-1092c3af9ef6).

## Add the Telerik ZIP Library Assembly

In order to use the __Zip Library__ in your application, you need to add a reference to the __Telerik.Windows.Zip.dll__ assembly. This is a cross-platform library that lets you load, create and update ZIP archives on the fly with easy to use API.

The assembly will be automatically added to the Bin folder when you create a Telerik Web Forms site or you can manually find it in the AdditionalLibraries folder in the Telerik UI for ASP.NET AJAX installation (automated and manual) and in the internal builds archive. It supports .NET 4 and .NET 4.5, so depending on the target framework of your project, you need to take the assembly from the Bin40 or Bin45 folder respectively.

For a full list of the Telerik assemblies you can refer to the[Included Assemblies](http://www.telerik.com/help/aspnet-ajax/introduction-included-assemblies.html) article.

## Open Zip Archive

The following code snippet demonstrates how to open existing Zip archive using the __ZipArchive__ class.

>tabbedCode

````C#
	    using (Stream stream = File.Open("test.zip", FileMode.Open))
	{
	    using (ZipArchive archive = new ZipArchive(stream))
	    {
	        // Display the list of the files in the selected zip file using the ZipArchive.Entries property.
	    }
	}
````



````VB.NET
	Using stream As Stream = File.Open("test.zip", FileMode.Open)
	    ' Display the list of the files in the selected zip file using the ZipArchive.Entries property.
		Using archive As New ZipArchive(stream)
		End Using
	End Using
````


>end

The *archive* variable holds the files that are compressed in the selected zip. You can access the list of these files through the __ZipArchive.Entries__ property. It holds a collection of __ZipArchiveEntry__ elements - the elements that describe the files archived in the zip file. You can use these elements to get the name of the compressed file, its uncompressed and compressed size and other file attributes.

## Create Zip Archive

The example below shows how to create a new Zip archive using the __ZipArchive__ class and place a text file in it.

>tabbedCode

````C#
	using (Stream stream = File.Open("test.zip", FileMode.Create))
	{
	    using (ZipArchive archive = new ZipArchive(stream, ZipArchiveMode.Create, false, null))
	    {
	        using (ZipArchiveEntry entry = archive.CreateEntry("text.txt"))
	        {
	            StreamWriter writer = new StreamWriter(entry.Open());
	            writer.WriteLine("Hello world!");
	            writer.Flush();
	        }
	    }
	}
````



````VB.NET
	    Using stream As Stream = File.Open("test.zip", FileMode.Create)
		Using archive As New ZipArchive(stream, ZipArchiveMode.Create, False, Nothing)
			Using entry As ZipArchiveEntry = archive.CreateEntry("text.txt")
	    Dim writer As New StreamWriter(entry.Open())
				writer.WriteLine("Hello world!")
				writer.Flush()
			End Using
		End Using
	End Using
````


>end

>tip If you use __StreamWriter__ to write content to the stream you should call the Flush() method in order to flush the data to the stream.
>


>note Do not close the stream opened by the __ZipArchiveEntry.Open()__ method. Otherwise the result is unpredictable.
>


# See Also

 * [Update ZipArchive]({%slug ziplibrary/functionality/update-ziparchive%})
