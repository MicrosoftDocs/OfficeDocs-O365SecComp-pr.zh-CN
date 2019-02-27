---
title: 垃圾邮件和批量邮件之间有什么差异？
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/7/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: 客户有时 askwhat 是垃圾邮件和批量电子邮件之间的区别？本主题旨在说明不同之处, 并提供有关 exchange online 和 exchange online Protection (EOP) 中可用的不同选项的信息。
ms.openlocfilehash: 877912c94af5d4b399769759189d091c62d50075
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275712"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>垃圾邮件和批量邮件之间有什么差异？

客户有时会询问"垃圾邮件和批量邮件之间有什么差异？"本主题的目地是说明差异，并提供关于适用于 Exchange Online 和 Exchange Online Protection (EOP) 的不同选项的信息。
  
 **什么是垃圾邮件？**
  
垃圾邮件是经服务筛选的未经请求的（并且通常是不必要的）电子邮件。默认情况下，服务根据发送 IP 地址的信誉拒绝垃圾邮件。但是，如果邮件通过 IP 检查，但内容筛选器将其归为垃圾邮件，那么该邮件将会被发送到预期收件人的"垃圾邮件"文件夹。 
  
> [!NOTE]
> 对内容筛选邮件执行的操作可通过 Exchange 管理中心 (EAC) 中的内容筛选器策略进行配置, 如[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述。此外, 如果您不同意垃圾邮件分类, 您可以通过几种方式报告您认为是垃圾邮件或非垃圾邮件的邮件, 如[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交到 microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)中所述。 
  
 **什么是批量邮件？**
  
批量邮件也称为灰色邮件，是一种更难分类的电子邮件。垃圾邮件是一种持续性的威胁，而批量邮件通常包含广告或营销信息，不太可能重复向您发送。某些用户希望接收批量邮件，并且他们实际上可能是有意注册以接收这些邮件，而其他用户则可能会将这些类型的邮件视为垃圾邮件。例如，某些用户希望接收来自 Contoso Corporation 的广告电子邮件或参加即将举行的网络安全相关会议的邀请，而其他用户则将此类电子邮件视为垃圾邮件。
  
## <a name="how-to-manage-bulk-email"></a>如何管理批量邮件

确定如何管理批量邮件并非轻而易举之事，因为如果将批量邮件归为垃圾邮件，那么希望接收这类邮件的用户可能会提出投诉，并将其提交为错误标记为垃圾邮件的误报（非垃圾邮件）邮件。另一方面，如果允许发送所有批量邮件，那么不希望接收这类邮件的用户可能会提出投诉，并将其提交为错误发送到其收件箱的漏报垃圾邮件（假负）。
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>在内容筛选器策略中启用批量邮件敏感度控件

根据贵公司对批量电子邮件的策略, 管理员可以选择分配批量电子邮件的阈值。可通过 EAC 中的内容筛选器策略配置该设置。有关步骤, 请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。您可以从1-9 中选择一个阈值设置, 其中1将最大批量电子邮件标记为垃圾邮件, 9 允许传递大多数批量电子邮件。然后, 该服务执行配置的操作, 例如, 将邮件发送到收件人的 "垃圾邮件" 文件夹。 
  

