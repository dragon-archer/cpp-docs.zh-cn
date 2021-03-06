---
title: 区域设置名称、语言和国家-地区字符串
ms.date: 12/10/2018
f1_keywords:
- c.strings
helpviewer_keywords:
- country/region strings
- localization, locale
- locales
- setlocale function
- language strings
ms.assetid: a0e5a0c5-5602-4da0-b65f-de3d6c8530a2
ms.openlocfilehash: 512eb589d964da9ef8e87f4193362c739b39b4b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500063"
---
# <a name="ucrt-locale-names-languages-and-countryregion-strings"></a>UCRT 区域设置名称、语言和国家/地区字符串

可使用 Windows NLS API 支持的区域设置名称、语言、国家/地区代码和代码页，设置 [setlocale、\_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)、[\_create\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) 和 [\_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) 函数的 locale  参数。 *locale* 参数采取以下格式：

> locale  :: "locale-name  "<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| "language  \[\_  country-region  \[.  code-page  ]]"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| ".  code-page  "<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| "C"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| ""<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| NULL

locale-name  是简易格式的 IETF 标准化字符串；例如，`en-US` 表示英语（美国），或 `bs-Cyrl-BA` 表示波斯尼亚语（西里尔文，波斯尼亚和黑塞哥维那）。 首选这些格式。 有关 Windows 操作系统版本支持的区域设置名称的列表，请参阅以下表中的“语言标记”  列：[附录 A：产品行为](https://msdn.microsoft.com/library/cc233982.aspx)（位于 [MS-LCID]：Windows 语言代码标识符 (LCID) 参考内）。 该资源列出了支持的语言、脚本和区域设置名称的地区部分。 有关采用非默认排序顺序的受支持的区域设置名称的信息，请参阅 [Sort Order Identifiers（排序顺序标识符）](/windows/win32/Intl/sort-order-identifiers) 中的“区域性名称”  列。 在 Windows 10 或更高版本下，允许使用与有效的 [BCP-47](https://tools.ietf.org/html/bcp47) 语言标记对应的区域设置名称。 例如，`jp-US` 是一个有效的 BCP-47 标记，但实际上只有 `US` 对于区域设置功能有效。

如果语言字符串或语言字符串和国家/地区字符串用于创建区域设置，language  \[\_  country-region  \[.  code-page  ]] 格式存储在类别对应的区域设置中。 [语言字符串](../c-runtime-library/language-strings.md)介绍了一系列受支持的语言字符串，[国家/地区字符串](../c-runtime-library/country-region-strings.md)列出了受支持的国家和地区字符串。 如果指定语言没有与指定国家/地区关联，指定国家/地区的默认语言存储在区域设置中。 我们不建议将区域设置字符串的该格式嵌入到代码中或序列化到存储中，因为操作系统的更新更改这些字符串的可能性要高于区域设置名称格式。

code-page  是与区域设置关联的 ANSI/OEM 代码页。 通过语言或通过语言和国家/地区单独指定区域设置时，代码页已为你确定。 特殊值 `.ACP` 将指定国家/地区的 ANSI 代码页。 特殊值 `.OCP` 将指定国家/地区的 OEM 代码页。 例如，如果指定 `"Greek_Greece.ACP"` 作为区域设置，区域设置则存储为 `Greek_Greece.1253` （希腊语的 ANSI 代码页）；如果指定 `"Greek_Greece.OCP"` 作为区域设置，它则存储为 `Greek_Greece.737` （希腊语的 OEM 代码页）。 有关代码页的详细信息，请参见 [Code Pages](../c-runtime-library/code-pages.md)。 有关 Windows 支持的代码页列表，请参阅 [Code Page Identifiers（代码页标识符）](/windows/win32/Intl/code-page-identifiers)。

如果你仅使用代码页指定区域设置，则将使用 [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename) 所报告的用户的默认语言和国家/地区。 例如，如果指定 `".1254"`（ANSI 土耳其语）作为系统上为英语（美国）配置的用户区域设置，则存储的区域设置是 `English_United States.1254`。 我们不建议使用该格式，因为它可能导致不一致的行为。

`C` 的 *locale* 参数值 为 C 转换指定最小的符合 ANSI 标准的环境。 `C` 区域设置假定每个 char 数据类型为 1 字节，并且其值始终小于 256  。 如果 *locale* 指向一个空字符串，则区域设置是实现定义的本机环境。

使用 `setlocale` 类别，可以为 `_wsetlocale` 和 `LC_ALL` 函数同时指定所有区域设置类别。 这些类别可以全部设置为同一区域设置，你也可以使用具有该格式的区域设置参数分别设置每个类别：

> LC-ALL-specifier  :: locale <br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| \[LC_COLLATE=  locale  ]\[;LC_CTYPE=  locale  ]\[;LC_MONETARY=  locale  ]\[;LC_NUMERIC=  locale  ]\[;LC_TIME=  locale  ]

你可以指定多个类别类型，由分号分隔。 未指定的类别类型使用当前的区域设置。 例如，该代码片段将所有类别的当前区域设置设为 `de-DE`，然后将类别 `LC_MONETARY` 设为 `en-GB`，将 `LC_TIME` 设为 `es-ES`：

```C
_wsetlocale(LC_ALL, L"de-DE");
_wsetlocale(LC_ALL, L"LC_MONETARY=en-GB;LC_TIME=es-ES");
```

## <a name="see-also"></a>请参阅

[C 运行时库参考](../c-runtime-library/c-run-time-library-reference.md)<br/>
[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[语言字符串](../c-runtime-library/language-strings.md)<br/>
[国家/地区字符串](../c-runtime-library/country-region-strings.md)
