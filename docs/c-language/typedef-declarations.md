---
title: Typedef 声明
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, typedef
- typedef declarations
- types [C], declarations
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
ms.openlocfilehash: b4bf7bc82cdf792e5a23f6d5533cc4d800fe4252
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149617"
---
# <a name="typedef-declarations"></a>Typedef 声明

typedef 声明是具有作为存储类的 typedef 的声明。 声明符将成为新类型。 您可以使用 typedef 声明为已由 C 定义的类型或您已声明的类型构造更短和更有意义的名称。 利用 Typedef 名称，您可以封装可能会发生更改的实现详细信息。

typedef 声明的解释方式与变量或函数声明的解释方式相同，只不过标识符没有假定由声明指定的类型，而是成为了该类型的同义词。

## <a name="syntax"></a>语法

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers init-declarator-list*<sub>opt</sub> **;**

*declaration-specifiers*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*storage-class-specifier declaration-specifiers*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier declaration-specifiers*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier declaration-specifiers*<sub>opt</sub>

*storage-class-specifier*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**typedef**

*type-specifier*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**void**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**char**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**short**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**long**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**float**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**double**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**signed**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**unsigned**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-union-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enum-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*typedef-name*

*typedef-name*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

请注意，typedef 声明不会创建类型， 而是创建现有类型的同义词或可通过其他方式指定的类型的名称。 当使用 typedef 名称作为类型说明符时，可以将其与特定的类型说明符组合，但不可以将其与其他类型说明符组合。 可接受的修饰符包括 const 和 `volatile`。

Typedef 名称与普通标识符共享命名空间（有关详细信息，请参阅[命名空间](../c-language/name-spaces.md)）。 因此，程序可以有一个 typedef 名称和一个具有相同名称的本地范围标识符。 例如:

```C
typedef char FlagType;

int main()
{
}

int myproc( int )
{
    int FlagType;
}
```

当通过与 typedef 相同的名称声明本地范围标识符时，或者在同一范围内或内部范围内声明结构或联合的成员时，必须指定类型说明符。 以下示例演示了此约束：

```C
typedef char FlagType;
const FlagType x;
```

若要对标识符、结构成员或联合成员重用 `FlagType` 名称，则必须提供类型：

```C
const int FlagType;  /* Type specifier required */
```

仅仅编写以下语句是不够的

```C
const FlagType;      /* Incomplete specification */
```

由于 `FlagType` 被当做该类型的一部分，因此没有要重新声明的标识符。 此声明被视为非法声明，例如

```C
int;  /* Illegal declaration */
```

可以使用 typedef 声明任何类型，包括指针、函数和数组类型。 只要定义具有与声明相同的可见性，那么在定义结构或联合类型之前，您就可以为指向结构或联合类型的指针声明 typedef 名称。

Typedef 名称可用于提高代码可读性。 `signal` 的所有以下三个声明指定了完全相同的类型，第一个声明没有使用任何 typedef 名称。

```C
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */

void ( *signal( int, void (*) (int)) ) ( int );
fv *signal( int, fv * );   /* Uses typedef type */
pfv signal( int, pfv );    /* Uses typedef type */
```

## <a name="examples"></a>示例

以下示例演示了 typedef 声明：

```C
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */
```

请注意，`WHOLE` 现在可用于变量声明，如 `WHOLE i;` 或 `const WHOLE i;`。 但是，声明 `long WHOLE i;` 是非法的。

```C
typedef struct club
{
    char name[30];
    int size, year;
} GROUP;
```

此语句将 `GROUP` 声明为具有三个成员的结构类型。 由于也指定了结构标记 `club`，因此 typedef 名称 (`GROUP`) 或结构标记可用于声明。 您必须使用带标记的 struct 关键字，并且不能使用带 typedef 名称的 struct 关键字。

```C
typedef GROUP *PG; /* Uses the previous typedef name
                      to declare a pointer            */
```

类型 `PG` 被声明为指向 `GROUP` 类型的指针，而  类型又被定义为结构类型。

```C
typedef void DRAWF( int, int );
```

此示例为不返回值并采用两个 int 参数的函数提供了类型 `DRAWF`。 例如，这意味着声明

```C
DRAWF box;
```

等效于声明

```C
void box( int, int );
```

## <a name="see-also"></a>请参阅

[声明和类型](../c-language/declarations-and-types.md)
