---
title: CPaneDivider 类
ms.date: 11/04/2016
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
helpviewer_keywords:
- CPaneDivider [MFC], CPaneDivider
- CPaneDivider [MFC], AddPaneContainer
- CPaneDivider [MFC], AddPane
- CPaneDivider [MFC], AddRecentPane
- CPaneDivider [MFC], CalcExpectedDockedRect
- CPaneDivider [MFC], CalcFixedLayout
- CPaneDivider [MFC], CheckVisibility
- CPaneDivider [MFC], CreateEx
- CPaneDivider [MFC], DoesAllowDynInsertBefore
- CPaneDivider [MFC], DoesContainFloatingPane
- CPaneDivider [MFC], FindPaneContainer
- CPaneDivider [MFC], FindTabbedPane
- CPaneDivider [MFC], GetDefaultWidth
- CPaneDivider [MFC], GetFirstPane
- CPaneDivider [MFC], GetPaneDividerStyle
- CPaneDivider [MFC], GetRootContainerRect
- CPaneDivider [MFC], GetWidth
- CPaneDivider [MFC], Init
- CPaneDivider [MFC], InsertPane
- CPaneDivider [MFC], IsAutoHideMode
- CPaneDivider [MFC], IsDefault
- CPaneDivider [MFC], IsHorizontal
- CPaneDivider [MFC], Move
- CPaneDivider [MFC], NotifyAboutRelease
- CPaneDivider [MFC], OnShowPane
- CPaneDivider [MFC], ReleaseEmptyPaneContainers
- CPaneDivider [MFC], RemovePane
- CPaneDivider [MFC], ReplacePane
- CPaneDivider [MFC], RepositionPanes
- CPaneDivider [MFC], Serialize
- CPaneDivider [MFC], SetAutoHideMode
- CPaneDivider [MFC], SetPaneContainerManager
- CPaneDivider [MFC], ShowWindow
- CPaneDivider [MFC], StoreRecentDockSiteInfo
- CPaneDivider [MFC], StoreRecentTabRelatedInfo
- CPaneDivider [MFC], GetPanes
- CPaneDivider [MFC], GetPaneDividers
- CPaneDivider [MFC], m_nDefaultWidth
- CPaneDivider [MFC], m_pSliderRTC
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
ms.openlocfilehash: d4888fbf2a95652b0a38adc8ecd059a7515636cb
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866116"
---
# <a name="cpanedivider-class"></a>CPaneDivider 类

有关更多详细信息, 请参阅位于 Visual Studio 安装的**VC\\atlmfc\\src\\mfc**文件夹中的源代码。

`CPaneDivider`类分为两个窗格, 将两组窗格相除, 或将一组窗格与主框架窗口的工作区分隔开。

## <a name="syntax"></a>语法

```
class CPaneDivider : public CBasePane
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[CPaneDivider::CPaneDivider](#cpanedivider)||

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||
|[CPaneDivider::AddPane](#addpane)||
|[CPaneDivider::AddRecentPane](#addrecentpane)||
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|(重写[CBasePane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout)。)|
|[CPaneDivider::CheckVisibility](#checkvisibility)||
|[CPaneDivider::CreateEx](#createex)|(重写[CBasePane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex)。)|
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(重写[CBasePane::D oesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)。)|
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||
|[CPaneDivider::GetFirstPane](#getfirstpane)||
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||
|[CPaneDivider::GetWidth](#getwidth)||
|[CPaneDivider::Init](#init)||
|[CPaneDivider::InsertPane](#insertpane)||
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(重写[CBasePane:: IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode)。)|
|[CPaneDivider::IsDefault](#isdefault)||
|[CPaneDivider::IsHorizontal](#ishorizontal)|(重写[CBasePane:: IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal)。)|
|[CPaneDivider::Move](#move)||
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||
|[CPaneDivider::OnShowPane](#onshowpane)||
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||
|[CPaneDivider::RemovePane](#removepane)||
|[CPaneDivider::ReplacePane](#replacepane)||
|[CPaneDivider::RepositionPanes](#repositionpanes)||
|[CPaneDivider::Serialize](#serialize)|（重写 `CBasePane::Serialize`。）|
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||
|[CPaneDivider::ShowWindow](#showwindow)||
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CPaneDivider::GetPanes](#getpanes)|返回驻留在[CPaneContainer 类](../../mfc/reference/cpanecontainer-class.md)中的窗格的列表。 只应为默认的窗格分隔符调用此方法。|
|[CPaneDivider::GetPaneDividers](#getpanedividers)|返回驻留在[CPaneContainer 类](../../mfc/reference/cpanecontainer-class.md)中的窗格分隔线的列表。 只应为默认的窗格分隔符调用此方法。|

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CPaneDivider::m_nDefaultWidth](#m_ndefaultwidth)|指定应用程序中所有窗格分隔线的默认宽度 (以像素为单位)。|
|[CPaneDivider::m_pSliderRTC](#m_psliderrtc)|保存指向有关`CPaneDivider`派生对象的运行时类信息的指针。|

## <a name="remarks"></a>备注

停靠窗格时`CPaneDivider` , 框架会自动创建对象。

有两种类型的窗格分隔线:

- 当一组窗格停靠在主框架窗口的一侧时, 将创建默认窗格分隔符。 默认的窗格分隔符包含指向[CPaneContainerManager 类](../../mfc/reference/cpanecontainermanager-class.md)的指针, 并重定向窗格组上的大多数操作 (例如, 重设窗格大小或停靠其他窗格或容器) 到容器管理器。 每个停靠窗格都维护一个指向其默认窗格分隔线的指针。

- 常规窗格分隔符只是将两个窗格分成一个容器。 有关详细信息, 请参阅[CPaneContainer 类](../../mfc/reference/cpanecontainer-class.md)。

## <a name="example"></a>示例

下面的示例演示如何从 `CWorkspaceBar` 对象获取 `CPaneDivider` 对象。 此代码片段是[MDI 选项卡演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CPaneDivider](../../mfc/reference/cpanedivider-class.md)

## <a name="requirements"></a>要求

**标头:** afxPaneDivider

##  <a name="setautohidemode"></a>CPaneDivider::SetAutoHideMode

```
void SetAutoHideMode(BOOL bMode);
```

### <a name="parameters"></a>参数

中*bMode*<br/>

### <a name="remarks"></a>备注

##  <a name="setpanecontainermanager"></a>CPaneDivider::SetPaneContainerManager

```
void SetPaneContainerManager(CPaneContainerManager* p);
```

### <a name="parameters"></a>参数

[in] *p*<br/>

### <a name="remarks"></a>备注

##  <a name="addpane"></a>CPaneDivider::AddPane

```
virtual void AddPane(CDockablePane* pBar);
```

### <a name="parameters"></a>参数

中*pBar*<br/>

### <a name="remarks"></a>备注

##  <a name="addpanecontainer"></a>CPaneDivider::AddPaneContainer

```
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,
    CPaneContainerManager& barContainerManager,
    DWORD dwAlignment);
