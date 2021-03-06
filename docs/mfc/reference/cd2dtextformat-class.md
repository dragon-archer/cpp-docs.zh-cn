---
title: CD2DTextFormat 类
ms.date: 03/27/2019
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
ms.openlocfilehash: fa2f3b663cb5258c64ec0405abacf2e4eedeb987
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396205"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat 类

IDWriteTextFormat 包装器。

## <a name="syntax"></a>语法

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|构造一个 CD2DTextFormat 对象。|
|[CD2DTextFormat::~CD2DTextFormat](#_dtorcd2dtextformat)|析构函数。 当 D2D 文本格式对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CD2DTextFormat::Create](#create)|创建 CD2DTextFormat。 (重写[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create)。)|
|[CD2DTextFormat::Destroy](#destroy)|销毁 CD2DTextFormat 对象。 (重写[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)。)|
|[CD2DTextFormat::Get](#get)|返回 IDWriteTextFormat 接口|
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|获取字体系列名称的副本。|
|[CD2DTextFormat::GetLocaleName](#getlocalename)|获取区域设置名称的副本。|
|[CD2DTextFormat::IsValid](#isvalid)|检查资源有效性 (重写[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)。)|
|[CD2DTextFormat::ReCreate](#recreate)|重新创建 CD2DTextFormat。 (重写[CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate)。)|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DTextFormat::operator IDWriteTextFormat*](#operator_idwritetextformat_star)|返回 IDWriteTextFormat 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|name|描述|
|----------|-----------------|
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|指向 IDWriteTextFormat 的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>要求

**标头：** afxrendertarget.h

##  <a name="_dtorcd2dtextformat"></a>  CD2DTextFormat::~CD2DTextFormat

析构函数。 当 D2D 文本格式对象被销毁时调用。

```
virtual ~CD2DTextFormat();
```

##  <a name="cd2dtextformat"></a>  CD2DTextFormat::CD2DTextFormat

构造一个 CD2DTextFormat 对象。

```
CD2DTextFormat(
    CRenderTarget* pParentTarget,
    const CString& strFontFamilyName,
    FLOAT fontSize,
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,
    const CString& strFontLocale = _T(""),
    IDWriteFontCollection* pFontCollection = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>参数

*pParentTarget*<br/>
指向该呈现器目标的指针。

*strFontFamilyName*<br/>
CString 对象，其中包含字体系列的名称。

*fontSize*<br/>
以 DIP （"与设备无关像素"） 为单位的字体的逻辑大小。 Dip 等于 1/96 英寸。

*fontWeight*<br/>
一个值，指示文本对象的字体粗细。

*fontStyle*<br/>
一个值，指示文本对象的字体样式。

*fontStretch*<br/>
一个值，指示文本对象的字体拉伸。

*strFontLocale*<br/>
CString 对象包含区域设置名称。

*pFontCollection*<br/>
指向字体集合对象的指针。 当此值为 NULL 时，指示系统字体集。

*bAutoDestroy*<br/>
指示所有者 (pParentTarget) 将销毁该对象。

##  <a name="create"></a>  CD2DTextFormat::Create

创建 CD2DTextFormat。

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>返回值

如果该方法成功，它会返回 S_OK。 否则，它返回一个 HRESULT 错误代码。

##  <a name="destroy"></a>  CD2DTextFormat::Destroy

销毁 CD2DTextFormat 对象。

```
virtual void Destroy();
```

##  <a name="get"></a>  CD2DTextFormat::Get

返回 IDWriteTextFormat 接口

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>返回值

指向 IDWriteTextFormat 接口或如果对象尚未初始化，则为 NULL 指针。

##  <a name="getfontfamilyname"></a>  CD2DTextFormat::GetFontFamilyName

获取字体系列名称的副本。

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>返回值

CString 对象，其中包含当前的字体系列名称。

##  <a name="getlocalename"></a>  CD2DTextFormat::GetLocaleName

获取区域设置名称的副本。

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>返回值

CString 对象，其中包含当前区域设置名称。

##  <a name="isvalid"></a>  CD2DTextFormat::IsValid

检查资源有效性

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>返回值

如果资源是有效，则为，TRUE否则为 FALSE。

##  <a name="m_ptextformat"></a>  CD2DTextFormat::m_pTextFormat

指向 IDWriteTextFormat 的指针。

```
IDWriteTextFormat* m_pTextFormat;
```

##  <a name="operator_idwritetextformat_star"></a>  CD2DTextFormat::operator IDWriteTextFormat*

返回 IDWriteTextFormat 接口

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>返回值

指向 IDWriteTextFormat 接口或如果对象尚未初始化，则为 NULL 指针。

##  <a name="recreate"></a>  CD2DTextFormat::ReCreate

重新创建 CD2DTextFormat。

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>返回值

如果该方法成功，它会返回 S_OK。 否则，它返回一个 HRESULT 错误代码。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
