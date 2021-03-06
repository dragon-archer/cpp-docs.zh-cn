---
title: 标题控件和列表控件
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
ms.openlocfilehash: 934b54de3266138225087d5519af2be51972cf9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240070"
---
# <a name="header-control-and-list-control"></a>标题控件和列表控件

在大多数情况下，您将使用标头控件中嵌入[CListCtrl](../mfc/reference/clistctrl-class.md)或[CListView](../mfc/reference/clistview-class.md)对象。 但是，有一个单独的标头控件对象有意义，如操作排列在列或行中的数据的情况下[CView](../mfc/reference/cview-class.md)-派生的对象。 在这些情况下，您需要更好地控制外观和嵌入标头控件的默认行为。

您希望提供标准标头控件的常见情况下，默认行为，可能需要使用[CListCtrl](../mfc/reference/clistctrl-class.md)或[CListView](../mfc/reference/clistview-class.md)相反。 使用`CListCtrl`时所需的默认标头控件，嵌入在列表视图公共控件的功能。 使用[CListView](../mfc/reference/clistview-class.md)时所需的默认标头控件，嵌入视图对象中的功能。

> [!NOTE]
>  这些控件只包含一个内置的标头控件，如果使用创建列表视图控件**LVS_REPORT**样式。

在大多数情况下，可以通过更改包含列表视图控件的样式修改嵌入的标头控件的外观。 此外，可以通过父列表视图控件的成员函数获取标头控件有关的信息。 但是，完全控制和访问的特性和样式的内嵌的标题控件中，建议获取到标头控件对象的指针。

可以从访问嵌入的标头控件对象`CListCtrl`或`CListView`通过相应类的调用`GetHeaderCtrl`成员函数。 下面的代码演示此：

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [标头控件使用图像列表](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>请参阅

[使用 CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
