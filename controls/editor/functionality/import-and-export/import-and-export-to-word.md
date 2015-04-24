---
title: Import and Export to Word
page_title: Import and Export to Word | RadEditor for ASP.NET AJAX Documentation
description: Import and Export to Word
slug: editor/functionality/import-and-export/import-and-export-to-word
tags: import,and,export,to,word
published: True
position: 1
---

# Import and Export to Word



This article provides the basics to get you started with the **Telerik Editor**import and export from/to Word document functionality.

As of **Q3 2014**, the **RadEditor** control offers built-in integration with the[Telerik document processing libraries](d17653ff-fe96-41c5-8739-01671fb45fba) that provides the import and export from/to DOCX and RTF feature.

Since **Q2 2014**, the installation of the **Telerik UI for ASP.NET AJAX** suite provides you with the**Telerik.Windows.Document** assemblies, which can be used for conversion from HTML to DOCX or RTF and vise-versa.	Information about the provided libraries, their purpose and how to get them is available in the [](65112864-d4c8-4ad6-8e5a-26f28c32ea8f) article.

>important The **Telerik document processing libraries** support **.NET Framework** versions **4.0** and above.As of **Q3 2014** the **RadEditor** export/import to RTF is not supported under **.NET 3.5** .
>


## Getting Started

The following articles explain the basics of the import and export functionality.

* [Export to DOCX and RTF]({%slug editor/functionality/import-and-export/export-to-docx-and-rtf%})—explains how to setup and use the Export to DOCX and RTF.

* [Import from DOCX and RTF]({%slug editor/functionality/import-and-export/import-from-docx-and-rtf%})—explains how to setup and use the Import from DOCX and RTF.

* [Event: OnExportContent]({%slug editor/server-side-programming/events/onexportcontent%})—explains how to use the **OnExportContent** event to export the file to the server and prevent it from being sent to the client (**Example 1**).

* [Event: OnImportContent]({%slug editor/server-side-programming/events/onimportcontent%})—explains how to use the **OnImportContent** event to modify the **ExportSettings** of the **HtmlFormatProvider** instance (**Example 1**).

* [Live demo: Import and Export to DOCX](http://demos.telerik.com/aspnet-ajax/editor/examples/export-and-import-to-docx/defaultcs.aspx)—online example that shows the import and export to DOCX functionality.

* [Live demo: Import and Export to RTF](http://demos.telerik.com/aspnet-ajax/editor/examples/rtfexport/defaultcs.aspx)—online example that shows the import and export to RTF functionality.

## Extensibility of the Import/Export Interface

If you are looking for a way to extend the built-in export/import functionality or implement a new, custom one, the following resources will provide guidelines to achieve that:

* [Event: OnExportContent]({%slug editor/server-side-programming/events/onexportcontent%})—explains how to use the **OnExportContent** event to dynamically add header and footer elements (**Example 2**).

* [Event: OnImportContent]({%slug editor/server-side-programming/events/onimportcontent%})—explains how to use the **OnImportContent** event to add additional content programmatically to the **RadFlowDocument** (**Example 2**).

* [How to Enhance the RTF Export of RadEditor for ASP.NET AJAX](http://blogs.telerik.com/blogs/13-07-19/how-to-enhance-the-rtf-export-of-radeditor-for-asp.net-ajax)—blog post that explains how to use an external, third-party library to extend the built-in export to RTF functionality. The same approach can be used to modify the DOCX exporting functionality.

* [Import and Export to DOCX by using the Telerik document processing libraries](http://www.telerik.com/community/code-library/import-and-export-to-docx-by-using-the-telerik-document-processing-library)—a Code Library entry that shows how to build a new export template class and integrate it with the **RadEditor** control. You can use this approach to integrate older versions of the **Telerik UI for ASP.NET AJAX** with the Telerik document processing libraries.

# See Also

 * [Export to DOCX and RTF]({%slug editor/functionality/import-and-export/export-to-docx-and-rtf%})

 * [Import from DOCX and RTF]({%slug editor/functionality/import-and-export/import-from-docx-and-rtf%})

 * [Export to PDF]({%slug editor/functionality/import-and-export/export-to-pdf%})[](65112864-d4c8-4ad6-8e5a-26f28c32ea8f)[Telerik Document Processing Libraries - Overview](d17653ff-fe96-41c5-8739-01671fb45fba)
