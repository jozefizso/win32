﻿---
Description: 'Sets the number of worker threads that are used by a video decoder.'
ms.assetid: 'A1570BB5-62BC-46C0-B9C9-61F99AA13BBE'
title: 'CODECAPI\_AVDecNumWorkerThreads property'
---

# CODECAPI\_AVDecNumWorkerThreads property

Sets the number of worker threads that are used by a video decoder.

## Data type

**LONG** (**VT\_I4**)

## Property GUID

CODECAPI\_AVDecNumWorkerThreads

## Remarks

If the value is –1, the decoder selects the number of threads.

For the [**ICodecAPI**](dshow.icodecapi) interface, set this property as a **LONG** value (**VT\_I4**). For the [**IMFAttributes**](imfattributes.md) interface, set this property as a **UINT32**, although the value is signed.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8 \[desktop apps \| UWP apps\]<br/>                                     |
| Minimum supported server<br/> | Windows Server 2012 \[desktop apps \| UWP apps\]<br/>                           |
| Header<br/>                   | <dl> <dt>Codecapi.h</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Properties](media-foundation-properties.md)
</dt> <dt>

[**ICodecAPI**](dshow.icodecapi)
</dt> </dl>

 

 



