---
title: 编译器错误 C2271
ms.date: 11/04/2016
f1_keywords:
- C2271
helpviewer_keywords:
- C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
ms.openlocfilehash: bddd5a413c0ca16d7b344e5d6c478b07f82ca1a5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758705"
---
# <a name="compiler-error-c2271"></a>编译器错误 C2271

"operator"： new/delete 不能有形式表修饰符

使用内存模型说明符声明运算符（`new` 或 `delete`）。

下面的示例生成 C2271：

```cpp
// C2271.cpp
// compile with: /c
void* operator new(size_t) const {   // C2271
// try the following line instead
// void* operator new(size_t) {
   return 0;
}

struct X {
   static void* operator new(size_t) const;   // C2271
   // try the following line instead
   // void * X::operator new(size_t) const;   // static member operator new
};
```
