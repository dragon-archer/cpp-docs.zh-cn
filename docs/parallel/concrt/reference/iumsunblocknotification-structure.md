---
title: IUMSUnblockNotification 结构
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: bdf083e2ad418269e49e53dc164f2a60f693d5d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180203"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 结构

表示来自资源管理器的通知，说明阻止并触发返回到计划程序的指定计划上下文的线程代理已解除阻止，并已准备好进行计划。 一旦重新计划该线程代理的关联执行上下文（从 `GetContext` 方法返回），此接口将变得无效。

## <a name="syntax"></a>语法

```
struct IUMSUnblockNotification;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[IUMSUnblockNotification::GetContext](#getcontext)|返回`IExecutionContext`与已解除阻止该线程代理关联的执行上下文的接口。 此方法返回，并通过调用已重新计划基础的执行上下文后`IThreadProxy::SwitchTo`方法，此接口将不再有效。|
|[IUMSUnblockNotification::GetNextUnblockNotification](#getnextunblocknotification)|返回下一步`IUMSUnblockNotification`从方法返回链中的接口`IUMSCompletionList::GetUnblockNotifications`。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`IUMSUnblockNotification`

## <a name="requirements"></a>要求

**标头：** concrtrm.h

**命名空间：** 并发

##  <a name="getcontext"></a>  Iumsunblocknotification:: Getcontext 方法

返回`IExecutionContext`与已解除阻止该线程代理关联的执行上下文的接口。 此方法返回，并通过调用已重新计划基础的执行上下文后`IThreadProxy::SwitchTo`方法，此接口将不再有效。

```
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>返回值

`IExecutionContext`已解除阻止的线程代理的执行上下文的接口。

##  <a name="getnextunblocknotification"></a>  Iumsunblocknotification:: Getnextunblocknotification 方法

返回下一步`IUMSUnblockNotification`从方法返回链中的接口`IUMSCompletionList::GetUnblockNotifications`。

```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>返回值

下一步`IUMSUnblockNotification`从方法返回链中的接口`IUMSCompletionList::GetUnblockNotifications`。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[IUMSScheduler 结构](iumsscheduler-structure.md)<br/>
[IUMSCompletionList 结构](iumscompletionlist-structure.md)
