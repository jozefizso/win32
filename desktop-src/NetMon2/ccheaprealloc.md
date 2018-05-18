---
Description: 'The CCHeapReAlloc function reallocates memory allocated by the CCHeapAlloc function.'
ms.assetid: '82365ce2-3980-44ff-be0f-062a65f676fc'
title: CCHeapReAlloc function
---

# CCHeapReAlloc function

The **CCHeapReAlloc** function reallocates memory allocated by the **CCHeapAlloc** function.

## Syntax


```C++
LPVOID WINAPI CCHeapReAlloc(
  �LPVOID lpMem,
  �DWORD �dwBytes,
  �BOOL ��bZeroInit
);
```



## Parameters

<dl> <dt>

*lpMem* 
</dt> <dd>

Pointer to the original allocated memory.

</dd> <dt>

*dwBytes* 
</dt> <dd>

Size of the reallocated memory, measured in bytes.

</dd> <dt>

*bZeroInit* 
</dt> <dd>

Indicator of whether reallocated memory was initialized. If the parameter value is **TRUE**, the newly reallocated memory initializes to zero.

</dd> </dl>

## Return value

If the function is successful, the return value is a pointer to the reallocated memory.

If the function is unsuccessful, the return value is **NULL**.

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�2000 Professional \[desktop apps only\]<br/>                           |
| Minimum supported server<br/> | Windows�2000 Server \[desktop apps only\]<br/>                                 |
| Header<br/>                   | <dl> <dt>Netmon.h</dt> </dl>  |
| Library<br/>                  | <dl> <dt>Nmapi.lib</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Nmapi.dll</dt> </dl> |



## See also

<dl> <dt>

[SetCCInstPtr](setccinstptr.md)
</dt> <dt>

[GetCCInstPtr](getccinstptr.md)
</dt> <dt>

[CCHeapAlloc](ccheapalloc.md)
</dt> <dt>

[CCHeapFree](ccheapfree.md)
</dt> <dt>

[CCHeapSize](ccheapsize.md)
</dt> </dl>

�

�



