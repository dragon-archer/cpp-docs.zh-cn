---
title: 异常处理（C++/CLI 和 C++/CX）
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- structured exception handling [C++], managed exceptions
- Exception class, managed applications
- exception handling
- C++ exception handling
- exception handling, types of
- System::Exception class in managed applications
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
ms.openlocfilehash: b477f7355ee1f4f70a0ad3df8b85c4276c07d397
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516572"
---
# <a name="exception-handling--ccli-and-ccx"></a>异常处理（C++/CLI 和 C++/CX）

使用 `/ZW` 编译器选项或 `/clr` 编译器选项编译的应用程序，都使用异常来处理程序执行期间出现的意外错误。 以下主题讨论 C++/CX 或 C++/CLI 应用程序中的异常处理。

## <a name="in-this-section"></a>本节内容

[使用托管异常中的基本概念](../dotnet/basic-concepts-in-using-managed-exceptions.md)<br/>
介绍了如何抛出异常和使用 try/catch 块。

[/clr 下的异常处理行为区别](../dotnet/differences-in-exception-handling-behavior-under-clr.md)<br/>
讨论与 C++ 异常处理的标准行为的区别。

[finally](../dotnet/finally.md)<br/>
讨论如何使用 finally 关键字。

[如何：定义和安装全局异常处理程序](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
演示如何捕获未经处理的异常。

[如何：在本机代码中捕获从 MSIL 抛出的异常](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)<br/>
讨论如何捕获本机代码中的 CLR 和 C++ 异常。

[如何：定义和安装全局异常处理程序](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
演示如何捕获所有未经处理的异常。

## <a name="related-sections"></a>相关章节

[异常处理](../cpp/exception-handling-in-visual-cpp.md)<br/>
介绍了标准 C++ 中的异常处理。

## <a name="see-also"></a>请参阅

[ .NET 和 UWP 的组件扩展](component-extensions-for-runtime-platforms.md)