---
title: 保管人数据的高级索引
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 158af8acf4acdb8ad6650c377a23b44ed28c6f54
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607420"
---
# <a name="advanced-indexing-of-custodian-data"></a>保管人数据的高级索引

管理员添加到为高级电子数据展示 （预览） 用例，被视为的 Office 365 中的任何内容部分编制索引时重新处理，使其完全可供搜索。 此过程称为*高级索引*。内容可以部分数量的原因包括图像、 不受支持的文件类型或遇到索引文件大小限制时存在编制索引。 若要了解有关部分索引项目的详细信息，请参阅[部分，索引项目在 Office 365 中的内容搜索](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)。

## <a name="viewing-advanced-indexing-results"></a>查看高级索引的结果

高级索引过程完成后，您可以获取了解重新处理的有效性。 在 Custodian 索引视图中，图列出添加到*混合索引*的所有项。 混合索引是高级电子数据展示 （预览） 存储重新处理的内容的位置。

此图还包含需要修复的项目数和另一个关系图按文件类型的错误。有关详细信息，请参阅[错误修复处理数据时](error-remediation.md)。

## <a name="updating-advanced-indexes-for-custodians"></a>管理员更新高级的索引

当管理员添加到为高级电子数据展示 （预览） 用例时，要重新处理所有部分索引的项。不过，随着时间的推移，多个部分索引的项目可能会添加到用户的邮箱或 OneDrive 帐户。 当需要您可以更新索引。

> [!NOTE]
> 更新 custodian 索引是长时间运行的过程。建议您不更新索引多次种情况下，每天。
