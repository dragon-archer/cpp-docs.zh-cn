---
title: 弃用的 ANSI API
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ANSI deprecated methods
ms.assetid: c7c5a6fd-95e4-4bee-b3d5-d3826c30947d
ms.openlocfilehash: 88fb249e053a88a93510cb8f6f9b3092d41a0113
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153549"
---
# <a name="deprecated-ansi-apis"></a>弃用的 ANSI API

Microsoft 基础类 (MFC) 库迁移到类和方法，基于 Unicode 字符集中。 因此，已弃用某些 MFC 方法的 ANSI 版本。 在以后的应用程序中使用这些方法的 Unicode 版本。

Windows 公共控件版本 6.1、 预装 Windows Vista 中，从开始不推荐使用以下 ANSI 方法。

## <a name="cbutton-class"></a>CButton 类

```
AFX_ANSI_DEPRECATED BOOL GetIdealSize(LPSIZE psize) const;

AFX_ANSI_DEPRECATED BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist) const;

AFX_ANSI_DEPRECATED BOOL GetTextMargin(LPRECT pmargin) const;

AFX_ANSI_DEPRECATED BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);

AFX_ANSI_DEPRECATED BOOL SetTextMargin(LPRECT pmargin);
```

## <a name="ccomboboxex-class"></a>CComboBoxEx 类

```
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

## <a name="cedit-class"></a>CEdit 类

```
AFX_ANSI_DEPRECATED BOOL GetCueBanner(LPWSTR lpszText,
    int cchText) const;

AFX_ANSI_DEPRECATED BOOL SetCueBanner(LPCWSTR lpszText,
    BOOL fDrawIfFocused = FALSE);
```

## <a name="clinkctrl-class"></a>CLinkCtrl 类

整个类已弃用。

## <a name="clistctrl-class"></a>CListCtrl 类

```
AFX_ANSI_DEPRECATED void CancelEditLabel();

AFX_ANSI_DEPRECATED int EnableGroupView(BOOL fEnable);

AFX_ANSI_DEPRECATED int GetGroupInfo(int iGroupId,
    PLVGROUP pgrp) const;

AFX_ANSI_DEPRECATED void GetGroupMetrics(PLVGROUPMETRICS pGroupMetrics) const;

AFX_ANSI_DEPRECATED BOOL GetInsertMark(LPLVINSERTMARK lvim) const;

AFX_ANSI_DEPRECATED COLORREF GetInsertMarkColor() const;

AFX_ANSI_DEPRECATED int GetInsertMarkRect(LPRECT pRect) const;

AFX_ANSI_DEPRECATED COLORREF GetOutlineColor() const;

AFX_ANSI_DEPRECATED UINT GetSelectedColumn() const;

AFX_ANSI_DEPRECATED BOOL GetTileInfo(PLVTILEINFO pti) const;

AFX_ANSI_DEPRECATED BOOL GetTileViewInfo(PLVTILEVIEWINFO ptvi) const;

AFX_ANSI_DEPRECATED DWORD GetView() const;

AFX_ANSI_DEPRECATED BOOL HasGroup(int iGroupId) const;

AFX_ANSI_DEPRECATED int InsertGroup(int index,
    PLVGROUP pgrp);

AFX_ANSI_DEPRECATED void InsertGroupSorted(PLVINSERTGROUPSORTED pStructInsert);

AFX_ANSI_DEPRECATED int InsertMarkHitTest(LPPOINT pPoint,
    LPLVINSERTMARK lvim) const;

AFX_ANSI_DEPRECATED BOOL IsGroupViewEnabled() const;

AFX_ANSI_DEPRECATED void MoveGroup(int iGroupId,
    int toIndex);

AFX_ANSI_DEPRECATED void MoveItemToGroup(int idItemFrom,
    int idGroupTo);

AFX_ANSI_DEPRECATED void RemoveAllGroups();

AFX_ANSI_DEPRECATED int RemoveGroup(int iGroupId);

AFX_ANSI_DEPRECATED BOOL SetGroupInfo(int iGroupId,
    PLVGROUP pGroup);

AFX_ANSI_DEPRECATED void SetGroupMetrics(PLVGROUPMETRICS pGroupMetrics);

AFX_ANSI_DEPRECATED BOOL SetInfoTip(PLVSETINFOTIP plvInfoTip);

AFX_ANSI_DEPRECATED BOOL SetInsertMark(LPLVINSERTMARK lvim);

AFX_ANSI_DEPRECATED COLORREF SetInsertMarkColor(COLORREF color);

AFX_ANSI_DEPRECATED COLORREF SetOutlineColor(COLORREF color);

AFX_ANSI_DEPRECATED void SetSelectedColumn(int iCol);

AFX_ANSI_DEPRECATED BOOL SetTileInfo(PLVTILEINFO pti);

AFX_ANSI_DEPRECATED BOOL SetTileViewInfo(PLVTILEVIEWINFO ptvi);

AFX_ANSI_DEPRECATED DWORD SetView(int iView);

AFX_ANSI_DEPRECATED BOOL SortGroups(PFNLVGROUPCOMPARE _pfnGroupCompare,
    LPVOID _plv);
```

## <a name="crebarctrl-class"></a>CReBarCtrl 类

```
AFX_ANSI_DEPRECATED void GetBandMargins(PMARGINS pMargins) const;

AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

## <a name="ctoolbarctrl-class"></a>CToolBarCtrl 类

```
AFX_ANSI_DEPRECATED void GetMetrics(LPTBMETRICS ptbm) const;

AFX_ANSI_DEPRECATED void SetMetrics(LPTBMETRICS ptbm);

AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

## <a name="ctooltipctrl-class"></a>CToolTipCtrl 类

```
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

## <a name="see-also"></a>请参阅

[Windows Vista 公用控件的生成要求](../mfc/build-requirements-for-windows-vista-common-controls.md)
