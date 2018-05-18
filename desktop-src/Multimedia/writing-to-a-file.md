---
title: Writing to a File
description: Writing to a File
ms.assetid: 'a01f93e9-e0fe-4e81-aa9f-62cdca7bce4a'
keywords: ["AVIFileWriteData function"]
---

# Writing to a File

You can write supplementary information to a file that has been opened with write privileges by using the [**AVIFileWriteData**](avifilewritedata.md) function. This function copies the information from an application-supplied buffer and places it in one or more chunks in the file. The "INFO" chunk is a common RIFF chunk type in which the function stores supplementary information. For a description of RIFF files and their data chunks, see [Resource Interchange File Format Services](resource-interchange-file-format-services.md).

 

 



