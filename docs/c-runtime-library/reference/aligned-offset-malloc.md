---
title: _aligned_offset_malloc
ms.date: 11/04/2016
api_name:
- _aligned_offset_malloc
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _aligned_offset_malloc
- aligned_offset_malloc
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
ms.openlocfilehash: 3e8d6f839f3c675b7543ff14f3f633b0c7d5151f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943859"
---
# <a name="_aligned_offset_malloc"></a>_aligned_offset_malloc

在指定对齐边界分配内存。

## <a name="syntax"></a>语法

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>参数

*size*<br/>
请求的内存分配的大小。

*alignment*<br/>
对齐值，必须是 2 的整数次幂。

*offset*<br/>
用于强制对齐的内存分配中的偏移量。

## <a name="return-value"></a>返回值

指向分配的内存块的指针; 如果操作失败，则为**NULL** 。

## <a name="remarks"></a>备注

**_aligned_offset_malloc**在嵌套元素上需要对齐的情况下很有用;例如，如果在嵌套类上需要对齐。

**_aligned_offset_malloc**基于**malloc**;有关详细信息，请参阅[malloc](malloc.md)。

**_aligned_offset_malloc**被标记`__declspec(noalias)` `__declspec(restrict)`为，这意味着该函数不能修改全局变量，并且返回的指针没有化名。 有关详细信息，请参阅 [noalias](../../cpp/noalias.md) 和[限制](../../cpp/restrict.md)。

如果内存分配失败或请求的大小大于 **_HEAP_MAXREQ**，则此函数会将**Errno**设置为**ENOMEM** 。 有关**errno**的详细信息，请参阅[errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。 此外， **_aligned_offset_malloc**还会验证其参数。 如果*对齐*不是2的幂或如果*offset*大于或等于*大小*且非零，则此函数将调用无效参数处理程序，如[参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果允许执行继续，则此函数将返回**NULL** ，并将**Errno**设置为**EINVAL**。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>示例

有关详细信息，请参阅 [_aligned_malloc](aligned-malloc.md)。

## <a name="see-also"></a>请参阅

[数据对齐](../../c-runtime-library/data-alignment.md)<br/>
