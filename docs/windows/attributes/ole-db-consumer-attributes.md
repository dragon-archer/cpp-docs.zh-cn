---
title: OLE DB 使用者特性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], database
- attributes [C++/CLI], data access
- databases [C++], attributes
- OLE DB consumers [C++], attributes
- database attributes [C++/CLI]
- attributes [C++/CLI], OLE DB consumer
ms.assetid: 017b591f-8f9a-42b4-84d5-cc42a21ab0cc
ms.openlocfilehash: 9f89af963c9c49a8a94b2a4f0c8930ab714926e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407557"
---
# <a name="ole-db-consumer-attributes"></a>OLE DB 使用者特性
OLE DB 使用者特性注入代码中，基于[OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-reference.md)，若要创建使用 OLE DB 使用者执行任务，例如打开表执行命令和访问数据。

|特性|描述|
|---------------|-----------------|
|[db_accessor](db-accessor.md)|绑定行集中的列，并将它们绑定到相应的访问器映射。|
|[db_column](db-column.md)|将指定的列绑定到行集。|
|[db_command](db-command.md)|执行 OLE DB 命令。|
|[db_param](db-param.md)|将指定的成员变量与输入或输出参数相关联。|
|[db_source](db-source.md)|创建并封装到数据源的提供程序通过建立的连接。|
|[db_table](db-table.md)|将打开一个 OLE DB 表。|

## <a name="see-also"></a>请参阅

[按组分的特性](attributes-by-group.md)