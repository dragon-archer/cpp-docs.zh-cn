---
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 606f553060e71ece18b3d48159ec40133be28965
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155093"
---
# <a name="comerrorerror"></a>_com_error::Error

**Microsoft 专用**

检索传递给构造函数的 HRESULT。

## <a name="syntax"></a>语法

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>返回值

原始 HRESULT 项传递到构造函数。

## <a name="remarks"></a>备注

检索中的封装的 HRESULT 项`_com_error`对象。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)