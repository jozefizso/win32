﻿---
Description: 'Gets a certificate for a display driver.'
ms.assetid: 'eceaf151-1dae-4ff0-9139-7f1789f6c682'
title: GetCertificate function
---

# GetCertificate function

> \[!Important\]  
> This function is used by [Output Protection Manager](output-protection-manager.md) (OPM) to access functionality in the display driver. Applications should not call this function.

 

Gets a certificate for a display driver.

## Syntax


```C++
NTSTATUS WINAPI GetCertificate(
  _In_  PUNICODE_STRING          pstrDeviceName,
  _In_  DXGKMDT_CERTIFICATE_TYPE ctPVPCertificateType,
  _Out_ BYTE                     *pbCertificate,
  _Out_ ULONG                    ulCertificateLength
);
```



## Parameters

<dl> <dt>

*pstrDeviceName* \[in\]
</dt> <dd>

A pointer to a [**UNICODE\_STRING**](security.unicode_string) structure that contains the name of the display device, as returned by the [**GetMonitorInfo**](gdi.getmonitorinfo) function.

</dd> <dt>

*ctPVPCertificateType* \[in\]
</dt> <dd>

The type of certificate, specified as a member of the **DXGKMDT\_CERTIFICATE\_TYPE** enumeration.

</dd> <dt>

*pbCertificate* \[out\]
</dt> <dd>

A pointer to a buffer that receives the certificate.

</dd> <dt>

*ulCertificateLength* \[out\]
</dt> <dd>

The size of the *pbCertificate* buffer, in bytes. To get the size of the certificate, call [**GetCertificateSize**](getcertificatesize.md).

</dd> </dl>

## Return value

If the method succeeds, it returns **STATUS\_SUCCESS**. Otherwise, it returns an **NTSTATUS** error code.

## Remarks

Applications should call the [**IOPMVideoOutput::StartInitialization**](iopmvideooutput-iopmvideooutput--startinitialization.md) method instead of this function.

This function has no associated import library. To call this function, you must use the [**LoadLibrary**](base.loadlibrary) and [**GetProcAddress**](base.getprocaddress) functions to dynamically link to Gdi32.dll.

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                       |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                 |
| DLL<br/>                      | <dl> <dt>Gdi32.dll</dt> </dl> |



## See also

<dl> <dt>

[OPM Functions](opm-functions.md)
</dt> <dt>

[Output Protection Manager](output-protection-manager.md)
</dt> </dl>

 

 



