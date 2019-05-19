---
title: 准备用于 Office 365 高级电子数据展示的数据
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: '了解如何使用 Microsoft 365 安全&amp;合规中心来准备 office 365 数据, 以便使用 Office 365 高级电子数据展示进行分析。 '
ms.openlocfilehash: be778acb3356071e9575ed708623a0b94e2b3c7a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157454"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a>准备用于 Office 365 高级电子数据展示的数据

本主题介绍如何将内容搜索的结果加载到高级电子数据展示的案例中。 
  
> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a>步骤 1: 为高级电子数据展示准备 Office 365 数据

若要使用高级电子数据展示分析数据, 可以使用在 Microsoft 365 安全&amp;合规性中心 (在 Microsoft 365 安全&amp;合规中心的**内容搜索**页中列出) 中运行的内容搜索的结果或与电子数据展示事例相关联的搜索 (在安全&amp;合规中心中的**电子数据展示**页面上列出)。 
  
有关在高级电子数据展示中准备搜索结果以供分析的详细步骤, 请参阅[Prepare search results For Office 365 Advanced ediscovery](prepare-search-results-for-advanced-ediscovery.md)。
  
> [!NOTE]
> 如果您的数据在 Office 365 外部, 并且想要将其导入到 Office 365 以便在高级电子数据展示中准备和分析它, 请参阅在 Office 365 中将[PST 文件导入到 office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)和[存档第三方数据](https://go.microsoft.com/fwlink/p/?linkid=716918)的概述。 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>步骤 2: 将搜索结果数据加载到高级电子数据展示中的案例

准备好安全&amp;合规中心中的搜索结果进行分析之后, 下一步是在高级电子数据展示中将搜索结果加载到一个案例中。 有关更多详细信息, 请参阅[运行 Process module](run-the-process-module-in-advanced-ediscovery.md)。
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用工作或学校帐户登录到 Office 365。
    
3. 在安全与合规中心内，依次单击“搜索和调查”**** 和“电子数据展示”****，以显示组织中的案件集列表。 
    
4. 在高级电子数据展示中, 单击要在其中将数据加载到的事例旁边的 "**打开**"。 
    
5. 在此案件集的“主页”**** 上，单击“高级电子数据展示”****。 
    
    ![单击 "切换到高级电子数据展示" 以在高级电子数据展示中打开事例](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    将显示 "**连接到高级电子数据展示**进度栏"。 当您连接到高级电子数据展示时, 会在 "设置" 页上显示一个容器列表。 
    
    ![事例显示在高级电子数据展示](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     这些容器代表您在步骤1中的高级电子数据展示中准备进行分析的搜索结果。 请注意, 在安全&amp;合规中心的情况下, 容器名称与内容搜索的名称相同。 列表中的容器是您准备的容器。 如果其他用户为高级电子数据展示准备了搜索结果, 则相应的容器将不会包含在列表中。 
    
6. 若要在高级电子数据展示中将容器中的搜索结果数据加载到事例中, 请选择一个容器, 然后单击 "**处理**"。
    
将安全&amp;合规中心中的搜索结果添加到高级电子数据展示的事例中后, 下一步是使用高级电子数据展示中的工具来分析和挑选与事例相关的数据。 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[设置用户和案例](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[分析事例数据](analyze-case-data-with-advanced-ediscovery.md)
  
[管理相关性设置](manage-relevance-setup-in-advanced-ediscovery.md)
  
[使用相关性模块](use-relevance-in-advanced-ediscovery.md)
  
[导出事例数据](export-case-data-in-advanced-ediscovery.md)

