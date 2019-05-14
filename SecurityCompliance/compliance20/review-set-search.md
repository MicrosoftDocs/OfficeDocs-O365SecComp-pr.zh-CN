---
title: 查询评审集中的数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 395cc01238f4dbc91de5dd652e10121f5e0cc926
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527111"
---
# <a name="query-the-data-in-a-review-set"></a>查询评审集中的数据

在大多数情况下, 能够深入了解审阅集中存在的内容, 并对其进行组织以提高效率以供查看, 这将非常有用。 在审阅集中的查询使您能够将重点放在符合您一次定义的条件的文档子集上。

## <a name="creating-and-running-a-query-within-a-review-set"></a>在审阅集中创建和运行查询

若要在审阅集中创建和运行查询, 请单击您的审阅集中的 "新建查询"。 命名查询并定义条件后, 请单击 "保存" 以运行查询。 若要运行以前保存的查询, 只需单击已保存的查询即可。 有关可以搜索的元数据列表, 请参阅[文档元数据字段](document-metadata-fields.md)。

## <a name="building-your-query"></a>构建查询

您可以在关键字条件卡中使用条件卡片和查询语言的组合生成查询。 您可以将条件卡组合成一个块, 以创建更复杂的查询。

### <a name="condition-card"></a>条件卡片

审阅集中的每个可搜索字段都有一个对应的条件卡, 可用于生成查询。

有多种类型的条件卡:
- Freetext: freetext 条件卡片用于文本字段, 如 subject。 您可以通过用逗号分隔多个搜索词来列出它们。
- 日期: 日期条件卡片用于日期字段 (如 "上次修改日期")。
- 搜索选项: 搜索选项条件卡片将为您的审阅集中的特定字段提供可能的值列表。 这用于在您的审核集中有有限数量的可能值的字段, 如发件人。
- 关键字: 关键字条件卡片是 freetext 条件卡的特定实例, 可用于搜索术语, 或在中使用类似 KQL 的查询语言。 有关更多详细信息, 请参阅下文。

### <a name="query-language"></a>查询语言

除了条件卡片之外, 还可以使用关键字卡片中类似于 KQL 的查询语言来手工创建查询。 查询语言支持标准 KQL 语法, 如 AND、OR、NOT 和 NEAR (n)。 它还支持单字符通配符 (？) 和多字符通配符 (*)。

## <a name="filter"></a>筛选

除了可以保存的查询之外, 还可以使用筛选器将其他条件动态覆盖到查询结果中。 筛选器与查询的不同之处在于以下几个重要方式:
- 筛选器是瞬态的 (即它们不会持续在不同的会话中), 而是将查询保存到评审集。
- 筛选器始终是累加的;筛选器将应用于您在此时生效的查询的顶部, 而应用查询将替换有效的查询。