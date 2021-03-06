---
title: 使用调试版本检查内存改写
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 42e3a7f1f1c34ba5a263adfca7496c24e162ab5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314281"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>使用调试版本检查内存改写

若要使用的调试版本检查内存改写，首先必须重新生成用于调试的项目。 然后，转到应用程序的最开始`InitInstance`函数，并添加以下行：

```
afxMemDF |= checkAlwaysMemDF;
```

调试内存分配器会将保护字节周围的所有内存分配。 但是，这些保护字节不做任何良好，除非检查它们是否具有已更改 （这将指示内存改写）。 否则，这只是提供可能，实际上，允许您不再需要内存改写的缓冲区。

通过开启`checkAlwaysMemDF`，则会强制 MFC，以便调用`AfxCheckMemory`函数调用的每次**新**或**删除**进行。 如果检测到内存改写的它会生成类似于以下的跟踪消息：

```
Damage Occurred! Block=0x5533
```

如果你看到以下消息之一，您需要单步执行代码以确定发生损坏的位置。 若要隔离内存改写发生位置更准确地说，您可以显式调用`AfxCheckMemory`自己。 例如：

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

如果第一个断言成功而第二个失败，这意味着，必须在两个调用之间的函数中发生内存改写。

具体取决于你的应用程序的性质，可能会发现`afxMemDF`导致你的程序运行速度太慢甚至测试。 `afxMemDF`变量会导致`AfxCheckMemory`调用的每个调用新的和删除。 应在这种情况下，散点对调用`AfxCheckMemory`（如上所示），然后重试隔离内存覆盖这种方式。

## <a name="see-also"></a>请参阅

[修复发行版本问题](fixing-release-build-problems.md)
