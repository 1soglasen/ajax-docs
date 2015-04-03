---
title: Getting Started
page_title: Getting Started | UI for ASP.NET AJAX Documentation
description: Getting Started
slug: cloudupload/getting-started
tags: getting,started
published: True
position: 1
---

# Getting Started



This tutorial will walk you through creating a Web page that uses __RadCloudUpload__ control. It shows how to use __RadClodUpload__ to upload files.

## Getting Started

1. Create a new page and add a __RadCloudUpload__ control to it.

1. Click the Smart Tag of the __RadCloudUpload__ control to add __RadScriptManager__ to the page:
>caption Figure 1. Adding RadScriptManager

![cloud-upload-getting-started](images/cloud-upload-getting-started.png)

1. Adding the __RadAScriptManager__ will automatically register the __Telerik.Web.UI.WebResource.axd__ handler in the web.config file. This handler is used by both __RadScriptManager__ and __RadCloudUpload__ as demonstrated in the Figure 2. below:
>caption Figure 2. Registering Telerik.Web.UI.WebResource.axd handler

![cloud-upload-getting-started 2](images/cloud-upload-getting-started2.png)

1. Select and configure the __ProviderType__ as in Figure 3:
>caption Figure 3. Provider Type

![cloud-upload-getting-started 3](images/cloud-upload-getting-started3.png)

>caution All Cloud Storage Providers are depending on third party assemblies. To learn how to reference and configure them look at the[ Telerik Backend Services (formerly Everlive) ]({%slug cloudupload/cloud-storage-providers/telerik-backend-services%}),[ AmazonS3 ]({%slug cloudupload/cloud-storage-providers/amazon-s3%})or[ Azure ]({%slug cloudupload/cloud-storage-providers/azure-blob-storage%})Cloud Storages Sections.
>


# See Also

 * [Configuring Telerik Backend Services Provider]({%slug cloudupload/cloud-storage-providers/telerik-backend-services%})

 * [Configuring Azure Blob Storage Provider]({%slug cloudupload/cloud-storage-providers/azure-blob-storage%})

 * [Configuring Amazon S3 Provider]({%slug cloudupload/cloud-storage-providers/amazon-s3%})

 * [Troubleshooting]({%slug cloudupload/troubleshooting%})
