---
title: 表达式计算器错误 CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: 71e4e3e87b33849e6b487b79268ebc9574c2e5a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299473"
---
# <a name="expression-evaluator-error-cxx0064"></a>表达式计算器错误 CXX0064

不能在绑定的虚拟成员函数上设置断点

如通过指向对象的指针的虚拟成员函数上设置了断点：

```
pClass->vfunc( int );
```

可以通过输入类，如在虚函数上设置断点：

```
Class::vfunc( int );
```

此错误是与 CAN0064 相同。