---
title: RadAsyncUpload Object
page_title: RadAsyncUpload Object | RadAsyncUpload for ASP.NET AJAX Documentation
description: RadAsyncUpload Object
slug: asyncupload/client-side-programming/radasyncupload-object
tags: radasyncupload,object
published: True
position: 1
---

# RadAsyncUpload Object

## 

The following table lists the important **RadAsyncUpload** client-side methods:


>caption  

| Name | Parameters | Return Type | Description |
| ------ | ------ | ------ | ------ |
| **addFileInput** |none|none|Adds a new row to the **RadAsyncUpload** control.|

````ASPNET
<telerik:RadAsyncUpload runat="server" id="RadAsyncUpload1" />
<input type="button" value="Add" onclick="myAdd()" />
<script type="text/javascript">
    function myAdd() {
        $find("<%= RadAsyncUpload1.ClientID%>").addFileInput();
    }
</script>
````

>caption  

|  **deleteFileInputAt**  | integer | none | Deletes the row at the specified (0-based) index if it exists. |
| ------ | ------ | ------ | ------ |

>note Be careful to use the right index because in different scenarios file inputs may be ordered differently in **RadAsyncUpload** .
>

````JavaScript
function DeleteInvalidFiles() {
  var upload = $find("<%= RadAsyncUpload1.ClientID %>");
  var inputs = upload.getUploadedFiles();
  for (i = inputs.length - 1; i >= 0;i--) {
    if(!upload.isExtensionValid(inputs[i].value))
       upload.deleteFileInputAt(i);
  }
}		
````
>caption  

|  **deleteAllFileInputs**  | none | none | Deletes all rows with the uploaded files. |
| ------ | ------ | ------ | ------ |

>caption  

|  **getUploadedFiles**  | none | array | Returns an array containing the names of the uploaded files. |
| ------ | ------ | ------ | ------ |

````JavaScript
function ClearInvalidInputs() {
  var upload = $find("<%= RadAsyncUpload1.ClientID %>");
  var inputs = upload.getUploadedFiles();
  for (i = inputs.length - 1; i >= 0;i--) {
    alert(inputs[i] + " was  uploaded");    
  }
}			
````

>caption  

|  **getID**  | string | string | Creates a new ID, based on the **RadAsyncUpload** ClientID, the supplied parameter, and the zero based index of the current row. |
| ------ | ------ | ------ | ------ |

>caution This method must be used when[adding custom fields]({%slug asyncupload/application-scenarios/adding-information-to-uploaded-files%})to a **RadAsyncUpload** instance.
>

````ASPNET
<telerik:RadAsyncUpload runat="server" id="RadAsyncUpload1" OnClientAdded="addTitle" />
<script type="text/javascript">
    function addTitle(RadAsyncUpload, args) {
        var row = args.get_row();
        var title = document.createElement("input");
        title.id = title.name = RadAsyncUpload.getID("title");
        row.insertBefore(title, row.firstChild);
    }
</script>
````

>caption  

|  **isExtensionValid**  | string | boolean | Validates the extension of the file name that is passed as a parameter. |
| ------ | ------ | ------ | ------ |

````JavaScript
function ClearInvalidInputs() {
	var upload = $find("<%= RadAsyncUpload1.ClientID %>");
	var inputs = upload.getUploadedFiles();
	for (i = inputs.length - 1; i >=0; i--) {
	if (!upload.isExtensionValid(inputs[i]))
		alert("extension is invalid!")	  
}		
````

>caption  

|  **get_maxFileCount**  | none | integer | Returns the maximum number of rows in the **RadAsyncUpload** control. |
| ------ | ------ | ------ | ------ |
| **set_maxFileCount** |integer|none|Sets the maximum number of rows in the **RadAsyncUpload** control.|
| **get_initialFileInputsCount** |none|integer|Returns the initial number of rows when the **RadAsyncUpload** control is first loaded.|
| **get_allowedFileExtensions** |none|array|Returns an array containing the allowed file extensions.|
| **get_element** |none|HTML element|Returns the DOM element for the **RadAsyncUpload** control.|
| **get_loadedModuleName** |none|string|Returns string representation of the loaded upload module name. It could be one of the following: Silverlight/Flash/IFrame|

## See Also

[Getting Started]({%slug asyncupload/getting-started%})

[Client-Side Basics]({%slug asyncupload/client-side-programming/overview%})

[Client-Side Events]({%slug asyncupload/client-side-programming/events%})