```

### <a name="parameters"></a>参数

[in] *barContainerManager*<br/>
中*bOuterEdge*<br/>
[in] *pTargetBar*<br/>
中*dwAlignment*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="addrecentpane"></a>CPaneDivider::AddRecentPane

```
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>参数

中*pBar*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="calcexpecteddockedrect"></a>CPaneDivider::CalcExpectedDockedRect

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>参数

[in] *pWndToDock*<br/>
中*ptMouse*<br/>
中*rectResult*<br/>
[in] *bDrawTab*<br/>
[in] *ppTargetBar*<br/>

### <a name="remarks"></a>备注

##  <a name="calcfixedlayout"></a>CPaneDivider:: CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>参数

中*bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="checkvisibility"></a>CPaneDivider::CheckVisibility

```
virtual BOOL CheckVisibility();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="cpanedivider"></a>CPaneDivider::CPaneDivider

```
CPaneDivider();

CPaneDivider(
    BOOL bDefaultSlider,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>参数

[in] *bDefaultSlider*<br/>
[in] *pParent*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="createex"></a>CPaneDivider:: CreateEx

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext);
```

### <a name="parameters"></a>参数

中*dwStyleEx*<br/>
中*dwStyle*<br/>
中*rect*<br/>
[in] *pParentWnd*<br/>
中*nID*<br/>
中*pContext*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="doesallowdyninsertbefore"></a>CPaneDivider::D oesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="doescontainfloatingpane"></a>CPaneDivider::D oesContainFloatingPane

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="findpanecontainer"></a>CPaneDivider::FindPaneContainer

```
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>参数

中*pBar*<br/>
[in] *bLeftBar*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="findtabbedpane"></a>CPaneDivider::FindTabbedPane

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>参数

中*nID*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="getdefaultwidth"></a>CPaneDivider::GetDefaultWidth

```
static int __stdcall GetDefaultWidth();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="getfirstpane"></a>CPaneDivider::GetFirstPane

```
const CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="getpanedividers"></a>CPaneDivider::GetPaneDividers

返回驻留在[CPaneContainer 类](../../mfc/reference/cpanecontainer-class.md)中的窗格分隔线的列表。 只应为默认的窗格分隔符调用此方法。

```
void GetPaneDividers(CObList& lstSliders);
```

### <a name="parameters"></a>参数

*lstSliders*<br/>
弄包含位于窗格容器中的窗格分隔线的列表。

### <a name="remarks"></a>备注

只应为默认的窗格分隔条调用此方法。 默认窗格分隔符是调整整个窗格容器大小的分隔线。

##  <a name="getpanedividerstyle"></a>CPaneDivider::GetPaneDividerStyle

