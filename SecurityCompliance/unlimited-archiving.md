---
title: Office 365 中的无限制存档的概述
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自动扩展 Office 365 中的存档，从而提高了对不受限制的存档存储为 Exchange Online 邮箱。
ms.openlocfilehash: 83eb49b3f2a7da418b61e509f44023809ed396c3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29740814"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>Office 365 中的无限制存档的概述

Office 365 中的存档邮箱向用户提供其他邮箱存储空间。启用用户的存档邮箱后，最多 100 GB 的额外是存储的可用。当达到 100 GB 存储配额时，组织必须与 Microsoft 联系到存档邮箱的请求额外的存储空间。不再是这样。（称为*自动扩展存档*） 的 Office 365 中的新的无限制存档功能提供存档邮箱中存储无限的的量。现在，当达到存储配额的存档邮箱中时，Office 365 自动增加存档，这意味着用户不会运行邮箱存储空间不足，且管理员无法请求其他存储存档邮箱的大小.
  
有关分步说明开启自动扩展存档，请参阅[启用无限制存档的 Office 365](enable-unlimited-archiving.md)。
  
> [!NOTE]
> 自动扩展存档还支持共享的邮箱。若要共享邮箱的存档，请使用 Exchange Online Archiving 的许可证的 Exchange Online 计划 1 许可证或 Exchange Online 计划 2 许可证，则需要。 
  
## <a name="how-auto-expanding-archiving-works"></a>如何自动扩展存档工作原理

为前面所述、 其他邮箱启用用户的存档邮箱后创建的存储空间。当启用自动扩展存档时，Office 365 定期检查存档邮箱的大小。当存档邮箱获取接近其存储限制时，Office 365 自动创建额外的存储空间为存档。如果用户运行此额外的存储空间不足，Office 365 用户的存档添加更多存储空间。此过程会自动进行，这意味着管理员无需请求其他存档存储或管理自动扩展存档。 
  
下面是过程的快速概述。
  
![自动扩展存档过程概述](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. 对用户邮箱或共享的邮箱启用存档。创建存档邮箱与 100 GB 的存储空间，并存档邮箱的警告配额设置为 90 GB。
    
2. 管理员启用自动扩展存档邮箱。然后，当存档邮箱 （包括可恢复邮件文件夹） 到达 90 GB，它将转换为自动扩展存档和 Office 365 添加到存档存储空间。请注意，可能需要额外的存储空间设置为最多 30 天。
    
3. Office 365 自动存档在必要时添加更多存储空间。
  
> [!IMPORTANT]
> 如果邮箱置于保持状态或者分配给 Office 365 保留策略，存档 maibox 的存储配额增加到 110 GB 启用自动扩展存档。同样，存档警告配额增加到 100 GB。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>什么获取移动到其他存档存储空间？

若要使高效地利用自动扩展存档存储，可能会获取移动文件夹。Office 365 确定哪些文件夹获取移动到存档中添加其他存储时。当移动文件夹时，会自动在 Outlook 中的文件夹列表的存档部分的原始文件夹下创建子文件夹。此新的子文件夹指向已移动的项。此文件夹命名为 Office 365 使用的命名约定为**\<文件夹名称\>_yyyy （上创建 mmm dd，yyyy h_mm）**，其中： 
  
- **yyyy**是文件夹中的邮件已收到的年份。 
    
- **mmm dd，yyyy h_m**是日期和时间的 UTC 格式，基于用户的时区和 Outlook 中的区域设置 Office 365 中，创建子文件夹。 
    
以下屏幕截图显示文件夹列表之前和之后邮件移自动扩展存档中。
  
 **之前添加额外的存储空间**
  
![存档邮箱之前设置自动扩展存档文件夹列表](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 **添加额外的存储空间后**
  
![文件夹列表中的存档邮箱后自动扩展存档设置](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>用于访问自动扩展存档中的项目的 outlook 要求

若要访问存储在自动扩展存档的消息，用户必须使用以下 Outlook 客户端之一：
  
- Outlook 2016 或 Windows 的 Outlook 2019
    
- Outlook 网页版 
    
- Outlook 2016 或 Outlook 2019 for Mac 
    
> [!NOTE]
> Outlook 2013 用户可以仅在最初存储其存档邮箱中的 access 项目。他们也不能以访问移动到其他存档存储的项目。 
  
以下是使用 Outlook 或 Outlook web 访问邮件中自动扩展存档存储上的时要考虑的事项。
  
- 您可以访问存档邮箱，包括那些被移动到的自动扩展存储区中的任何文件夹。
    
- 您可以搜索仅通过搜索文件夹本身，已将它们移动到其他存储区的项目。这意味着您必须在文件夹列表中选择的搜索范围作为**当前文件夹**选项中选择存档文件夹。同样，如果自动扩展存储区中的文件夹中包含子文件夹，您需要单独搜索每个子文件夹。 
    
- 在 Outlook 中的项计数和自动扩展存档中 （在 Outlook 和 Outlook web 上的） 的读取/未读取计数可能不准确。
    
- 您可以删除自动扩展存储区域中，指向子文件夹中的项目，但不能删除该文件夹本身。
    
- 恢复已删除邮件功能不能用于恢复已删除自动扩展存储区域中的项。
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>自动扩展存档和其他 Office 365 合规性功能

本节介绍之间自动扩展存档其他 Office 365 合规性和数据管理功能的功能。
  
- **电子数据展示**-当您使用 Office 365 电子数据展示工具，如内容搜索或就地电子数据展示，自动扩展存档中的其他存储区域还搜索。
    
- **保留**-时将邮箱置于挂起使用工具，例如诉讼保留在 Exchange Online 或电子数据展示案例包含，并且也是自动扩展存档中位于 Office 365 安全性 & 合规性中心，内容中的保留策略置于保持状态。
    
- 也会删除**消息记录管理 (MRM)** -如果在 Exchange Online 中使用 MRM 删除策略永久删除过期的邮箱项目，位于自动扩展存档的过期项目。
    
- **导入服务**-您可以使用导入 Office 365 服务 PST 文件导入用户的自动扩展存档。您可以从导入数据的最多 100 GB PST 文件到用户的存档邮箱。 

## <a name="more-information"></a>更多信息

有关更多技术详细信息自动扩展存档，请参阅[Office 365： 自动扩展存档常见问题](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。