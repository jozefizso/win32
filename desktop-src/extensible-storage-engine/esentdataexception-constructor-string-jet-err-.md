---
description: "Learn more about: EsentDataException constructor (String, JET_err)"
title: EsentDataException constructor (String, JET_err)
TOCTitle: EsentDataException constructor (String, JET_err)
ms:assetid: M:Microsoft.Isam.Esent.Interop.EsentDataException.#ctor(System.String,Microsoft.Isam.Esent.Interop.JET_err)
ms:mtpsurl: https://msdn.microsoft.com/library/microsoft.isam.esent.interop.esentdataexception.esentdataexception(v=EXCHG.10)
ms:contentKeyID: 55101571
ms.date: 07/30/2014
ms.topic: reference
dev_langs:
- vb
- csharp
api_name: 
- Microsoft.Isam.Esent.Interop.EsentDataException..ctor
topic_type: 
- apiref
- kbSyntax
api_type: 
- Managed
api_location: 
- Microsoft.Isam.Esent.Interop.dll
ROBOTS: INDEX,FOLLOW

---

# EsentDataException constructor (String, JET_err)

Initializes a new instance of the EsentDataException class.

**Namespace:**  [Microsoft.Isam.Esent.Interop](./microsoft.isam.esent.interop-namespace.md)  
**Assembly:**  Microsoft.Isam.Esent.Interop (in Microsoft.Isam.Esent.Interop.dll)

## Syntax

``` vb
'Declaration
Protected Sub New ( _
    description As String, _
    err As JET_err _
)
'Usage
Dim description As String
Dim err As JET_err

Dim instance As New EsentDataException(description, _
    err)
```

``` csharp
protected EsentDataException(
    string description,
    JET_err err
)
```

#### Parameters

  - description  
    Type: [System.String](/dotnet/api/system.string)  
    
    The description of the error.

<!-- end list -->

  - err  
    Type: [Microsoft.Isam.Esent.Interop.JET_err](./jet-err-enumeration.md)  
    
    The error code of the exception.

## See also

#### Reference

[EsentDataException class](./esentdataexception-class.md)

[EsentDataException members](./esentdataexception-members.md)

[EsentDataException overload](./esentdataexception-constructor.md)

[Microsoft.Isam.Esent.Interop namespace](./microsoft.isam.esent.interop-namespace.md)