```
DWORD GetPaneDividerStyle() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="getpanes"></a>CPaneDivider::GetPanes

返回驻留在[CPaneContainer 类](../../mfc/reference/cpanecontainer-class.md)中的窗格的列表。 只应调用此方法来检索默认窗格分隔线。

```
void GetPanes(CObList& lstBars);
```

### <a name="parameters"></a>参数

*lstBars*<br/>
弄包含位于窗格容器中的窗格的列表。

### <a name="remarks"></a>备注

只应为默认的窗格分隔条调用此方法。 默认窗格分隔符是调整整个窗格容器大小的分隔线。

##  <a name="getrootcontainerrect"></a>CPaneDivider::GetRootContainerRect

```
CRect GetRootContainerRect();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="getwidth"></a>CPaneDivider::GetWidth

```
int GetWidth() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="init"></a>CPaneDivider:: Init

```
void Init(
    BOOL bDefaultSlider = FALSE,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>参数

[in] *bDefaultSlider*<br/>
[in] *pParent*<br/>

### <a name="remarks"></a>备注

##  <a name="insertpane"></a>CPaneDivider::InsertPane

```
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,
    CDockablePane* pTargetBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>参数

[in] *pBarToInsert*<br/>
[in] *pTargetBar*<br/>
中*dwAlignment*<br/>
[in] *lpRect*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="isautohidemode"></a>CPaneDivider::IsAutoHideMode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="isdefault"></a>CPaneDivider:: IsDefault

```
BOOL IsDefault() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="ishorizontal"></a>CPaneDivider::IsHorizontal

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="m_ndefaultwidth"></a>CPaneDivider::m_nDefaultWidth

指定应用程序中所有窗格分隔线的默认宽度 (以像素为单位)。

```
AFX_IMPORT_DATA static int m_nDefaultWidth;
```

##  <a name="move"></a>CPaneDivider:: Move

```
virtual void Move(
    CPoint& ptOffset,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>参数

[in] *ptOffset*<br/>
中*bAdjustLayout*<br/>

### <a name="remarks"></a>备注

##  <a name="m_psliderrtc"></a>CPaneDivider::m_pSliderRTC

保存指向有关派生对象的`CPaneDivider`运行时类信息的指针。

```
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;
```

### <a name="remarks"></a>备注

如果创建自定义窗格分隔符, 请设置此成员变量。 这使框架能够在绘制窗格时创建窗格分隔符。

### <a name="example"></a>示例

下面的示例演示如何设置`m_pSliderRTC`成员变量:

```
class CMySplitter : public CPaneDivider
{
...
};

CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```

##  <a name="notifyaboutrelease"></a>CPaneDivider::NotifyAboutRelease

```
virtual void NotifyAboutRelease();
```

### <a name="remarks"></a>备注

##  <a name="onshowpane"></a>CPaneDivider::OnShowPane

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>参数

中*pBar*<br/>
中*bShow*<br/>

### <a name="remarks"></a>备注

##  <a name="releaseemptypanecontainers"></a>CPaneDivider::ReleaseEmptyPaneContainers

```
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>备注

##  <a name="removepane"></a>CPaneDivider::RemovePane

```
virtual void RemovePane(CDockablePane* pBar);
```

### <a name="parameters"></a>参数

中*pBar*<br/>

### <a name="remarks"></a>备注

##  <a name="replacepane"></a>CPaneDivider::ReplacePane

```
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,
    CDockablePane* pBarToReplaceWith);
```

### <a name="parameters"></a>参数

[in] *pBarToReplace*<br/>
[in] *pBarToReplaceWith*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

##  <a name="repositionpanes"></a>CPaneDivider::RepositionPanes

```
virtual void RepositionPanes(
    CRect& rectNew,
    HDWP& hdwp);
```

### <a name="parameters"></a>参数

[in] *rectNew*<br/>
[in] *hdwp*<br/>

### <a name="remarks"></a>备注

##  <a name="serialize"></a>CPaneDivider:: 串行化

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>参数

[in] *ar*<br/>

### <a name="remarks"></a>备注

##  <a name="showwindow"></a>CPaneDivider:: ShowWindow

```
void ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>参数

[in] *nCmdShow*<br/>

### <a name="remarks"></a>备注

##  <a name="storerecentdocksiteinfo"></a>CPaneDivider::StoreRecentDockSiteInfo

```
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>参数

中*pBar*<br/>

### <a name="remarks"></a>备注

##  <a name="storerecenttabrelatedinfo"></a>CPaneDivider::StoreRecentTabRelatedInfo

```
void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>参数

[in] *pDockingBar*<br/>
中*pTabbedBar*<br/>

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)<br/>
[CPaneContainerManager 类](../../mfc/reference/cpanecontainermanager-class.md)<br/>
[CPaneContainer 类](../../mfc/reference/cpanecontainer-class.md)<br/>
[CDockingManager 类](../../mfc/reference/cdockingmanager-class.md)<br/>
[CBasePane 类](../../mfc/reference/cbasepane-class.md)
