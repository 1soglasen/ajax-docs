---
title: AJAX And File Upload
page_title: AJAX And File Upload | UI for ASP.NET AJAX Documentation
description: AJAX And File Upload
slug: ajax/troubleshooting/ajax-and-file-upload
tags: ajax,and,file,upload
published: True
position: 2
---

# AJAX And File Upload



## 

You may experience difficulties trying to upload files with ajaxified controls. For example using the standard <INPUT type=file> on AJAX request the uploaded files items will be empty.

Indeed, there are browser restrictions and __XmlHttpRequest__ object limitations which makes uploading files through AJAX requests impossible. Thus, if you want to use __Telerik RadAjax__ controls with a page, where a control perform uploading files, this control should make regular post-backs instead.

In a typical scenario you may have the whole page (or a part of it) nested within an __RadAjaxPanel__. In this case you have to manually exclude from ajaxifying the control, which is implemented to upload files. Detailed information how this could be achieved may be found in the "[Exclude controls from ajaxifying]({%slug ajax/application-scenarios/exclude-controls-from-ajaxifying%})" help topic.

Using __RadAjaxManager__ in a page, where files are uploaded, should not be a problem. You should only take care of not setting the correspondent control as ajaxified in Manager's __AjaxSettings__.

>caution When you instantiate file upload control through ajax call (e.g. set Visible="true" or control is nested in template control) you will need to manually add enctype="multipart/form-data" to the page form tag as our ajax controls (ASP.NET as well) do not update the form tag.
>




# See Also

 * [File Upload with RadAjax](http://demos.telerik.com/aspnet-ajax/Ajax/Examples/Common/FileUpload/DefaultCS.aspx)
