---
title: 异常 (C++/CX)
ms.date: 07/02/2019
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
ms.openlocfilehash: ade406dc5db6022978f83715555c425caef4375b
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740174"
---
# <a name="exceptions-ccx"></a>异常 (C++/CX)

/Cx 中C++的错误处理基于异常。 在最基本的级别上，Windows 运行时组件将错误报告为 HRESULT 值。 在C++/cx 中，这些值将转换为包含 HRESULT 值的强类型异常以及可通过编程方式访问的字符串说明。  异常作为从 `ref class` 派生的 `Platform::Exception`来实现。  `Platform` 命名空间为最常见的 HRESULT 值定义独特的异常类，而所有其他值都通过 `Platform::COMException` 类来报告。 所有异常类都有一个 [Exception::HResult](platform-exception-class.md#hresult) 字段，可用于检索原始 HRESULT。 你还可以在调试器中检查用户代码的调用堆栈信息，这些信息可帮助确定异常的原始来源，即使该代码源自以以外C++的语言编写的代码中。

## <a name="exceptions"></a>Exceptions

在C++程序中，你可以引发和捕获来自 Windows 运行时操作的异常、派生自`std::exception`的异常或用户定义的类型。 仅当它将跨越应用程序二进制接口（ABI）边界时（例如，当捕获异常的代码是用 JavaScript 编写的时），才必须引发 Windows 运行时异常。 当某个非 Windows 运行时C++异常到达 ABI 边界时，该异常将转换为一个`Platform::FailureException`异常，该异常表示 E_FAIL HRESULT。 有关 ABI 的更多信息，请参见 [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)。

您可以使用以下两个构造函数之一来声明[Platform：： Exception](platform-exception-class.md) ，该构造函数采用 hresult 参数或者 hresult 参数和[Platform：： String](platform-string-class.md)^ 参数，该参数可跨 ABI 传递到处理它的任何 Windows 运行时应用。 也可以使用两个 [Exception::CreateException 方法](platform-exception-class.md#createexception) 重载之一声明异常，这两个方法重载采用 HRESULT 参数或者 HRESULT 参数和 `Platform::String^` 参数。

## <a name="standard-exceptions"></a>标准异常

C++/CX 支持一组表示典型 HRESULT 错误的标准异常。 每个标准异常从 [Platform::COMException](platform-comexception-class.md)派生，而 Platform::COMException 从 `Platform::Exception`派生。 当跨 ABI 边界引发异常时，必须引发一个标准异常。

不能从 `Platform::Exception`派生您自己的异常类型。 若要引发自定义异常，请使用用户定义的 HRESULT 构造 `COMException` 对象。

下表列出了标准异常。

|name|基础 HRESULT|描述|
|----------|------------------------|-----------------|
|COMException|*用户定义的 hresult*|从 COM 方法调用返回无法识别的 HRESULT 时引发。|
|AccessDeniedException|E\_ACCESSDENIED|被拒绝访问资源或功能时引发。|
|ChangedStateException|E\_已\_更改状态|在父集合更改后调用集合迭代器或集合视图的方法时引发，从而使方法的结果无效。|
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|当 COM 类尚未注册时引发。|
|DisconnectedException|RPC\_E\_已断开连接|当对象与其客户端的连接断开时引发。|
|FailureException|E\_失败|操作失败时引发。|
|InvalidArgumentException|E\_INVALIDARG|当提供给方法的参数之一无效时引发。|
|InvalidCastException|E\_NOINTERFACE|当类型无法转换为另一种类型时引发。|
|NotImplementedException|E\_NOTIMPL|当接口方法尚未在类上实现时引发。|
|NullReferenceException|E\_指针|尝试取消引用空对象引用时引发。|
|ObjectDisposedException|RO\_E\_已关闭|对已释放对象执行操作时引发。|
|OperationCanceledException|E\_中止|操作中止时引发。|
|OutOfBoundsException|E\_边界|某个操作尝试在有效范围外访问数据时引发。|
|OutOfMemoryException|E\_OUTOFMEMORY|没有足够内存来完成操作时引发。|
|WrongThreadException|RPC\_E\_错误\_的线程|当一个线程通过专用于代理对象而不属于该线程单元的接口指针调用时引发。|

## <a name="hresult-and-message-properties"></a>HResult 和 Message 属性

所有异常都有一个 [HResult](platform-comexception-class.md#hresult) 属性和一个 [Message](platform-comexception-class.md#message) 属性。 [Exception::HResult](platform-exception-class.md#hresult) 属性获取异常的基础数字 HRESULT 值。 [Exception::Message](platform-exception-class.md#message) 属性获取系统提供的描述异常的字符串。 在 Windows 8 中，消息仅在调试器中提供，并且是只读的。 这意味着，重新引发异常时将无法对其进行更改。 在 Windows 8.1 中，可通过编程方式访问消息字符串，并在重新引发异常时提供新的消息。 调试器中还提供了更详细的调用堆栈信息，包括异步方法调用的调用堆栈。

### <a name="examples"></a>示例

此示例演示如何为同步操作引发 Windows 运行时异常：

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

下一个示例演示如何捕获该异常。

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

若要捕捉异步操作期间引发的异常，请使用任务类并添加一个错误处理继续符。 错误处理延续将其他线程上引发的异常封送回调用线程，以便你可以在代码中一个地方处理所有潜在异常。 有关更多信息，请参见 [使用 C++ 异步编程](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)。

## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected 事件

在 Windows 8.1 您可以订阅[Windows：： windows.applicationmodel.resources.core：： Core：： CoreApplication：： UnhandledErrorDetected](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror.unhandlederrordetected)静态事件，该事件可访问即将关闭进程的未处理的错误。 无论错误源于何处，它都作为与事件参数一起传入的 [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) 对象到达此处理程序。 对该对象调用 `Propagate` 时，它根据错误代码创建并引发相应类型的 `Platform::*Exception` 。 在 catch 块内，可根据需要保存用户状态，然后通过调用 `throw`让进程终止，或者执行其他操作让程序返回已知的状态。 下面的示例演示了基本模式：

在 app.xaml 中：

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

在 app.xaml 中：

```cpp
// Subscribe to the event, for example in the app class constructor:
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);

// Event handler implementation:
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)
{
    auto err = e->UnhandledError;

    if (!err->Handled) //Propagate has not been called on it yet.
{
    try
    {
        err->Propagate();
    }
    // Catch any specific exception types if you know how to handle them
    catch (AccessDeniedException^ ex)
    {
        // TODO: Log error and either take action to recover
        // or else re-throw exception to continue fail-fast
    }
}
```

### <a name="remarks"></a>备注

C++/Cx 不使用`finally`子句。

## <a name="see-also"></a>请参阅

[C++/CX 语言参考](visual-c-language-reference-c-cx.md)<br/>
[命名空间参考](namespaces-reference-c-cx.md)
