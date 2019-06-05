---
title: 生成评审集的搜索词报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34714991"
---
# <a name="generate-search-term-report-for-a-review-set"></a>生成评审集的搜索词报告

在电子数据展示中, 用于查询文档的最常用条件之一是使用关键字搜索词。 通过识别包含特定关键字 (也称为*术语*) 的文档, 审阅者可开始对其所面临的内容进行深入了解。 在 Microsoft 365 中的高级电子数据展示中, 可以通过在审阅集中对已保存的查询生成搜索词报告来精确执行此操作。

## <a name="step-1-create-a-saved-query-in-the-review-set"></a>步骤 1: 在审阅集中创建保存的查询

若要生成有意义的搜索词报告, 请创建一个保存的查询, 该查询将定义要为其生成搜索词报告的审阅集中的一组文档。 例如, 可以使用日期范围或实际的搜索词集 (通过使用关键字条件卡片) 创建查询。 若要了解有关审阅集查询的详细信息, 请参阅[在审阅集中查询数据](review-set-search.md)。

## <a name="step-2-generate-a-search-term-report"></a>步骤 2: 生成搜索词报告

有两种不同的方法可以生成搜索词报告: 通过您在步骤1中创建的已保存查询的上下文菜单, 或通过搜索词报告管理控制台。

- 若要使用上下文菜单, 请打开您在步骤1中创建的已保存查询的上下文菜单, 然后单击 "**生成搜索词报告**"。

- 若要使用管理控制台, 请转到 "**管理审阅集" > 查看搜索词报告**", 单击"**新建**", 然后选择您在步骤1中创建的已保存的查询。

然后, 输入要报告的术语, 由行分隔;如果在第1步使用的关键字条件卡中创建了已保存的查询, 则浮出控件页面将使用保存的查询中使用的第一个关键字条件卡片中的术语预先填充。

然后, 选择 "最大为三个轴进行报告", 然后单击 "**生成**", 这将启动搜索词报告生成作业。

### <a name="what-is-a-pivot"></a>什么是透视？

透视是将如何组织报告。 请考虑以下示例。

- 已保存的查询检索10个文档: doc1 到 doc10。

- doc1、doc2、doc3、doc4、doc5、doc6 和 doc7 包含术语 "电子数据展示"。

- doc6、doc7、doc8、doc9 和 doc10 包含 "调查" 一词。

- doc1、doc3、doc5、doc7、doc9 来自保管人 A。

- doc2、doc4、doc6、doc8、doc10 来自保管人 B。

在这种情况下, 如果您要根据保管人生成搜索词 "电子数据展示" 和 "调查", 并在保管人上进行透视, 则搜索词报告将按如下方式进行组织:

- "电子数据展示"-管理员 A: 4 个文档

- "电子数据展示"-管理员 B: 3 个文档

- "调查"-管理员 A: 2 个文档

- "调查"-管理员 B: 3 个文档

## <a name="step-3-download-report"></a>步骤 3: 下载报告

在搜索术语管理控制台中, 可以跟踪以前创建的搜索词报告作业的状态。 作业完成后, 可以单击搜索词报告所在的行, 然后单击 "下载", 这将下载 CSV 格式的搜索词报告。 每个行都有一个 (搜索词, 透视) 元组, 并且每行都包含以下信息:

- 检索的文档数量是多少？

- 在文档中找到的搜索词有多少次？

- 检索到的文档总容量是多少？

- 检索了多少个系列？

- 这些系列的总文档数是多少 (包括没有搜索词的文档) 是什么？

- 上述总容量是多少？