---
title: _Cbuild、_FCbuild、_LCbuild
ms.date: 03/30/2018
api_name:
- _Cbuild
- _FCbuild
- _LCbuild
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
ms.openlocfilehash: b0ae50f40f0ca0a926e1eef586c6610a04b6ea7a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943214"
---
# <a name="_cbuild-_fcbuild-_lcbuild"></a>_Cbuild、_FCbuild、_LCbuild

构造实部和虚部的复数。

## <a name="syntax"></a>语法

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>参数

*real*<br/>
要构造的复数的实部。

*imaginary*<br/>
要构造的复数的虚部。

## <a name="return-value"></a>返回值

一个 **_Dcomplex**、 **_Fcomplex**或 **_Lcomplex**结构，它表示指定浮点类型的值的复数（*实*，*虚部* \* i）。

## <a name="remarks"></a>备注

**_Cbuild**、 **_FCbuild**和 **_LCbuild**函数简化了复杂类型的创建。 使用[creal、crealf、creall](creal-crealf-creall.md)和[cimag、cimagf 和 cimagl](cimag-cimagf-cimagl.md)函数检索所表示复数的实部和虚部。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**_Cbuild**、 **_FCbuild**、 **_LCbuild**|\<complex.h>|\<ccomplex>|

这些函数是 Microsoft 特定的。 类型 **_Dcomplex**、 **_Fcomplex**和 **_Lcomplex**是特定于 Microsoft 的等效项，适用于未实现的 C99 本机类型**double _Complex**、 **float _Complex**和**long double _Complex**。 有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[按字母顺序的函数参考](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc、_FCmulcc、_LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr、_FCmulcr、_LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
