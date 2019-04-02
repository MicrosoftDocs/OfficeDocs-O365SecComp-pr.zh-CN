---
title: 调查数据的高级索引
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
ms.openlocfilehash: 9537cf743b89da7167ce3a37a5915027f4eb717a
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31029930"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>调查数据的高级索引

可以对实时系统中的内容进行部分索引, 其中包括映像的存在、不受支持的文件类型或在遇到索引文件大小限制时遇到的多种原因。 当处理高风险数据溢出时, 您需要确保您的搜索捕获了要调查的所有数据。 当向数据调查中添加了感兴趣的人时, 将重新处理 Office 365 中被视为部分索引的任何内容, 以使其完全可搜索。 此过程称为 "*高级索引*"。 

若要了解有关 Office 365 中的处理支持和部分索引项目的详细信息, 请参阅:

- [数据调查中支持的文件类型](supported-filetypes-datainvestigations.md)

- [处理 Office 365 内容搜索中的部分索引项](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)

- [由 Exchange 搜索编制索引的文件格式](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高级索引结果

完成高级索引过程后, 您可以了解重新处理的有效性。  在感兴趣的 "索引" 视图中, 图形列出了添加到*混合索引*中的所有项目。  混合索引是数据调查 (预览) 存储重新处理的内容的地方。

该图还包括需要修正的项目数, 以及按文件类型列出的错误的另一个关系图。 有关详细信息, 请参阅[处理数据时的错误修正](error-remediation.md)。

## <a name="updating-advanced-indexes-for-people-of-interest"></a>为感兴趣的人员更新高级索引

当向数据调查中添加了感兴趣的人时, 将重新处理所有部分索引的项目。 但是, 随着时间的推移, 可以向用户的邮箱或 OneDrive 帐户中添加更多部分索引的项目。  如果需要, 可以更新索引。

> [!NOTE]
> 更新感兴趣的人员索引是一个长时间运行的过程。 建议在调查中每日更新索引不超过一次。
