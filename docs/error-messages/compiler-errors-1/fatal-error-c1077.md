---
title: 错误 C1077
ms.date: 11/04/2016
f1_keywords:
- C1077
helpviewer_keywords:
- C1077
ms.assetid: 514d66f4-b512-479a-b793-ebf45c91e15b
ms.openlocfilehash: 4529e29e51a9c4d54597735583333757d25a6c7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229968"
---
# <a name="fatal-error-c1077"></a>错误 C1077

编译器限制：命令行选项数不得超过其限定值

命令行选项数超过了内部限制。

可能多用 [/D](../../build/reference/d-preprocessor-definitions.md)定义的符号太多。 （改为将定义放置在头文件中。）