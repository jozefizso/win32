---
Description: COM+ Visual Basic Debugging Support Contrasted with MTS
ms.assetid: 'aa012f88-1f88-4c7f-b774-82b9e29da5e9'
title: COM+ Visual Basic Debugging Support Contrasted with MTS
---

# COM+ Visual Basic Debugging Support Contrasted with MTS

COM+ removes or reduces several limitations of debugging with Microsoft Visual Basic 6.0 and MTS. The following list summarizes changes you can expect with COM+:

-   Debugging multiple components—In COM+, you can debug scenarios in which a client running in one instance of the IDE makes calls to any number of DLLs running in another as a project group. The objects in the grouped DLL projects can call each other arbitrarily, flowing context as needed. Of course, this also works when the DLLs and the client are in the same project group in the same instance of the IDE.

-   Debugging Limitations on Class\_Initialize and Class\_Terminate Events—With COM+, you can put code in the Class\_Initialize and Class\_Terminate events of a COM+ application component even if that code attempts to access the object or its corresponding context object. You can set breakpoints there and use watches. You can also set breakpoints in the Class\_Terminate event.

    Although it is no longer needed as a workaround, you can still implement the [**IObjectControl**](iobjectcontrol.md) interface and use its [**Activate**](iobjectcontrol-activate.md) and [**Deactivate**](iobjectcontrol-deactivate.md) methods if you need to execute code during startup and shutdown of your component. You can also now put breakpoints in code for the **Deactivate** or [**CanBePooled**](iobjectcontrol-canbepooled.md) methods.

-   Watching MTS Objects—With COM+, you can add watches for object variables returned by COM+, including return values from the [**SafeRef**](saferef.md), [**GetObjectContext**](getobjectcontext.md), and [**IObjectContext::CreateInstance**](iobjectcontext-createinstance.md) methods.

-   Increased stability when components fail—In COM+, a component failure will no longer always stop Visual Basic (which runs in the same process as the debugged component). For example, support for just-in-time (JIT) reactivation failures now allows you to look at the object context while debugging.

-   Debugger may reactivate objects released by COM+—As with MTS, Visual Basic 6.0 may reactivate COM+ objects while you are debugging single-step through a client. Because of the way that Visual Basic 6.0 discovers information about objects, this is expected behavior. For example, consider the following code:

    ``` syntax
    Dim obj As Object
    Set obj = CreateObject("MyApp.MyClass")
    obj.Test  'Call the user-defined subroutine named Test.
    Set obj = Nothing
    ```

    If the obj.Test method calls [**IObjectContext::SetComplete**](iobjectcontext-setcomplete.md), COM+ immediately frees obj from memory, but obj has not yet been set to Nothing. When obj.Test returns, the Visual Basic debugger calls [**QueryInterface**](https://msdn.microsoft.com/library/windows/desktop/ms682521) on obj for the [**IProvideClassInfo**](https://msdn.microsoft.com/library/windows/desktop/ms687303) interface. The context wrapper associated with obj creates a new instance of MyApp.MyClass to service the **QueryInterface** call. As a result, you will see this uninitialized object in the debugger after obj.Test has returned. This object appears only in the debugger and is removed by the subsequent instruction to set obj to Nothing.

## Related topics

<dl> <dt>

[Debugging Compiled Visual Basic Components](debugging-compiled-visual-basic-components.md)
</dt> <dt>

[Debugging in the Visual Basic IDE](debugging-in-the-visual-basic-ide.md)
</dt> </dl>

 

 


