---
title: Office 365 中的无限制存档概述
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解 Office 365 中的自动扩展存档, 该存档为 Exchange Online 邮箱提供无限制的存档存储。
ms.openlocfilehash: 38fab68ee8e5c2bdd38bc60b08929bd6f6025e1b
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000785"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>Office 365 中的无限制存档概述

在 Office 365 中, 存档邮箱为用户提供额外的邮箱存储空间。 启用用户的存档邮箱后, 最多可有 100 GB 的附加存储空间。 达到 100 GB 的存储配额时, 组织必须与 Microsoft 联系以请求存档邮箱的额外存储空间。 这就不再是这样。 Office 365 中新增的无限制存档功能 (称为*自动扩展存档*) 在存档邮箱中提供了不受限制的存储量。 现在, 当达到存档邮箱中的存储配额时, Office 365 会自动增加存档大小, 这意味着用户将不会用尽邮箱存储空间, 并且管理员无需为存档邮箱请求额外的存储空间.
  
有关启用自动扩展存档的分步说明, 请参阅[在 Office 365 中启用无限制存档](enable-unlimited-archiving.md)。
  
> [!NOTE]
> 自动扩展存档还支持共享邮箱。 若要为共享邮箱启用存档, 需要具有 exchange online 存档许可证的 exchange online 计划2许可证或 exchange online 计划1许可证。 
  
## <a name="how-auto-expanding-archiving-works"></a>自动扩展存档的工作方式

如前所述, 在启用用户的存档邮箱时, 会创建额外的邮箱存储空间。 启用自动扩展存档后, Office 365 将定期检查存档邮箱的大小。 当存档邮箱接近其存储限制时, Office 365 会自动为存档创建额外的存储空间。 如果用户在此额外的存储空间中耗尽, Office 365 将为用户的存档增加更多的存储空间。 此过程会自动发生, 这意味着管理员无需请求额外存档存储或管理自动扩展存档。 
  
以下是此过程的快速概述。
  
![自动扩展存档过程概述](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. 对用户邮箱或共享邮箱启用存档。 将创建一个具有 100 GB 存储空间的存档邮箱, 并将存档邮箱的警告配额设置为 90 GB。
    
2. 管理员可自动展开邮箱的存档。 然后, 当存档邮箱 (包括 "可恢复的项目" 文件夹) 达到 90 GB 时, 它将转换为自动扩展存档, 而 Office 365 会将存储空间添加到存档中。 请注意, 要设置额外的存储空间, 可能需要长达30天的时间。
    
3. 必要时, Office 365 会自动向存档中添加更多的存储空间。
  
> [!IMPORTANT]
> 如果将邮箱置于保留状态或分配到 Office 365 保留策略, 则在启用自动扩展存档时, 存档 maibox 的存储配额将增加到 110 GB。 同样, 存档警告配额增加到 100 GB。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>移动到其他存档存储空间的内容是什么？

为了高效地使用自动扩展存档存储, 文件夹可能会移动。 Office 365 确定在将其他存储添加到存档中时哪些文件夹发生移动。 移动文件夹时, 将自动在 Outlook 的文件夹列表的存档部分中的原始文件夹下创建子文件夹。 这个新的子文件夹指向已移动的项目。 Office 365 用来为此文件夹命名的命名约定是** \<文件夹名称\>_yyyy (在 mmm dd, yyyy h_mm 创建)**, 其中: 
  
- **yyyy**是接收文件夹中邮件的年份。 
    
- **mmm dd, yyyy h_m**是 Office 365 创建子文件夹的日期和时间, 以 UTC 格式表示, 基于用户的时区和 Outlook 中的区域设置。 
    
下面的屏幕截图显示在自动展开的存档中移动邮件前后的文件夹列表。
  
 **添加额外的存储之前**
  
![预配自动扩展存档之前的存档邮箱的文件夹列表](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 **添加额外的存储后**
  
![预配自动扩展存档后存档邮箱的文件夹列表](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>用于访问自动扩展存档中的项目的 Outlook 要求

若要访问存储在自动扩展的存档中的邮件, 用户必须使用以下 Outlook 客户端之一:
  
- outlook 2016 或 outlook 2019 for Windows
    
- Outlook 网页版 
    
- outlook 2016 或 outlook 2019 for Mac 
    
> [!NOTE]
> Outlook 2013 用户只能访问最初存储在其存档邮箱中的项目。 他们将无法访问移动到其他存档存储的项目。 
  
以下是在使用 outlook 或 web 上的 outlook 访问存储在自动扩展的存档中的邮件时需要考虑的一些事项。
  
- 您可以访问存档邮箱中的任何文件夹, 包括已移动到自动扩展存储区域的文件夹。
    
- 您可以仅通过搜索文件夹本身来搜索已移动到其他存储区域的项目。 这意味着您必须在文件夹列表中选择 "存档" 文件夹, 以选择**当前文件夹**选项作为搜索范围。 同样, 如果自动扩展存储区域中的文件夹包含子文件夹, 则必须单独搜索每个子文件夹。 
    
- outlook 中的项目计数和可读/未读的计数 (在 outlook 和 web 上的 outlook 中) 在自动展开的存档中可能不准确。
    
- 您可以删除子文件夹中指向自动扩展存储区域的项目, 但不能删除该文件夹本身。
    
- 无法使用 "恢复已删除邮件" 功能恢复从自动扩展的存储区域中删除的项目。
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>自动扩展存档和其他 Office 365 合规性功能

本部分介绍自动扩展存档和其他 Office 365 合规性和数据管理功能之间的功能。
  
- **电子数据展示**-当您使用 Office 365 电子数据展示工具 (如内容搜索或就地电子数据展示) 时, 还会搜索自动扩展存档中的其他存储区域。
    
- **保留**-通过在 Exchange Online 或电子数据展示事例保留和合规性中心中使用诉讼保留等工具将邮箱置于保留状态时, 位于自动扩展存档中的内容也会置于保留状态。
    
- **邮件记录管理 (MRM)** -如果您使用 Exchange Online 中的 MRM 删除策略以永久删除过期的邮箱项目, 则也会删除位于自动展开的存档中的已过期项目。
    
- **导入服务**-您可以使用 Office 365 导入服务将 PST 文件导入到用户的自动扩展存档中。 你可以将 PST 文件中的最大为 100 GB 的数据导入用户的存档邮箱。 

## <a name="more-information"></a>更多信息

有关自动扩展存档的更多技术详细信息, 请参阅[Office 365: 自动扩展存档常见问题解答](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。