---
title: 编译器警告 C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: b1870d076d21c02574793a8079c4658b39ebf121
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623635"
---
# <a name="compiler-warning-c4368"></a>编译器警告 C4368

无法将 "member" 定义为托管 "type" 的成员：不支持混合类型

不能将本机数据成员嵌入 CLR 类型中。

但是，您可以声明一个指向本机类型的指针，并在托管类的构造函数、析构函数和终结器中控制其生命周期。 有关详细信息，请参阅[析构函数和终结](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)器。

此警告总是作为错误发出。 使用[警告](../../preprocessor/warning.md)杂注禁用 C4368。

## <a name="example"></a>示例

下面的示例生成 C4368。

```cpp
// C4368.cpp
// compile with: /clr /c
struct N {};
ref struct O {};
ref struct R {
    R() : m_p( new N ) {}
    ~R() { delete m_p; }

   property N prop;   // C4368
   int i[10];   // C4368

   property O ^ prop2;   // OK
   N * m_p;   // OK
};
```